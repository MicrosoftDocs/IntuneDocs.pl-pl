---
title: "Jak edukować użytkowników końcowych na temat usługi Microsoft Intune | Microsoft Intune"
description: "Udostępnij informacje użytkownikom końcowym, aby wdrożenie usługi Intune było pomyślne."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 48914533-f138-4dc0-8b93-4cea3ac61f7b
ms.reviewer: robstack
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e0ecc775f70703574c4e1adf0f0aa204f2745b72
ms.openlocfilehash: a0ae4d74ad99adcfab596eb0c441c845fbca3a9e
ms.lasthandoff: 04/20/2017


---

# <a name="how-to-educate-your-end-users-about-microsoft-intune"></a>Jak edukować użytkowników końcowych na temat usługi Microsoft Intune

Usługa Microsoft Intune ułatwia pracę pracowników mających urządzenia przenośne, chroniąc dane firmowe. Istnieje wiele kroków niezbędnych do zapewnienia pomyślnego wdrożenia, w tym ocena usługi Intune przy użyciu [bezpłatnej wersji próbnej](/Intune/Understand/mobile-device-management-trial-guide-microsoft-intune), [ochrona poczty e-mail](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices) i [osadzanie aplikacji za pomocą zestawu SDK usługi Intune](/intune/develop/intune-app-sdk).

Żadna z tych technologii nie gwarantuje, że użytkownicy będą rozumieć, dlaczego zarządzanie ich urządzeniami jest istotne. W rzeczywistości wielu użytkowników może mieć wrażenie, że naruszasz ich prywatność — zwłaszcza jeśli usługa Intune jest wdrażana jako [rozwiązanie typu „Przynieś własne urządzenie” (BYOD, Bring Your Own Device)](/enterprise-mobility-security/solutions/byod-design-considerations-guide).

> [!Important]
> Zrozumienie i aktywne rozwiewanie wątpliwości użytkowników dotyczących powodów, dla których konieczne jest zarządzanie urządzeniami w firmie, ma krytyczne znaczenie dla pomyślnego wdrożenia.

Przyjęcie rozwiązania nie polega wyłącznie na uruchomieniu technologii i jej rozpowszechnieniu wśród pracowników, ale również na akceptacji przez użytkowników końcowych bezpiecznego dostępu zapewnianego przez usługę Intune. Użytkownicy mogą być zaniepokojeni mobilnością w przedsiębiorstwie, ponieważ zwykle nie jest im wyjaśniane, jaki jest cel mobilności w przedsiębiorstwie oraz jakie są jej możliwości i ograniczenia.

## <a name="things-to-consider-about-your-end-users"></a>Kwestie dotyczące użytkowników końcowych, które należy rozważyć

__Jaki jest poziom doświadczenia użytkowników końcowych?__ Użytkownicy końcowi mogą mieć różne doświadczenia dotyczące różnych technologii. Te doświadczenia mogą być pozytywne i negatywne, począwszy od pamiątkowych zdjęć dzieci po upuszczenie urządzenia do zlewu i utratę wszystkich danych, dla których nie utworzono kopii zapasowej. Te doświadczenia mają wpływ na ich podejście do technologii oraz postrzeganie osobistych i firmowych zastosowań urządzeń.

__Co zarządzanie mobilnością oznacza dla mnie?__ Użytkownicy mogą nie rozumieć w pełni, do jakich funkcji ich urządzeń oraz informacji masz dostęp. Użytkownicy mogą mieć wątpliwości dotyczące możliwości śledzenia ich wszystkich działań przez dział IT i kierownictwo. Może to być szczególnie niepokojące dla mniej doświadczonych użytkowników, którzy mogą uważać, że wszystkie działania na ich urządzeniach są prywatne. Bardziej doświadczony użytkownik może mieć określone obawy związane ze śledzeniem przez „wielkiego brata” na urządzeniach i może informować współpracowników o swoich obawach.

__Jakie niedogodności może to stanowić dla użytkowników końcowych?__ Instalowanie aplikacji, rejestrowanie urządzeń i zachowywanie zgodności jest czasochłonne. Zapewnienie bezpieczeństwa danych firmowych to główny priorytet każdego wdrożenia usługi Intune, ale nieuzasadnione wymaganie kodu dostępu na osobistym urządzeniu spowoduje, że użytkownicy będą niezadowoleni z zarządzania ich urządzeniami. Wysyłanie wymaganych aktualizacji aplikacji w trakcie połączeń konferencyjnych o krytycznym znaczeniu dla firmy może mieć negatywny wpływ na produktywność pracowników, co jest sprzeczne z celem zapewnienia im urządzeń przenośnych.

## <a name="things-you-should-do"></a>Co należy zrobić

Rozwianie obaw sprawi, że wdrożenie będzie płynniejsze. Mamy listę spraw, które należy wziąć pod uwagę, aby ułatwić użytkownikom końcowym przyjęcie zarządzania urządzeniami.

