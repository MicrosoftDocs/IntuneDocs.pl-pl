---
title: Rozwiązywanie problemów z dostępem warunkowym
titleSuffix: Microsoft Intune
description: Co zrobić, gdy użytkownicy nie mogą uzyskać dostępu do zasobów za pomocą dostępu warunkowego usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d6dc10eca80a7d403d0ff44c25d3cfaed85fafa
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514204"
---
# <a name="troubleshoot-conditional-access"></a>Rozwiązywanie problemów z dostępem warunkowym
W tym artykule opisano, co zrobić, gdy użytkownicy nie mogą uzyskać dostępu do zasobów chronionych przy użyciu dostępu warunkowego, lub gdy użytkownicy mogą uzyskiwać dostęp do chronionych zasobów, ale powinni być blokowani.

Za pomocą usługi Intune i dostępu warunkowego można chronić dostęp do usług, takich jak:
- Usługi pakietu Office 365, takie jak Exchange Online, SharePoint Online i Skype dla firm Online
- Lokalna instalacja programu Exchange
- Różne inne usługi

Ta możliwość pozwala upewnić się, że tylko urządzenia zarejestrowane w usłudze Intune i zgodne z zasadami dostępu warunkowego ustawionymi w konsoli administracyjnej usługi Intune lub w usłudze Azure Active Directory mają dostęp do zasobów firmowych. 

## <a name="requirements-for-conditional-access"></a>Wymagania dotyczące dostępu warunkowego

Aby dostęp warunkowy działał, muszą być spełnione następujące wymagania:

- Urządzenie musi być zarejestrowane w oprogramowaniu MDM i zarządzane przez usługę Intune.

- Użytkownik i urządzenie muszą być zgodni z przypisanymi zasadami zgodności usługi Intune.

- Domyślnie użytkownikowi muszą być przypisane zasady zgodności urządzenia. Może to zależeć od konfiguracji ustawienia **Oznacz urządzenia bez przypisanych zasad zgodności jako** w obszarze **Zgodność urządzeń** > **Ustawienia zasad zgodności** w portalu administracyjnym usługi Intune.

- Na urządzeniu musi być aktywowany program Exchange ActiveSync, jeśli użytkownik korzysta z natywnego klienta poczty urządzenia, a nie z programu Outlook. Dzieje się to automatycznie w przypadku urządzeń z systemem iOS, Windows Phone i Android Knox.

- W przypadku lokalnego programu Exchange program Intune Exchange Connector musi zostać poprawnie skonfigurowany. Aby uzyskać więcej informacji, zobacz artykuł [Rozwiązywanie problemów z programem Exchange Connector w usłudze Microsoft Intune](troubleshoot-exchange-connector.md).

- W przypadku lokalnego programu Skype należy skonfigurować nowoczesne uwierzytelnianie hybrydowe. Zobacz temat [Hybrid Modern Auth Overview](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) (Omówienie nowoczesnego uwierzytelniania hybrydowego).

Te warunki można wyświetlić dla każdego urządzenia w witrynie Azure Portal i w raporcie ze spisu urządzeń.

## <a name="devices-appear-compliant-but-users-are-still-blocked"></a>Urządzenia są widoczne jako zgodne, ale użytkownicy nadal są blokowani

- Upewnij się, że użytkownik ma przypisaną licencję usługi Intune, aby właściwie ocenić zgodność.

- Urządzenia z systemem Android innym niż Knox nie uzyskają dostępu, dopóki użytkownik nie kliknie linku **Rozpocznij teraz** w otrzymanej wiadomości e-mail o kwarantannie. Ma to zastosowanie nawet w przypadku, gdy użytkownik jest już zarejestrowany w usłudze Intune. Jeśli użytkownik nie odbiera wiadomości e-mail z linkiem na telefonie, może użyć komputera, aby uzyskać dostęp do swojej poczty e-mail i przekazać ją na konto poczty e-mail na urządzeniu.

- Gdy urządzenie jest rejestrowane po raz pierwszy, może upłynąć trochę czasu, zanim informacje o zgodności zostaną zarejestrowane dla urządzenia. Odczekaj kilka minut i spróbuj ponownie.

