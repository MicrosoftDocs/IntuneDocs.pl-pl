---
title: "Rozwiązywanie problemów z dostępem warunkowym | Microsoft Intune"
description: "Co zrobić, gdy użytkownicy nie mogą uzyskać dostępu do zasobów za pomocą dostępu warunkowego usługi Intune."
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 21ae91f0d2866b621d9353929bab6d41d95dc8cc


---

# Rozwiązywanie problemów z dostępem warunkowym

W tym temacie opisano, co należy zrobić, gdy użytkownicy nie mogą uzyskać dostępu do zasobów za pomocą dostępu warunkowego usługi Intune. 

### Podstawy pomyślnego działania dostępu warunkowego

Aby dostęp warunkowy działał, niezbędne są następujące warunki:

-   Urządzenie musi być zarządzane przez usługę Intune.
-   Urządzenie musi zostać zarejestrowane w usłudze Azure Active Directory (AAD).
-   Urządzenie musi być zgodne z zasadami zgodności, które zostały skonfigurowane w usłudze Intune. 
-   Na urządzeniu musi być aktywowany program EAS, jeśli użytkownik pobiera pocztę za pomocą natywnego klienta poczty, a nie za pomocą programu Outlook.

Te warunki można wyświetlić dla każdego urządzenia w portalu zarządzania Azure i w raporcie ze spisu urządzeń.





Zazwyczaj użytkownik próbuje uzyskać dostęp do poczty e-mail lub programu SharePoint i otrzymuje monit o rejestrację. Ten monit doprowadzi użytkownika do portalu firmy. Poniżej przedstawiono możliwe wyjaśnienia tego zachowania oraz sugerowane rozwiązania:

## Scenariusze nowoczesnego uwierzytelniania

### Problemy dotyczące rejestracji

 -  Urządzenie nie jest zarejestrowane, więc rejestracja rozwiąże problem.
 -  Użytkownik zarejestrował urządzenie, ale dołączanie w miejscu pracy nie powiodło się. Użytkownik powinien zaktualizować rejestrację w portalu firmy. 
 
### Problemy ze zgodnością

 -  Urządzenie nie jest zgodne z zasadami usługi Intune. Typowymi problemami są wymagania dotyczące szyfrowania i hasła. Użytkownik zostanie przekierowany do portalu firmy, w którym może skonfigurować swoje urządzenie tak, aby było zgodne.
 -  W przypadku urządzeń z systemem iOS istniejący profil poczty e-mail utworzony przez użytkownika będzie blokował wdrożenie zgodnego profilu (utworzonego przez administratora usługi Intune) z usługi Intune. Jest to powszechny problem, ponieważ użytkownicy systemu iOS zwykle najpierw tworzą profil poczty e-mail, a potem rejestrują urządzenie. Portal firmy poinformuje użytkownika, że nie urządzenie nie jest zgodne z powodu ręcznie skonfigurowanego profilu poczty e-mail i wyświetli monit o usunięcie tego profilu. Użytkownik powinien usunąć swój profil poczty e-mail, aby umożliwić wdrożenie profilu z usługi Intune. Aby uniknąć problemu, poinstruuj użytkowników, aby dokonali rejestracji bez instalowana profilu poczty e-mail i pozwolili usłudze Intune na wdrożenie profilu.  
 -  Może upłynąć trochę czasu, zanim informacje o zgodności zostaną zarejestrowane dla urządzenia. Odczekaj kilka minut i spróbuj ponownie.

### Problemy dotyczące zasad

W przypadku tworzenia zasad zgodności i łączenia ich z zasadami poczty e-mail obie zasady muszą być wdrożone dla tego samego użytkownika, więc należy uważać podczas planowania, które zasady są wdrażane dla których grup. Użytkownicy, dla których stosowane są tylko jedne zasady, prawdopodobnie stwierdzą, że ich urządzenia nie są zgodne.


## Scenariusze programu Exchange ActiveSync


- Urządzenie Android, które jest zarejestrowane i zgodne, może nadal otrzymywać powiadomienie o kwarantannie podczas próby uzyskania dostępu do zasobów firmy. Przed wybraniem linku **Rozpocznij** użytkownik powinien upewnić się, że portal firmy nie był otwarty podczas próby uzyskania dostępu do zasobów. Użytkownicy powinni zamknąć portal firmy, ponownie spróbować uzyskać dostęp do zasobów, a następnie wybrać link **Rozpocznij**.

- Wycofane urządzenie może nadal mieć dostęp przez kilka godzin po wycofaniu. Jest to spowodowane tym, że program Exchange buforuje prawa dostępu przez 6 godzin. Należy rozważyć inne sposoby ochrony danych na wycofanych urządzeniach w tym scenariuszu.
- Możliwy problem: nie można zastosować poprawki EASID do usługi AAD. Typową przyczyną tego problemu jest ograniczanie, więc odczekaj kilka minut i spróbuj ponownie. 

## Zbieranie dzienników skrzynki pocztowej usługi OWA

Jeśli problemy z łącznością programu Exchange nadal występują po wykonaniu rozwiązywania problemów z wdrożeniem, zbierz dzienniki skrzynki pocztowej usługi OWA przed skontaktowaniem się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

1. Zaloguj się za pośrednictwem usługi OWA i wybierz symbol ustawień (koło zębate) obok swojej nazwy w prawym górnym rogu. 
2. Wybierz pozycję **Opcje**.
3. Wybierz pozycję **Telefon** (**Urządzenie przenośne**) w kolumnie po lewej stronie.
4. Z górnego menu wybierz pozycję **Urządzenia przenośne**. 
5. Wybierz swoje urządzenie z listy, a następnie wybierz pozycję **Rozpocznij rejestrowanie**. 
6. Po wyświetleniu monitu wybierz **Tak** w wyskakującym oknie dialogowym. 
7. Wykonaj akcję, która spowodowała problem, aby go odtworzyć. 
8. Poczekaj 1–2 minuty, a następnie wróć do listy telefonów w usłudze OWA (upewnij się, Twój telefon jest zaznaczony na liście) i wybierz z górnego menu wybierz polecenie **Pobierz dzienniki**. 
9. Teraz masz wiadomość e-mail od siebie z załącznikiem. Po otwarciu biletu pomocy technicznej udostępnij zawartość wiadomości e-mail pomocy technicznej firmy Microsoft.


### Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).



<!--HONumber=Jul16_HO3-->


