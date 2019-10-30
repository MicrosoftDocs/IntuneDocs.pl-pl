---
title: Scenariusz z przewodnikiem – Komputer nowoczesny zarządzany przez chmurę
titleSuffix: Microsoft Intune
description: Poznaj scenariusz z przewodnikiem, aby przygotować i skonfigurować komputer nowoczesny z poziomu portalu zarządzania urządzeniami na platformie Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3372fc83e467b08b479490b3707f2be03409156
ms.sourcegitcommit: c2e62f1ebdf75599c8e544287123c602f0f15f2b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "72749328"
---
# <a name="guided-scenario---cloud-managed-modern-desktop"></a>Scenariusz z przewodnikiem – Komputer nowoczesny zarządzany przez chmurę

Komputer nowoczesny to najnowocześniejsza platforma produkcyjna dla pracownika przetwarzającego informacje. Pakiet Office 365 ProPlus i system Windows 10 to podstawowe składniki komputera nowoczesnego wraz z najnowszymi punktami odniesienia zabezpieczeń dla systemu Windows 10 i zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender. 

Zarządzanie komputerem nowoczesnym z chmury zapewnia dodatkową korzyść w zakresie akcji realizowanych zdalnie przez Internet. Zarządzanie z poziomu chmury korzysta z wbudowanych zasad zarządzania urządzeniami przenośnymi systemu Windows i usuwa zależności lokalnych zasad grupy usługi Active Directory. 

Jeśli chcesz ocenić wprowadzenie komputera nowoczesnego zarządzanego przez chmurę we własnej organizacji, ten scenariusz z przewodnikiem definiuje wszystkie konfiguracje niezbędne do wykonania wdrożenia podstawowego. W tym scenariuszu z przewodnikiem utworzysz bezpieczne środowisko, w którym można wypróbować możliwości zarządzania urządzeniami w usłudze Intune. 