- W przypadku urządzeń z systemem iOS/iPadOS istniejący profil poczty e-mail może zablokować wdrożenie profilu poczty e-mail utworzonego przez administratora usługi Intune i przypisanego do danego użytkownika, przez co urządzenie jest niezgodne. W tym scenariuszu aplikacja Portal firmy powiadamia użytkownika, że nie jest on zgodny ze względu na ręcznie skonfigurowany profil poczty e-mail, i wyświetla monit o usunięcie tego profilu. Gdy użytkownik usunie istniejący profil poczty e-mail, będzie można pomyślnie wdrożyć profil poczty e-mail usługi Intune. Aby uniknąć tego problemu, poinstruuj użytkowników, aby usunęli wszystkie istniejące profile poczty e-mail na swoim urządzeniu przed rozpoczęciem rejestrowania.

- Urządzenie może zostać zablokowane w stanie sprawdzania zgodności, co uniemożliwia użytkownikowi rozpoczęcie kolejnego ewidencjonowania. Jeśli masz urządzenie w tym stanie:
  - Upewnij się, że urządzenie korzysta z najnowszej wersji aplikacji Portal firmy.
  - Uruchom urządzenie ponownie.
  - Zobacz, czy problem nadal występuje w różnych sieciach (na przykład komórkowych, Wi-Fi itp.).

  Jeśli problem nie został rozwiązany, skontaktuj się z pomocą techniczną zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md).

- Niektóre urządzenia z systemem Android mogą wyglądać na zaszyfrowane, jednak aplikacja Portal firmy rozpoznaje je jako niezaszyfrowane i oznacza je jako niezgodne. W tym scenariuszu w aplikacji Portal firmy zostanie wyświetlone powiadomienie z prośbą o ustawienie startowego kodu dostępu dla urządzenia. Po naciśnięciu powiadomienia i potwierdzeniu istniejącego numeru PIN lub hasła wybierz **Wymagaj numeru PIN do uruchomienia urządzenia** na ekranie **Bezpieczny start**, a następnie naciśnij przycisk **Sprawdź zgodność** dla urządzenia z poziomu aplikacji Portal firmy. Urządzenie powinno teraz zostać wykryte jako zaszyfrowane. 

  > [!NOTE]
  > Niektórzy producenci urządzeń szyfrują urządzenia przy użyciu domyślnego numeru PIN, a nie numeru PIN ustawionego przez użytkownika. Usługa Intune rozpoznaje szyfrowanie korzystające z domyślnego numeru PIN jako niezabezpieczone i oznacza te urządzenia jako niezgodne, dopóki użytkownik nie utworzy nowego numeru PIN innego niż domyślny.

- Zarejestrowane i zgodne urządzenie z systemem Android nadal może być blokowane i otrzymać powiadomienie o kwarantannie podczas pierwszej próby uzyskania dostępu do zasobów firmy. W takiej sytuacji upewnij się, że aplikacja Portal firmy nie została uruchomiona, a następnie wybierz link **Rozpocznij teraz** w wiadomości e-mail o kwarantannie, aby wyzwolić ocenę. Należy to zrobić tylko w przypadku, gdy najpierw włączono dostęp warunkowy.

- Zarejestrowane urządzenie z systemem Android może monitować użytkownika przy użyciu komunikatu „Nie znaleziono certyfikatów” i nie ma przyznanych praw dostępu do zasobów usługi O365. Użytkownik musi włączyć opcję *Włącz dostęp za pomocą przeglądarki* na zarejestrowanym urządzeniu w następujący sposób:
  1. Otwórz aplikację Portal firmy.
  2. Przejdź do strony Ustawienia za pomocą przycisku wielokropka (...) lub przycisku menu sprzętu.
  3. Wybierz przycisk *Włącz dostęp za pomocą przeglądarki*.
  4. W przeglądarce Chrome wylogować się z usługi Office 365 i ponownie uruchomić przeglądarkę Chrome.  


## <a name="devices-are-blocked-and-no-quarantine-email-is-received"></a>Urządzenia są blokowane i nie otrzymano żadnej wiadomości e-mail o kwarantannie

- Sprawdź, czy urządzenie jest obecne w konsoli administracyjnej usługi Intune jako urządzenie z programem Exchange ActiveSync. Jeśli nie, prawdopodobnie odnajdywanie urządzenia kończy się niepowodzeniem, zazwyczaj z powodu problemu z programem Exchange Connector. Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z lokalnym łącznikiem Exchange Connector usługi Intune](troubleshoot-exchange-connector.md).

