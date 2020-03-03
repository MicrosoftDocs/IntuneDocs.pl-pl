---
title: Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10
titleSuffix: Microsoft Intune
description: Dowiedz się, jak pracownicy mogą ręcznie dodać aplikację Portal firmy dla systemu Windows 10 do swoich komputerów z poziomu sklepu Microsoft Store.
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
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c2083d6f259b62b2856e08fec5ebcb696cbc0df
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576451"
---
# <a name="add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>Dodawanie aplikacji Portal firmy dla systemu Windows 10 przy użyciu usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Użytkownicy mogą samodzielnie zainstalować aplikację Portal firmy ze sklepu Microsoft Store, aby zarządzać urządzeniami i instalować aplikacje. Jeśli jednak w Twojej organizacji wymagane jest przypisanie aplikacji Portal firmy do użytkowników, aplikację Portal firmy dla systemu Windows 10 można przypisać bezpośrednio z poziomu usługi Intune. Można to zrobić, nawet jeśli usługa Intune nie została zintegrowana ze sklepem Microsoft Store dla Firm.

 > [!IMPORTANT]
 > Jeśli pobrano aplikację Portal firmy, opcja opisana w tym artykule wymaga ręcznego przypisywania aktualizacji po każdym wydaniu aktualizacji aplikacji. Aby uzyskać informacje na temat wdrażania aplikacji Portal firmy dla systemu Windows 10 na urządzeniach aprowizowanych za pomocą rozwiązania Autopilot, zobacz [Dodawanie aplikacji Portal firmy dla systemu Windows 10 na urządzeniach rozwiązania Autopilot](~/apps/store-apps-company-portal-autopilot.md).

