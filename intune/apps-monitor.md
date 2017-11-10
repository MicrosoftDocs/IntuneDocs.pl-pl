---
title: "Monitorowanie informacji o aplikacji i przypisań"
titlesuffix: Azure portal
description: "Informacje pozwalające monitorować stan aplikacji przypisanej do użytkowników lub urządzeń."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune zapewnia szereg sposobów monitorowania właściwości zarządzanych aplikacji oraz stanu ich przypisania.

1. Zaloguj się do witryny Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** + **Intune**.
3. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w grupie **Zarządzaj**.
     
    ![Blok stanu instalacji aplikacji.](./media/monitor-apps.png)
5. W bloku listy aplikacji wybierz aplikację. Zostanie wyświetlony blok **Stan instalacji urządzenia** dla aplikacji <*nazwa aplikacji*> .

Raport o stanie instalacji urządzeń zawiera następujące kolumny:

1.  **Nazwa urządzenia** — nazwa typu urządzenia.
2.  **Nazwa użytkownika** — nazwa użytkownika.
3.   **Platforma** — system operacyjny zainstalowany na urządzeniu.
4.  **Wersja** — numer wersji aplikacji.
5.   **Stan** — możliwe stany aplikacji obejmują: **Zainstalowana**, **Niezainstalowana**, **Oczekiwanie na instalację** i **Błąd**.
6. **Szczegóły stanu** — czytelny opis stanu aplikacji na urządzeniu.
7. **Ostatnie zaewidencjonowanie** — czas ostatniego zaewidencjonowania urządzenia w usłudze Intune.

Następnie wykonaj jedną z następujących czynności, aby dowiedzieć się więcej o aplikacjach i ich przypisaniach.

## <a name="general"></a>Ogólne

- **Przegląd** — podstawowe informacje o aplikacji oraz o stanie wszelkich przypisań dotyczących danej aplikacji. Możesz wybrać jeden z wykresów, aby otworzyć bloki **Stan instalacji urządzenia** lub **Stan instalacji użytkownika** w celu uzyskania bardziej szczegółowych informacji.

## <a name="manage"></a>Zarządzanie programem Endpoint Protection usługi

- **Właściwości** — umożliwia wyświetlanie i modyfikowanie informacji na temat wybranej aplikacji. Aby uzyskać więcej informacji na temat właściwości aplikacji, zobacz artykuł [Jak dodawać aplikacje do usługi Microsoft Intune](apps-add.md).
- **Przypisania** — informacje o przypisaniach danej aplikacji. Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune).

## <a name="monitor"></a>Monitor

- **Stan instalacji urządzenia** — zawiera szczegółowe informacje na temat każdego urządzenia, do którego została przypisana dana aplikacja, takie jak nazwa urządzenia, system operacyjny, czas ostatniego zaewidencjonowania urządzenia w usłudze Intune oraz stan instalacji aplikacji.
- **Stan instalacji użytkownika** — zawiera szczegółowe informacje o użytkowniku, do którego została przypisana dana aplikacja, takie jak liczba instalacji aplikacji na wszystkich urządzeniach użytkownika oraz informacje o wszelkich błędach instalacji.