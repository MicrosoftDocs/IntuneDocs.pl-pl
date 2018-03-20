---
title: "Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10"
titleSuffix: Microsoft Intune
description: "Dowiedz się, jak ręcznie dodać aplikację Portal firmy dla systemu Windows 10."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 06ed9395d06e2d64edcedcaadfe819ad03f1d495
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10 przy użyciu usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Użytkownicy mogą zainstalować aplikację Portal firmy ze Sklepu Microsoft, aby zarządzać urządzeniami i instalować aplikacje. Jeśli jednak w Twojej organizacji wymagane jest przypisanie aplikacji Portal firmy, aplikację Portal firmy dla systemu Windows 10 można przypisać ręcznie bezpośrednio z poziomu usługi Intune, nawet jeśli usługa Intune nie została zintegrowana ze Sklepem Microsoft dla Firm.

 > [!NOTE]
 > Ta opcja wymaga ręcznego przypisywania aktualizacji po każdym wydaniu nowej aktualizacji aplikacji.

## <a name="configure-settings-to-show-offline-apps"></a>Konfiguracja ustawień w celu wyświetlania aplikacji w trybie offline
1. Przejdź do [Sklepu Microsoft dla Firm](https://www.microsoft.com/business-store) i upewnij się, że do logowania użyto konta administratora.
2. Wybierz kartę **Zarządzaj** w górnej części okna.
3. Wybierz opcję **Ustawienia** w lewej kolumnie nawigacji.
4. Ustaw opcję **Pokaż aplikacje w trybie offline** w sekcji **Środowisko użytkownika sklepu** na **Wł.** Dzięki temu licencjonowane aplikacje w trybie offline będą wyświetlane w sklepie Microsoft Store dla Firm.

## <a name="download-the-offline-company-portal-app"></a>Pobieranie aplikacji Portal firmy w trybie offline
1. Wyszukaj i wybierz aplikację **Portal firmy**.
2. Ustaw opcję **Typ licencji** na **Offline**.
3. Kliknij opcję **Pobierz aplikację**, aby pobrać i dodać aplikację Portal firmy w trybie offline do swojego magazynu.
4. Kliknij opcję **Zarządzaj** na stronie aplikacji **Portal firmy**.
5. Wybierz pozycję **Wszystkie urządzenia z systemem Windows 10** w polu **Platforma**, a następnie odpowiednie wartości w polach **Wersja minimalna**, **Architektura** i Pobierz metadane aplikacji**. 
6. Kliknij opcję **Pobierz**, aby zapisać plik na maszynie lokalnej.

    ![Obraz systemu Windows 10 wszystkich urządzeń i szczegóły pakietu Architektura X86 do pobrania](./media/Win10CP-all-devices.png)

7. Pobierz wszystkie pakiety w obszarze „Wymagane struktury”. Jest to niezbędne dla architektury x86, x64 i ARM — co składa się na całkowitą liczbę 12 pakietów.
8. Przed przekazaniem aplikacji Portal firmy usługi Intune utwórz folder (na przykład C:&#92;Portal firmy) z pakietami umieszczonymi w następujący sposób:
  - Umieść pakiet Portal firmy w folderze C:\Portal firmy. W tej lokalizacji utwórz również podfolder Zależności.  

    ![Obraz folderu Zależności zapisany w pliku APPXBUN](./media/Win10CP-Dependencies-save.png)

  - Umieść pakiety zależności w folderze *Zależności*. 

     > [!NOTE]
     > Jeśli zależności nie będą wprowadzone w prawidłowym formacie, usługa Intune nie będzie mogła rozpoznać i przekazać plików podczas przekazywania pakietu, co spowoduje niepowodzenie przekazania oraz wyświetlenie następującego błędu.

9. Wróć do usługi Microsoft Intune w witrynie Azure Portal.
10. Przekaż aplikację Portal firmy jako nową aplikację. Przypisz ją jako wymaganą aplikację dla żądanej grupy użytkowników docelowych.  

Aby uzyskać więcej informacji na temat sposobu obsługi zależności dla aplikacji uniwersalnych w usłudze Intune, zobacz temat [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Wdrażanie pliku appxbundle z zależnościami poprzez rozwiązanie MDM programu Microsoft Intune).  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak zaktualizować aplikację Portal firmy na urządzeniach moich użytkowników, jeśli już mają zainstalowane starsze aplikacje ze sklepu?
Jeśli użytkownicy mają już zainstalowane aplikacje Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 ze sklepu, powinny one zostać automatycznie zaktualizowane do nowej wersji bez konieczności wykonania jakichkolwiek czynności przez Ciebie lub użytkowników. Jeśli aktualizacja nie miała miejsca, poproś użytkowników, aby sprawdzili, czy na swoich urządzeniach mają włączoną opcję automatycznych aktualizacji.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić moją załadowaną bezpośrednio aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?
Zalecana przez nas ścieżka migracji polega na usunięciu przypisania aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji przypisania na „Odinstaluj”. Następnie aplikację Portal firmy dla systemu Windows 10 można przypisać przy użyciu dowolnej z powyższych opcji.  

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została przypisana bez rejestrowania jej za pomocą certyfikatu firmy Symantec, wykonaj instrukcje zawarte w poprzedniej sekcji dotyczącej bezpośredniego przypisywania za pomocą usługi Intune, aby ukończyć uaktualnianie.

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została podpisana i przypisana za pomocą certyfikatu firmy Symantec, wykonaj instrukcje zawarte w sekcji poniżej.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić podpisaną i ładowaną bezpośrednio aplikację Portal firmy dla systemu Windows Phone 8.1 lub aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?
Zalecana przez nas ścieżka migracji polega na usunięciu istniejącego przypisania aplikacji Portal firmy dla systemu Windows Phone 8.1 lub aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji przypisania na „Odinstaluj”. Następnie aplikację Portal firmy dla systemu Windows 10 można przypisać w zwykły sposób.  

W przeciwnym razie aplikacja Portal firmy dla systemu Windows 10 musi zostać odpowiednio aktualizowana i podpisana w celu zapewnienia, że ścieżka uaktualnienia jest zachowana.  

Jeśli aplikacja Portal firmy dla systemu Windows 10 została podpisana i przypisana w ten sposób, konieczne będzie powtórzenie tego procesu dla każdej nowej aktualizacji aplikacji, gdy będzie ona dostępna w sklepie. Aplikacja nie będzie automatycznie aktualizowana podczas aktualizacji sklepu.  

Poniżej przedstawiono procedurę podpisywania i przypisywania aplikacji w ten sposób:

1. Pobierz skrypt podpisywania aplikacji Portal firmy dla systemu Windows 10 usługi Microsoft Intune ze strony [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Ten skrypt wymaga wcześniejszego zainstalowania pakietu Windows SDK dla systemu Windows 10 na komputerze-hoście. Aby pobrać pakiet Windows SDK dla systemu Windows 10, odwiedź stronę [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Pobierz aplikację Portal firmy dla systemu Windows 10 ze Sklepu Microsoft dla Firm zgodnie z powyższym opisem.  
3. Uruchom skrypt z parametrami wejściowymi wyszczególnionymi w nagłówku skryptu, aby podpisać aplikację Portal firmy dla systemu Windows 10 (wyodrębnioną poniżej). Zależności nie trzeba przekazać do skryptu. Są one wymagane tylko w przypadku, gdy aplikacja jest przekazywana do konsoli administracyjnej usługi Intune.

|Parametr | Opis|
| ------------- | ------------- |
|InputWin10AppxBundle |Ścieżka, w której znajduje się źródłowy plik appxbundle |
|OutputWin10AppxBundle |Ścieżka wyjściowa dla podpisanego pliku appxbundle.  Win81Appx — ścieżka, w której znajduje się plik aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 (plik APPX).|
|PfxFilePath |Ścieżka pliku z certyfikatem podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych (pliku PFX). |
|PfxPassword| Hasło certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych. |
|PublisherId |Identyfikator wydawcy przedsiębiorstwa. Jeśli go nie ma, używane jest pole Podmiot certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych.|
|SdkPath | Ścieżka do głównego folderu pakietu Windows SDK dla systemu Windows 10. Ten argument jest opcjonalny i domyślnie ustawiony na wartość ${env:ProgramFiles(x86)}\Windows Kits\10|
Po zakończeniu działania skryptu zostanie wygenerowana podpisana wersja aplikacji Portal firmy dla systemu Windows 10. Następnie można przypisać podpisaną wersję aplikacji jako aplikację biznesową za pomocą usługi Intune, która spowoduje uaktualnienie aktualnie przypisanych wersji do tej nowej aplikacji.  

## <a name="next-steps"></a>Następne kroki

- [Jak przypisać aplikacje do grup](apps-deploy.md)