- Zanim program Exchange Connector zablokuje urządzenie, wysyła wiadomości e-mail dotyczącą aktywacji (kwarantanny). Jeśli urządzenie jest w trybie offline, może nie otrzymać wiadomości e-mail dotyczącej aktywacji. 

- Sprawdź, czy klient poczty e-mail urządzenia został skonfigurowany do pobierania poczty w trybie **wypychania** zamiast **sondowania**. Jeśli tak, może to spowodować przeoczenie wiadomości e-mail przez użytkownika. Zmień tryb na **Sondowanie** i sprawdź, czy urządzenie otrzyma wiadomość e-mail.

## <a name="devices-are-noncompliant-but-users-are-not-blocked"></a>Urządzenia są niezgodne, ale użytkownicy nie są blokowani

- W przypadku komputerów z systemem Windows dostęp warunkowy blokuje tylko natywną aplikację poczty e-mail, pakiet Office 2013 z nowoczesnym uwierzytelnianiem lub pakiet Office 2016. Blokowanie wcześniejszych wersji programu Outlook lub wszystkich aplikacji poczty na komputerach z systemem Windows wymaga konfiguracji usługi Rejestracja urządzeń w usłudze AAD i usług Active Directory Federation Services (AD FS) zgodnie z opisem w artykule [Konfigurowanie usług SharePoint Online i Exchange Online na potrzeby dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication).

- Jeśli urządzenie zostanie selektywnie wyczyszczone lub wycofane z usługi Intune, może nadal mieć dostęp przez kilka godzin po wycofaniu. Jest to spowodowane tym, że program Exchange buforuje prawa dostępu przez sześć godzin. Należy rozważyć inne sposoby ochrony danych na wycofanych urządzeniach w tym scenariuszu.

- Urządzenia Surface Hub, zarejestrowane zbiorczo i urządzenia z systemem Windows zarejestrowane w programie DEM mogą obsługiwać dostęp warunkowy, gdy użytkownik z przypisaną licencją usługi Intune jest zalogowany. Jednak w celu poprawnej oceny należy wdrożyć zasady zgodności w grupach urządzeń (a nie w grupach użytkowników).

- Sprawdź przypisania zasad zgodności i zasad dostępu warunkowego. Jeśli użytkownik nie należy do grupy, do której przypisano zasady, lub znajduje się w wykluczonej grupie, nie jest blokowany. Tylko urządzenia użytkowników znajdujących się w przypisanej grupie są sprawdzane pod kątem zgodności.

## <a name="noncompliant-device-is-not-blocked"></a>Niezgodne urządzenie nie jest blokowane

Jeśli urządzenie nie jest zgodne, ale nadal ma dostęp, wykonaj poniższe czynności.

- Sprawdź grupy docelowe i wykluczenia. Jeśli użytkownik nie znajduje się w odpowiedniej grupie docelowej lub znajduje się w grupie wykluczenia, nie zostanie zablokowany. Tylko urządzenia użytkowników w grupie docelowej są sprawdzane pod kątem zgodności.

- Upewnij się, że urządzenie jest wykrywane. Czy program Exchange Connector wskazuje urzędy certyfikacji Exchange 2010, gdy użytkownik korzysta z serwera programu Exchange 2013? W tym przypadku, jeśli domyślna reguła programu Exchange to Zezwalaj, nawet jeśli użytkownik znajduje się w grupie docelowej, usługa Intune nie monitoruje połączenia urządzenia z usługą Exchange.

- Sprawdź występowanie urządzenia/stan dostępu w programie Exchange:
  - Użyj następującego polecenia cmdlet programu PowerShell, aby wyświetlić listę wszystkich urządzeń przenośnych skrzynki pocztowej: „Get-ActiveSyncDeviceStatistics -mailbox mbx”. Jeśli urządzenia nie ma na liście, nie ma ono dostępu do programu Exchange.
  
  - Jeśli urządzenie znajduje się na liście, użyj polecenia cmdlet „Get-CASmailbox -identity:’upn’ | fl”, aby uzyskać szczegółowe informacje na temat stanu jego dostępu, oraz przekaż te informacje do pomocy technicznej firmy Microsoft.

## <a name="next-steps"></a>Następne kroki
Jeśli te informacje nie pomogą w rozwiązaniu problemu, możesz również [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md).
