---
title: Aktualizowanie aplikacji
description: W tym temacie opisano sposób aktualizowania aplikacji w sytuacji, gdy jest wymagana nowa wersja.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ee48f751c181cd12c8e549c5aa4aab0c6252add
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="update-apps-using-microsoft-intune"></a>Aktualizowanie aplikacji przy użyciu usługi Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune ułatwia zarządzanie aktualizacjami aplikacji. W tym temacie opisano sposób aktualizowania aplikacji w sytuacji, gdy jest wymagana nowa wersja.

## <a name="how-to-update-apps"></a>Jak aktualizować aplikacje
Po wydaniu nowej wersji wdrożonej aplikacji usługa Intune umożliwia aktualizację i wdrożenie nowszej wersji aplikacji. Można jedynie zastąpić wdrożenie za pomocą nowszej wersji tej samej aplikacji (z tym samym identyfikatorem). Nie można użyć aktualizacji aplikacji do zaktualizowania wdrożenia przy użyciu pakietu innej aplikacji.

### <a name="app-identifiers"></a>Identyfikatory aplikacji
Identyfikator aplikacji jest właściwością, która unikatowo identyfikuje aplikację. Nie można zainstalować wielu kopii aplikacji o tym samym identyfikatorze. Poniżej przedstawiono kilka przykładów identyfikatorów aplikacji:

- **iOS** — Bundle ID (na przykład: com.microsoft.excel)
- **Android** — Package ID (na przykład: com.microsoft.excel)
- **Windows Phone** — (xap installer) użyj identyfikatora produktu (GUID)
- **Windows** — (appx/appxbundle), użyj pełnej nazwy pakietu



> [!IMPORTANT]
> W przypadku wdrożenia aplikacji z akcją wdrożenia **Wymagana instalacja** i późniejszej zmiany akcji wdrożenia na **Dostępna instalacja**, aktualizacje aplikacji nie są automatycznie instalowane na urządzeniach, na których zainstalowano aplikację przed dokonaniem zmiany wdrożenia. Aby rozwiązać ten problem, można wykonać następujące czynności:
>
> -   Użytkownik urządzenia powinien przejść do portalu firmy, wybrać zainstalowaną aplikację i wybrać pozycję **Instaluj**.
> -   Następnie należy zmienić akcję wdrażania na **Odinstaluj**i po odinstalowaniu aplikacji ponownie wdrożyć aplikację z akcją wdrożenia **Dostępna instalacja**.

### <a name="to-update-an-app"></a>Aby zaktualizować aplikację

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Aplikacje** &gt; **Aplikacje**.

2.  Z listy **Aplikacje** wybierz aplikację, którą chcesz zaktualizować, a następnie wybierz pozycję **Edytuj**.

3.  W kreatorze **Edytowanie oprogramowania** podaj nowe szczegóły pakietu aplikacji.

4.  Gdy skończysz, wybierz pozycję **Dalej**.

Przy następnym sprawdzeniu dostępnych aplikacji przez urządzenia aplikacja zostanie automatycznie zaktualizowana do najnowszej wersji.
W przypadku aplikacji instalowanych z pakietu aplikacji (aplikacji biznesowych) aplikacja będzie uaktualniana automatycznie zarówno w przypadku wymaganych, jak i dostępnych wdrożeń, jeśli tylko aplikacja ma taki sam identyfikator.

W przypadku aplikacji wdrożonych jako link do sklepu aktualizacja jest zarządzana przez sklep, z którego pochodzi aplikacja.
