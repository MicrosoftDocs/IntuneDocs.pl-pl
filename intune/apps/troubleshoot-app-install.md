---
title: Rozwiązywanie problemów z instalacją aplikacji
titleSuffix: Microsoft Intune
description: Użyj okienka rozwiązywania problemów w usłudze Microsoft Intune do rozwiązywania problemów z instalacją aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be66f99006b06dce9f9bfe21eafa9f2be302e7b9
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540983"
---
# <a name="troubleshoot-app-installation-issues"></a>Rozwiązywanie problemów z instalacją aplikacji

Na urządzeniach zarządzanych przez oprogramowanie MDM w usłudze Microsoft Intune czasami operacje instalacji aplikacji mogą zakończyć się niepowodzeniem. W takich sytuacjach zrozumienie przyczyny niepowodzenia lub rozwiązanie problemu może okazać się wyzwaniem. Usługa Microsoft Intune udostępnia szczegóły niepowodzeń instalacji aplikacji, które ułatwiają operatorom pomocy technicznej i administratorom usługi Intune wyświetlanie informacji o aplikacji pomocnych podczas obsługi żądań użytkowników dotyczących pomocy. Okienko rozwiązywania problemów w usłudze Intune zawiera szczegóły niepowodzenia, w tym szczegółowe informacje o aplikacjach zarządzanych na urządzeniu użytkownika. W obszarze każdego urządzenia w okienku **Aplikacje zarządzane** są dostępne kompleksowe szczegóły cyklu eksploatacji. Można zapoznać się z problemami dotyczącymi instalacji, takimi jak występujące podczas tworzenia, modyfikowania i wybierania aplikacji oraz dostarczania jej na urządzenie. 

> [!NOTE]
> Informacje o określonych kodach błędów instalacji aplikacji można znaleźć w temacie [Dokumentacja błędów instalacji aplikacji przy użyciu usługi Intune](~/apps/app-install-error-codes.md).

## <a name="app-troubleshooting-details"></a>Szczegóły dotyczące rozwiązywania problemów z aplikacją

