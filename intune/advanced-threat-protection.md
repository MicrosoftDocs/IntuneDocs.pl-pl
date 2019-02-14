---
title: Korzystanie z usługi Windows Defender ATP w usłudze Microsoft Intune —Azure | Microsoft Docs
description: Dowiedz się, jak włączyć usługę Windows Defender Advanced Threat Protection (ATP) w scenariuszu typu end-to-end, m.in. w przypadku włączania ATP w usługach Intune oraz Windows Defender Security Center (portal ATP), dodawania urządzeń przy użyciu profilu konfiguracji ATP, tworzenia zasad zgodności z urządzeniami w usłudze Intune, tworzenia zasad dostępu warunkowego usługi Azure AD oraz monitorowania zgodności z urządzeniami.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 1/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: afa2ef4cf1199597f61af99d631243e2d3b51e64
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845180"
---
# <a name="enforce-compliance-for-windows-defender-atp-with-conditional-access-in-intune"></a>Wymuszanie zgodności usługi Windows Defender ATP z dostępem warunkowym w usłudze Intune

Usługi Windows Defender Advanced Threat Protection (ATP) i Microsoft Intune współpracują ze sobą i ułatwiają zapobieganie naruszeniom bezpieczeństwa oraz pomagają ograniczyć wpływ naruszeń w organizacji.

Ta funkcja ma zastosowanie do: Urządzenia z systemem Windows 10

Na przykład ktoś wysyła użytkownikowi w organizacji załącznik programu Word z osadzonym złośliwym kodem. Użytkownik otwiera załącznik i uaktywnia zawartość. Rozpoczyna się atak z udziałem podniesionego przywileju i atakujący korzystający z maszyny zdalnej ma prawa administratora do urządzenia ofiary. Następnie atakujący uzyskuje zdalnie dostęp do innych urządzeń użytkownika.

Takie naruszenie zabezpieczeń może mieć wpływ na całą organizację.

Za pomocą usługi Windows Defender ATP można rozpoznać zdarzenia zabezpieczeń podobne do zdarzeń z tego scenariusza. Usługa Windows Defender Security Center (konsola ATP) zgłasza urządzenia jako urządzenia „wysokiego ryzyka” i dołącza szczegółowy raport na temat podejrzanych działań. W naszym przykładzie usługa Windows Defender ATP wykrywa, że urządzenie wykonało nietypowy kod, doszło do eskalacji uprawnienia korzystania z procesu, wprowadzenia złośliwego kodu i wywołania podejrzanej powłoki zdalnej. Usługa Windows Defender ATP proponuje następnie możliwości ograniczenia zagrożenia.

Przy użyciu usługi Intune można utworzyć zasady zgodności określające akceptowalny poziom ryzyka. Jeśli urządzenie przekroczy ustalony poziom ryzyka, staje się niezgodne z tymi zasadami. W połączeniu z zastosowaniem dostępu warunkowego w usłudze Azure Active Directory (AD) dostęp użytkownika do zasobów firmy zostaje zablokowany.

W tym artykule wyjaśniono, jak:

- Włączyć usługę Intune w usłudze ATP oraz włączyć usługę ATP w usłudze Intune. Te zadania tworzą połączenie typu usługa do usługi między usługą Intune, a usługą Windows Defender ATP. To połączenie umożliwia usłudze Windows Defender ATP zapisanie ryzyka urządzenia dla urządzeń usługi Intune.
- Utwórz zasady zgodności w usłudze Intune.
- Włącz dostęp warunkowy w usłudze Azure Active Directory (AD) na urządzeniach w zależności od poziomu zagrożenia.

## <a name="prerequisites"></a>Wymagania wstępne

Aby używać usługi ATP z usługą Intune, należy się upewnić, że następujące elementy są skonfigurowane i gotowe do użycia:

- Licencjonowana dzierżawa dla pakietu Enterprise Mobility + Security E3 i systemu Windows E5 (lub pakietu Microsoft 365 Enterprise E5)
- Środowisko usługi Microsoft Intune oraz urządzenia z systemem Windows 10 [zarządzane przy użyciu usługi Intune](windows-enroll.md) przyłączone również do usługi Azure AD
- Usługa [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) oraz dostęp do usługi Windows Defender Security Center (portal ATP)

