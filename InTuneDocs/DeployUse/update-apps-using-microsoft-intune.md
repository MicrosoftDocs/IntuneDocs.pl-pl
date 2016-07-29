---
title: Aktualizowanie aplikacji | Microsoft Intune
description: "W tym temacie opisano sposób aktualizowania aplikacji w sytuacji, gdy jest wymagana nowa wersja."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 5e163cf4e8190d0bc967415f1d907465e4e13f36


---

# Aktualizowanie aplikacji przy użyciu usługi Microsoft Intune
Usługa Microsoft Intune ułatwia zarządzanie aktualizacjami aplikacji. W tym temacie opisano sposób aktualizowania aplikacji w sytuacji, gdy jest wymagana nowa wersja.

## Jak aktualizować aplikacje
Po wydaniu nowej wersji wdrożonej aplikacji usługa Intune umożliwia aktualizację i wdrożenie nowszej wersji aplikacji. Można jedynie zastąpić wdrożenie na nowszą wersję tej samej aplikacji (przy użyciu tego samego identyfikatora). Nie można użyć aktualizacji aplikacji do zaktualizowania wdrożenia przy użyciu pakietu innej aplikacji.

### Identyfikatory aplikacji
Identyfikator aplikacji jest właściwością, która unikatowo identyfikuje aplikację. Nie można zainstalować wielu kopii aplikacji o tym samym identyfikatorze. Na przykład:

- **iOS** — Bundle ID (na przykład: com.microsoft.excel)
- **Android** — Package ID (na przykład: com.microsoft.excel)
- **Windows Phone** — (xap installer) użyj identyfikatora produktu (GUID)
- **Windows** — (appx/appxbundle), użyj pełnej nazwy pakietu



> [!IMPORTANT]
> W przypadku wdrożenia aplikacji z akcją wdrożenia **Wymagana instalacja** i późniejszej zmiany akcji wdrożenia na **Dostępna instalacja**, aktualizacje aplikacji nie są automatycznie instalowane na urządzeniach, na których zainstalowano aplikację przed dokonaniem zmiany wdrożenia. Aby rozwiązać ten problem, można wykonać następujące czynności:
> 
> -   Użytkownik urządzenia powinien przejść do portalu firmy, wybrać zainstalowaną aplikację i wybrać pozycję **Instaluj**.
> -   Następnie należy zmienić akcję wdrażania na **Odinstaluj**i po odinstalowaniu aplikacji ponownie wdrożyć aplikację z akcją wdrożenia **Dostępna instalacja**.

### Aby zaktualizować aplikację

1.  W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Aplikacje** &gt; **Aplikacje**.

2.  Z listy **Aplikacje** wybierz aplikację, którą chcesz zaktualizować, a następnie wybierz pozycję **Edytuj**.

3.  W kreatorze **Edytowanie oprogramowania** podaj nowe szczegóły pakietu aplikacji.

4.  Gdy skończysz, wybierz pozycję **Dalej**.

Przy następnym sprawdzeniu dostępnych aplikacji przez urządzenia aplikacja zostanie automatycznie zaktualizowana do najnowszej wersji.
W przypadku aplikacji instalowanych z pakietu aplikacji (aplikacji biznesowych) aplikacja będzie uaktualniana automatycznie zarówno dla wymaganych, jak i dostępnych wdrożeń, jeśli tylko aplikacja ma taki sam identyfikator.
W przypadku aplikacji wdrożonych jako link do sklepu aktualizacja jest zarządzana przez sklep, z którego pochodzi aplikacja.






<!--HONumber=Jul16_HO4-->


