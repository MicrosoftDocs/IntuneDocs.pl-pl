---
title: "Żądanie i zapewnianie pomocy zdalnej dla komputerów osobistych z systemem Windows | Microsoft Docs"
description: "W tym artykule opisano kroki wykonywane przez użytkownika i administratora IT zapewniające uzyskanie pomocy zdalnej dla komputerów z systemem Windows zarządzanych jako komputery osobiste i zdalne uruchamianie komputera osobistego."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 10dd2caa9ce1b96424f55e373e904a778390eb15
ms.openlocfilehash: 628875c2f874c824761befd9886d7f7987c045df
ms.lasthandoff: 12/16/2016


---

# <a name="request-and-provide-remote-assistance-for-windows-pcs"></a>Żądanie i zapewnianie pomocy zdalnej dla komputerów z systemem Windows

Informacje w tym temacie dotyczą tylko komputerów z systemem Windows, które są zarządzane jako komputery osobiste przy użyciu oprogramowania klienckiego usługi Intune.

Usługa Intune może korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom komputerów z uruchomionym oprogramowaniem klienckim usługi Intune. Gdy użytkownik zażąda pomocy w programie Microsoft Intune Center, otrzymasz alert informujący o żądaniu, a następnie możesz zaakceptować żądanie i udzielić użytkownikowi pomocy. Ta funkcja zastępuje istniejącą funkcję Pomoc zdalna systemu Windows w usłudze Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

Zanim zaczniesz korzystać z żądań pomocy zdalnej i odpowiadać na nie, upewnij się, że zostały spełnione następujące wymagania wstępne:

- Masz [utworzone konto programu TeamViewer](https://login.teamviewer.com/LogOn#register) w celu logowania się do witryny sieci Web programu TeamViewer.
- Komputery osobiste z systemem Windows, którymi chcesz administrować, muszą być [zarządzane przez oprogramowanie klienckie systemu Windows](manage-windows-pcs-with-microsoft-intune.md)
- Można administrować wszystkimi systemami operacyjnymi Windows obsługiwanymi przez usługę Intune.

## <a name="configure-the-teamviewer-connector"></a>Konfigurowanie łącznika programu TeamViewer

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja**.
2. W obszarze roboczym **Administracja** wybierz pozycję **TeamViewer**.
3. Na stronie **TeamViewer** w obszarze **Łącznik programu TeamViewer** wybierz opcję **Włącz**.
4. W oknie dialogowym **Włączanie programu TeamViewer** przejrzyj, a następnie **Zaakceptuj** postanowienia licencyjne. Jeśli nie masz jeszcze licencji programu TeamViewer, wybierz opcję **Kup licencję programu TeamViewer**.
5. Po otwarciu okna przeglądarki programu TeamViewer zaloguj się do witryny przy użyciu poświadczeń programu TeamViewer.
6. W witrynie programu TeamViewer przeczytaj, a następnie zaakceptuj opcje, aby umożliwić usłudze Intune połączenie z programem TeamViewer.
7. W konsoli usługi Intune upewnij się, że element **Łącznik programu TeamViewer** jest wyświetlany jako **Włączony**.


## <a name="open-a-remote-assistance-request-end-user"></a>Otwieranie żądania pomocy zdalnej (użytkownik końcowy)

1. Na komputerze klienckim z systemem Windows otwórz program **Microsoft Intune Center**.
2. W obszarze **Pomoc zdalna** wybierz pozycję **Żądaj pomocy zdalnej**.
3. Po zatwierdzeniu żądania (patrz poniżej) program TeamViewer jest otwierany na komputerze klienckim. Użytkownik musi zaakceptować komunikaty wskazujące, że przeglądarka sieci Web próbuje otworzyć aplikację TeamViewer.
4. Użytkownik zobaczy komunikat z pytaniem, czy możesz przejąć kontrolę nad jego komputerem. Musi zaakceptować ten komunikat, aby kontynuować.
5. Podczas sesji pomocy zdalnej użytkownik widzi okno wskazujące, że masz z nim połączenie. Jeśli zamknie to okno, sesja zdalna zostanie zakończona.

## <a name="respond-to-a-remote-assistance-request"></a>Odpowiadanie na żądanie pomocy zdalnej

1. Gdy użytkownik prześle żądanie pomocy zdalnej, możesz je wyświetlić w obszarze roboczym **Alerty** w obszarze **Monitorowanie** > **Pomoc zdalna**. Na przykład:
> ![Zrzut ekranu przedstawiający żądanie pomocy zdalnej](./media/team-viewer.png)

<br>Jeśli żądanie pozostanie bez odpowiedzi przez więcej niż 4 godziny, zostanie usunięte.
2. Aby zaakceptować żądanie, wybierz pozycję **Zatwierdź żądanie i uruchom pomoc zdalną**.
3. W oknie dialogowym **Oczekuje nowe żądanie pomocy zdalnej** wybierz pozycję **Zaakceptuj żądanie pomocy zdalnej**. Jeśli jeszcze ich nie zainstalowano, program TeamViewer zainstaluje wszelkie niezbędne aplikacje na komputerze osobistym.
4. Program TeamViewer powiadomi następnie użytkownika końcowego, że chcesz przejąć kontrolę nad jego komputerem. Po zatwierdzeniu żądania przez użytkownika okno programu TeamViewer zostanie otwarte i możesz sterować jego komputerem.

Podczas sesji pomocy zdalnej możesz korzystać ze wszystkich dostępnych poleceń programu TeamViewer do sterowania komputerem zdalnym. Aby uzyskać pomoc dotyczącą tych poleceń, pobierz publikację [Manual for remote control](http://www.teamviewer.com/en/support/documents/) (Podręcznik zdalnego sterowania) z witryny sieci Web programu TeamViewer.

## <a name="close-the-remote-assistance-session"></a>Zamykanie sesji pomocy zdalnej

Z menu **Akcje** okna programu **TeamViewer** wybierz polecenie **Zakończ sesję**.

## <a name="remotely-restart-a-windows-pc"></a>Zdalne ponowne uruchamianie komputera z systemem Windows
W trakcie udzielania pomocy użytkownikom w rozwiązywaniu problemów od czasu do czasu może okazać się konieczne ponowne uruchomienie komputera zdalnie. Wykonaj następujące kroki, aby zdalnie ponownie uruchomić komputer z systemem Windows.

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer osobisty, który chcesz ponownie uruchomić).

2.  Wybierz co najmniej jeden komputer osobisty, a następnie wybierz kolejno pozycje **Zadania zdalne** &gt; **Uruchom ponownie komputer**.

3.  Aby wyświetlić stan zadania, wybierz pozycję **Zadania zdalne** w prawym dolnym rogu strony.

4.  W oknie dialogowym **Stan zadania** przejrzyj bieżące zadania zdalne, stan zadania, nazwę urządzenia i wszystkie zgłoszone błędy.

### <a name="see-also"></a>Zobacz także

[Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta oprogramowania usługi Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
