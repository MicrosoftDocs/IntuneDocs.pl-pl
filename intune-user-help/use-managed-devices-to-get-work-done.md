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
ms.openlocfilehash: 2f698f03ed3c7523ef1d768d2a1361d6d1a55008
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883870"
---
# <a name="enroll-device-for-access-to-work-or-school-resources"></a>Rejestrowanie urządzenia w celu uzyskania dostępu do zasobów służbowych
Aby zarejestrować urządzenie i uzyskać dostęp do poczty e-mail i aplikacji, musisz zainstalować aplikację Intune — Portal firmy lub Microsoft Intune aplikację. Po zarejestrowaniu podstawowe zasady zarządzania, które zostały skonfigurowane przez organizacji, takie jak hasło, numer PIN i szyfrowanie, są stosowane na urządzeniu. Gdy ustawienia urządzenia spełnią wszystkie wymagania organizacji, możesz bezpiecznie uzyskać dostęp do informacji służbowych praktycznie z dowolnego miejsca.  

Aplikacje Portal firmy i Microsoft Intune zachowują swoje zarejestrowane urządzenie, upewniając się, że ustawienia urządzenia są zgodne z zasadami organizacji. 

Aplikacja Portal firmy również:  
* Utrzymuje osobne informacje osobiste i służbowe.  
* Ułatwia znajdowanie i Instalowanie odpowiednich aplikacji służbowych.   

## <a name="get-the-apps"></a>Pobierz aplikacje
Aby uzyskać aplikację Portal firmy:

- Zainstaluj aplikację Portal firmy ze sklepu z aplikacjami specyficznymi dla platformy. W niektórych przypadkach organizacja zainstaluje Portal firmy aplikację.  
- Przejdź do [witryny sieci web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980) , aby uzyskać dostęp do aplikacji z przeglądarki.  

Jeśli jest wymagane użycie aplikacji Microsoft Intune, organizacja zainstaluje ją.  


## <a name="what-information-can-my-company-see-when-i-enroll"></a>Jakie informacje może wyświetlać moja firma po mojej rejestracji?
Po zarejestrowaniu urządzenia pracownicy działu pomocy technicznej Twojej organizacji mogą zobaczyć tylko te informacje, które są istotne do pracy. Twoje dane osobowe nie będą widoczne. Jeśli rejestrujesz urządzenie osobiste do użytku w pracy, [Dowiedz się dokładnie, co może być widoczne](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).  


## <a name="whats-the-difference-between-the-apps-and-the-website"></a>Jakie są różnice między aplikacjami a witryną internetową?
Aplikacja Portal firmy jest dostępna dla urządzeń z systemami Windows 10, iOS, macOS i Android. Bezproblemowo integruje się z odpowiednią platformą urządzenia. Wersja w witrynie internetowej jest dostępna z dowolnego urządzenia i udostępnia to samo uniwersalne środowisko niezależnie od tego, którego urządzenia używasz. 

Aplikacja Microsoft Intune jest dla urządzeń z systemem Android należących do firmy.  

## <a name="what-kind-of-devices-can-you-enroll-with-company-portal"></a>Jakiego rodzaju urządzenia można zarejestrować za pomocą Portal firmy?
- Urządzenia firmy Apple z systemem iOS (np. iPhone oraz iPad) i macOS (np. MacBook oraz iMac)
- Urządzenia z systemem Android
- Urządzenia z systemem Windows
  - Windows 10 Mobile
  - Windows 10 Desktop
  - Windows Phone 8,1
  - Windows 8.1

## <a name="what-kind-of-devices-can-you-enroll-with-the-microsoft-intune-app"></a>Jakiego rodzaju urządzenia można zarejestrować w aplikacji Microsoft Intune?  
Można rejestrować firmowe urządzenia z systemem Android, które organizacja skonfigurował do korzystania z aplikacji. Aplikacja obsługuje system Android 6,0 i nowsze. 

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Czy można usunąć komputer lub urządzenie z Portalu firmy?
Tak, można usunąć komputer lub urządzenie z Portalu firmy lub zresetować je. Istnieje różnica między **usunięciem** a **zresetowaniem**.

