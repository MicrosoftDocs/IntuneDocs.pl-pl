---
title: Dodawanie i przypisywanie aplikacji Portal firmy dla systemu Windows 10 do urządzeń aprowizowanych za pomocą rozwiązania Autopilot
titleSuffix: Microsoft Intune
description: Dodaj i przypisz aplikację Portal firmy dla systemu Windows 10 do urządzeń aprowizowanych za pomocą rozwiązania Autopilot usługi Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c13d8d774037f0d2db5832af7f39c864330fef30
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77577288"
---
# <a name="add-and-assign-the-windows-10-company-portal-app-for-autopilot-provisioned-devices"></a>Dodawanie i przypisywanie aplikacji Portal firmy dla systemu Windows 10 do urządzeń aprowizowanych za pomocą rozwiązania Autopilot

Do zarządzania urządzeniami i instalowania aplikacji, Twoi użytkownicy mogą użyć aplikacji Portal firmy. Aplikację Portal firmy dla systemu Windows 10 można przypisywać bezpośrednio z poziomu usługi Intune. 

## <a name="prerequisites"></a>Wymagania wstępne

W przypadku urządzeń aprowizowanych za pomocą rozwiązania Autopilot w systemie Windows 10 zaleca się skojarzenie konta w sklepie Microsoft Store dla Firm z usługą Intune. Aby uzyskać więcej informacji, zobacz [Jak zarządzać aplikacjami zakupionymi zbiorczo w sklepie Microsoft Store dla Firm za pomocą usługi Microsoft Intune](~/apps/windows-store-for-business.md).

Aplikacja Portal firmy (wersja offline) powinna zostać zainstalowana według poniższej instrukcji. Aplikacja Portal firmy zostanie zainstalowana w kontekście urządzenia przypisanego do grupy rozwiązania Autopilot, zanim nastąpi zalogowanie użytkownika. 

## <a name="configure-settings-to-show-offline-apps"></a>Konfiguracja ustawień w celu wyświetlania aplikacji w trybie offline
1. Zaloguj się do sklepu [Microsoft Store dla Firm](https://www.microsoft.com/business-store) przy użyciu konta administratora.
2. Wybierz kartę **Zarządzaj** w górnej części okna.
3. W okienku po lewej stronie wybierz pozycję **Ustawienia**.
4. W sekcji **Środowisko użytkownika sklepu** ustaw opcję **Pokaż aplikacje w trybie offline** na **Wł.**  
    Zostaną wyświetlone licencjonowane aplikacje w trybie offline.

## <a name="get-the-offline-company-portal-app"></a>Pobieranie aplikacji Portal firmy w trybie offline
1. Wyszukaj i wybierz aplikację **Portal firmy**.
2. Ustaw opcję **Typ licencji** na **Offline**.
3. Wybierz pozycję **Pobierz aplikację**, aby pobrać i dodać aplikację Portal firmy w trybie offline do swojego magazynu.

## <a name="assign-the-company-portal-app"></a>Przypisywanie aplikacji Portal firmy
1. Zaloguj się do  [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) za pomocą konta administratora. 
2. Wybierz kartę **Aplikacje** w prawym okienku. 
3. W obszarze  **Według platformy** wybierz pozycję **Windows**. 
4. Wybierz aplikację **Portal firmy (wersja offline)** .   
5. Musisz zaczekać na zakończenie harmonogramu synchronizacji lub wykonać ręczną synchronizację z poziomu centrum administracyjnego usługi Microsoft Endpoint Manager.
6. Przypisz aplikację Portal firmy jako aplikację wymaganą do wybranych grup urządzeń rozwiązania Autopilot.

## <a name="next-steps"></a>Następne kroki

- Aby dowiedzieć się więcej na temat przypisywania aplikacji, zobacz [Przypisywanie aplikacji do grup](apps-deploy.md).