Usługa Intune dostarcza szczegółowe informacje na temat rozwiązywania problemów z aplikacją w oparciu o aplikacje zainstalowane na urządzeniu określonego użytkownika.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz pozycję **Rozwiązywanie problemów i pomoc techniczna**.
4. Kliknij pozycję **Wybierz użytkownika**, aby wybrać użytkownika na potrzeby rozwiązywania problemów. Zostanie wyświetlone okienko **Wybieranie użytkowników**.
5. Wybierz użytkownika przez wpisanie jego nazwy lub adresu e-mail. Kliknij pozycję **Wybierz** w dolnej części okienka. Informacje dotyczące rozwiązywania problemów użytkownika zostaną wyświetlone w okienku **Rozwiązywanie problemów**. 
6. Wybierz urządzenie, którego problemy chcesz rozwiązać, z listy **Urządzenia**.
    ![Okienku Rozwiązywanie problemów w usłudze Intune.](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. Wybierz pozycję **Aplikacje zarządzane** w okienku wybranego urządzenia. Zostanie wyświetlona lista aplikacji zarządzanych.
    ![Szczegółowe informacje dotyczące określonego urządzenia zarządzanego przez usługę Intune.](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. Z listy wybierz aplikację, dla której **Stan instalacji** wskazuje niepowodzenie.
    ![Wybrana aplikacja z wyświetlonymi szczegółami niepowodzenia instalacji.](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > Tę samą aplikację można przypisać do wielu grup, ale z inną zamierzoną akcją (intencją) dla aplikacji. Na przykład rozpoznaną intencją aplikacji będzie wartość **wykluczona**, jeśli aplikacja została wykluczona w przypadku użytkownika podczas przypisywania aplikacji. Aby uzyskać więcej informacji, zobacz [Jak są rozwiązywane konflikty intencji aplikacji](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > W przypadku wystąpienia błędu instalacji wymaganej aplikacji użytkownik lub dział pomocy technicznej będzie w stanie zsynchronizować urządzenie i ponowić próbę instalacji aplikacji.

Szczegóły błędu instalacji aplikacji będą wskazywać problem. Tych szczegółów można użyć, aby określić najlepszą akcję do podjęcia w celu rozwiązania problemu. Aby uzyskać więcej informacji na temat rozwiązywania problemów z instalacją aplikacji, zobacz [Błędy instalacji aplikacji systemu Android](app-install-error-codes.md#android-app-installation-errors) i [Błędy instalacji aplikacji systemu iOS](app-install-error-codes.md#ios-app-installation-errors).

> [!Note]  
> Dostęp do okienka **Rozwiązywanie problemów** można też uzyskać przez przejście w przeglądarce do strony [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Instalacja aplikacji dostosowanej do grupy użytkowników nie dociera do urządzenia
Jeśli masz problemy z instalowaniem aplikacji, należy wziąć pod uwagę następujące działania:
- Jeśli aplikacja nie jest wyświetlana w Portalu firmy, upewnij się, że aplikacja jest wdrożona z zamiarem **Dostępne** i że użytkownik uzyskuje dostęp do Portalu firmy za pomocą typu urządzenia obsługiwanego przez aplikację.
- W przypadku urządzeń z systemem Windows w modelu BYOD użytkownik musi dodać do urządzenia konto służbowe.
- Sprawdź, czy użytkownik przekracza limit urządzeń usługi AAD:
  1. Przejdź do [ustawień urządzenia usługi Azure Active Directory](https://portal.azure.com/#pane/Microsoft_AAD_IAM/DevicesMenupane/DeviceSettings/menuId).
  2. Zanotuj wartość ustawioną dla pozycji **Maksymalna liczba urządzeń na użytkownika**.
  3. Przejdź do pozycji [Użytkownicy usługi Azure Active Directory](https://portal.azure.com/#pane/Microsoft_AAD_IAM/UsersManagementMenupane/AllUsers).
  4. Wybierz użytkownika, którego to dotyczy, a następnie kliknij pozycję **Urządzenia**.
  5. Jeśli użytkownik przekracza ustawiony limit, usuń wszystkie nieodświeżone rekordy, które nie są już potrzebne.
- W przypadku urządzeń z systemem iOS w ramach programu DEP upewnij się, że użytkownik jest wymieniony jako **użytkownik rejestrujący** w okienku przeglądu urządzeń usługi Intune. Jeśli jest wyświetlana wartość ND, wdróż zasady konfiguracji dla aplikacji Intune — Portal firmy. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji Portal firmy](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Rozwiązywanie problemów z instalacją aplikacji Win32

Wybierz aplikację Win32 wdrożoną za pomocą rozszerzenia do zarządzania usługi Intune. Jeśli instalacja aplikacji Win32 kończy się niepowodzeniem, możesz zaznaczyć opcję **Zbieraj dzienniki**. 

> [!IMPORTANT]
> Opcja **Zbieraj dzienniki** nie będzie dostępna, jeśli aplikacja Win32 została pomyślnie zainstalowana na urządzeniu.<p>Aby móc zbierać informacje dzienników aplikacji Win32, na kliencie z systemem Windows musi być zainstalowane rozszerzenie do zarządzania usługi Intune. Rozszerzenie zarządzania usługi Intune jest instalowane, gdy skrypt programu PowerShell lub aplikacja Win32 jest wdrażana do grupy zabezpieczeń użytkowników lub urządzeń. Aby uzyskać więcej informacji, zobacz [Intune Management extension — Prerequisites (Rozszerzenie do zarządzania usługi Intune — wymagania wstępne)](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Zbieranie plików dziennika

Aby zbierać dzienniki instalacji aplikacji Win32, najpierw wykonaj czynności przedstawione w sekcji [Szczegóły dotyczące rozwiązywania problemów z aplikacją](troubleshoot-app-install.md#app-troubleshooting-details). Następnie wykonaj następujące czynności:

1. Kliknij opcję **Zbieraj dzienniki** w okienku **Szczegóły instalacji**.

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. Podaj ścieżki do plików oraz nazwy plików dziennika, aby rozpocząć proces zbierania plików dziennika, a następnie kliknij przycisk **OK**.

    > [!NOTE]
    > Zbieranie dzienników potrwa mniej niż dwie godziny. Obsługiwane typy plików to *log, txt, dmp, cab, zip, xml, evtx i evtl*. Maksymalna liczba ścieżek do plików to 25.

3. Po zebraniu plików dziennika możesz je pobrać, wybierając link **dzienniki**.

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Zostanie wyświetlone powiadomienie o powodzeniu zbierania dzienników aplikacji.

#### <a name="win32-log-collection-requirements"></a>Wymagania dotyczące zbierania dzienników Win32

Aby możliwe było zbieranie plików dziennika, muszą zostać spełnione określone wymagania:

- Należy podać pełną ścieżkę do pliku. 
- Można podać zmienne środowiskowe na potrzeby zbierania dzienników, na przykład:<br>
  *%PROGRAMFILES%, %PROGRAMDATA% %PUBLIC%, %WINDIR%, %TEMP%, %TMP%*
- Dozwolone są tylko dokładne rozszerzenia plików, na przykład:<br>
  *log, txt, dmp, cab, zip, xml*
- Maksymalnie można przekazać 60 MB danych lub 25 plików, w zależności od tego, który limit zostanie wyczerpany wcześniej. 
- Opcja zbierania dzienników instalacji aplikacji Win32 jest dostępna w przypadku aplikacji z intencją przypisywania aplikacji „wymagane”, „dostępne” oraz „odinstaluj”.
- Przechowywane dzienniki są szyfrowane, aby chronić wszelkie dane osobowe zawarte w dziennikach.
- Otwierając bilet pomocy technicznej dotyczący błędów aplikacji Win32, dołącz do niego odpowiednie dzienniki błędów, korzystając z powyższych instrukcji.

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Rozwiązywanie problemów z aplikacjami ze Sklepu Microsoft

Informacje zawarte w temacie [Troubleshooting packaging, deployment, and query of Microsoft Store apps (Tworzenie pakietów, wdrażanie i zapytania aplikacji ze Sklepu Microsoft)](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) pomagają w rozwiązywaniu typowych problemów, które mogą wystąpić podczas instalowania aplikacji ze Sklepu Microsoft za pomocą usługi Intune lub w inny sposób.

## <a name="app-troubleshooting-resources"></a>Zasoby rozwiązywania problemów z aplikacją
- [Wdrażanie programów Visio i Project w ramach wdrożenia pakietu Office Pro Plus](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Podejmowanie działań w celu zagwarantowania, że aplikacje MSfB wdrożone przy użyciu usługi Intune są instalowane w systemie Windows 10 1903](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Rozwiązywanie problemów z wdrożeniami aplikacji MSI w usłudze Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Najlepsze rozwiązania dotyczące dystrybucji oprogramowania do klasycznego agenta komputera z systemem Windows w usłudze Intune](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów z usługą Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](../fundamentals/help-desk-operators.md). 
- Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Sukces klientów usługi Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md).
