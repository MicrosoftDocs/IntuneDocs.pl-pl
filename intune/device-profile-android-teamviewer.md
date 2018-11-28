---
title: Zdalne administrowanie urządzeniami w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z rolami wymaganymi do korzystania z programu TeamViewer, sposobem instalowania łącznika programu TeamViewer oraz szczegółowymi wskazówkami dotyczącymi zdalnego administrowania urządzeniami w usłudze Microsoft Intune w witrynie Azure Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7cb7c23e673c9e0c074f45991333fde9bfc8e930
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186192"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Używanie programu TeamViewer do zdalnego administrowania urządzeniami usługi Intune

Urządzeniami zarządzanymi przez usługę Intune można administrować zdalnie za pomocą programu [TeamViewer](https://www.teamviewer.com). TeamViewer to kupowany osobno program firmy zewnętrznej. W tym temacie przedstawiono sposób konfigurowania programu TeamViewer w usłudze Intune, a także zdalnego administrowania urządzeniem. 

## <a name="prerequisites"></a>Wymagania wstępne

- Korzystanie z obsługiwanego urządzenia. Urządzenia z systemami Android, Windows, iOS i macOS zarządzane przez usługę Intune obsługują administrację zdalną. Program TeamViewer może nie obsługiwać systemu Windows Holographic (HoloLens), Windows Team (Surface Hub) lub Windows 10 S. Listę obsługiwanych produktów i odpowiednie aktualizacje można znaleźć w witrynie programu [TeamViewer](https://www.teamviewer.com).

- Administrator usługi Intune w witrynie Azure Portal musi mieć następujące [role usługi Intune](role-based-access-control.md):  

    - **Aktualizowanie pomocy zdalnej**: umożliwia administratorom modyfikowanie ustawień łącznika programu TeamViewer
    - **Żądanie pomocy zdalnej**: umożliwia administratorom rozpoczynanie nowej sesji pomocy zdalnej dla dowolnego użytkownika. Użytkownicy z tą rolą nie są ograniczani przez żadną rolę usługi Intune w zakresie. Ponadto grupy użytkowników lub urządzeń z przypisaną rolą usługi Intune w zakresie mogą również żądać pomocy zdalnej. 

- Konto programu [TeamViewer](https://www.teamviewer.com) z poświadczeniami logowania

Użycie programu TeamViewer umożliwi łącznikowi programu TeamViewer dla usługi Intune tworzenie sesji programu TeamViewer, odczytywanie danych usługi Active Directory oraz zapisywanie tokenu dostępu do konta programu TeamViewer.

## <a name="configure-the-teamviewer-connector"></a>Konfigurowanie łącznika programu TeamViewer

Aby świadczyć pomoc zdalną dla urządzeń, skonfiguruj łącznik programu TeamViewer w usłudze Intune, wykonując następujące kroki:

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz opcję **Wszystkie usługi** i wyszukaj usługę **Microsoft Intune**.
2. W obszarze **Microsoft Intune** wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Łącznik programu TeamViewer**.
3. Wybierz pozycję **Połącz**, a następnie zaakceptuj umowę licencyjną.
4. Wybierz pozycję **Zaloguj się do programu TeamViewer, aby autoryzować**.
5. Zostanie otwarta strona sieci Web w witrynie programu TeamViewer. Wprowadź swoje poświadczenia licencji programu TeamViewer, a następnie kliknij pozycję **Zaloguj się**.

## <a name="remotely-administer-a-device"></a>Zdalne administrowanie urządzeniem

Po skonfigurowaniu łącznika można rozpocząć zdalne administrowanie urządzeniem. Wykonaj następujące kroki: 

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz opcję **Wszystkie usługi** i wyszukaj usługę **Microsoft Intune**.
2. W obszarze **Microsoft Intune** wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
3. Z listy wybierz urządzenie, którym chcesz zdalnie administrować. We właściwościach urządzenia wybierz pozycję **Nowa sesja pomocy zdalnej**.
4. Po połączeniu usługi Intune z usługą programu TeamViewer zostaną wyświetlone pewne informacje o urządzeniu. Wybierz pozycję **Połącz**, aby rozpocząć sesję zdalną.

![Używanie programu TeamViewer do zdalnego administrowania urządzeniem z systemem Android — przykład](./media/android-teamviewer.png)

Po rozpoczęciu sesji zdalnej użytkownicy będą widzieć flagę powiadomienia na ikonie aplikacji Portal firmy na swoim urządzeniu. Po otwarciu aplikacji jest również wyświetlane powiadomienie. Użytkownik może zaakceptować żądanie pomocy zdalnej.

> [!NOTE]
> Powiadomienia programu TeamViewer w aplikacji Portal firmy nie są wyświetlane dla urządzeń z systemem Windows zarejestrowanych przy użyciu metod „bez użytkownika”, takich jak DEM i WCD. W tych przypadkach zaleca się użycie portalu programu TeamViewer do wygenerowania sesji.

W programie TeamViewer można wykonywać wiele akcji w urządzeniu, łączenie z przejęciem kontroli nad nim. Aby uzyskać szczegółowe informacje na temat czynności możliwych do wykonania, zobacz [wskazówki dotyczące programu TeamViewer](https://www.teamviewer.com/support/documents/).

Po zakończeniu zamknij okno programu TeamViewer.
