---
title: Korzystanie z usługi Microsoft Defender ATP w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się, jak włączyć usługę Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (Microsoft Defender ATP) w scenariuszu typu end-to-end, m.in. w przypadku włączania usługi Microsoft Defender ATP w usługach Intune oraz Microsoft Defender Security Center, dołączania urządzeń przy użyciu profilu konfiguracji usługi Microsoft Defender ATP, tworzenia zasad zgodności z urządzeniami w usłudze Intune, tworzenia zasad dostępu warunkowego usługi Azure AD oraz monitorowania zgodności z urządzeniami.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 069658bdd231be96d7f9fbe23de1b4e38fdc5a9e
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885145"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Wymuszanie zgodności usługi Microsoft Defender ATP z dostępem warunkowym w usłudze Intune  

Usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (Microsoft Defender ATP) i Microsoft Intune współpracują ze sobą i ułatwiają zapobieganie naruszeniom bezpieczeństwa oraz pomagają ograniczyć wpływ naruszeń w organizacji.

Ta funkcja ma zastosowanie do: Urządzenia z systemem Windows 10

Na przykład ktoś wysyła użytkownikowi w organizacji załącznik programu Word z osadzonym złośliwym kodem. Użytkownik otwiera załącznik i uaktywnia zawartość. Rozpoczyna się atak z udziałem podniesionego przywileju i atakujący korzystający z maszyny zdalnej ma prawa administratora do urządzenia ofiary. Następnie atakujący uzyskuje zdalnie dostęp do innych urządzeń użytkownika.

Takie naruszenie zabezpieczeń może mieć wpływ na całą organizację.

Za pomocą usługi Microsoft Defender ATP można rozpoznać zdarzenia zabezpieczeń podobne do zdarzeń z tego scenariusza. Usługa Microsoft Defender Security Center zgłasza urządzenia jako urządzenia „wysokiego ryzyka” i dołącza szczegółowy raport na temat podejrzanych działań. W naszym przykładzie usługa Microsoft Defender ATP wykrywa, że urządzenie wykonało nietypowy kod, doszło do eskalacji uprawnienia korzystania z procesu, wprowadzenia złośliwego kodu i wywołania podejrzanej powłoki zdalnej. Usługa Microsoft Defender ATP proponuje następnie możliwości ograniczenia zagrożenia.

Przy użyciu usługi Intune można utworzyć zasady zgodności określające akceptowalny poziom ryzyka. Jeśli urządzenie przekroczy ustalony poziom ryzyka, staje się niezgodne z tymi zasadami. W połączeniu z zastosowaniem dostępu warunkowego w usłudze Azure Active Directory (AD) dostęp użytkownika do zasobów firmy zostaje zablokowany.

W tym artykule wyjaśniono, jak:

- Włączyć usługę Intune w usłudze Microsoft Defender Security Center oraz usługę Microsoft Defender ATP w usłudze Intune. Te zadania tworzą połączenie typu usługa do usługi między usługą Intune i usługą Microsoft Defender ATP. To połączenie umożliwia usłudze Microsoft Defender ATP zapisanie ryzyka urządzenia dla urządzeń usługi Intune.
- Utwórz zasady zgodności w usłudze Intune.
- Włącz dostęp warunkowy w usłudze Azure Active Directory (AD) na urządzeniach w zależności od poziomu zagrożenia.

## <a name="prerequisites"></a>Wymagania wstępne

Aby używać usługi Microsoft Defender ATP z usługą Intune, należy się upewnić, że następujące elementy zostały skonfigurowane i są gotowe do użycia:

- Licencjonowana dzierżawa dla pakietu Enterprise Mobility + Security E3 i systemu Windows E5 (lub pakietu Microsoft 365 Enterprise E5)
- Środowisko usługi Microsoft Intune oraz urządzenia z systemem Windows 10 [zarządzane przy użyciu usługi Intune](windows-enroll.md) przyłączone również do usługi Azure AD
- Usługa [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) oraz dostęp do usługi Microsoft Defender Security Center (portal ATP)