Gdy usuniesz komputer lub urządzenie z Portalu firmy, urządzenie zostanie wyrejestrowane z usługi Intune. Po wyrejestrowaniu nie będzie można uzyskać dostępu do Portalu firmy za pomocą tego urządzenia, a niektóre dane firmowe mogą zostać z niego usunięte. Aby dowiedzieć się, jak usunąć urządzenie z Portal firmy, zobacz następujące linki:  

- [Wyrejestrowywanie urządzenia z systemem Android](unenroll-your-device-from-intune-android.md)
- [Wyrejestrowywanie urządzenia z systemem iOS](unenroll-your-device-from-intune-ios.md)
- [Wyrejestrowywanie urządzenia z systemem macOS](unenroll-your-device-from-intune-macos.md)
- [Wyrejestrowywanie urządzenia z systemem Windows](unenroll-your-device-from-intune-windows.md)

Po zresetowaniu komputera lub urządzenia Portal firmy podejmuje próbę przywrócenia domyślnych ustawień fabrycznych komputera lub urządzenia. Zresetowanie urządzenia spowoduje usunięcie wszystkich danych osobistych i firmowych z urządzenia. Jeśli zgubisz urządzenie, możesz zresetować je zdalnie z poziomu witryny internetowej Portal firmy.  

Aby dowiedzieć się, jak zresetować urządzenie, zobacz [Resetowanie urządzenia z poziomu witryny sieci web Portal firmy](reset-erase-your-device-cpwebsite.md).  

## <a name="can-you-remove-a-computer-or-device-from-the-microsoft-intune-app"></a>Czy można usunąć komputer lub urządzenie z aplikacji Microsoft Intune?
Nie, nie ma możliwości usunięcia urządzenia należącego do firmy z aplikacji Microsoft Intune.  

## <a name="what-if-i-cant-see-my-device-in-the-company-portal-or-microsoft-intune-app"></a>Co zrobić, jeśli nie mogę zobaczyć mojego urządzenia w aplikacji Portal firmy lub Microsoft Intune?
Aby można było wyświetlić urządzenie, należy najpierw dodać je do Portalu firmy. Przejdź do któregokolwiek Portalu firmy wskazanego przez administratora, a następnie postępuj zgodnie z instrukcjami dotyczącymi urządzenia. Ponadto urządzenia będące własnością firmy i zarządzane przez firmę nie będą widoczne.

Jeśli używasz aplikacji Microsoft Intune, zobaczysz tylko aktualnie używane urządzenie. Inne zarejestrowane urządzenia nie będą widoczne dla Ciebie w aplikacji.  

## <a name="where-else-can-i-go-for-help"></a>Gdzie indziej szukać pomocy?  
Aby rozwiązać typowe problemy i pytania, zapoznaj się z następującymi dokumentami dotyczącymi danej platformy:  

- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem Android](check-compliance-on-your-device-android.md)  
- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem iOS](troubleshoot-your-device-ios.md)
- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem macOS](troubleshoot-your-device-macos.md)
- [Rozwiązywanie typowych problemów dotyczących urządzeń z systemem Windows](troubleshoot-your-device-windows.md)

Możesz również skontaktować się z osobą odpowiedzialną za pomoc techniczną. Aplikacja Portal firmy i Microsoft Intune oferują strony pomocy i obsługi technicznej, które wyświetlają informacje kontaktowe i sposoby zgłaszania problemu. Informacje kontaktowe są również dostępne w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980)organizacji.  

## <a name="next-steps"></a>Następne kroki  

Uzyskaj pomoc dotyczącą rejestracji, która jest specyficzna dla platformy urządzenia:  

- [Korzystanie z urządzenia z systemem Android](using-your-android-device-with-intune.md)
- [Korzystanie z urządzenia z systemem iOS](using-your-ios-device-with-intune.md)
- [Korzystanie z urządzenia z systemem macOS](using-your-macos-device-with-intune.md)
- [Korzystanie z urządzenia z systemem Windows](using-your-windows-device-with-intune.md)
- [Korzystanie z witryny sieci Web Portal firmy](using-the-intune-company-portal-website.md)


