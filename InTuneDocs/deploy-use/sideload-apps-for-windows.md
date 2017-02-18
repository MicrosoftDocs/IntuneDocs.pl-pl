---
title: "Ładowanie bezpośrednie aplikacji dla systemów Windows i Windows Phone | Microsoft Docs"
description: "Dowiedz się, jak podpisywać aplikacje biznesowe, aby umożliwić ich wdrażanie za pomocą usługi Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2e8220f850e3b38a24aa4c48bcc3a59088251c24


---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Podpisywanie aplikacji biznesowych w celu wdrażania ich na urządzeniach z systemem Windows za pomocą usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Jako administrator usługi Intune możesz wdrażać aplikacje biznesowe, w tym aplikację Portal firmy, na urządzeniach z systemami Windows i Windows 10 Mobile. Aby wdrażać aplikacje w formacie APPX lub XAP na urządzeniach z systemami Windows 10 i Windows 10 Mobile lub aby wdrażać dowolne aplikacje biznesowe na urządzeniach z systemami Windows 8.1 i Windows Phone 8.1, musisz uzyskać **certyfikat podpisywania kodu Symantec Enterprise Mobile**. Tylko certyfikat firmy Symantec jest zaufany dla tych aplikacji na urządzeniach z tymi wersjami systemu Windows. W przypadku aplikacji dla systemu Windows 10 i aplikacji „uniwersalnych” możesz używać własnego urzędu certyfikacji. Ten certyfikat jest wymagany do:

-   podpisywania aplikacji Portal firmy na potrzeby wdrażania na komputerach z systemem Windows oraz urządzeń z systemami Windows 10 Mobile i Windows Phone,

-   podpisywania aplikacji biznesowych firmy w celu umożliwienia usłudze Intune wdrożenia ich na urządzeniach z systemem Windows.

Poniższe instrukcje ułatwią uzyskanie wymaganego certyfikatu i podpisanie aplikacji. Musisz mieć konto Centrum deweloperów systemu Windows Phone oraz kupić certyfikat firmy Symantec.


