---
title: Ładowanie bezpośrednie aplikacji systemów Windows i Windows Phone
titleSuffix: Microsoft Intune
description: Dowiedz się, jak podpisywać aplikacje biznesowe, aby umożliwić ich wdrażanie za pomocą usługi Intune.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 09/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7500000f8a34120e69c27ce01a6cfdb85f447abe
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414697"
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Podpisywanie aplikacji biznesowych w celu wdrażania ich na urządzeniach z systemem Windows za pomocą usługi Intune

Jako administrator usługi Intune możesz wdrażać uniwersalne aplikacje biznesowe (LOB) na urządzeniach z systemem Windows 8.1 Desktop lub Windows 10 Desktop & Mobile, w tym aplikację Portal firmy. Aby wdrożyć aplikacje .appx na urządzeniach z systemem Windows 8.1 Desktop lub Windows 10 Desktop & Mobile, można użyć certyfikatu podpisywania kodu z publicznego urzędu certyfikacji uznanego już za zaufany przez urządzenia z systemem Windows lub własnego urzędu certyfikacji.

 > [!NOTE]
 > Windows 8.1 Desktop wymaga, by zasady przedsiębiorstwa włączały ładowanie bezpośrednie lub użycie kluczy ładowania bezpośredniego (włączane automatycznie dla urządzeń przyłączonych do domeny). Więcej informacji znajduje się w artykule dotyczącym [ładowania bezpośredniego w systemie Windows 8](https://blogs.technet.microsoft.com/scd-odtsp/2012/09/27/windows-8-sideloading-requirements-from-technet/).

## <a name="windows-10-sideloading"></a>Ładowanie bezpośrednie systemu Windows 10

W systemie Windows 10 ładowanie bezpośrednie jest inne niż w starszych wersjach systemu Windows:

- Można odblokować urządzenie do ładowania bezpośredniego przy użyciu zasad przedsiębiorstwa. Usługa Intune udostępnia zasady konfiguracji urządzeń o nazwie „instalacja aplikacji zaufanej”. W przypadku urządzeń, które ufają już certyfikatowi używanemu do podpisywania aplikacji appx wystarczy ustawić tę opcję na <allow>.

- Nie są wymagane certyfikaty Symantec Phone ani klucze licencji ładowania bezpośredniego. Jednak jeśli lokalny urząd certyfikacji nie jest dostępny, może być konieczne uzyskanie certyfikatu podpisywania kodu z publicznego urzędu certyfikacji. Aby uzyskać więcej informacji, zobacz [Wprowadzenie do podpisywania kodu](https://docs.microsoft.com/windows/desktop/SecCrypto/cryptography-tools#introduction-to-code-signing).

### <a name="code-sign-your-app"></a>Podpisywanie aplikacji kodem

Pierwszym krokiem jest podpisanie kodem pakietu appx. Aby uzyskać szczegółowe informacje, zobacz [Podpisywanie pakietu aplikacji przy użyciu narzędzia SignTool](https://docs.microsoft.com/windows/uwp/packaging/sign-app-package-using-signtool).

### <a name="upload-your-app"></a>Przekazywanie aplikacji

Następnie musisz przekazać podpisany plik appx. Aby uzyskać szczegółowe informacje, zobacz [Dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune](lob-apps-windows.md).

W przypadku wdrażania aplikacji zależnie od potrzeb dla użytkowników lub urządzeń nie jest potrzebna aplikacja Portal firmy w usłudze Intune. Jeśli jednak aplikacja zostanie wdrożona jako dostępna dla użytkowników, mogą oni użyć aplikacji Portal firmy z publicznego sklepu Microsoft Store, użyć aplikacji Portal firmy z prywatnego sklepu Microsoft Store dla Firm lub trzeba będzie podpisać i ręcznie wdrożyć aplikację Portal firmy w usłudze Intune.

### <a name="upload-the-code-signing-certificate"></a>Przekazywanie certyfikatu podpisywania kodu

Jeśli urządzenie z systemem Windows 10 nie ufa jeszcze urzędowi certyfikacji, po podpisaniu pakietu appx i przekazaniu go do usługi Intune trzeba przekazać certyfikat podpisywania kodu do portalu usługi Intune:

1. Kliknij pozycję Aplikacje klienckie
2. Kliknij pozycję Certyfikaty przedsiębiorstwa systemu Windows
3. W obszarze Certyfikat podpisywania kodu wybierz pozycję Wybierz plik
4. Wybierz plik .cer i kliknij przycisk Przekaż

Teraz każde urządzenie z systemem Windows 10 Desktop & Mobile z wdrożeniem appx przez usługę Intune automatycznie pobierze odpowiedni certyfikat przedsiębiorstwa i aplikacja będzie mogła zostać uruchomiona po zakończeniu instalacji.

Usługa Intune wdraża tylko najnowszy przekazany plik. cer. Jeśli istnieje wiele plików appx utworzonych przez różnych deweloperów, które nie są skojarzone z organizacją, trzeba będzie zażądać od nich dostarczenia niepodpisanych plików appx do podpisania za pomocą certyfikatu organizacji lub przekazać im certyfikat podpisywania kodu używany przez organizację.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Jak odnowić certyfikat podpisywania kodu przedsiębiorstwa firmy Symantec

Certyfikat używany do wdrażania aplikacji mobilnych systemu Windows Phone 8.1 został wycofany 28 lutego 2019 r. i nie jest już dostępny do odnawiania przez firmę Symantec. W przypadku wdrażania do systemu Windows 10 Mobile można nadal używać certyfikatów podpisywania kodu usługi Symantec Desktop Enterprise, postępując zgodnie z instrukcjami [ładowania bezpośredniego systemu Windows 10](app-sideload-windows.md#windows-10-sideloading).

## <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Jak zainstalować zaktualizowany certyfikat dla aplikacji biznesowych

Windows Phone 8,1

Usługa Intune nie może już wdrażać aplikacji biznesowych dla tej platformy po wygaśnięciu istniejącego certyfikatu podpisywania kodu usługi Symantec Mobile Enterprise. Nadal będzie można bezpośrednio ładować niepodpisane pliki XAP/APPX przy użyciu karty SD lub przez pobranie pliku na urządzenie. Aby uzyskać więcej informacji, zobacz temat [How to install XAP files on Windows Phone](https://answers.microsoft.com/en-us/mobiledevices/forum/mdlumia-mdapps/how-to-install-xap-file-in-windows-phone-8/da09ee72-51ae-407c-9b85-bc148df89280) (Jak zainstalować pliki XAP na urządzeniu z systemem Windows Phone).

Windows 8.1 Desktop/Windows 10 Desktop & Mobile

Jeśli upłynął okres ważności certyfikatu, pliki appx mogą przestać być uruchamiane. Należy uzyskać nowy plik .cer i postępować zgodnie z instrukcjami w celu podpisania kodem każdego wdrożonego pliku appx i ponownego przekazania wszystkich plików appx oraz zaktualizowanego pliku .cer do sekcji Certyfikaty przedsiębiorstwa systemu Windows w portalu usługi Intune.

## <a name="manually-deploy-windows-10-company-portal-app"></a>Ręczne wdrażanie aplikacji Portal firmy dla systemu Windows 10

Jeśli nie chcesz zapewnić dostępu do sklepu Microsoft Store, aplikację Portal firmy dla systemu Windows 10 można wdrożyć ręcznie bezpośrednio z poziomu usługi Intune, nawet jeśli usługa Intune nie została zintegrowana ze sklepem Microsoft Store dla Firm. Alternatywnie, jeśli doszło do integracji,możesz wdrożyć aplikację Portal firmy za pomocą [aplikacji wdrażania przy użyciu MSFB](store-apps-windows.md).

 > [!NOTE]
 > Ta opcja wymaga ręcznego wdrażania aktualizacji po każdym wydaniu nowej aktualizacji aplikacji.

1. Zaloguj się do swojego konta w [sklepie Microsoft Store dla Firm](https://www.microsoft.com/business-store) i kup wersję **licencji offline** aplikacji Portal firmy.  
2. Po nabyciu aplikacji wybierz ją ze strony **Spis**.  
3. Wybierz pozycję **Wszystkie urządzenia systemu Windows 10** w polu **Platforma**, a następnie odpowiednią wartość pola **Architektura** i pobierz aplikację. Plik licencji aplikacji nie jest wymagany dla tej aplikacji.
   ![Obraz przedstawiający szczegóły pakietu systemu Windows 10 X86 do pobrania](./media/app-sideload-windows/Win10CP-all-devices.png)
4. Pobierz wszystkie pakiety w obszarze „Wymagane struktury”. Jest to niezbędne dla architektury x86, x64 i ARM — co składa się na całkowitą liczbę 9 pakietów, jak pokazano poniżej.

   ![Obraz plików zależności do pobrania ](./media/app-sideload-windows/Win10CP-dependent-files.png)
5. Przed przekazaniem aplikacji Portal firmy usługi Intune utwórz folder (np. C:&#92;Portal firmy) z pakietami umieszczonymi w następujący sposób:
   1. Umieść pakiet Portal firmy w folderze C:\Portal firmy. W tej lokalizacji utwórz również podfolder Zależności.  
      ![Obraz folderu Zależności zapisany w pliku APPXBUN](./media/app-sideload-windows/Win10CP-Dependencies-save.png)
   2. Umieść dziewięć pakietów zależności w folderze Zależności.  
      Jeśli zależności nie będą wprowadzone w tym formacie, usługa Intune nie będzie mogła ich rozpoznać i przekazać podczas przekazywania pakietu, co spowoduje niepowodzenie przekazania z powodu następującego błędu.  
      ![Komunikat o błędzie — należy określić zależności aplikacji systemu Windows.](./media/app-sideload-windows/Win10CP-error-message.png)
6. Wróć do usługi Intune, a następnie przekaż aplikację Portal firmy jako nową aplikację. Wdróż ją jako wymaganą aplikację dla żądanej grupy użytkowników docelowych.  

Aby uzyskać więcej informacji na temat sposobu obsługi zależności dla aplikacji uniwersalnych w usłudze Intune, zobacz temat [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Wdrażanie pliku appxbundle z zależnościami poprzez rozwiązanie MDM programu Microsoft Intune).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak zaktualizować aplikację Portal firmy na urządzeniach moich użytkowników, jeśli już mają zainstalowane starsze aplikacje ze sklepu?

Jeśli użytkownicy mają już zainstalowane aplikacje Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 ze sklepu, powinny one zostać automatycznie zaktualizowane do nowej wersji bez konieczności wykonania jakichkolwiek czynności przez Ciebie lub użytkowników. Jeśli aktualizacja nie miała miejsca, poproś użytkowników, aby sprawdzili, czy na swoich urządzeniach mają włączoną opcję automatycznych aktualizacji.

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić moją załadowaną bezpośrednio aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?

Zalecana przez nas ścieżka migracji polega na usunięciu wdrożenia aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji wdrożenia na „Odinstaluj”. Po tej operacji aplikację Portal firmy systemu Windows 10 można wdrożyć przy użyciu dowolnej z powyższych opcji.  

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy dla systemu Windows 8.1 została wdrożona bez rejestrowania jej za pomocą certyfikatu firmy Symantec, wykonaj instrukcje zawarte w sekcji Wdróż bezpośrednio za pomocą sekcji usługi Intune powyżej, aby ukończyć uaktualnianie.

Jeśli aplikacja ma zostać załadowana bezpośrednio, a aplikacja Portal firmy systemu Windows 8.1 została podpisana i wdrożona za pomocą certyfikatu firmy Symantec, wykonaj instrukcje zawarte w sekcji poniżej.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak uaktualnić podpisaną i ładowaną bezpośrednio aplikację Portal firmy dla systemu Windows Phone 8.1 lub aplikację Portal firmy dla systemu Windows 8.1 do aplikacji Portal firmy dla systemu Windows 10?

Zalecana przez nas ścieżka migracji polega na usunięciu istniejącego wdrożenia aplikacji Portal firmy dla systemu Windows Phone 8.1 lub aplikacji Portal firmy dla systemu Windows 8.1 przez ustawienie akcji wdrożenia na „Odinstaluj”. Po tej operacji aplikację Portal firmy dla systemu Windows 10 można wdrożyć w zwykły sposób.  

W przeciwnym razie aplikacja Portal firmy dla systemu Windows 10 musi zostać odpowiednio aktualizowana i podpisana w celu zapewnienia, że ścieżka uaktualnienia jest zachowana.  

Jeśli aplikacja Portal firmy dla systemu Windows 10 została podpisana i wdrożona w ten sposób, konieczne będzie powtórzenie tego procesu dla każdej nowej aktualizacji aplikacji, gdy będzie ona dostępna w sklepie. Aplikacja nie będzie automatycznie aktualizowana podczas aktualizacji sklepu.  

Poniżej przedstawiono procedurę rejestrowania i wdrażania aplikacji w ten sposób:

1. Pobierz skrypt podpisywania aplikacji Portal firmy systemu Windows 10 dla usługi Microsoft Intune ze strony [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Ten skrypt wymaga wcześniejszego zainstalowania pakietu Windows SDK dla systemu Windows 10 na komputerze-hoście. Aby pobrać zestaw Windows SDK dla systemu Windows 10, odwiedź stronę [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Pobierz aplikację Portal firmy dla systemu Windows 10 ze Sklepu Microsoft dla Firm zgodnie z powyższym opisem.  
3. Uruchom skrypt z parametrami wejściowymi wyszczególnionymi w nagłówku skryptu, aby podpisać aplikację Portal firmy dla systemu Windows 10 (wyodrębnioną poniżej). Zależności nie trzeba przekazać do skryptu. Są one wymagane tylko w przypadku, gdy aplikacja jest przekazywana do konsoli administracyjnej usługi Intune.

|       Parametr       |                                                                    Opis                                                                    |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                             Ścieżka pliku źródłowego appxbundle.                                              |
| OutputWin10AppxBundle |                                                  Ścieżka wyjściowa dla podpisanego pliku appxbundle.                                                  |
|       Win81Appx       |                          Ścieżka pliku aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1 (pliku APPX).                           |
|      PfxFilePath      |                                   Ścieżka pliku z certyfikatem podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych (pliku PFX).                                    |
|      PfxPassword      |                                     Hasło certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych.                                      |
|      PublisherId      |      Identyfikator wydawcy przedsiębiorstwa. Jeśli go nie ma, używane jest pole Podmiot certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych.       |
|        SdkPath        | Ścieżka do głównego folderu pakietu Windows SDK dla systemu Windows 10. Ten argument jest opcjonalny i domyślnie ustawiony na wartość ${env:ProgramFiles(x86)}\Windows Kits\10 |

Po zakończeniu działania skryptu zostanie wygenerowana podpisana wersja aplikacji Portal firmy dla systemu Windows 10. Następnie można wdrożyć podpisaną wersję aplikacji jako aplikację biznesową za pomocą usługi Intune, która spowoduje uaktualnienie aktualnie wdrożonych wersji do tej nowej aplikacji.  
