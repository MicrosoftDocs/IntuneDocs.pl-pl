---
title: Wymagania dotyczące haseł dla urządzeń w Intune — Portal firmy | Microsoft Docs
description: W tym artykule opisano typowe wymagania dotyczące haseł, które organizacja może wymusić.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: efb3c261-1f6c-4d39-bfa4-18661f8c59c7
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9181510dad2640fcc8ea84ce2db2856bd02cbaf5
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502181"
---
# <a name="device-password-requirements-for-enrolled-devices"></a>Wymagania dotyczące hasła urządzenia dla zarejestrowanych urządzeń

Organizacja może wymagać utworzenia bezpieczniejszego hasła przed umożliwieniem dostępu do zasobów służbowych. W tym artykule opisano typowe wymagania dotyczące haseł dla urządzeń z systemami Windows 10, iOS, macOS i Android. Organizacja może nie wymusić wszystkich tych wymagań.  


Gdy hasło lub kod dostępu nie spełnia już wymagań, otrzymasz komunikat z Portal firmy. Opisze zmiany, które należy wprowadzić. Jeśli w komunikacie nie są podane żadne szczegóły, użyj tego artykułu jako odniesienia do porównania z bieżącym hasłem.  

> [!IMPORTANT]
> Jeśli hasło zostało zmienione w celu spełnienia wymagań, ale nadal trwa otrzymywanie powiadomień, należy ponownie uruchomić urządzenie.  

Aby uzyskać dodatkową pomoc lub dowiedzieć się, jakie są określone wymagania organizacji, skontaktuj się z osobą odpowiedzialną za pomoc techniczną IT. Zapoznaj się z [witryną internetową Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), aby uzyskać informacje kontaktowe.  

## <a name="windows-10-password-requirements"></a>Wymagania dotyczące haseł systemu Windows 10

| Wiadomość | Jak naprawić |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hasło jest wymagane. | Ustaw hasło. Twoja organizacja wymaga wprowadzenia hasła w celu odblokowania urządzenia. |
| Hasło jest za proste. |  Upewnij się, że hasło nie zawiera numerów sekwencyjnych ani powtarzających się, na przykład 1234 lub 1111. |
| Hasło jest za krótkie.| Zaktualizuj lub ustaw hasło zawierające więcej znaków. Twoja organizacja wymaga, aby hasło miało określoną długość. Rzeczywiste wybór będą się różnić, ale minimalna długość, którą mogą wymagać, wynosi 4 znaki, a maksymalna to 16. |
| Hasło musi zawierać tylko cyfry. | Ustaw hasło, które zawiera tylko cyfry.|
| Hasło musi zawierać tylko znaki alfanumeryczne. | Ustaw hasło, które zawiera kombinację cyfr i cyfr.|
| Hasło musi zawierać znaki złożone. | Dodaj znaki złożone, takie jak cyfry, wielkie litery i symbole, takie jak `$`, `%`i `#`. Twoja organizacja wymaga kombinacji liter, cyfr i znaków innych niż alfanumeryczne, aby utrudnić innym odgadnięcie hasła.|  
| Hasło wygasło. | Ustaw nowe hasło. Twoja organizacja wymaga zmiany hasła po określonej liczbie dni. |
| Hasło było używane niedawno. | Wybierz hasło, które nie było dotąd używane. Twoja organizacja wymaga, aby określony czas został przeszedł przed ponownym użyciem hasła. |

## <a name="ios-passcode-requirements"></a>wymagania dotyczące kodów dostępu systemu iOS

| Wiadomość | Jak naprawić |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kod dostępu jest wymagany.| Ustaw kod dostępu. Twoja organizacja wymaga wprowadzenia kodu dostępu w celu odblokowania urządzenia. |
| Kod dostępu jest zbyt prosty. |  Upewnij się, że kod dostępu nie zawiera numerów sekwencyjnych ani powtarzających się, na przykład 1234 lub 1111. |
| Kod dostępu jest za krótki. | Zaktualizuj lub ustaw kod dostępu zawierający więcej znaków. Twoja organizacja wymaga, aby kod dostępu miał określoną długość. Rzeczywiste wybór będą się różnić, ale minimalna długość, którą mogą wymagać, wynosi 4 znaki, a maksymalna to 14. Po zmianie kodu dostępu może zostać wyświetlony monit od firmy Apple informujący o wprowadzeniu co najmniej 6 znaków. Ten komunikat jest rekomendacją systemu firmy Apple. Jeśli Twoja organizacja wymaga tylko kodu dostępu zawierającego 4 lub 5 znaków, nie trzeba wprowadzać 6-cyfrowy kod dostępu.|  
| Kod dostępu musi zawierać tylko cyfry. | Ustaw kod dostępu, który zawiera tylko cyfry.|
| Kod dostępu musi zawierać tylko znaki alfanumeryczne.| Ustaw kod dostępu, który zawiera kombinację cyfr i liter.|
| Kod dostępu musi zawierać znaki inne niż alfanumeryczne. | Dodaj znaki specjalne, takie jak `&`, `!`, `$`, `%`i `#`. Twoja organizacja wymaga kombinacji liter, cyfr i znaków innych niż alfanumeryczne, aby utrudnić innym odgadnięcie kodu dostępu.|
| Kod dostępu wygasł. | Ustaw nowe hasło. Twoja organizacja wymaga zmiany hasła po określonej liczbie dni. |
| Kod dostępu był niedawno używany.| Wybierz kod dostępu, który nie był wcześniej używany. Twoja organizacja wymaga, aby określony czas został przeszedł przed ponownym użyciem kodu dostępu. |
|Wymagane jest uwierzytelnianie dotyku lub identyfikator urządzenia. | Skonfiguruj identyfikator touch lub identyfikator kroju. Twoja organizacja wymaga uwierzytelniania przy użyciu jednej z tych metod przed użyciem Autowypełniania haseł lub informacji o karcie kredytowej. | 

