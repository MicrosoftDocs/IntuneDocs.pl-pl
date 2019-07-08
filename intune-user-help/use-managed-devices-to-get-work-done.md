---
title: Wykonywanie pracy przy użyciu urządzeń zarządzanych | Microsoft Docs
description: Dowiedz się, na czym polega rejestrowanie urządzeń w usłudze Intune w celu zarządzania nimi.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2c0d3484311d044842daf6718b306d45fc93edf2
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67545929"
---
# <a name="enroll-device-for-access-to-work-or-school-resources"></a>Rejestrowanie urządzeń do uzyskiwania dostępu do zasobów służbowe.
Aby zarejestrować urządzenie i uzyskać dostęp do poczty e-mail i aplikacji, musisz zainstalować aplikację Portal firmy usługi Intune lub aplikacji Microsoft Intune. Podczas rejestrowania, zasad podstawowych operacji zarządzania, które organizacji została skonfigurowana, takie jak hasła, kod PIN i szyfrowanie, są stosowane do Twojego urządzenia. Gdy ustawienia urządzenia spełniają wszystkie wymagania organizacji, będziesz mieć bezpieczny dostęp informacji o pracy z dowolnego miejsca.  

Aplikacje Portal firmy i Microsoft Intune bezpieczeństwo Twoim zarejestrowanym urządzeniu, zapewniając, że ustawienia urządzenia są zgodne zasadami organizacji. 

Aplikacja Portal firmy również:  
* Twoje informacje prywatne i służbowe utrzymują osobne.  
* Ułatwia znajdowanie i instalowanie pracę i aplikacji.   

## <a name="get-the-apps"></a>Pobierz aplikacje
Aby uzyskać aplikację Portal firmy:

- Zainstaluj aplikację Portal firmy ze sklepu z aplikacjami specyficzne dla platformy. W niektórych przypadkach Twojej organizacji zostanie zainstalowana aplikacja Portal firmy dla Ciebie.  
- Przejdź do [witryny internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980) dostęp do aplikacji w przeglądarce.  

Jeśli są wymagane do korzystania z aplikacji Microsoft Intune, zostanie zainstalowany Twojej organizacji.  


## <a name="what-information-can-my-company-see-when-i-enroll"></a>Jakie informacje może wyświetlać moja firma po mojej rejestracji?
Po zarejestrowaniu urządzenia, osoby pomocy technicznej w Twojej organizacji może zobaczyć tylko informacje, które są odpowiednie do pracy. Twoje dane osobowe nie będą widoczne. Jeśli masz rejestrowania urządzenia osobistego do użytku w miejscu pracy, [Dowiedz się dokładnie, co można, a nie widać](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).  


## <a name="whats-the-difference-between-the-apps-and-the-website"></a>Jakie są różnice między aplikacjami a witryną internetową?
Aplikacja Portal firmy jest dostępna dla systemu Windows 10, iOS, macOS i urządzeń z systemem Android. Bezproblemowa integracja z odpowiedniej platformy urządzenia. Wersja w witrynie internetowej jest dostępna z dowolnego urządzenia i udostępnia to samo uniwersalne środowisko niezależnie od tego, którego urządzenia używasz. 

Aplikacja Microsoft Intune jest dla firmowych urządzeń z systemem Android.  

## <a name="what-kind-of-devices-can-you-enroll-with-company-portal"></a>Jakiego rodzaju urządzenia będą rejestrowane za pomocą aplikacji Portal firmy?
- Urządzenia firmy Apple z systemem iOS (np. iPhone oraz iPad) i macOS (np. MacBook oraz iMac)
- Urządzenia z systemem Android
- Urządzenia z systemem Windows
    - Windows 10 Mobile
    - Windows 10 Desktop
    - Windows Phone 8,1
    - Windows 8.1

## <a name="what-kind-of-devices-can-you-enroll-with-the-microsoft-intune-app"></a>Jakiego rodzaju urządzenia będą rejestrowane za pomocą aplikacji Microsoft Intune?  
Możesz zarejestrować firmowe urządzenia z systemem Android, które Twoja organizacja ma skonfigurowane do korzystania z aplikacji. Aplikacja obsługuje system Android 6.0 lub nowszy. 

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Czy można usunąć komputer lub urządzenie z Portalu firmy?
Tak, można usunąć komputer lub urządzenie z Portalu firmy lub zresetować je. Istnieje różnica między **usunięciem** a **zresetowaniem**.