## <a name="enable-windows-defender-atp-in-intune"></a>Włączanie usługi Windows Defender ATP w usłudze Intune

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz kolejno pozycje **Zgodność urządzeń** > **Windows Defender ATP** > **Otwórz usługę Windows Defender Security Center**.

    ![Wybieranie pozycji otwierającej usługę Windows Defender Security Center](./media/atp-device-compliance-open-windows-defender.png)

4. W usłudze **Windows Defender Security Center**:
    1. Wybierz pozycję **Ustawienia** > **Funkcje zaawansowane**.
    2. Dla pozycji **Połączenie z usługą Microsoft Intune** wybierz ustawienie **Wł.**:

        ![Włączanie połączenia z usługą Intune](./media/atp-security-center-intune-toggle.png)

    3. Wybierz pozycję **Zapisz preferencje**.

5. Wróć do usługi Intune, **Zgodność urządzeń** > **Windows Defender ATP**. Ustaw pozycję **Połącz urządzenia systemu Windows w wersji 10.0.15063 lub nowszej z usługą Windows Defender ATP** na **Wł.**
6. Wybierz pozycję **Zapisz**.

Zwykle należy wykonać to zadanie raz. Jeśli usługa ATP jest już włączona w zasobie usługi Intune, nie trzeba tego robić ponownie.

## <a name="onboard-devices-using-a-configuration-profile"></a>Dodawanie urządzeń przy użyciu profilu konfiguracji

Podczas rejestrowania użytkownika końcowego w usłudze Intune możesz wypchnąć inne ustawienia do urządzeniu przy użyciu profilu konfiguracji. Dotyczy to również usługi Windows Defender ATP.

Usługa Windows Defender zawiera dołączony pakiet konfiguracji, który komunikuje się z [usługami Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) w celu skanowania plików, wykrywania zagrożeń oraz zgłaszania ryzyka do usługi Windows Defender ATP.

Podczas dołączania usługa Intune pobiera automatycznie wygenerowany pakiet konfiguracyjny z usługi Windows Defender ATP. Gdy profil jest wypychany do urządzenia lub na nim wdrażany, ten pakiet konfiguracyjny jest również wypychany do urządzenia. Dzięki temu usługa Windows Defender ATP może monitorować urządzenie pod kątem zagrożeń.

Po dodaniu urządzenia przy użyciu pakietu konfiguracji nie musisz tego robić ponownie. Można również dodać urządzenia przy użyciu [zasad grupy lub programu System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-windows-defender-advanced-threat-protection).

### <a name="create-the-configuration-profile"></a>Tworzenie profilu konfiguracji

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W polu **Typ profilu** wybierz pozycję **Windows Defender ATP (Windows 10 Desktop)**.
6. Skonfiguruj ustawienia:

  - **Typ pakietu konfiguracji klienta usługi Windows Defender ATP**: Wybierz pozycję **Dodaj**, aby dodać pakiet konfiguracyjny do profilu. Wybierz pozycję **Odłącz**, aby usunąć pakiet konfiguracyjny z profilu.
  
    > [!NOTE] 
    > Jeśli połączenie z usługą Windows Defender ATP zostało ustanowione poprawnie, usługa Intune automatycznie **doda** profil konfiguracji dla użytkownika, a ustawienie **Typ pakietu konfiguracji klienta usługi Windows Defender ATP** nie będzie dostępne.
  
  - **Udostępnianie próbek dla wszystkich plików**: Pozycja **Włącz** umożliwia zbieranie przykładów oraz ich udostępnianie w usłudze Windows Defender ATP. Na przykład, jeśli widzisz podejrzany plik, możesz go przesłać do usługi Windows Defender ATP w celu wykonania szczegółowej analizy. Pozycja **Nieskonfigurowane** nie udostępnia żadnych przykładów w usłudze Windows Defender ATP.
  - **Usprawnij częstotliwość raportowania danych telemetrycznych**: Pozycja **Włącz** to ustawienie dla urządzeń narażonych na duże ryzyko, która pozwala na częstsze przekazywanie danych telemetrycznych do usługi Windows Defender ATP.

    Dodatkowe informacje na temat ustawień usługi Windows Defender ATP można znaleźć w artykule [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-sccm-windows-defender-advanced-threat-protection) (Dodawanie maszyn z systemem Windows 10 za pomocą programu System Center Configuration Manager).

7. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany i utworzyć profil.

## <a name="create-the-compliance-policy"></a>Tworzenie zasad zgodności
Zasady zgodności określają akceptowalny poziom ryzyka na urządzeniu.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W ustawieniach usługi **Windows Defender ATP** ustaw pozycję **Wymagaj, aby urządzenie było na poziomie niższym lub równym ocenie ryzyka maszyny** na preferowany poziom:

  - **Czyste**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.
  - **Niski**: Urządzenie jest zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Urządzenia ze średnim lub wysokim poziomem zagrożenia nie są zgodne.
  - **Średni**: Urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
  - **Wysoki**: Ta opcja jest najmniej bezpieczna, zezwala na wszystkie poziomy zagrożeń. Urządzenia z wysokim, średnim i niskim poziomem zagrożeń są więc uznawane za zgodne.

6. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany (i utworzyć zasady).

## <a name="assign-the-policy"></a>Przypisywanie zasad

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Zgodność urządzeń** > **Zasady**> i wybierz zasady zgodności usługi Windows Defender ATP.
3. Wybierz pozycję **Przypisania**.
4. Dołącz lub wyklucz grupy usługi Azure AD, aby przypisać do nich zasady.
5. Aby wdrożyć zasady do grup, wybierz przycisk **Zapisz**. Urządzenia użytkowników objęte zasadami zostaną ocenione pod kątem zgodności.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego usługi Azure AD
Zasady dostępu warunkowego blokują dostęp do zasobów, *jeśli* urządzenie jest niezgodne. Dlatego jeśli urządzenie przekroczy poziom zagrożenia, możesz zablokować dostęp do zasobów firmowych, np. do programu SharePoint lub usługi Exchange Online.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz kolejno pozycje **Azure Active Directory** > **Dostęp warunkowy** > **Nowe zasady**.
2. W polu **Nazwa** wprowadź nazwę zasad i wybierz pozycję **Użytkownicy i grupy**. Użyj opcji Dołącz lub Wyklucz, aby dodać grupy do zasad, i wybierz opcję **Gotowe**.
3. Wybierz opcję **Aplikacje w chmurze** i wybierz aplikacje, które będą chronione. Na przykład wybierz pozycję **Wybierz aplikacje**, a następnie pozycje **Office 365 SharePoint Online** i **Office 365 Exchange Online**.

    Wybierz przycisk **Gotowe**, aby zapisać zmiany.

4. Wybierz pozycję **Warunki** > **Aplikacje klienckie**, aby zastosować zasady do aplikacji i przeglądarek. Na przykład wybierz przycisk **Tak**, a następnie włącz opcje **Przeglądarka** oraz **Aplikacje mobilne i klienci stacjonarni**.

    Wybierz przycisk **Gotowe**, aby zapisać zmiany.

5. Wybierz pozycję **Udziel**, aby zastosować dostęp warunkowy w zależności od zgodności urządzeń. Na przykład wybierz pozycje **Udziel dostępu** > **Wymagaj, aby urządzenie było oznaczone jako zgodne**.

    Wybierz przycisk **Wybierz**, aby zapisać zmiany.

6. Wybierz pozycję **Włącz zasady**, a następnie **Utwórz**, aby zapisać zmiany.

Przydatne informacje znajdują się w artykule [Co to jest dostęp warunkowy?](conditional-access.md).

## <a name="monitor-device-compliance"></a>Monitorowanie zgodności urządzenia
Następnie monitoruj stan urządzeń objętych zasadami zgodności usługi Windows Defender ATP.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Zgodność urządzeń** > **Zgodność z zasadami**.
3. Znajdź na liście zasady usługi Windows Defender ATP i zobacz, które urządzenia są zgodne, a które niezgodne.

## <a name="more-good-stuff"></a>Więcej przydatnych informacji
[Windows Defender ATP conditional access](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/conditional-access-windows-defender-advanced-threat-protection) (Dostęp warunkowy usługi Windows Defender ATP)  
[Windows Defender ATP risk dashboard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) (Pulpit nawigacyjny ryzyka usługi Windows Defender ATP)  
[Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md)  
[Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