1. **Dołącz do Centrum deweloperów systemu Windows Phone**<br>
   Dołącz do [Centrum deweloperów systemu Windows Phone](http://go.microsoft.com/fwlink/?LinkId=268442) , podając dane konta firmowego podczas logowania się w celu zakupienia konta firmy. Ta prośba musi zostać autoryzowana przez specjalistę firmy, zanim otrzymasz certyfikat podpisywania kodu.

2. **Uzyskaj firmowy certyfikat firmy Symantec**<br>
  Posługując się swoim identyfikatorem firmy Symantec, kup certyfikat w [witrynie firmy Symantec](http://go.microsoft.com/fwlink/?LinkId=268441) . Po zakupie certyfikatu osoba zatwierdzająca w firmie wyznaczona w danych konta Centrum deweloperów systemu Windows Phone otrzyma wiadomość e-mail z prośbą o zatwierdzenie żądania certyfikatu. Więcej informacji o wymaganiu certyfikatu firmy Symantec znajduje się w sekcji [Dlaczego w systemie Windows Phone jest wymagany certyfikat firmy Symantec?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) często zadawanych pytań dotyczących rejestrowania urządzeń z systemem Windows.

3.  **Zaimportuj certyfikaty**<br>
    Po zatwierdzeniu żądania otrzymasz wiadomość e-mail z instrukcjami dotyczącymi importowania certyfikatów. Postępuj zgodnie z instrukcjami w wiadomości e-mail, aby zaimportować certyfikaty.

4.  **Zweryfikuj zaimportowane certyfikaty**<br>
    Aby zweryfikować, że certyfikaty zostały zaimportowane prawidłowo, przejdź do przystawki **Certyfikaty**, kliknij prawym przyciskiem myszy pozycję **Certyfikaty** i wybierz polecenie **Znajdź certyfikaty**. W polu **Zawiera** wprowadź „Symantec” i kliknij przycisk **Znajdź teraz**. Zaimportowane certyfikaty powinny być wyświetlane w wynikach.

    ![Znajdź certyfikat firmy Symantec](./media/wit.gif)

5. **Wyeksportuj certyfikat podpisywania**<br>
    Po sprawdzeniu, czy certyfikaty znajdują się na liście, możesz wyeksportować plik PFX w celu podpisania portalu firmy. Wybierz certyfikat firmy Symantec, dla którego w kolumnie **Zamierzony cel** znajduje się wartość „podpisywanie kodu”. Kliknij certyfikat podpisywania kodu prawym przyciskiem myszy i wybierz polecenie **Eksportuj**.

    ![Wyeksportuj certyfikat podpisywania](./media/wit-walk-cert2.gif)

    W **Kreatorze eksportu certyfikatów**wybierz opcję **Tak, eksportuj klucz prywatny** , a następnie kliknij przycisk **Dalej**. Wybierz pozycję **Wymiana informacji osobistych — PKCS #12 (PFX)** i zaznacz opcję **Jeśli jest to możliwe, dołącz wszystkie certyfikaty do ścieżki certyfikacji**. Ukończ pracę kreatora. Więcej informacji znajduje się w temacie [Eksportowanie certyfikatu z kluczem prywatnym](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Przekaż aplikację do usługi Intune**<br>
    Aby udostępnić aplikację użytkownikom końcowym, przekaż podpisany plik aplikacji oraz certyfikat podpisywania kodu.

    1.  W [konsoli administracyjnej usługi Intune](http://manage.microsoft.com) kliknij pozycję **Administracja** &gt; **Windows Phone**.

    2.  Kliknij pozycję **Przekaż podpisany plik aplikacji** i zaloguj się przy użyciu swojego identyfikatora administratora usługi Intune.

    3.  Dodaj wyeksportowany plik certyfikatu (PFX) w polu **Certyfikat podpisywania kodu** i utwórz hasło dla certyfikatu.

    4.  Ukończ pracę kreatora.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Przykład: pobieranie, rejestrowanie i wdrażanie aplikacji Portal firmy dla urządzeń z systemem Windows

Aplikację Portal firmy można wdrożyć na urządzeniach z systemem Windows, w tym z systemem Windows Phone i Windows 10 Mobile, przy użyciu usługi Intune, zamiast instalować ją ze Sklepu Windows. Musisz pobrać aplikację Portal firmy i podpisać ją przy użyciu swojego certyfikatu.  Jest to konieczne tylko wtedy, gdy użytkownicy nie będą korzystać ze sklepu firmowego, a aplikacja Portal firmy ma zostać wdrożona na urządzeniach z systemem Windows Phone 8.1.


1.  **Pobierz aplikację Portal firmy**

    Aby pobrać aplikację Portal firmy przy użyciu usługi Intune, możesz pobrać [aplikację Portal firmy w usłudze Microsoft Intune dla systemu Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) z Centrum pobierania i uruchomić plik samowyodrębniający (EXE). Ten plik zawiera dwa pliki:

    -   CompanyPortal.appx — aplikacja instalacyjna Portal firmy dla systemu Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 — skrypt programu PowerShell służący do podpisywania pliku aplikacji Portal firmy na potrzeby wdrożenia go na urządzeniach z systemem Windows Phone 8.1

    Możesz również pobrać aplikację Portal firmy systemu Windows Phone 8.1 (pakiet licencjonowany w trybie offline) lub Portal firmy systemu Windows 10 ze [Sklepu Windows dla firm](http://businessstore.microsoft.com/). Aby korzystać z aplikacji Portal firmy w trybie offline, należy ją uzyskać, pobierając ją z licencją trybu offline i odpowiednim pakietem offline. Elementy list dotyczących platform Windows 8 i Windows Phone 8 odpowiadają elementom systemu 8.1. Aby uzyskać szczegółowe informacje dotyczące wykonania tej czynności za pomocą usługi Intune, zobacz [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).

2.  **Pobierz zestaw Windows Phone SDK** Pobierz zestaw Windows Phone SDK 8.0 (http://go.microsoft.com/fwlink/?LinkId=615570) i zainstaluj go na komputerze. Zestaw SDK jest potrzebny do generowania tokenu rejestracji aplikacji.

3.  **Wygeneruj plik AETX** Wygeneruj plik tokenu rejestracji aplikacji (AETX) z pliku PFX firmy Symantec za pomocą narzędzia AETGenerator.exe wchodzącego w skład zestawu Windows Phone SDK 8.0. Aby uzyskać instrukcje dotyczące sposobu tworzenia pliku AETX, zobacz [Jak wygenerować token rejestracji aplikacji dla systemu Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)

4.  **Pobierz zestaw Windows SDK dla systemu Windows 8.1** Pobierz i zainstaluj zestaw [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525). Zwróć uwagę, że skrypt programu PowerShell dołączony do aplikacji Portal firmy używa domyślnej lokalizacji instalacji: `${env:ProgramFiles(x86)}\Windows Kits\8.1`. W przypadku instalacji w innym miejscu należy dołączyć lokalizację w parametrze polecenia cmdlet.

5.  **Podpisz kod aplikacji przy użyciu programu PowerShell** Jako administrator otwórz program **Windows PowerShell** na komputerze hosta z zainstalowanym pakietem Windows SDK i certyfikatem podpisywania kodu przedsiębiorstwa firmy Symantec, przejdź do pliku Sign-WinPhoneCompanyPortal.ps1, a następnie uruchom skrypt.

    **Przykład 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    W tym przykładzie skrypt podpisuje plik CompanyPortal.appx w lokalizacji C:\temp\ i tworzy plik CompanyPortalEnterpriseSigned.appx. Używa hasła 1234 do pliku PFX i odczytuje identyfikator wydawcy z pliku PFX. Odczytuje również identyfikator przedsiębiorstwa z pliku cert.aetx.

    **Przykład 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    W tym przykładzie skrypt podpisuje plik CompanyPortal.appx w lokalizacji C:\temp\ i tworzy plik CompanyPortalEnterpriseSigned.appx. Używa hasła 1234 do pliku PFX i określonego identyfikatora wydawcy.

    **Parametry:**

    -   `-InputAppx` — ścieżka lokalna do pliku CompanyPortal.appx ujęta w apostrofy. Na przykład 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` — ścieżka lokalna i nazwa pliku podpisanej aplikacji Portal firmy ujęta w apostrofy. Na przykład 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` — ścieżka lokalna i nazwa pliku dla wyeksportowanego pliku PFX certyfikatu firmy Symantec. Na przykład 'C:\signing\cert.pfx'

    -   `-PfxPassword` — hasło używane do podpisywania pliku PFX ujęte w apostrofy. Na przykład '1234'

    -   `-AetxPath` — ścieżka lokalna do pliku AETX, który służy do odczytywania identyfikatora przedsiębiorstwa, jeśli argument EnterpriseId nie został zdefiniowany. Należy podać ten argument albo argument EnterpriseId. Na przykład 'C:\signing\cert.aetx'

    -   `-PublisherId` — identyfikator wydawcy przedsiębiorstwa. Jeśli go nie ma, używane jest pole Podmiot certyfikatu podpisywania kodu firmy Symantec dla firmowych urządzeń przenośnych. Na przykład 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Tst 1'

    -   `-SdkPath` — ścieżka do głównego folderu zestawu Windows SDK dla systemu Windows 8.1. Ten argument jest opcjonalny i domyślnie ustawiany na wartość ${env:ProgramFiles(x86)}\Windows Kits\8.1.

    -   `-EnterpriseId` — identyfikator przedsiębiorstwa. Należy podać ten argument lub argument AetxPath. Jeśli ten argument nie zostanie podany, identyfikator przedsiębiorstwa zostanie odczytany z pliku AETX. Na przykład 1000000001

6.  Wdróż aplikację Portal firmy dla systemu Windows Phone 8.1 (SSP.appx). Aby uzyskać wskazówki, zobacz temat [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Jak odnowić certyfikat podpisywania kodu przedsiębiorstwa firmy Symantec

Okresowo należy odnawiać certyfikat firmy Symantec służący do wdrażania aplikacji mobilnych dla systemów Windows i Windows Phone.

1.  Poszukaj wiadomości e-mail dotyczącej odnowienia certyfikatu, która została wysłana przez firmę Symantec około 14 dni przed jego wygaśnięciem. Zawiera ona instrukcje od firmy Symantec w zakresie odnowienia certyfikatu przedsiębiorstwa.

    Aby uzyskać dodatkowe informacje o certyfikatach firmy Symantec, odwiedź witrynę [www.symantec.com](http://www.symantec.com) lub zadzwoń pod numer 1-877-438-8776 lub 1-650-426-3400.

2.  Przejdź do witryny internetowej (na przykład: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) i zaloguj się za pomocą identyfikatora wydawcy firmy Symantec oraz adresu e-mail skojarzonego z certyfikatem. Pamiętaj o tym, aby rozpocząć procedurę odnowienia na tym samym komputerze, na którym będzie pobierany certyfikat.

3.  Po zatwierdzeniu odnowienia i uregulowaniu płatności pobierz certyfikat.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Jak zainstalować zaktualizowany certyfikat dla aplikacji biznesowych

1.  Podpisz najnowszą wersję aplikacji biznesowej.

2.  Otwórz konsolę administracyjną usługi Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)), przejdź do pozycji **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**, a następnie kliknij pozycję **Przekaż podpisaną aplikację**.

3.  Przekaż nowo podpisaną aplikację Portal firmy. Konieczny jest nowo podpisany plik SSP.xap oraz nowy plik .PFX otrzymany od firmy Symantec lub token rejestracji aplikacji utworzony za pomocą tego nowego pliku .PFX.

4.  Po zakończeniu przekazywania usuń starą wersję aplikacji Portal firmy w obszarze roboczym **Oprogramowanie**.

5.  Podpisz wszystkie nowe i zaktualizowane aplikacje biznesowe przedsiębiorstwa przy użyciu nowego certyfikatu. Istniejące aplikacje nie muszą być ponownie podpisane i wdrożone.



<!--HONumber=Dec16_HO2-->