## <a name="macos-password-requirements"></a>Wymagania dotyczące hasła w systemie macOS
| Wiadomość | Jak naprawić |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hasło jest wymagane. | Ustaw hasło. Twoja organizacja wymaga wprowadzenia hasła w celu odblokowania urządzenia. |
| Hasło jest za proste.|  Upewnij się, że hasło nie zawiera numerów sekwencyjnych ani powtarzających się, na przykład 1234 lub 1111. |
| Hasło jest za krótkie. | Zaktualizuj lub ustaw hasło zawierające więcej znaków. Twoja organizacja wymaga, aby hasło miało określoną długość.|
| Hasło musi zawierać tylko cyfry. | Ustaw hasło, które zawiera tylko cyfry.|
| Hasło musi zawierać tylko znaki alfanumeryczne. | Ustaw hasło, które zawiera kombinację cyfr i cyfr.|
| Hasło musi zawierać znaki inne niż alfanumeryczne. | Dodaj znaki specjalne, takie jak `&`, `!`, `$`, `%`i `#`. Twoja organizacja wymaga kombinacji liter, cyfr i znaków innych niż alfanumeryczne, aby utrudnić innym odgadnięcie hasła.|
| Hasło wygasło. | Ustaw nowe hasło. Twoja organizacja wymaga zmiany hasła po określonej liczbie dni. |
| Hasło było używane niedawno. | Wybierz hasło, które nie było dotąd używane. Twoja organizacja wymaga, aby określony czas został przeszedł przed ponownym użyciem hasła. |

## <a name="android-password-requirements"></a>Wymagania dotyczące hasła systemu Android
| Wiadomość | Jak naprawić |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hasło jest wymagane. | Ustawianie hasła lub numeru PIN. Twoja organizacja wymaga wprowadzenia hasła w celu odblokowania urządzenia. |
| Hasło jest za proste. |  Upewnij się, że hasło lub kod PIN nie zawierają numerów sekwencyjnych ani powtarzających się, na przykład 1234 lub 1111. |
| Hasło jest za krótkie. | Zaktualizuj lub ustaw hasło zawierające więcej znaków. Twoja organizacja wymaga, aby hasło miało określoną długość.|
| Hasło musi zawierać cyfry. | Ustawianie hasła lub numeru PIN zawierającego liczby.|
| Hasło musi zawierać litery. | Ustaw hasło, które zawiera litery z alfabetu.|
| Hasło musi zawierać znaki alfanumeryczne. | Ustaw hasło, które zawiera kombinację cyfr i cyfr.|
| Hasło musi zawierać znaki alfanumeryczne i symbole. | Ustaw hasło, które zawiera kombinację liter, cyfr i znaków specjalnych, takich jak `&`, `!`, `$`, `%`i `#`. |
| Hasło musi używać technologii biometrycznej.| Skonfiguruj urządzenie do korzystania z uwierzytelniania biometrycznego, takiego jak odcisk palca lub rozpoznawanie twarzy.
| Hasło wygasło. | Ustaw nowe hasło. Twoja organizacja wymaga zmiany hasła po określonej liczbie dni. |
| Hasło było używane niedawno. | Wybierz hasło, które nie było dotąd używane. Twoja organizacja wymaga, aby określony czas został przeszedł przed ponownym użyciem hasła. |

## <a name="next-steps"></a>Następne kroki

Zapoznaj się z następującymi artykułami, aby utworzyć lub zmienić hasło urządzenia, kod dostępu lub kod PIN.  

- [Ustawianie hasła urządzenia z systemem Windows 10](set-or-change-your-password-windows.md)  
- [Ustawianie kodu dostępu urządzenia z systemem iOS](set-or-change-your-passcode-ios.md)  
- [Ustawianie numeru PIN lub hasła dla urządzenia z systemem Android](set-your-pin-or-password-android.md)  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  


