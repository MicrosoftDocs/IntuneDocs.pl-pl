---
title: "Rozwiązywanie problemów związanych z zarządzaniem aplikacjami mobilnymi | Dokumentacja firmy Microsoft"
description: "W tym temacie przedstawiono kilka wskazówek dotyczących rozwiązywania problemów związanych z wdrożeniami dostępu warunkowego."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Rozwiązywanie problemów związanych z zarządzaniem aplikacjami mobilnymi

Jeśli masz problemy z zarządzaniem aplikacjami mobilnymi Intune, rozpocznij tutaj. Ten temat zawiera omówienie niektórych często występujących problemów i zadawanych pytań oraz przedstawia odpowiednie rozwiązania i odpowiedzi.

## <a name="common-it-administrator-issues"></a>Typowe problemy administratora IT

1. **Problem:** zasady ochrony aplikacji bez rejestracji urządzenia wprowadzone w portalu Azure Portal nie są stosowane do aplikacji Skype dla firm na urządzeniach z systemem iOS i Android.

  **Rozwiązanie**: skonfiguruj aplikację Skype dla firm do korzystania z nowoczesnego uwierzytelniania.  Postępuj zgodnie z instrukcjami podanymi w temacie [Zapewnianie dzierżawcy możliwości nowoczesnego uwierzytelniania](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx), aby skonfigurować nowoczesne uwierzytelnianie dla aplikacji Skype.

2. **Problem:** zasady ochrony aplikacji nie są stosowane do dowolnej [obsługiwanej aplikacji pakietu Office](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) dla jakiegokolwiek użytkownika.

  **Rozwiązanie**: potwierdź, że użytkownik ma licencję na usługę Intune oraz że aplikacje pakietu Office są objęte wdrożonymi zasadami ochrony aplikacji. Zastosowanie nowo wdrożonych zasad ochrony aplikacji może potrwać do 8 godzin.

