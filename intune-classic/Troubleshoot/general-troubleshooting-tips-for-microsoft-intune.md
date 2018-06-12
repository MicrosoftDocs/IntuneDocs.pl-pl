---
title: Ogólne wskazówki dotyczące rozwiązywania problemów
description: Zasoby ogólne ułatwiające rozwiązywanie problemów z usługą Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/08/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bbcfa2de4b2d6ef7bff481817a289f56e746ee7f
ms.sourcegitcommit: 2061f7a442efc96c8afd5db764d11531563c7e39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34718033"
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Ogólne porady dotyczące rozwiązywania problemów w usłudze Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Po wdrożeniu usługi Microsoft Intune mogą wystąpić problemy z konfiguracją lub z urządzeniami klientów. Przedstawione poniżej zasoby mogą być pomocne w znalezieniu przyczyny problemu i w jego rozwiązaniu.

> [!NOTE]
> W celu utworzenia żądania obsługi lub wyświetlenia istniejącego żądania przejdź na stronę [pomocy i obsługi technicznej platformy Azure](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview). Aby uzyskać więcej informacji na temat opcji pomocy technicznej, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## <a name="define-the-problem"></a>Definiowanie problemu

-   Czym objawia się problem?

-   Kto napotyka takie zachowanie? Na jakich platformach i urządzeniach ma to miejsce?

-   Czy urządzenie działało wcześniej poprawnie?

-   Jakie zmiany wprowadzono w usłudze Intune lub w konfiguracji urządzenia?

-   Czy w używanym środowisku nie wprowadzono innych zmian niż zmiany konfiguracji?

-   Jak często występuje ten problem? Czy występuje sporadycznie czy cały czas?

-   Czy użytkownik może mieć problemy dotyczące uwierzytelniania? Jeśli takie problemy mają miejsce, sprawdź, czy użytkownik może zalogować się do innych usług używających usługi Azure Active Directory. Sprawdź też, czy użytkownik może zalogować się z innego urządzenia.

-   Czy sprawdzono stan usługi? Kondycję usługi Intune możesz monitorować w [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx). Wybierz pozycję **Kondycja usługi** w lewym okienku.

## <a name="collect-available-data"></a>Zbieranie dostępnych danych

- Następujące zasoby ułatwiają zapoznanie się ze sposobami gromadzenia dzienników urządzeń:
  - [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą kabla USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą poczty e-mail](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Wysyłanie błędów rejestracji systemu Android do administratora IT](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [Wysyłanie błędów rejestracji systemu iOS do administratora IT](/intune-user-help/send-errors-to-your-it-admin-ios)

- Korzystając z danych konsoli administracyjnej (na przykład w przypadku problemów z implementacją zasad), należy sprawdzić odpowiednie zasady i ich stan zgodnie z opisem w artykule [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="research-the-solution"></a>Wyszukiwanie rozwiązania

-   Wyszukaj rozwiązanie w sieci Web: Jeśli na przykład zostanie wyświetlony błąd 0x80073CF0, możesz wyszukać w sieci Web hasło **technet intune 0x80073cf0** i znaleźć w ten sposób artykuł [Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md). Wymieniony artykuł zawiera sugestie dotyczące usuwania tego błędu.

-   Możesz wyszukać odpowiedzi na [forum biblioteki TechNet dotyczącym usługi Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Jeśli problem nie został wcześniej opisany, zadaj pytanie, aby zapoznać się z ewentualnymi sugestii społeczności.

-   Otwórz żądanie obsługi. Pomoc techniczna usługi Intune będzie mogła lepiej udzielić pomocy w rozwiązaniu problemu, jeśli zostanie on zdefiniowany oraz zostaną zebrane dostępne dane.

    W celu utworzenia żądania obsługi [przejdź do centrum administracyjnego usługi Office 365](https://portal.office.com/admin/default.aspx). Aby uzyskać więcej informacji na temat opcji pomocy technicznej, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## <a name="find-community-resources"></a>Znajdowanie zasobów społeczności
Inne przydatne informacje można znaleźć w tych zasobach społeczności:

-   [Przewodnik po rzeczach niezbędnych w usłudze Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) zawiera linki do wielu zasobów, które mogą ułatwić konfigurowanie usługi Intune, zarządzanie nią i rozwiązywanie problemów z tą usługą.

-   [Blog poświęcony usłudze Intune](http://blogs.technet.com/b/windowsintune/)

-   [Śledź usługę Intune w serwisie Twitter](https://twitter.com/MSIntune)

-   [Fora dotyczące usługi Intune](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>Następne kroki
Tematy wymienione poniżej zawierają informacje na temat rozwiązywania określonych problemów. Jeśli te informacje nie będą pomocne, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

[Rozwiązywanie problemów z programem Endpoint Protection w usłudze Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Rozwiązywanie problemów z dostępem do zasobów firmy przy użyciu usługi Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Rozwiązywanie problemów z wdrażaniem aplikacji w usłudze Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune](troubleshoot-device-enrollment-in-intune.md)

[Rozwiązywanie problemów dotyczących zasad w usłudze Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Rozwiązywanie problemów z instalacją klientów w usłudze Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)
