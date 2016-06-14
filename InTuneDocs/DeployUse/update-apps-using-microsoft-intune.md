---
# required metadata

title: Aktualizowanie aplikacji przy użyciu usługi Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Aktualizowanie aplikacji przy użyciu usługi Microsoft Intune
Usługa Microsoft Intune ułatwia zarządzanie aktualizacjami aplikacji. W tym temacie opisano sposób aktualizowania aplikacji w sytuacji, gdy jest wymagana nowa wersja.

## Jak aktualizować aplikacje
Po wydaniu nowej wersji wdrożonej aplikacji usługa Intune umożliwia aktualizację i wdrożenie nowszej wersji aplikacji. Można jedynie zastąpić wdrożenie na nowszą wersję tej samej aplikacji (przy użyciu tego samego identyfikatora). Nie można użyć aktualizacji aplikacji do zaktualizowania wdrożenia przy użyciu pakietu innej aplikacji.

> [!IMPORTANT]
> W przypadku wdrożenia aplikacji z akcją wdrożenia **Wymagana instalacja** i późniejszej zmiany akcji wdrożenia na **Dostępna instalacja**, aktualizacje aplikacji nie są automatycznie instalowane na urządzeniach, na których zainstalowano aplikację przed dokonaniem zmiany wdrożenia. Aby rozwiązać ten problem, można wykonać następujące czynności:
> 
> -   Użytkownik urządzenia powinien przejść do portalu firmy, wybrać zainstalowaną aplikację i kliknąć pozycję **Zainstaluj**..
> -   Następnie należy zmienić akcję wdrażania na **Odinstaluj** i po odinstalowaniu aplikacji ponownie wdrożyć aplikację z akcją wdrożenia **Dostępna instalacja**..

### Aby zaktualizować aplikację

1.  W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Aplikacje** &gt; **Aplikacje**..

2.  Z listy **Aplikacje** wybierz aplikację, którą chcesz zaktualizować, a następnie kliknij pozycję **Edytuj**..

3.  W kreatorze **Edytowanie oprogramowania** podaj nowe szczegóły pakietu aplikacji.

4.  Po zakończeniu kliknij pozycję **Aktualizuj**.

Przy następnym sprawdzeniu dostępnych aplikacji przez urządzenia aplikacja zostanie automatycznie zaktualizowana do najnowszej wersji.





<!--HONumber=May16_HO1-->