Gdy usuniesz komputer lub urządzenie z Portalu firmy, urządzenie zostanie wyrejestrowane z usługi Intune. Po wyrejestrowaniu nie będzie można uzyskać dostępu do Portalu firmy za pomocą tego urządzenia, a niektóre dane firmowe mogą zostać z niego usunięte. Aby dowiedzieć się, jak usunąć urządzenie z portalu firmy, zobacz następujące linki:  

- [Wyrejestrowywanie urządzenia z systemem Android](unenroll-your-device-from-intune-android.md)
- [Wyrejestrowywanie urządzenia z systemem iOS](unenroll-your-device-from-intune-ios.md)
- [Wyrejestrowywanie urządzenia z systemem macOS](unenroll-your-device-from-intune-macos.md)
- [Wyrejestrowywanie urządzenia z systemem Windows](unenroll-your-device-from-intune-windows.md)

Po zresetowaniu komputera lub urządzenia Portal firmy podejmuje próbę przywrócenia domyślnych ustawień fabrycznych komputera lub urządzenia. Zresetowanie urządzenia spowoduje usunięcie wszystkich danych osobistych i firmowych z urządzenia. Jeśli zgubisz urządzenie, możesz zresetować je zdalnie z poziomu witryny internetowej Portal firmy.  

Aby dowiedzieć się, jak zresetować urządzenie, zobacz [Resetowanie urządzenia z witryny internetowej Portal firmy](reset-erase-your-device-cpwebsite.md).  

## <a name="can-you-remove-a-computer-or-device-from-the-microsoft-intune-app"></a>Można usunąć komputer lub urządzenie z aplikacji Microsoft Intune?
Nie, nie ma możliwości umożliwiające usunięcie urządzenia firmowe z aplikacji Microsoft Intune.  

## <a name="what-if-i-cant-see-my-device-in-the-company-portal-or-microsoft-intune-app"></a>Co zrobić, jeśli nie widzę mojego urządzenia w aplikacji Portal firmy lub Microsoft Intune?
Aby można było wyświetlić urządzenie, należy najpierw dodać je do Portalu firmy. Przejdź do któregokolwiek Portalu firmy wskazanego przez administratora, a następnie postępuj zgodnie z instrukcjami dotyczącymi urządzenia. Ponadto urządzenia będące własnością firmy i zarządzane przez firmę nie będą widoczne.

Jeśli używasz aplikacji Microsoft Intune będą widoczne tylko te urządzenia, którego obecnie używasz. Innymi zarejestrowanymi urządzeniami, nie będzie widoczne w aplikacji.  

## <a name="where-else-can-i-go-for-help"></a>Gdzie indziej szukać pomocy?  
Aby rozwiązać typowe problemy i pytania, zapoznaj się z tych docs specyficzne dla platformy:  

- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem Android](check-compliance-on-your-device-android.md)  
- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem iOS](troubleshoot-your-device-ios.md)
- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem macOS](troubleshoot-your-device-macos.md)
- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem Windows](troubleshoot-your-device-windows.md)

Użytkownik może również skontaktowanie się z pracownikiem pomocy technicznej. Portal firmy i Microsoft Intune app oferować Pomoc i Obsługa stron, w których przedstawiono informacje kontaktowe i sposoby, aby zgłosić problem. Informacje kontaktowe są również dostępne w Twojej organizacji, dla których [witryny internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="next-steps"></a>Następne kroki  

Uzyskaj pomoc, począwszy od rejestracji, które są specyficzne dla platformy urządzenia:  

- [Korzystanie z urządzenia z systemem Android](using-your-android-device-with-intune.md)
- [Korzystanie z urządzenia z systemem iOS](using-your-ios-device-with-intune.md)
- [Korzystanie z urządzenia z systemem macOS](using-your-macos-device-with-intune.md)
- [Korzystanie z urządzenia z systemem Windows](using-your-windows-device-with-intune.md)
- [Korzystanie z witryny sieci Web Portal firmy](using-the-intune-company-portal-website.md)