* __Bądź pomysłowy.__ Dokumentacja usługi Intune zawiera różną zawartość mającą na celu ułatwienie użytkownikom końcowym zrozumienia sposobu wykonywania określonych zadań, takich jak rejestrowanie urządzeń i rozwiązywanie problemów. Wśród nich znalazły się artykuły przesyłane do użytkowników z Portalu firmy, które zostały podzielone na sekcje dotyczące instalacji aplikacji Portal firmy i rejestracji w usłudze Intune, ogólnych zadań, które użytkownicy mogą wykonać na swoich urządzeniach, oraz rozwiązywania problemów. Tę dokumentację można znaleźć w naszym wyjaśnieniu sposobu [wykonywania pracy przy użyciu urządzeń zarządzanych](/Intune/EndUser/use-managed-devices-to-get-work-done).

* __Bądź dostępny.__ Użytkownicy końcowi muszą wiedzieć, gdzie mogą uzyskać pomoc dotyczącą swoich urządzeń. Upewnij się, że uwzględniasz informacje kontaktowe administratora IT podczas [dostosowywania Portalu firmy](/Intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-7), dzięki czemu użytkownicy będą mogli uzyskać pomoc w razie potrzeby.

* __Miej indywidualne podejście.__ W przypadku zapewnienia instrukcji, które nie są specyficzne dla danego wdrożenia, użytkownicy końcowi mogą mieć wrażenie, że ich doświadczenia nie zostały przemyślane. Korzystając z tego [możliwego do dostosowania szablonu rejestracji użytkowników końcowych w usłudze Intune przeznaczonego dla administratorów IT](https://gallery.technet.microsoft.com/office/Intune-End-User-Enrollment-3a0c9b0c), można utworzyć własne instrukcje dotyczące rejestrowania przeznaczone dla użytkowników końcowych.

* __Znajdź różne sposoby komunikacji.__ Podobnie jak w przypadku [różnych stylów uczenia](http://www.umassd.edu/dss/resources/facultystaff/howtoteachandaccommodate/howtoaccommodatedifferentlearningstyles/) użytkownicy mają preferowane sposoby korzystania z informacji. W przypadku użytkowników, który wolą wideo od dokumentacji, oferujemy m.in. [wersje wideo procedur rejestracji różnych typów urządzeń](https://channel9.msdn.com/Series/IntuneEnrollment) w witrynie Channel 9. Te filmy wideo są dostępne do osadzenia bezpośrednio we własnej [witrynie programu SharePoint](https://support.office.com/article/Embed-a-video-from-Office-365-Video-59e19984-c34e-4be8-889b-f6fa93910581) lub do pobrania jako kopia lokalna — w postaci filmu wideo lub tylko ścieżki dźwiękowej.

* __Bądź świadomy.__ Wrażenia użytkowników końcowych będą mieć wpływ na Twoją produktywność, a zrozumienie ich doświadczeń ułatwi rozwiązywanie problemów użytkowników, którzy się do Ciebie zwrócą. Zrozumienie skąd użytkownicy końcowi uzyskują swoje aplikacje może znacznie ułatwić diagnozowanie występujących problemów oraz przyspieszyć ich rozwiązywanie.

* **Android**
  * [Korzystanie z urządzenia z systemem Android i usługi Intune](https://docs.microsoft.com/Intune/EndUser/using-your-android-device-with-intune)
  * [Jak użytkownicy systemu Android uzyskują aplikacje](how-your-android-users-get-their-apps.md)

* **iOS**
  * [Korzystanie z urządzenia z systemem iOS i usługi Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macos-device-with-intune)
  * [Jak użytkownicy systemu iOS uzyskują aplikacje](how-your-ios-users-get-their-apps.md)

* **Windows**
  * [Korzystanie z urządzenia z systemem Windows i usługi Intune](https://docs.microsoft.com/Intune/EndUser/using-your-windows-device-with-intune)
  * [Jak użytkownicy systemu Windows uzyskują aplikacje](how-your-windows-users-get-their-apps.md)

* __Zrób pierwszy krok.__ Wyraźnie poinformuj użytkowników, że będziesz zarządzać ich urządzeniami. Poinformuj ich, jakiego rodzaju dane gromadzisz i dlaczego to robisz. Poinformuj ich, w jaki sposób zamierzasz używać wszystkich zasobów. [Firma Microsoft uważa, że masz prawo do jak największej ilości informacji dotyczących sposobu obsługi danych klientów w chmurze](https://www.microsoft.com/trustcenter/about/transparency), i wierzymy, że to podejście może znacząco zwiększyć zadowolenie użytkowników końcowych z usługi Intune.

>[!Note]
> Przejrzystość, tam gdzie to możliwe, to podstawa sukcesu wdrożenia.

Próbujesz połączyć zaufanie i dobrze przygotowane zasady zgodności, aby mieć pewność, że użytkownicy końcowi wiedzą, że nawet jeśli *byłoby możliwe* przeglądanie określonych typów danych osobowych, nie *chcesz* tego robić ani ponosić odpowiedzialności za naruszenie ich prywatności. Opracowanie oświadczenia we współpracy z działem prawnym i kadr może ułatwić przekonanie pracowników sprawiających największe trudności.

