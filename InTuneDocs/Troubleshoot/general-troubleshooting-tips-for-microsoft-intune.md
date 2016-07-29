---
title: "Ogólne porady dotyczące rozwiązywania problemów | Microsoft Intune"
description: "Zasoby ogólne ułatwiające rozwiązywanie problemów z usługą Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: d321930262a9bcf9542c757fdf0b945d0419930c


---

# Ogólne porady dotyczące rozwiązywania problemów w usłudze Microsoft Intune
Po wdrożeniu usługi Microsoft Intune mogą wystąpić problemy z konfiguracją lub klientami. Zasoby przedstawione poniżej mogą pomóc w poznaniu przyczyny problemu i w konsekwencji w jego rozwiązaniu.

> [!NOTE]
> W celu utworzenia żądania obsługi lub wyświetlenia istniejącego żądania przejdź do [centrum administracyjnego usługi Office 365](https://portal.office.com/admin/default.aspx). Aby uzyskać więcej informacji na temat opcji pomocy technicznej, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
## Definiowanie problemu

-   Czym objawia się problem?

-   Kto napotyka takie zachowanie? Na jakich platformach i urządzeniach ma to miejsce?

-   Czy urządzenie działało wcześniej poprawnie?

-   Jakie zmiany wprowadzono w usłudze Intune lub w konfiguracji urządzenia?

-   Należy rozważyć, czy w używanym środowisku nie wprowadzono innych zmian niż zmiany w konfiguracji.

-   Jak często występuje ten problem? Czy występuje sporadycznie czy cały czas?

-   Czy użytkownik może mieć problemy dotyczące uwierzytelniania? Jeśli jest taka możliwość, sprawdź, czy użytkownik może zalogować się do innych usług używających usługi Azure Active Directory. Sprawdź też, czy użytkownik może zalogować się z innego urządzenia.

-   Czy sprawdzono stan usługi? Kondycję usługi Intune możesz monitorować w [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx). Wybierz pozycję **Kondycja usługi** w lewym okienku.

## Zbieranie dostępnych danych

-   Dzienniki urządzenia. Aby dowiedzieć się, jak zbierać dzienniki urządzenia, zobacz:
  - [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą kabla USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą poczty e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Wysyłanie błędów rejestracji systemu Android do administratora IT](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [Wysyłanie błędów rejestracji systemu iOS do administratora IT](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Dane konsoli administracyjnej. Na przykład w przypadku problemów z implementacją zasad należy sprawdzić określone zasady i ich stan zgodnie z opisem w temacie [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## Wyszukiwanie rozwiązania

-   Wyszukaj rozwiązanie w sieci Web: Jeśli na przykład zostanie wyświetlony błąd 0x80073CF0, możesz wyszukać w sieci Web hasło **technet intune 0x80073cf0** i znaleźć w ten sposób artykuł [Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md), w którym znajdują się sugestie dotyczące tego problemu.

-   Możesz wyszukać odpowiedzi na [forum biblioteki TechNet dotyczącym usługi Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Jeśli problem nie został wcześniej rozpoznany, należy zadać pytanie, aby sprawdzić, jakie mogą być sugestie społeczności.

-   Można otworzyć żądanie obsługi. Pomoc techniczna usługi Intune łatwiej będzie mogła rozwiązać problem, jeśli zostanie on zdefiniowany i zostaną zebrane dostępne dane.

    W celu utworzenia żądania obsługi przejdź do [centrum administracyjnego usługi Office 365](https://portal.office.com/admin/default.aspx). Aby uzyskać więcej informacji na temat opcji pomocy technicznej, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## Zasoby społeczności
Inne przydatne informacje można znaleźć w tych zasobach społeczności:

-   [Przewodnik po rzeczach niezbędnych w usłudze Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) zawiera linki do wielu zasobów, które mogą ułatwić konfigurowanie usługi Intune, zarządzanie nią i rozwiązywanie problemów z tą usługą.

-   [Blog poświęcony usłudze Intune](http://blogs.technet.com/b/windowsintune/)

-   [Śledź usługę Intune w serwisie Twitter](https://twitter.com/MSIntune)

-   [Fora dotyczące usługi Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### Następne kroki
Tematy wymienione poniżej pomagają rozwiązywać określone problemy. Jeśli te informacje nie będą pomocne, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Rozwiązywanie problemów z dostępem do zasobów firmy przy użyciu usługi Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](troubleshoot-device-enrollment-in-intune.md)

[Rozwiązywanie problemów dotyczących zasad w usłudze Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Rozwiązywanie problemów z instalacją klientów w usłudze Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


