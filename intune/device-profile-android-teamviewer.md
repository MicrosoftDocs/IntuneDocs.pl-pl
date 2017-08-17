---
title: "Jak używać funkcji zdalnego administrowania urządzeniami z systemem Android przy użyciu programu TeamViewer"
titleSuffix: Intune on Azure
description: "Informacje dotyczące zdalnego administrowania urządzeniami z systemem Android przy użyciu programu TeamViewer."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bf25ec3fbdec76fb1defb5e4cb12be6dcdf03b0d
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/09/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Zapewnienie pomocy zdalnej dla urządzeń z systemem Android zarządzanych przy użyciu usługi Intune

Usługa Intune może korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Android. Informacje w tym temacie pomogą rozpocząć pracę.

## <a name="before-you-start"></a>Przed rozpoczęciem

### <a name="required-permissions"></a>Wymagane uprawnienia

Upewnij się, że użytkownik portalu Azure Portal ma przypisane następujące uprawnienia w postaci [roli usługi Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):
- Aby umożliwić administratorowi zmianę ustawień łącznika programu TeamViewer, przyznaj uprawnienie **Aktualizuj pomoc zdalną**.
- Aby umożliwić administratorowi zainicjowanie nowego żądania pomocy zdalnej, przyznaj uprawnienie **Żądaj pomocy zdalnej**. Użytkownicy z uprawnieniem **Żądaj pomocy zdalnej** mogą żądać zainicjowania sesji dla dowolnego użytkownika. Nie są oni ograniczeni przez jakikolwiek zakres przypisania roli usługi Intune. Zakresy przypisania roli usługi Intune nie ograniczają urządzeń ani użytkowników, dla których mogą być inicjowane żądania pomocy zdalnej.

>[!NOTE]
>Włączenie programu TeamViewer umożliwi programowi TeamViewer dla łącznika usługi Intune utworzenie sesji programu TeamViewer, odczytanie danych usługi Active Directory oraz zapisanie tokenu dostępu do konta programu TeamViewer.

### <a name="configure-the-intune-teamviewer-connector"></a>Konfigurowanie łącznika usługi Intune programu TeamViewer

Przed zapewnieniem pomocy zdalnej dla urządzeń z systemem Android musisz skonfigurować łącznik programu TeamViewer w usłudze Intune, wykonując następujące czynności:


1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia i grupy** wybierz kolejno pozycje **Konfiguracja** > **Łącznik programu TeamViewer**.
5. W bloku **Łącznik programu TeamViewer** kliknij pozycję **Włącz**, a następnie wyświetl i zaakceptuj umowę licencyjną usługi TeamViewer.
6. Wybierz pozycję **Zaloguj się do programu TeamViewer, aby autoryzować**.
7. Zostanie otwarta strona sieci Web w witrynie programu TeamViewer. Wprowadź swoje poświadczenia licencji programu TeamViewer, a następnie kliknij przycisk **Zaloguj się**.


## <a name="how-to-remotely-administer-an-android-device"></a>Jak zdalnie administrować urządzeniem z systemem Android

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz kolejno pozycje **Zarządzaj** > **Wszystkie urządzenia**.
5. Wybierz urządzenie, którym chcesz zdalnie administrować, a następnie w bloku właściwości urządzenia wybierz kolejno pozycje **Więcej** > **Nowa sesja Pomocy zdalnej**.
6. Po połączeniu usługi Intune z usługą programu TeamViewer zostaną wyświetlone pewne informacje o urządzeniu z systemem Android. Wybierz opcję **Połącz**, aby rozpocząć sesję zdalną.

![Okna programu TeamViewer na urządzeniach z systemem Android](./media/android-teamviewer.png)

W oknie programu TeamViewer można wykonać szereg akcji zdalnych na urządzeniu z systemem Android, m.in. zdalnie sterować urządzeniem. Aby uzyskać szczegółowe informacje na temat akcji, które można wykonać, zobacz [dokumentację programu TeamViewer](https://www.teamviewer.com/support/documents/).

Po zakończeniu zamknij okno programu TeamViewer.

## <a name="end-user-notifications"></a>Powiadomienia użytkownika końcowego

Użytkownik końcowy zobaczy flagę powiadomienia na ikonie aplikacji Portal firmy na swoim urządzeniu oraz powiadomienie po otwarciu aplikacji. Wtedy może zaakceptować żądanie pomocy zdalnej.

