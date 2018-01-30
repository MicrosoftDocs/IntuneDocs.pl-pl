---
title: "Jak używać funkcji zdalnego administrowania urządzeniami przy użyciu programu TeamViewer"
titlesuffix: Azure portal
description: "Informacje dotyczące zdalnego administrowania urządzeniami przy użyciu programu TeamViewer."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 476480ce3957ef2d411b37a0a078707c721fd2e6
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a>Zapewnienie pomocy zdalnej dla urządzeń zarządzanych przy użyciu usługi Intune

Usługa Intune może korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń, którymi zarządzasz. Informacje w tym temacie pomogą rozpocząć pracę.

## <a name="before-you-start"></a>Przed rozpoczęciem

### <a name="supported-devices"></a>Obsługiwane urządzenia

Urządzenia z systemami Windows i Android zarządzane przez usługę Intune obsługują administrację zdalną.

>[!NOTE]
>Systemy Windows Holographic (HoloLens), Windows Team (Surface Hub) i Windows 10 S nie są obsługiwane przez oprogramowanie TeamViewer. Nadal trzeba zarządzać urządzeniami przy użyciu [klienta](/intune-classic/deploy-use/pc-management-comparison?toc=/intune/toc.json) w klasycznym portalu usługi Intune.



### <a name="required-permissions"></a>Wymagane uprawnienia

Upewnij się, że użytkownik portalu Azure Portal ma przypisane następujące uprawnienia w postaci [roli usługi Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):
- Aby umożliwić administratorowi zmianę ustawień łącznika programu TeamViewer, przyznaj uprawnienie **Aktualizuj pomoc zdalną**.
- Aby umożliwić administratorowi zainicjowanie nowego żądania pomocy zdalnej, przyznaj uprawnienie **Żądaj pomocy zdalnej**. Użytkownicy z uprawnieniem **Żądaj pomocy zdalnej** mogą żądać zainicjowania sesji dla dowolnego użytkownika. Nie są oni ograniczeni przez jakikolwiek zakres przypisania roli usługi Intune. Zakresy przypisania roli usługi Intune nie ograniczają urządzeń ani użytkowników, dla których mogą być inicjowane żądania pomocy zdalnej.

>[!NOTE]
>Włączenie programu TeamViewer umożliwi programowi TeamViewer dla łącznika usługi Intune utworzenie sesji programu TeamViewer, odczytanie danych usługi Active Directory oraz zapisanie tokenu dostępu do konta programu TeamViewer.

### <a name="configure-the-intune-teamviewer-connector"></a>Konfigurowanie łącznika usługi Intune programu TeamViewer

Przed zapewnieniem pomocy zdalnej dla urządzeń musisz skonfigurować łącznik programu TeamViewer w usłudze Intune, wykonując następujące kroki:


1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz kolejno pozycje **Konfiguracja** > **Łącznik programu TeamViewer**.
5. W bloku **Łącznik programu TeamViewer** kliknij pozycję **Włącz**, a następnie wyświetl i zaakceptuj umowę licencyjną usługi TeamViewer.
6. Wybierz pozycję **Zaloguj się do programu TeamViewer, aby autoryzować**.
7. Zostanie otwarta strona sieci Web w witrynie programu TeamViewer. Wprowadź swoje poświadczenia licencji programu TeamViewer, a następnie kliknij przycisk **Zaloguj się**.


## <a name="how-to-remotely-administer-a-device"></a>Jak zdalnie administrować urządzeniem

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz kolejno pozycje **Zarządzaj** > **Wszystkie urządzenia**.
5. Wybierz urządzenie, którym chcesz zdalnie administrować, a następnie w bloku właściwości urządzenia wybierz kolejno pozycje **Więcej** > **Nowa sesja Pomocy zdalnej**.
6. Po połączeniu usługi Intune z usługą programu TeamViewer zostaną wyświetlone pewne informacje o urządzeniu. Wybierz opcję **Połącz**, aby rozpocząć sesję zdalną.

![Przykład zastosowania programu TeamViewer dla systemu Android](./media/android-teamviewer.png)

W oknie programu TeamViewer można wykonać szereg akcji zdalnych na urządzeniu, m.in. zdalnie nim sterować. Aby uzyskać szczegółowe informacje na temat akcji, które można wykonać, zobacz [dokumentację programu TeamViewer](https://www.teamviewer.com/support/documents/).

Po zakończeniu zamknij okno programu TeamViewer.

## <a name="next-steps"></a>Następne kroki

Użytkownik końcowy zobaczy flagę powiadomienia na ikonie aplikacji Portal firmy na swoim urządzeniu oraz powiadomienie po otwarciu aplikacji. Wtedy może zaakceptować żądanie pomocy zdalnej.