## <a name="configure-settings-to-show-offline-apps"></a>Konfiguracja ustawień w celu wyświetlania aplikacji w trybie offline
1. Zaloguj się do sklepu [Microsoft Store dla Firm](https://www.microsoft.com/business-store) przy użyciu konta administratora.
2. Wybierz kartę **Zarządzaj** w górnej części okna.
3. W okienku po lewej stronie wybierz pozycję **Ustawienia**.
4. W sekcji **Środowisko użytkownika sklepu** ustaw opcję **Pokaż aplikacje w trybie offline** na **Wł.**  
    Zostaną wyświetlone licencjonowane aplikacje w trybie offline.

## <a name="download-the-offline-company-portal-app"></a>Pobieranie aplikacji Portal firmy w trybie offline
1. Wyszukaj i wybierz aplikację **Portal firmy**.
2. Ustaw opcję **Typ licencji** na **Offline**.
3. Wybierz pozycję **Pobierz aplikację**, aby pobrać i dodać aplikację Portal firmy w trybie offline do swojego magazynu.
4. Na stronie aplikacji **Portal firmy** wybierz pozycję **Zarządzaj**.
5. W polu **Platforma** wybierz pozycję **Wszystkie urządzenia z systemem Windows 10**, a następnie wybierz odpowiednie wartości w polach **Wersja minimalna**, **Architektura** i **Pobierz metadane aplikacji**. 
6. Wybierz pozycję **Pobierz**, w obszarze **Szczegóły pakietu**, aby zapisać plik na maszynie lokalnej.

    ![Wybrana jest opcja urządzeń z systemem Windows 10 oraz architektury X86](./media/app-sideload-windows/Win10CP-all-devices.png)

7. Pobierz wszystkie pakiety w obszarze „Wymagane struktury” wybierając pozycję **Pobierz**.  

    Należy wykonać tę czynność dla architektury x86, x64 i ARM:<br> 
    *W przypadku wybrania opcji 1507 jako minimalnej wersji systemu operacyjnego istnieje 9 wymaganych pakietów struktury, w przypadku wybrania opcji 1511 — 12 pakietów, a w przypadku wybrania opcji 1607 — 15 pakietów.*

8. W usłudze Microsoft Intune w witrynie Azure Portal przekaż aplikację Portal firmy jako nową aplikację. Aby dodać tę aplikację, wybierz aplikację biznesową jako **Typ aplikacji** w okienku **Wybierz typ aplikacji**. Następnie wybierz plik pakietu aplikacji (z rozszerzeniem AppxBundle).

9. W obszarze **Wybieranie plików aplikacji zależności** zaznacz wszystkie zależności pobrane w kroku 7, używając kliknięcia z klawiszem Shift, i sprawdź, czy w kolumnie **Dodane** jest wyświetlana wartość **Tak** dla architektur, których potrzebujesz.

     > [!NOTE]
     > Jeśli zależności nie zostaną dodane, aplikacja może nie zostać zainstalowana na określonych typach urządzeń.

10. Kliknij przycisk **Ok**, wprowadź wszystkie żądane informacje w obszarze **Informacje o aplikacji**, a następnie kliknij pozycję **Dodaj**.

11. Przypisz aplikację Portal firmy jako aplikację wymaganą do wybranego zestawu użytkowników lub grup urządzeń.  

Aby uzyskać więcej informacji na temat sposobu obsługi zależności dla aplikacji uniwersalnych w usłudze Intune, zobacz temat [Deploying an appxbundle with dependencies via Microsoft Intune MDM (Wdrażanie pliku appxbundle z zależnościami poprzez rozwiązanie MDM programu Microsoft Intune)](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

## <a name="frequently-asked-questions"></a>Często zadawane pytania 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak zaktualizować aplikację Portal firmy na urządzeniach moich użytkowników, jeśli już mają zainstalowane starsze aplikacje ze sklepu?
Jeśli użytkownicy mają już zainstalowane aplikacje Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 ze sklepu Microsoft Store, powinny one zostać automatycznie zaktualizowane do najnowszej wersji bez konieczności wykonania jakichkolwiek czynności przez Ciebie lub użytkowników. Jeśli aktualizacja nie miała miejsca, poproś użytkowników, aby upewnili się, czy na swoich urządzeniach mają włączoną opcję automatycznych aktualizacji ze sklepu Microsoft Store.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić moją załadowaną bezpośrednio aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?
Zalecana przez nas ścieżka migracji polega na usunięciu przypisania aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji przypisania na **Odinstaluj**. Po wybraniu tego ustawienia możesz przypisać aplikację Portal firmy dla systemu Windows 10, używając dowolnej z opisanych wcześniej opcji.  

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została przypisana bez rejestrowania jej za pomocą certyfikatu firmy Symantec, wykonaj czynności opisane w poprzednich sekcjach tego artykułu, aby ukończyć uaktualnianie.

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została podpisana i przypisana za pomocą certyfikatu podpisywania kodu firmy Symantec, wykonaj instrukcje zawarte w następnej sekcji.

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić podpisaną i ładowaną bezpośrednio aplikację Portal firmy dla systemu Windows Phone 8.1 lub aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?
Zalecana przez nas ścieżka migracji polega na usunięciu istniejącego przypisania aplikacji Portal firmy dla systemu Windows Phone 8.1 lub aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji przypisania na **Odinstaluj**. Po wybraniu tego ustawienia możesz przypisać aplikację Portal firmy dla systemu Windows 10 zwykłą metodą.  

W przeciwnym razie aplikacja Portal firmy dla systemu Windows 10 musi zostać odpowiednio aktualizowana i podpisana w celu zapewnienia, że ścieżka uaktualnienia jest zachowana.  

Jeśli aplikacja Portal firmy dla systemu Windows 10 zostanie podpisana i przypisana w ten sposób, konieczne będzie powtórzenie tego procesu dla każdej nowej aktualizacji aplikacji, gdy będzie ona dostępna w sklepie. Aplikacja nie będzie automatycznie aktualizowana podczas aktualizacji sklepu.  

Poniżej przedstawiono procedurę podpisywania i przypisywania aplikacji w ten sposób:

1. Pobierz [skrypt podpisywania aplikacji Portal firmy systemu Windows 10 dla usługi Microsoft Intune](https://aka.ms/win10cpscript).  
    Ten skrypt wymaga wcześniejszego zainstalowania pakietu Windows SDK dla systemu Windows 10 na komputerze-hoście. [Pobierz zestaw Windows SDK dla systemu Windows 10](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Pobierz aplikację Portal firmy dla systemu Windows 10 ze sklepu Microsoft Store dla Firm zgodnie z powyższym opisem.  
3. Aby podpisać aplikację Portal firmy dla systemu Windows 10, uruchom skrypt z parametrami wejściowymi wyszczególnionymi w nagłówku skryptu, jak pokazano w poniższej tabeli.  
    Zależności nie trzeba przekazać do skryptu. Są one wymagane tylko w przypadku, gdy aplikacja jest przekazywana do konsoli administracyjnej usługi Intune.

| Parametr |  Opis  |
|---|---|
| InputWin10AppxBundle  |  Ścieżka pliku źródłowego appxbundle. |
| OutputWin10AppxBundle | Ścieżka wyjściowa dla podpisanego pliku appxbundle. 
| Win81Appx  | Ścieżka pliku aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 (pliku APPX). |
| PfxFilePath  |  Ścieżka pliku z certyfikatem podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych (pliku PFX).  |
| PfxPassword  | Hasło certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych. |
| PublisherId | Identyfikator wydawcy przedsiębiorstwa. Jeśli go nie ma, używane jest pole Podmiot certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych. |
| SdkPath | Ścieżka do głównego folderu pakietu Windows SDK dla systemu Windows 10. Ten argument jest opcjonalny i domyślnie ustawiony na wartość ${env:ProgramFiles(x86)}\Windows Kits\10.  |

Po zakończeniu działania skryptu zostanie wygenerowana podpisana wersja aplikacji Portal firmy dla systemu Windows 10. Następnie można przypisać podpisaną wersję aplikacji jako aplikację biznesową za pomocą usługi Intune, która spowoduje uaktualnienie aktualnie przypisanych wersji do tej nowej aplikacji.  

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)

