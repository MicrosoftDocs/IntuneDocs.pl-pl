---
title: "Rozwiązywanie problemów z profilami poczty e-mail | Microsoft Intune"
description: "Problemy dotyczące profilów poczty e-mail oraz opisano sposoby ich rozwiązywania."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 08/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb0aeac2f94dfde50d9398b09c6b21c7ae40624
ms.openlocfilehash: 79076b65fe85adeaffd5435915cb5eca2a15413f


---

# Rozwiązywanie problemów z profilami poczty e-mail w usłudze Microsoft Intune
W tym artykule wymieniono niektóre problemy dotyczące profilów poczty e-mail oraz opisano sposoby ich rozwiązywania.

Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md), aby znaleźć więcej sposobów uzyskania pomocy.


## Nie można wysyłać obrazów z konta e-mail
Użytkownicy, którzy mają automatycznie skonfigurowane konta e-mail, nie mogą wysyłać obrazów ze swoich urządzeń.
Dzieje się tak, gdy opcja **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm** jest wyłączona.

### Rozwiązanie przy użyciu usługi Intune

1.  Otwórz konsolę administracyjną usługi Microsoft Intune i wybierz obciążenie **Zasady** &gt; **Zasady konfiguracji**.

2.  Wybierz profil poczty e-mail i wybierz polecenie **Edytuj**.

3.  Wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

### Rozwiązanie przy użyciu programu Configuration Manager zintegrowanego z usługą Intune

1.  Otwórz program Configuration Manager &gt; **Zasoby i zgodność**.

2.  Rozwiń węzeł **Przegląd** -&gt; **Ustawienia zgodności** -&gt; **Dostęp do zasobów firmy** i wybierz pozycję **Profile poczty e-mail**.

3.  Kliknij prawym przyciskiem myszy profil poczty e-mail i otwórz pozycję **Właściwości**.

4.  Na karcie **Ustawienia synchronizacji** wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.


## Na urządzeniu jest już zainstalowany profil poczty e-mail

Jeśli użytkownik zainstalował profil poczty e-mail przed udostępnieniem profilu przez usługę Intune, wynik wdrożenia profilu poczty e-mail usługi Intune zależy od platformy urządzenia:

-**iOS**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Zduplikowany profil poczty e-mail utworzony przez użytkownika blokuje wdrożenie profilu utworzonego przez administratora usługi Intune. Jest to powszechny problem, ponieważ użytkownicy systemu iOS zwykle najpierw tworzą profil poczty e-mail, a potem rejestrują urządzenie. Portal firmy poinformuje użytkownika, że nie urządzenie nie jest zgodne z powodu ręcznie skonfigurowanego profilu poczty e-mail i wyświetli monit o usunięcie tego profilu. Użytkownik powinien usunąć swój profil poczty e-mail, aby umożliwić wdrożenie profilu z usługi Intune. Aby uniknąć problemu, poinstruuj użytkowników, aby dokonali rejestracji bez instalowania profilu poczty e-mail i pozwolili usłudze Intune na wdrożenie profilu.

-**Windows**: usługa Intune wykrywa istniejący, zduplikowany profil poczty e-mail na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastąpi istniejący profil poczty e-mail utworzony przez użytkownika.

-**Samsung KNOX**: usługa Intune zidentyfikuje zduplikowane konto e-mail na podstawie adresu e-mail i zastąpi je profilem usługi Intune. Jeśli użytkownik skonfiguruje to konto, zostanie ono ponownie zastąpione przez profil usługi Intune. Może to powodować dezorientację użytkownika, którego konfiguracja konta zostaje zastąpiona.

Ponieważ system Samsung KNOX nie używa nazwy hosta do identyfikowania profilu, nie zaleca się tworzenia wielu profilów poczty e-mail do wdrożenia dla tego samego adresu e-mail na różnych hostach, ponieważ będą one zastępowały siebie nawzajem.

## Błąd 0x87D1FDE8 dla urządzenia KNOX
**Problem**: Po utworzeniu i wdrożeniu profilu poczty e-mail programu Exchange Active Sync dla urządzenia Samsung KNOX w przypadku różnych urządzeń z systemem Android zgłaszany jest błąd **0x87D1FDE8** lub **korygowanie nie powiodło się ** na karcie Zasady &gt; Właściwości w urządzeniu.

Sprawdź konfigurację profilu EAS urządzenia Samsung KNOX i zasad źródłowych. Opcja synchronizacji notatek urządzenia Samsung nie jest już obsługiwana i ta opcja nie powinna być wybrana w Twoim profilu. Upewnij się, że urządzenia miały wystarczająco dużo czasu na przetwarzanie zasad, nawet do 24 godzin.

## Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).



<!--HONumber=Aug16_HO1-->