3. **Problem:** użytkownik będący administratorem IT nie może skonfigurować zasad ochrony aplikacji w portalu Azure Portal.

  **Rozwiązanie**:

  Następujące role użytkownika mają dostęp do portalu Azure Portal:

  - Administrator globalny, którego można skonfigurować w [portalu usługi Office](http://portal.office.com/)
  - Właściciel, którego można skonfigurować w [portalu Azure](https://portal.azure.com/).
  - Współautor, którego można skonfigurować w [portalu Azure](https://portal.azure.com/).<br>

  Zobacz [Przygotowywanie się do skonfigurowania zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md), aby uzyskać pomoc dotyczącą konfigurowania tych ról.

4. **Problem:** w raportach konsoli administratora nie są widoczne konta użytkowników, dla których niedawno wdrożono zasady ochrony aplikacji.

  **Rozwiązanie**: w przypadku użytkownika niedawno objętego zasadami ochrony aplikacji wyświetlenie informacji na jego temat w raportach może nastąpić po upływie nawet 24 godzin.

5. **Problem:** wprowadzanie zmian/aktualizacji zasad zajmuje nawet do 8 godzin.  

  **Rozwiązanie**: użytkownik końcowy może wylogować się z aplikacji i zalogować się do niej ponownie, aby wymusić synchronizację z usługą.  

6. **Problem:** zasady ochrony aplikacji nie są stosowane do urządzeń korzystających z programu DEP firmy Apple.

  **Rozwiązanie**: upewnij się, że używasz koligacji użytkownika na potrzeby programu Device Enrollment Program (DEP) firmy Apple. Koligacja użytkownika jest wymagana dla każdej aplikacji, która wymaga uwierzytelniania użytkownika w ramach programu DEP.
Zobacz [Rejestrowanie urządzeń firmowych z systemem iOS korzystających z programu Device Enrollment Program](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md), aby uzyskać więcej informacji dotyczących rejestrowania urządzeń z systemem iOS korzystających z programu DEP.

## <a name="common-end-user-issues"></a>Typowe problemy użytkowników końcowych

### <a name="issues-on-ios"></a>Problemy w systemie iOS

Okno dialogowe/komunikat o błędzie | Przyczyna | Korekty |
-- | --- | --- |
**Nie skonfigurowano aplikacji**: Nie skonfigurowano korzystania przez Ciebie z tej aplikacji. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Nie można wykryć zasad ochrony wymaganych dla tej aplikacji. |Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują tę aplikację.
**Intune Managed Browser — Zapraszamy**: Ta aplikacja działa najlepiej, gdy jest zarządzana przez usługę Microsoft Intune. Możesz przeglądać sieć Web za pomocą tej aplikacji, a jeśli jest ona zarządzana przez usługę Microsoft Intune, uzyskasz dostęp do dodatkowych funkcji ochrony danych. | Nie można wykryć zasad ochrony wymaganych dla aplikacji Intune Managed Browser. <br><br>Użytkownik nadal może korzystać z tej aplikacji do przeglądania sieci Web, ale nie jest ona zarządzana przez usługę Intune. | Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują aplikację Intune Managed Browser.
**Logowanie nie powiodło się**: Nie możemy Cię zalogować w tej chwili. Spróbuj ponownie później. | Nie można zarejestrować użytkownika przy użyciu usługi MAM po dokonaniu próby logowania z użyciem konta służbowego. | Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują tę aplikację.
**Nie skonfigurowano konta**: Twoja organizacja nie skonfigurowała na Twoim koncie dostępu do danych służbowych. Skontaktuj się z administratorem działu IT w celu uzyskania pomocy. | Konto użytkownika nie ma licencji Intune A Direct. | Upewnij się, że konto użytkownika ma przypisaną licencję usługi Intune w [portalu pakietu Office](http://portal.office.com).
**Niezgodne urządzenie**: nie można użyć tej aplikacji, ponieważ używasz urządzenia z usuniętymi ograniczeniami. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Usługa Intune wykryła, że użytkownik korzysta z urządzenia ze zdjętymi zabezpieczeniami systemu. | Przywróć ustawienia fabryczne urządzenia. Postępuj zgodnie z [tymi instrukcjami](https://support.apple.com/en-us/HT201274) z witryny pomocy technicznej firmy Apple.
**Wymagane jest połączenie z Internetem**: Aby zweryfikować, czy możesz używać tej aplikacji, musisz mieć połączenie z Internetem. | Urządzenie nie jest połączone z Internetem. | Połącz urządzenie z siecią Wi-Fi lub siecią transmisji danych.
**Nieznany błąd**: Spróbuj ponownie uruchomić tę aplikację. Jeśli ten problem będzie nadal występować, skontaktuj się z administratorem działu IT w celu uzyskania pomocy. | Wystąpił nieznany błąd. | Poczekaj chwilę i spróbuj ponownie. Jeśli błąd będzie nadal występować, utwórz bilet pomocy technicznej z użyciem usługi Intune [w tym miejscu](/how-to-get-support-for-microsoft-intune.md).
**Uzyskiwanie dostępu do danych organizacji**: Podane konto służbowe nie ma dostępu do tej aplikacji. Może być konieczne zalogowanie się przy użyciu innego konta. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Usługa Intune wykryła, że użytkownik próbował zalogować się przy użyciu drugiego konta służbowego, które różni się od konta zarejestrowanego w oprogramowaniu do zarządzania aplikacjami mobilnymi (MAM) dla tego urządzenia. Oprogramowanie MAM może zarządzać jednocześnie tylko jednym kontem służbowym na danym urządzeniu. | Zaloguj się przy użyciu konta, którego nazwa użytkownika jest wstępnie wypełniona na ekranie logowania. <br> <br> Ewentualnie zaloguj się przy użyciu nowego konta służbowego i usuń istniejące konto zarejestrowane w oprogramowaniu MAM.
**Problem z połączeniem**: Wystąpił nieoczekiwany problem z połączeniem. Sprawdź połączenie i spróbuj ponownie.  |  Nieoczekiwany błąd. | Poczekaj chwilę i spróbuj ponownie. Jeśli błąd będzie nadal występować, utwórz bilet pomocy technicznej z użyciem usługi Intune [w tym miejscu](/how-to-get-support-for-microsoft-intune.md).
**Alert**: Nie można już używać tej aplikacji. Aby uzyskać więcej informacji, skontaktuj się z administratorem działu IT. | Nie można zweryfikować certyfikatu aplikacji. | Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Zainstaluj aplikację ponownie.
**Błąd**: Ta aplikacja napotkała problem i musi zostać zamknięta. Jeśli ten błąd będzie się powtarzać, skontaktuj się z administratorem działu IT. | Nie można odczytać numeru PIN aplikacji MAM z pęku kluczy systemu Apple iOS. | Uruchom urządzenie ponownie. Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Zainstaluj aplikację ponownie.


### <a name="issues-on-android"></a>Problemy w systemie Android

Okno dialogowe/komunikat o błędzie | Przyczyna | Korekty |
-- | --- | --- |
**Nie skonfigurowano aplikacji**: Nie skonfigurowano korzystania przez Ciebie z tej aplikacji. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Nie można wykryć zasad ochrony wymaganych dla tej aplikacji. |Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują tę aplikację.
**Uruchomienie aplikacji nie powiodło się**: Wystąpił problem podczas uruchamiania aplikacji. Spróbuj zaktualizować aplikację lub aplikację Portal firmy usługi Intune. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT. | Usługa Intune wykryła prawidłowe zasady ochrony dla tej aplikacji, ale podczas inicjowania oprogramowania MAM występuje awaria aplikacji. | Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Upewnij się, że aplikacja Portal firmy usługi Intune jest zainstalowana na urządzeniu i jest aktualna. <br><br> Jeśli błąd będzie się powtarzać, wyślij dzienniki do usługi Intune przy użyciu aplikacji Portal firmy lub utwórz bilet pomocy technicznej [w tym miejscu](/how-to-get-support-for-microsoft-intune.md).
**Nie znaleziono aplikacji**: Na tym urządzeniu nie ma żadnych aplikacji, którym organizacja zezwala na otwieranie tej zawartości. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Użytkownik próbował otworzyć dane służbowe za pomocą innej aplikacji, ale usługa Intune nie można odnaleźć żadnych innych zarządzanych aplikacji, które mają zezwolenie na otwieranie tych danych. | Upewnij się, zasady ochrony aplikacji systemu Android są wdrożone w zabezpieczeniach użytkownika i obejmują co najmniej jedną inną aplikację z obsługą zarządzania aplikacjami mobilnymi (MAM), przy użyciu której można otworzyć te dane.
**Logowanie nie powiodło się**: Ponów próbę zalogowania. Jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT w celu uzyskania pomocy. | Nie można uwierzytelnić konta, przy użyciu którego użytkownik próbował się zalogować. | Upewnij się, że użytkownik loguje się przy użyciu konta służbowego, które jest już zarejestrowane w usłudze Intune MAM (pierwszego konta służbowego, przy użyciu którego wykonano pomyślne logowanie w tej aplikacji). <br><br> Wyczyść dane aplikacji. <br><br> Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Upewnij się, że wersja aplikacji Portal firmy jest aktualna.
**Wymagane jest połączenie z Internetem**: Aby zweryfikować, czy możesz używać tej aplikacji, musisz mieć połączenie z Internetem. | Urządzenie nie jest połączone z Internetem. | Połącz urządzenie z siecią Wi-Fi lub siecią transmisji danych.
**Niezgodne urządzenie**: Nie można korzystać z tej aplikacji, ponieważ używane przez Ciebie urządzenie ma zdjęte zabezpieczenia (root). Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Usługa Intune wykryła, że użytkownik korzysta z urządzenia z odblokowanym dostępem. | Przywróć ustawienia fabryczne urządzenia.
**Nie skonfigurowano konta**: Ta aplikacja musi być zarządzana przez usługę Microsoft Intune, ale Twoje konto nie zostało skonfigurowane. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Konto użytkownika nie ma licencji Intune A Direct. | Upewnij się, że konto użytkownika ma przypisaną licencję usługi Intune w [portalu pakietu Office](http://portal.office.com).
**Nie można zarejestrować aplikacji**: Ta aplikacja musi być zarządzana przez usługę Microsoft Intune, ale w tej chwili nie udało nam się jej zarejestrować. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Nie można automatycznie zarejestrować aplikacji przy użyciu usługi zarządzania aplikacjami mobilnymi, gdy wymagane są zasady ochrony aplikacji. | Wyczyść dane aplikacji. <br><br> Wyślij dzienniki do usługi Intune za pomocą aplikacji Portal firmy lub pliku biletu pomocy technicznej [tutaj](/how-to-get-support-for-microsoft-intune.md).





### <a name="see-also"></a>Zobacz także
- [Weryfikowanie konfiguracji zarządzania aplikacjami mobilnymi](../deploy-use/validate-mobile-application-management.md)
- [Przygotowywanie się do konfigurowania zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