## <a name="prerequisites"></a>Wymagania wstępne
- [Ustawianie usługi Intune jako urzędu MDM](~/fundamentals/mdm-authority-set.md#set-mdm-authority-to-intune) — ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.
- Minimalnie M356 E3 (lub M365 E5 w celu uzyskania najlepszych zabezpieczeń)
- Urządzenie z systemem Windows 10 1903 (zarejestrowane za pomocą rozwiązania Windows Autopilot w celu uzyskania najlepszego środowiska użytkownika końcowego)
- Aby ukończyć ten scenariusz z przewodnikiem, wymagane są uprawnienia administratora usługi Intune:
  - konfiguracja urządzenia – odczytywanie, tworzenie, usuwanie, przypisywanie i aktualizowanie;
  - programy rejestracji – odczytywanie urządzenia, odczytywanie profilu, tworzenie profilu, przypisywanie profilu, usuwanie profilu;
  - aplikacje mobilne – odczytywanie, tworzenie, usuwanie, przypisywanie i aktualizowanie;
  - organizacja – odczytywanie i aktualizowanie;
  - punkty odniesienia zabezpieczeń – odczytywanie, tworzenie, usuwanie, przypisywanie i aktualizowanie;
  - zestawy zasad – odczytywanie, tworzenie, usuwanie, przypisywanie i aktualizowanie.

## <a name="step-1---introduction"></a>Krok 1. Wprowadzenie

Korzystając z tego scenariusza z przewodnikiem, skonfigurujesz użytkownika testowego, zarejestrujesz urządzenie w usłudze Intune i wdrożysz urządzenie z ustawieniami zalecanymi przez usługę Intune, a także z systemem Windows 10 i oprogramowaniem Office ProPlus. Urządzenie zostanie również skonfigurowane pod kątem zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender, jeśli wybierzesz opcję [włączenia tej ochrony w usłudze Intune](~/protect/advanced-threat-protection.md#enable-microsoft-defender-atp-in-intune). Skonfigurowany przez Ciebie użytkownik i zarejestrowane urządzenie zostaną dodane do nowych grup zabezpieczeń i zostaną skonfigurowane z zalecanymi ustawieniami zabezpieczeń i produktywności. 

### <a name="what-you-will-need-to-continue"></a>Co jest konieczne, aby przejść dalej

W tym scenariuszu z przewodnikiem należy zapewnić urządzenie testowe i użytkownika testowego. Upewnij się, że zakończono wykonywanie następujących zadań:
- Skonfiguruj konto użytkownika testowego w usłudze Azure Active Directory.
- Utwórz urządzenie testowe z systemem Windows 10 w wersji 1903 lub nowszej.
- (Opcjonalnie) [Zarejestruj urządzenie testowe przy użyciu rozwiązania Windows Autopilot](~/enrollment/enrollment-autopilot.md#add-devices).
- (Opcjonalnie) Włącz [znakowanie strony logowania w usłudze Azure Active Directory organizacji](https://go.microsoft.com/fwlink/?linkid=2102455).

## <a name="step-2---user"></a>Krok 2. Użytkownik

Wybierz użytkownika, który ma zostać skonfigurowany na urządzeniu. Ta osoba będzie podstawowym użytkownikiem urządzenia.

Jeśli chcesz dodać więcej użytkowników lub urządzeń do tej konfiguracji, po prostu dodaj użytkowników i urządzenia do grup zabezpieczeń usługi AAD wygenerowanych w kreatorze. W przeciwieństwie do innych scenariuszy z przewodnikiem nie trzeba uruchamiać kreatora więcej niż raz, ponieważ tej konfiguracji nie można dostosowywać. Po prostu dodaj więcej użytkowników i urządzeń do utworzonych grup usługi AAD. Po zakończeniu działania kreatora będzie możliwe wyświetlenie wygenerowanej grupy z wdrożonymi zalecanymi zasadami. 

## <a name="step-3---device"></a>Krok 3. Urządzenie

Upewnij się, że na urządzeniu uruchomiony jest system Windows 10 w wersji 1903 lub nowszej.  Użytkownik podstawowy będzie musiał skonfigurować urządzenie po jego otrzymaniu. Dostępne są dwie opcje konfiguracji dla użytkownika. 

### <a name="option-a--windows-autopilot"></a>Opcja A — Windows Autopilot
System Windows automatyzuje konfigurację nowych urządzeń, aby użytkownicy mogli je skonfigurować prosto po rozpakowaniu, bez pomocy technicznej z zakresu IT. Jeśli urządzenie jest już zarejestrowane w rozwiązaniu Windows Autopilot, wybierz je przy użyciu numeru seryjnego. Aby uzyskać więcej informacji o korzystaniu z rozwiązania Windows Autopilot, zobacz [Rejestracja urządzenia przy użyciu rozwiązania Windows Autopilot (opcjonalnie)](~/fundamentals/guided-scenarios-cloud-managed-pc.md#register-device-with-windows-autopilot-optional).

### <a name="option-b--manual-device-enrollment"></a>Opcja B — Ręczna rejestracja urządzenia
Użytkownicy będą ręcznie konfigurować i rejestrować nowe urządzenia w usłudze zarządzania urządzeniami przenośnymi. Po zakończeniu tego scenariusza zresetuj urządzenie i przekaż podstawowemu użytkownikowi instrukcje dotyczące rejestracji urządzeń z systemem Windows. Aby uzyskać więcej informacji, zobacz [Dołączanie urządzenia z systemem Windows 10 do usługi Azure AD podczas pierwszego uruchomienia](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device).

## <a name="step-4---review--create"></a>Krok 4. Przegląd + tworzenie

W ostatnim kroku możesz zapoznać się podsumowaniem skonfigurowanych ustawień. Po sprawdzeniu swoich wyborów kliknij opcję **Wdróż**, aby ukończyć scenariusz z przewodnikiem. Po zakończeniu scenariusza z przewodnikiem zostanie wyświetlona tabela zasobów. Możesz edytować te zasoby później, ale gdy opuścisz widok podsumowania, tabela nie jest zapisywana.

> [!IMPORTANT]
> Po zakończeniu scenariusza z przewodnikiem zostanie wyświetlone podsumowanie. Możesz zmodyfikować zasoby wymienione w podsumowaniu później, ale tabela z tymi zasobami nie zostanie zapisana.

### <a name="verification"></a>Weryfikacja
1. Sprawdzenie wyboru przypisanego zakresu użytkownika oprogramowania MDM
    - Upewnij się, że [zakres użytkownika oprogramowania MDM](~/enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) jest następujący:
        - ustawiono wartość **Wszystkie** dla aplikacji **Microsoft Intune**; lub
        - ustawiono wartość **Niektóre**. Ponadto dodaj grupę użytkowników utworzoną w tym scenariuszu z przewodnikiem.
2. Sprawdź, czy wybrany użytkownik może dołączać urządzenia do usługi Azure Active Directory.
    - Upewnij się, że dołączanie do usługi ADD jest skonfigurowane w następujący sposób:
        - ustawiono wartość **Wszystkie**; lub
        - ustawiono wartość **Niektóre**. Dodaj również grupę użytkowników utworzoną w tym scenariuszu z przewodnikiem.
3. Wykonaj odpowiednie kroki na urządzeniu, aby dołączyć je do usługi Azure AD w oparciu o następujące instrukcje:
    - Przy użyciu rozwiązania Autopilot. Aby uzyskać więcej informacji, zobacz [Tryb sterowany przez użytkownika z rozwiązaniem Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven).
    - Bez rozwiązania Autopilot: Aby uzyskać więcej informacji, zobacz [Dołączanie urządzenia z systemem Windows 10 do usługi Azure AD podczas pierwszego uruchomienia](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device).

### <a name="what-happens-when-i-click-deploy"></a>Co się stanie po kliknięciu przycisku Wdróż?
Użytkownik i urządzenie zostaną dodane do nowych grup zabezpieczeń. Zostaną one również skonfigurowane przy użyciu ustawień zalecanych przez usługę Intune na potrzeby zabezpieczeń i produktywności w szkole lub w pracy. Po dołączeniu urządzenia do usługi Azure AD przez użytkownika do urządzenia zostaną dodane dodatkowe aplikacje i ustawienia. Aby dowiedzieć się więcej o tych dodatkowych konfiguracjach, zobacz [Szybki start: Rejestrowanie urządzenia z systemem Windows 10](~/enrollment/quickstart-enroll-windows-device.md).

## <a name="additional-information"></a>Dodatkowe informacje

### <a name="register-device-with-windows-autopilot-optional"></a>Rejestracja urządzenia przy użyciu rozwiązania Windows Autopilot (opcjonalnie)

Opcjonalnie możesz wybrać opcję użycia urządzenia zarejestrowanego w rozwiązaniu Autopilot. W przypadku użycia rozwiązania Autopilot w tym scenariuszu z przewodnikiem zostanie przypisany profil wdrożenia rozwiązania Autopilot oraz profil strony stanu rejestracji. Profil wdrożenia rozwiązania Autopilot zostanie skonfigurowany w następujący sposób:
- Tryb sterowany przez użytkownika — użytkownik końcowy musi wprowadzić nazwę użytkownika i hasło podczas instalacji systemu Windows.
- Dołączanie do usługi Azure AD.
- Dostosowywanie Instalatora systemu Windows:
  - Ukrywanie ekranu postanowień licencyjnych dotyczących oprogramowania firmy Microsoft
  - Ukrywanie ustawień prywatności 
  - Tworzenie profilu użytkownika lokalnego bez uprawnień administratora lokalnego
  - Ukrywanie opcji zmiany konta na firmowej stronie logowania

Strona stanu rejestracji zostanie skonfigurowana jako włączona tylko w przypadku urządzeń korzystających z rozwiązania Autopilot. Nie będzie blokować oczekiwania na zainstalowanie wszystkich aplikacji.

Scenariusz z przewodnikiem przypisze również użytkownika do wybranego urządzenia korzystającego z rozwiązania Autopilot w celu uzyskania spersonalizowanego środowiska instalacji.

#### <a name="post-requisites"></a>Wymagania końcowe
Po dołączeniu urządzenia do usługi Azure Active Directory przez użytkownika wobec urządzenia zostaną zastosowane następujące konfiguracje:
1. Usługa Office 365 ProPlus zostanie automatycznie zainstalowana na komputerze zarządzanym przez chmurę. Obejmuje ona znane aplikacje, w tym programy Access, Excel, OneNote, Outlook, PowerPoint, Publisher, Skype dla firm oraz Word. Za pomocą tych aplikacji można łączyć się z usługami Office 365, takimi jak SharePoint Online, Exchange Online i Skype dla firm Online. Usługa Office 365 ProPlus jest regularnie aktualizowana i rozbudowywana o nowe funkcje, w przeciwieństwie do wersji usługi Office bez subskrypcji. Aby zapoznać się z listą nowych funkcji, zobacz Co nowego w usłudze Office 365.
2. Punkty odniesienia zabezpieczeń systemu Windows zostaną zainstalowane na komputerze zarządzanym przez chmurę. Jeśli skonfigurowano funkcję zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender, scenariusz z przewodnikiem również skonfiguruje ustawienia punktu odniesienia dla usługi Defender. Zaawansowana ochrona przed zagrożeniami w usłudze Defender zapewnia nową warstwę ochrony po naruszeniu zabezpieczeń stosu zabezpieczeń systemu Windows 10. Korzystając z połączenia technologii klienta wbudowanej w system Windows 10 oraz niezawodnej usługi w chmurze, pomaga w wykrywaniu zagrożeń, które przeszły przez inne formy ochrony. 

## <a name="next-steps"></a>Następne kroki

- W przypadku korzystania z funkcji zaawansowanego wykrywania zagrożeń w usłudze Windows Defender należy utworzyć [Zasady zgodności z usługą Intune](~/protect/advanced-threat-protection.md#create-and-assign-the-compliance-policy), aby wymagać analizy zagrożeń usługi Defender w celu zapewnienia zgodności.
- Utwórz [Zasady dostępu warunkowego opartego na urządzeniach](~/protect/advanced-threat-protection.md#create-a-conditional-access-policy), aby zablokować dostęp, jeśli urządzenie nie będzie zgodne z zasadami usługi Intune.
