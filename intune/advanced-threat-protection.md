---
title: Korzystanie z usługi Windows Defender ATP w usłudze Microsoft Intune —Azure | Microsoft Docs
description: Dowiedz się, jak włączyć usługę Windows Defender Advanced Threat Protection (ATP) w scenariuszu typu end-to-end, m.in. w przypadku włączania ATP w usługach Intune oraz Windows Defender Security Center (portal ATP), dodawania urządzeń przy użyciu profilu konfiguracji ATP, tworzenia zasad zgodności z urządzeniami w usłudze Intune, tworzenia zasad dostępu warunkowego usługi Azure AD oraz monitorowania zgodności z urządzeniami.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e99ed0bd1eb5bae90913aedba5973e5e1282f70
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/02/2018
---
# <a name="enable-windows-defender-atp-with-conditional-access-in-intune"></a>Włączanie usługi Windows Defender ATP z dostępem warunkowym w usłudze Intune

Usługi Windows Defender Advanced Threat Protection (ATP) i Microsoft Intune współpracują ze sobą i ułatwiają zapobieganie naruszeniom bezpieczeństwa oraz pomagają ograniczyć wpływ naruszeń w organizacji.

Ta funkcja dotyczy: urządzeń z systemem Windows 10

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

- Licencjonowana dzierżawa dla pakietu Enterprise Mobility + Security E5 i systemu Windows E5 (lub pakietu Microsoft 365 Enterprise E5)
- Środowisko usługi Microsoft Intune oraz urządzenia z systemem Windows 10 [zarządzane przy użyciu usługi Intune](windows-enroll.md) przyłączone również do usługi Azure AD
- Usługa [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) oraz dostęp do usługi Windows Defender Security Center (portal ATP)

## <a name="enable-windows-defender-atp-in-intune"></a>Włączanie usługi Windows Defender ATP w usłudze Intune

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz kolejno pozycje **Zgodność urządzeń** > **Windows Defender ATP** > **Otwórz konsolę administratora zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender**.

    ![Tekst alternatywny](./media/atp-device-compliance-open-windows-defender.png)

4. W usłudze **Windows Defender Security Center**:
    1. Wybierz pozycję **Ustawienia** > **Funkcje zaawansowane**.
    2. Dla pozycji **Połączenie z usługą Microsoft Intune** wybierz ustawienie **Wł.**:

        ![Tekst alternatywny](./media/atp-security-center-intune-toggle.png)

    3. Wybierz pozycję **Zapisz preferencje**.

5. Wróć do usługi Intune, **Zgodność urządzeń** > **Windows Defender ATP**. Ustaw opcję **Połącz urządzenia z systemem Windows 10.0.15063+ z zaawansowaną ochroną przed zagrożeniami w usłudze Windows Defender** w pozycji **Wł.**
6. Wybierz pozycję **Zapisz**.

Zwykle należy wykonać to zadanie raz. Jeśli usługa ATP jest już włączona w zasobie usługi Intune, nie trzeba tego robić ponownie.

## <a name="onboard-devices-using-a-configuration-profile"></a>Dodawanie urządzeń przy użyciu profilu konfiguracji

Usługa Windows Defender zawiera pakiet konfiguracji dołączania, który jest instalowany na urządzeniach. Po zainstalowaniu pakiet komunikuje się z [usługami Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) w celu skanowania plików, wykrywania zagrożeń oraz zgłaszania ryzyka do usługi Windows Defender ATP. Przy użyciu usługi Intune możesz utworzyć profil konfiguracji, który korzysta z tego pakietu konfiguracji. Następnie przypisz ten profil do urządzeń, które dodajesz po raz pierwszy.

Po dodaniu urządzenia przy użyciu pakietu konfiguracji nie musisz tego robić ponownie. Zwykle jest to jednorazowa czynność.

Można również dodać urządzenia przy użyciu [zasad grupy lub programu System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-windows-defender-advanced-threat-protection).

W następnych krokach pokazano, jak dodawać urządzenia przy użyciu usługi Intune.

#### <a name="download-configuration-package"></a>Pobieranie pakietu konfiguracji

1. W usłudze [Windows Defender Security Center](https://securitycenter.windows.com) wybierz kolejno pozycje **Ustawienia** > **Dołączanie**.
2. Podaj następujące ustawienia:
  - **System operacyjny**: Windows 10
  - **Dodaj maszynę** > **Metoda wdrażania**: Zarządzanie urządzeniami przenośnymi/Microsoft Intune
3. Wybierz pozycję **Pobierz pakiet** i zapisz plik **WindowsDefenderATPOnboardingPackage.zip**. Wyodrębnij plik.

Ten plik zip zawiera plik **WindowsDefenderATP.onboarding**, który jest wymagany w następnych krokach.

#### <a name="create-the-atp-configuration-profile"></a>Tworzenie profilu konfiguracji usługi ATP

Ten profil korzysta z pakietu dołączania pobranego w poprzednich krokach.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W polu **Typ profilu** wybierz pozycję **Windows Defender ATP (Windows 10 Desktop)**.
6. Skonfiguruj ustawienia:

  - **Dodaj pakiet konfiguracji**: przeglądaj i wybierz pobrany plik **WindowsDefenderATP.onboarding**. Plik ten umożliwia ustawienie, zgodnie z którym urządzenia będą mogły raportować do usługi Windows Defender ATP.
  - **Udostępnianie próbek dla wszystkich plików**: umożliwia zbieranie przykładów oraz ich udostępnianie w usłudze Windows Defender ATP. Na przykład, jeśli widzisz podejrzany plik, możesz go przesłać do usługi Windows Defender ATP w celu wykonania szczegółowej analizy.
  - **Usprawnij częstotliwość raportowania danych telemetrycznych**: włącz to ustawienie dla urządzeń narażonych na duże ryzyko, co pozwoli na częstsze przekazywanie danych telemetrycznych do usługi Windows Defender ATP.
  - **Pakiet konfiguracji odłączania**: jeśli chcesz usunąć lub „odciążyć” monitorowanie usługi Windows Defender ATP, możesz pobrać pakiet odciążania w usłudze [Windows Defender Security Center](https://securitycenter.windows.com) i dodać go. W przeciwnym razie pomiń tę właściwość.

    Dodatkowe informacje na temat ustawień usługi Windows Defender ATP można znaleźć w artykule [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-sccm-windows-defender-advanced-threat-protection) (Dodawanie maszyn z systemem Windows 10 za pomocą programu System Center Configuration Manager).

7. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany i utworzyć profil.

## <a name="create-the-compliance-policy"></a>Tworzenie zasad zgodności
Zasady zgodności określają akceptowalny poziom ryzyka na urządzeniu.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W ustawieniach **Kondycja urządzenia** ustaw opcję **Wymagaj, aby poziom zagrożenia urządzenia był niższy lub równy podanemu poziomowi zagrożenia urządzenia** na preferowany poziom:

  - **Zabezpieczone**: ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.
  - **Niski**: urządzenie jest zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Urządzenia ze średnim lub wysokim poziomem zagrożenia nie są zgodne.
  - **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
  - **Wysoki**: ta opcja jest najmniej bezpieczna, zezwala na wszystkie poziomy zagrożeń. Urządzenia z wysokim, średnim i niskim poziomem zagrożeń są więc uznawane za zgodne.

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