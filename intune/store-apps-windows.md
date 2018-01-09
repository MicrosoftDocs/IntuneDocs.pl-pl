---
title: "Jak dodać aplikacje ze sklepu z aplikacjami dla systemu Windows do usługi Intune"
titleSuffix: Azure portal
description: "Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu Windows do usługi Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 19339bee8b362b1168e62da9716dbfd3144e85e7
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu Windows do usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W bloku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
7. W bloku **Edytuj aplikację** skonfiguruj następujące informacje. Gdy wszystko będzie gotowe, kliknij pozycję **Dodaj**. W zależności od wybranej aplikacji niektóre wartości w tym bloku mogą zostać wypełnione automatycznie:
    - **Nazwa aplikacji** — wprowadź nazwę aplikacji, która będzie wyświetlana w Portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis aplikacji** — wprowadź opis aplikacji. Ta informacja będzie widoczna dla użytkowników w Portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu z aplikacjami** — wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria (opcjonalnie)** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
    - **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Przekaż ikonę** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
8. Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Zapisz**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

## <a name="manually-assign-windows-10-company-portal-app"></a>Ręczne przypisywanie aplikacji Portal firmy dla systemu Windows 10
Użytkownicy mogą zainstalować aplikację Portal firmy ze Sklepu Microsoft, aby zarządzać urządzeniami i instalować aplikacje. Jeśli jednak w Twojej organizacji wymagane jest przypisanie aplikacji Portal firmy, aplikację Portal firmy dla systemu Windows 10 można przypisać ręcznie bezpośrednio z poziomu usługi Intune, nawet jeśli usługa Intune nie została zintegrowana ze Sklepem Microsoft dla Firm.

 > [!NOTE]
 > Ta opcja wymaga ręcznego przypisywania aktualizacji po każdym wydaniu nowej aktualizacji aplikacji.

1. Zaloguj się do swojego konta w [Sklepie Microsoft dla Firm](https://www.microsoft.com/business-store) i kup wersję **licencji offline** aplikacji Portal firmy.  
2. Po nabyciu aplikacji wybierz ją ze strony **Spis**.  
3. Wybierz pozycję **Wszystkie urządzenia systemu Windows 10** w polu **Platforma**, a następnie odpowiednią wartość pola **Architektura** i pobierz aplikację. Plik licencji aplikacji nie jest wymagany dla tej aplikacji.
![Obraz systemu Windows 10 wszystkich urządzeń i szczegóły pakietu Architektura X86 do pobrania](./media/Win10CP-all-devices.png)
4. Pobierz wszystkie pakiety w obszarze „Wymagane struktury”. Jest to niezbędne dla architektury x86, x64 i ARM — co składa się na całkowitą liczbę 9 pakietów, jak pokazano poniżej.

![Obraz plików zależności do pobrania ](./media/Win10CP-dependent-files.png)
5. Przed przekazaniem aplikacji Portal firmy usługi Intune utwórz folder (np. C:&#92;Portal firmy) z pakietami umieszczonymi w następujący sposób:
  1. Umieść pakiet Portal firmy w folderze C:\Portal firmy. W tej lokalizacji utwórz również podfolder Zależności.  
  ![Obraz folderu Zależności zapisany w pliku APPXBUN](./media/Win10CP-Dependencies-save.png)
  2. Umieść dziewięć pakietów zależności w folderze Zależności.  
  Jeśli zależności nie będą wprowadzone w tym formacie, usługa Intune nie będzie mogła ich rozpoznać i przekazać podczas przekazywania pakietu, co spowoduje niepowodzenie przekazania z powodu następującego błędu.  
  ![W folderze aplikacji nie znaleziono zależności aplikacji systemu Windows dla tego instalatora oprogramowania. Możesz kontynuować tworzenie i przypisywanie tej aplikacji, ale nie będzie ona działać, dopóki nie zostaną dostarczone brakujące zależności aplikacji systemu Windows.](./media/Win10CP-error-message.png)
6. Wróć do usługi Intune, a następnie przekaż aplikację Portal firmy jako nową aplikację. Przypisz ją jako wymaganą aplikację dla żądanej grupy użytkowników docelowych.  

Aby uzyskać więcej informacji na temat sposobu obsługi zależności dla aplikacji uniwersalnych w usłudze Intune, zobacz temat [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Wdrażanie pliku appxbundle z zależnościami poprzez rozwiązanie MDM programu Microsoft Intune).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak zaktualizować aplikację Portal firmy na urządzeniach moich użytkowników, jeśli już mają zainstalowane starsze aplikacje ze sklepu?
Jeśli użytkownicy mają już zainstalowane aplikacje Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 ze sklepu, powinny one zostać automatycznie zaktualizowane do nowej wersji bez konieczności wykonania jakichkolwiek czynności przez Ciebie lub użytkowników. Jeśli aktualizacja nie miała miejsca, poproś użytkowników, aby sprawdzili, czy na swoich urządzeniach mają włączoną opcję automatycznych aktualizacji.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić moją załadowaną bezpośrednio aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?
Zalecana przez nas ścieżka migracji polega na usunięciu przypisania aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji przypisania na „Odinstaluj”. Po tej operacji aplikację Portal firmy dla systemu Windows 10 można przypisać przy użyciu dowolnej z powyższych opcji.  

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została przypisana bez rejestrowania jej za pomocą certyfikatu firmy Symantec, wykonaj instrukcje zawarte w poprzedniej sekcji dotyczącej bezpośredniego przypisywania za pomocą usługi Intune, aby ukończyć uaktualnianie.

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została podpisana i przypisana za pomocą certyfikatu firmy Symantec, wykonaj instrukcje zawarte w sekcji poniżej.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić podpisaną i ładowaną bezpośrednio aplikację Portal firmy dla systemu Windows Phone 8.1 lub aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?
Zalecana przez nas ścieżka migracji polega na usunięciu istniejącego przypisania aplikacji Portal firmy dla systemu Windows Phone 8.1 lub aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji przypisania na „Odinstaluj”. Po tej operacji aplikację Portal firmy dla systemu Windows 10 można przypisać w zwykły sposób.  

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
