---
title: "Monitorowanie informacji o aplikacji i przypisań | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje pozwalające monitorować stan aplikacji przypisanej do użytkowników lub urządzeń."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7c39c904cd2a7bd20525d9072067c6e484b4437a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Usługa Intune zapewnia szereg sposobów monitorowania właściwości zarządzanych aplikacji oraz stanu ich przypisania.

1. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
2. W bloku listy aplikacji wybierz aplikację, o której chcesz wyświetlić informacje. Zostanie wyświetlony blok **Stan instalacji urządzenia** dotyczące aplikacji <*nazwa aplikacji*> : ![blok stanu instalacji aplikacji.](./media/monitor-apps.png)

Następnie wykonaj jedną z następujących czynności, aby dowiedzieć się więcej o aplikacjach i ich przypisaniach.

## <a name="general"></a>Ogólne

- **Przegląd** — podstawowe informacje o aplikacji oraz o stanie wszelkich przypisań dotyczących danej aplikacji. Możesz wybrać jeden z wykresów, aby otworzyć bloki **Stan instalacji urządzenia** lub **Stan instalacji użytkownika** w celu uzyskania bardziej szczegółowych informacji.

## <a name="manage"></a>Zarządzanie programem Endpoint Protection usługi

- **Właściwości** — umożliwia wyświetlanie i modyfikowanie informacji na temat wybranej aplikacji. Aby uzyskać więcej informacji na temat właściwości aplikacji, zobacz artykuł [Jak dodawać aplikacje do usługi Microsoft Intune](apps-add.md).
- **Przypisania** — informacje o przypisaniach danej aplikacji. Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune).

## <a name="monitor"></a>Monitor

- **Stan instalacji urządzenia** — zawiera szczegółowe informacje na temat każdego urządzenia, do którego została przypisana dana aplikacja, takie jak nazwa urządzenia, system operacyjny, czas ostatniego zaewidencjonowania urządzenia w usłudze Intune oraz stan instalacji aplikacji.
- **Stan instalacji użytkownika** — zawiera szczegółowe informacje o użytkowniku, do którego została przypisana dana aplikacja, takie jak liczba instalacji aplikacji na wszystkich urządzeniach użytkownika oraz informacje o wszelkich błędach instalacji.
