---
title: Zdalne administrowanie urządzeniami w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z rolami wymaganymi do korzystania z programu TeamViewer, sposobem instalowania łącznika programu TeamViewer oraz szczegółowymi wskazówkami dotyczącymi zdalnego administrowania urządzeniami w usłudze Microsoft Intune w witrynie Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 812b2e40c32b1442e632739c3964eb57027e6d9e
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77413730"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Używanie programu TeamViewer do zdalnego administrowania urządzeniami usługi Intune

Urządzeniami zarządzanymi przez usługę Intune można administrować zdalnie za pomocą programu [TeamViewer](https://www.teamviewer.com). TeamViewer to kupowany osobno program firmy zewnętrznej. W tym temacie przedstawiono sposób konfigurowania programu TeamViewer w usłudze Intune, a także zdalnego administrowania urządzeniem. 

## <a name="prerequisites"></a>Wymagania wstępne

- Korzystanie z obsługiwanego urządzenia. Administrator urządzenia z systemem Android, profil służbowy systemu Android oraz urządzenia z systemami Android, Windows, iOS, iPadOS i macOS zarządzane przez usługę Intune obsługują administrację zdalną. Program TeamViewer może nie obsługiwać systemu Windows Holographic (HoloLens), Windows Team (Surface Hub) lub Windows 10 S. Listę obsługiwanych produktów i odpowiednie aktualizacje można znaleźć w witrynie programu [TeamViewer](https://www.teamviewer.com).

> [!NOTE]
> Dedykowane i w pełni zarządzane urządzenia z systemem Android nie są obsługiwane.

- Administrator usługi Intune w witrynie Azure Portal musi mieć następujące [role usługi Intune](../fundamentals/role-based-access-control.md):  

  - **Aktualizowanie pomocy zdalnej**: Umożliwia administratorom modyfikowanie ustawień łącznika programu TeamViewer
  - **Żądanie pomocy zdalnej**: Umożliwia administratorom rozpoczynanie nowej sesji pomocy zdalnej dla dowolnego użytkownika. Użytkownicy z tą rolą nie są ograniczani przez żadną rolę usługi Intune w zakresie. Ponadto grupy użytkowników lub urządzeń z przypisaną rolą usługi Intune w zakresie mogą również żądać pomocy zdalnej. 

- Konto programu [TeamViewer](https://www.teamviewer.com) z poświadczeniami logowania. Tylko niektóre licencje programu TeamViewer mogą obsługiwać integrację z usługą Intune. Jeśli masz konkretne potrzeby dotyczące programu TeamViewer, zobacz stronę [TeamViewer Integration Partner: Microsoft Intune (Partner integracji programu TeamViewer: Microsoft Intune)](https://www.teamviewer.com/integrations/microsoft-intune/).

Użycie programu TeamViewer umożliwi łącznikowi programu TeamViewer dla usługi Intune tworzenie sesji programu TeamViewer, odczytywanie danych usługi Active Directory oraz zapisywanie tokenu dostępu do konta programu TeamViewer.

## <a name="configure-the-teamviewer-connector"></a>Konfigurowanie łącznika programu TeamViewer

Aby świadczyć pomoc zdalną dla urządzeń, skonfiguruj łącznik programu TeamViewer w usłudze Intune, wykonując następujące kroki:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Administracja dzierżawą** > **Łączniki i tokeny** > **Łącznik programu TeamViewer**.
3. Wybierz pozycję **Połącz**, a następnie zaakceptuj umowę licencyjną.
4. Wybierz pozycję **Zaloguj się do programu TeamViewer, aby autoryzować**.
5. Zostanie otwarta strona sieci Web w witrynie programu TeamViewer. Wprowadź swoje poświadczenia licencji programu TeamViewer, a następnie kliknij pozycję **Zaloguj się**.

## <a name="remotely-administer-a-device"></a>Zdalne administrowanie urządzeniem

Po skonfigurowaniu łącznika można rozpocząć zdalne administrowanie urządzeniem. Wykonaj następujące kroki: 

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
3. Z listy wybierz urządzenie, którym chcesz zdalnie administrować > **...**  > **Nowa sesja Pomocy zdalnej**.
4. Po połączeniu usługi Intune z usługą programu TeamViewer zostaną wyświetlone pewne informacje o urządzeniu. Wybierz pozycję **Połącz**, aby rozpocząć sesję zdalną.

![Używanie programu TeamViewer do zdalnego administrowania urządzeniem z systemem Android — przykład](./media/teamviewer-support/android-teamviewer.png)

Po rozpoczęciu sesji zdalnej użytkownicy będą widzieć flagę powiadomienia na ikonie aplikacji Portal firmy na swoim urządzeniu. Po otwarciu aplikacji jest również wyświetlane powiadomienie. Użytkownik może zaakceptować żądanie pomocy zdalnej.

> [!NOTE]
> Powiadomienia programu TeamViewer w aplikacji Portal firmy nie są wyświetlane dla urządzeń z systemem Windows zarejestrowanych przy użyciu metod „bez użytkownika”, takich jak DEM i WCD. W tych przypadkach zaleca się użycie portalu programu TeamViewer do wygenerowania sesji.

W programie TeamViewer można wykonywać wiele akcji w urządzeniu, łączenie z przejęciem kontroli nad nim. Aby uzyskać szczegółowe informacje na temat czynności możliwych do wykonania, zobacz [wskazówki dotyczące programu TeamViewer](https://www.teamviewer.com/support/documents/).

Po zakończeniu zamknij okno programu TeamViewer.