## <a name="enable-microsoft-defender-atp-in-intune"></a>Włączanie usługi Microsoft Defender ATP w usłudze Intune

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzenie** > **Microsoft Defender ATP**, a następnie pod obszarem *Ustawienia łącznika* wybierz pozycję **Otwórz usługę Microsoft Defender Security Center**.

    ![Wybieranie pozycji otwierającej usługę Microsoft Defender Security Center](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. W usłudze **Microsoft Defender Security Center**:
    1. Wybierz pozycję **Ustawienia** > **Funkcje zaawansowane**.
    2. Dla pozycji **Połączenie z usługą Microsoft Intune** wybierz ustawienie **Wł.** :

        ![Włączanie połączenia z usługą Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Wybierz pozycję **Zapisz preferencje**.

4. Wróć do usługi Intune i wybierz pozycję **Zgodność urządzeń** > **Microsoft Defender ATP**. Ustaw pozycję **Połącz urządzenia systemu Windows w wersji 10.0.15063 lub nowszej z usługą Microsoft Defender ATP** na **Wł.**
5. Wybierz pozycję **Zapisz**.

Zwykle należy wykonać to zadanie raz. Jeśli usługa Microsoft Defender ATP została już włączona w zasobie usługi Intune, nie trzeba tego robić ponownie.

## <a name="onboard-devices-using-a-configuration-profile"></a>Dodawanie urządzeń przy użyciu profilu konfiguracji

Podczas rejestrowania użytkownika końcowego w usłudze Intune możesz wypchnąć inne ustawienia do urządzeniu przy użyciu profilu konfiguracji. Dotyczy to również usługi Microsoft Defender ATP.

Usługa Microsoft Defender ATP zawiera pakiet konfiguracji dołączania, który komunikuje się z [usługami Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) w celu skanowania plików, wykrywania zagrożeń oraz zgłaszania ryzyka do usługi Microsoft Defender ATP.

Podczas dołączania usługa Intune pobiera automatycznie wygenerowany pakiet konfiguracji z usługi Microsoft Defender ATP. Usługa Intune wypycha pakiet konfiguracji do urządzenia podczas wysyłania profilu konfiguracji do urządzenia, co umożliwia usłudze Microsoft Defender ATP monitorowanie urządzenia pod kątem zagrożeń.

Po dodaniu urządzenia przy użyciu pakietu konfiguracji nie musisz tego robić ponownie. Można również dodać urządzenia przy użyciu [zasad grupy lub programu System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-configuration-profile"></a>Tworzenie profilu konfiguracji

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W polu **Typ profilu** wybierz pozycję **Microsoft Defender ATP (Windows 10 Desktop)** .
6. Skonfiguruj ustawienia:

    - **Typ pakietu konfiguracji klienta usługi Microsoft Defender ATP**: Wybierz pozycję **Dodaj**, aby dodać pakiet konfiguracyjny do profilu. Wybierz pozycję **Odłącz**, aby usunąć pakiet konfiguracyjny z profilu.
  
    > [!NOTE]  
    > Jeśli połączenie z usługą Microsoft Defender ATP zostało ustanowione poprawnie, usługa Intune automatycznie **dołączy** profil konfiguracji dla użytkownika, a ustawienie **Typ pakietu konfiguracji klienta usługi Microsoft Defender ATP** nie będzie dostępne.
  
    - **Udostępnianie próbek dla wszystkich plików**: pozycja **Włącz** umożliwia zbieranie przykładów oraz ich udostępnianie w usłudze Microsoft Defender ATP. Na przykład, jeśli widzisz podejrzany plik, możesz go przesłać do usługi Microsoft Defender ATP w celu wykonania szczegółowej analizy. Pozycja **Nieskonfigurowane** nie udostępnia żadnych przykładów w usłudze Microsoft Defender ATP.
    - **Usprawnij częstotliwość raportowania danych telemetrycznych**: pozycja **Włącz** to ustawienie dla urządzeń narażonych na duże ryzyko, które pozwala na częstsze przekazywanie danych telemetrycznych do usługi Microsoft Defender ATP.

    Dodatkowe informacje na temat ustawień usługi Microsoft Defender ATP można znaleźć w artykule [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) (Dołączanie maszyn z systemem Windows 10 za pomocą programu System Center Configuration Manager).

7. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany i utworzyć profil.

## <a name="create-the-compliance-policy"></a>Tworzenie zasad zgodności
Zasady zgodności określają akceptowalny poziom ryzyka na urządzeniu.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W ustawieniach usługi **Microsoft Defender ATP** ustaw pozycję **Wymagaj, aby urządzenie było na poziomie niższym lub równym ocenie ryzyka maszyny** na preferowany poziom. Klasyfikacja poziomów zagrożenia jest [określana przez usługę Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Czyste**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne. (Usługa Microsoft Defender ATP używa wartości *Bezpieczny*).
   - **Niski**: Urządzenie jest zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Urządzenia ze średnim lub wysokim poziomem zagrożenia nie są zgodne.
   - **Średni**: Urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
   - **Wysoki**: Ta opcja jest najmniej bezpieczna, zezwala na wszystkie poziomy zagrożeń. Urządzenia z wysokim, średnim i niskim poziomem zagrożeń są więc uznawane za zgodne.

6. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany (i utworzyć zasady).

## <a name="assign-the-policy"></a>Przypisywanie zasad

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Zgodność urządzeń** > **Zasady** i wybierz zasady zgodności usługi Microsoft Defender ATP.
3. Wybierz pozycję **Przypisania**.
4. Dołącz lub wyklucz grupy usługi Azure AD, aby przypisać do nich zasady.
5. Aby wdrożyć zasady do grup, wybierz przycisk **Zapisz**. Urządzenia użytkowników objęte zasadami zostaną ocenione pod kątem zgodności.

## <a name="create-a-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego
Zasady dostępu warunkowego blokują dostęp do zasobów, *jeśli* urządzenie jest niezgodne. Dlatego jeśli urządzenie przekroczy poziom zagrożenia, możesz zablokować dostęp do zasobów firmowych, np. do programu SharePoint lub usługi Exchange Online.  

> [!TIP]  
> Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure Active Directory (Azure AD). Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*.  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), a następnie wybierz kolejno pozycje **Dostęp warunkowy** > **Nowe zasady**.
2. W polu **Nazwa** wprowadź nazwę zasad i wybierz pozycję **Użytkownicy i grupy**. Użyj opcji Dołącz lub Wyklucz, aby dodać grupy do zasad, i wybierz opcję **Gotowe**.
3. Wybierz opcję **Aplikacje w chmurze** i wybierz aplikacje, które będą chronione. Na przykład wybierz pozycję **Wybierz aplikacje**, a następnie pozycje **Office 365 SharePoint Online** i **Office 365 Exchange Online**.

    Wybierz przycisk **Gotowe**, aby zapisać zmiany.

4. Wybierz pozycję **Warunki** > **Aplikacje klienckie**, aby zastosować zasady do aplikacji i przeglądarek. Na przykład wybierz przycisk **Tak**, a następnie włącz opcje **Przeglądarka** oraz **Aplikacje mobilne i klienci stacjonarni**.

    Wybierz przycisk **Gotowe**, aby zapisać zmiany.

5. Wybierz pozycję **Udziel**, aby zastosować dostęp warunkowy w zależności od zgodności urządzeń. Na przykład wybierz pozycje **Udziel dostępu** > **Wymagaj, aby urządzenie było oznaczone jako zgodne**.

    Wybierz przycisk **Wybierz**, aby zapisać zmiany.

6. Wybierz pozycję **Włącz zasady**, a następnie **Utwórz**, aby zapisać zmiany.

Przydatne informacje znajdują się w artykule [Co to jest dostęp warunkowy?](conditional-access.md)

## <a name="monitor-device-compliance"></a>Monitorowanie zgodności urządzenia
Następnie monitoruj stan urządzeń objętych zasadami zgodności usługi Microsoft Defender ATP.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Zgodność urządzeń** > **Zgodność z zasadami**.
3. Znajdź na liście zasady usługi Microsoft Defender ATP i zobacz, które urządzenia są zgodne, a które niezgodne.

## <a name="more-good-stuff"></a>Więcej przydatnych informacji
[Microsoft Defender ATP conditional access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access) (Dostęp warunkowy usługi Microsoft Defender ATP)  
[Microsoft Defender ATP risk dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard) (Pulpit nawigacyjny ryzyka usługi Microsoft Defender ATP)  

[Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md)  
[Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)