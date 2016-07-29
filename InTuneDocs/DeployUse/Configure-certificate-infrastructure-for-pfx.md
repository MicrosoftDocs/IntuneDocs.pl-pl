---
title: "Konfigurowanie infrastruktury certyfikatów dla profilu PFX | Microsoft Intune"
description: "Tworzenie i wdrażanie profilów certyfikatów PFX."
keywords: 
author: nbigman
manager: angrobe
ms.date: 05/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 2f45c54d18156469488c77600626ea359374a588



---
# Konfigurowanie infrastruktury certyfikatu
W tym temacie opisano elementy potrzebne do utworzenia i wdrożenia profilów certyfikatów PFX.

Aby przeprowadzać uwierzytelnianie oparte na certyfikatach w organizacji, należy zastosować urząd certyfikacji przedsiębiorstwa.

Do korzystania z profilów certyfikatu PFX w połączeniu z urzędem certyfikacji przedsiębiorstwa są wymagane również następujące elementy:

-   Komputer, który może komunikować się z urzędem certyfikacji, lub komputer urzędu certyfikacji.

 -  Łącznik certyfikatów usługi Intune uruchamiany na komputerze, który może komunikować się z urzędem certyfikacji.

## Opis infrastruktury lokalnej


-    **Domena usługi Active Directory:** wszystkie serwery wymienione w tej części (z wyjątkiem serwera proxy aplikacji sieci Web) muszą należeć do Twojej domeny usługi Active Directory.

-  **Urząd certyfikacji** (CA): wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. Instrukcje dotyczące sposobu konfigurowania urzędu certyfikacji znajdują się w temacie [Instalacja urzędu certyfikacji](http://technet.microsoft.com/library/jj125375.aspx).
    Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2, należy najpierw [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).

 -  **Komputer, który może komunikować się z urzędem certyfikacji**: alternatywnie można użyć komputera urzędu certyfikacji.
-  **Łącznik certyfikatów usługi Microsoft Intune**: używając konsoli administracyjnej usługi Intune, możesz pobrać instalatora **łącznika certyfikatów** (**ndesconnectorssetup.exe**). Następnie możesz uruchomić plik **ndesconnectorssetup.exe** na komputerze, na którym chcesz zainstalować łącznik certyfikatów. W przypadku profilów certyfikatów PFX zainstaluj łącznik certyfikatów na komputerze, który komunikuje się z urzędem certyfikacji.
-  **Serwer proxy aplikacji sieci Web** (opcjonalnie): jako serwera proxy aplikacji sieci Web (WAP) można użyć serwera z systemem Windows Server 2012 R2 lub nowszym. Ta konfiguracja:
    -  Umożliwia urządzeniom otrzymywanie certyfikatów przy użyciu połączenia internetowego.
    -  Jest zalecana ze względów bezpieczeństwa w przypadku używania połączenia internetowego do pobierania i odnawiania certyfikatów przez urządzenia.

 > [!NOTE]           
> -    Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych. Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Ponadto serwer, który hostuje serwer proxy aplikacji sieci Web, musi mieć certyfikat SSL odpowiadający nazwie opublikowanej dla klientów zewnętrznych oraz uznawać certyfikat SSL używany na serwerze usługi NDES za zaufany. Te certyfikaty umożliwiają serwerowi proxy aplikacji sieci Web zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z serwerem usługi NDES.
    Informacje na temat certyfikatów dla serwera proxy aplikacji sieci Web zawiera sekcja **Planowanie certyfikatów** w temacie [Planowanie publikowania aplikacji przy użyciu serwera proxy aplikacji sieci Web](https://technet.microsoft.com/library/dn383650.aspx). Ogólne informacje na temat serwerów proxy aplikacji sieci Web znajdują się w temacie [Praca z serwerem proxy aplikacji sieci Web](http://technet.microsoft.com/library/dn584113.aspx).|


### Certyfikaty i szablony

|Obiekt|Szczegóły|
|----------|-----------|
|**Szablon certyfikatu**|Ten szablon należy skonfigurować na serwerze wystawiającego urzędu certyfikacji.|
|**Certyfikat zaufanego głównego urzędu certyfikacji**|Ten certyfikat należy wyeksportować w pliku w formacie **.cer** z urzędu wystawiającego certyfikaty lub dowolnego urządzenia traktującego urząd wystawiający certyfikaty jako zaufany, a następnie wdrożyć go na urządzeniach, korzystając z profilu certyfikatu zaufanego urzędu certyfikacji.<br /><br />Należy użyć jednego certyfikatu zaufanego głównego urzędu certyfikacji dla każdej platformy systemu operacyjnego i powiązać te certyfikaty z poszczególnymi utworzonymi profilami zaufanych certyfikatów głównych.<br /><br />W razie potrzeby można użyć dodatkowych certyfikatów zaufanego głównego urzędu certyfikacji. Można na przykład zrobić to, aby urząd certyfikacji podpisujący certyfikaty uwierzytelniania serwera dla punktów dostępowych Wi-Fi był traktowany jako zaufany.|


## Konfigurowanie infrastruktury
Skonfigurowanie profili certyfikatów będzie możliwe po wykonaniu poniższych zadań wymagających znajomości systemu Windows Serwer 2012 R2 oraz usług certyfikatów Active Directory (ADCS):

**Zadanie 1** — Konfigurowanie szablonów certyfikatów w urzędzie certyfikacji **Zadanie 2** — Włączanie, instalowanie i konfigurowanie łącznika certyfikatów usługi Intune

### Zadanie 1 — Konfigurowanie szablonów certyfikatu w urzędzie certyfikacji
To zadanie obejmuje publikowanie szablonu certyfikatu

##### Aby skonfigurować urząd certyfikacji

1.  Za pomocą przystawki Szablony certyfikatów dla wystawiającego urzędu certyfikacji utwórz nowy szablon niestandardowy lub skopiuj istniejący szablon i zmodyfikuj go (na przykład szablon użytkownika), aby używać go z profilem PFX.

    Szablon wymaga następującej konfiguracji:

    -   Określ przyjazną **nazwę wyświetlaną szablonu** .

    -   Na karcie **Nazwa podmiotu** zaznacz opcję **Dostarcz w żądaniu**. (Zabezpieczenia są wymuszane przez moduł zasad usługi Intune dla usługi NDES).

    -   Na karcie **Rozszerzenia** upewnij się, że **Opis zasad aplikacji** obejmuje pozycję **Uwierzytelnianie klienta**.

        > [!IMPORTANT]
        > W przypadku szablonów certyfikatów dla systemu iOS i Mac OS X na karcie **Rozszerzenia** edytuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.


3.  Sprawdź **Okres ważności** na karcie **Ogólne** szablonu. Domyślnie usługa Intune używa wartości skonfigurowanej w szablonie. Można jednak skonfigurować urząd certyfikacji tak, aby umożliwiał żądającemu określenie innej wartości, którą można następnie ustawić przy użyciu konsoli administratora w usłudze Intune. Jeśli chcesz, aby zawsze była używana wartość określona w szablonie, pomiń pozostałe czynności w tym kroku.

    > [!IMPORTANT]
    > W przypadku platform iOS i Mac OS X wartość ustawiona w szablonie jest używana zawsze, niezależnie od innych ustawień.

    W celu skonfigurowania urzędu certyfikacji tak, aby umożliwiał żądającemu określenie okresu ważności, uruchom następujące polecenia w urzędzie certyfikacji:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Użyj przystawki Urząd certyfikacji dla wystawiającego urzędu certyfikacji, aby opublikować szablon certyfikatu.

    1.  Zaznacz węzeł **Szablony certyfikatów**, kliknij pozycję **Akcja**-&gt; **Nowy** &gt; **Szablon certyfikatu do wystawienia**, a następnie wybierz szablon utworzony w kroku 2.

    2.  Sprawdź, czy certyfikat został opublikowany, wyświetlając go w folderze **Szablony certyfikatów** .

5.  Na komputerze urzędu certyfikacji sprawdź, czy komputer hostujący łącznik certyfikatów usługi Intune ma uprawnienia do rejestracji, dzięki czemu może uzyskiwać dostęp do szablonu używanego podczas tworzenia profilu PFX. Ustaw to uprawnienie na karcie **Zabezpieczenia** właściwości komputera urzędu certyfikacji.

### Zadanie 2 — Włączanie, instalacja i konfiguracja łącznika certyfikatów dla usługi Intune
To zadanie obejmuje:

Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów

##### Aby włączyć obsługę łącznika certyfikatów

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com) i kliknij pozycję **Administracja** &gt; **Łącznik certyfikatów**.

2.  Kliknij pozycję **Skonfiguruj lokalny łącznik certyfikatów**.

3.  Kliknij pozycję **Włącz łącznik certyfikatów**, a następnie kliknij przycisk **OK**.

##### Aby pobrać, zainstalować i skonfigurować łącznik certyfikatów

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com), a następnie kliknij pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Łącznik certyfikatów** &gt; **Pobierz łącznik certyfikatów**.

2.  Po zakończeniu uruchom pobrany program instalacyjny (**ndesconnectorssetup.exe**):

  Uruchom instalatora na komputerze, który może połączyć się z urzędem certyfikacji. Wybierz opcję dystrybucji certyfikatu PFX i kliknij pozycję Zainstaluj. Po ukończeniu instalacji utwórz profil certyfikatu zgodnie z opisem w sekcji [Konfigurowanie profilów certyfikatów](configure-intune-certificate-profiles.md).

   <!-- Not sure about step 3 below -->

3.  Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, kliknij pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany w zadaniu 3.

    Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune** . Chociaż wybrany certyfikat nie jest wyświetlany, kliknij przycisk **Dalej** , aby wyświetlić właściwości certyfikatu. Kliknij przycisk **Dalej**, a następnie kliknij przycisk **Zainstaluj**.

4.  Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

    > [!TIP]
    > Jeśli kreator zostanie zamknięty przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz uruchomić go za pomocą następującego polecenia:
    >
    > **&lt;ścieżka_instalacji&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  W interfejsie użytkownika **łącznika certyfikatów** :

    Kliknij pozycję **Zaloguj** i wprowadź swoje poświadczenia administratora usługi Intune lub poświadczenia administratora dzierżawy z uprawnieniami administratora globalnego.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    Wybierz kartę **Zaawansowane** , wprowadź poświadczenia konta, do którego przypisano uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** w urzędzie wystawiającym certyfikaty, a następnie kliknij pozycję **Zastosuj**.

    Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.

6.  Otwórz wiersz polecenia, wpisz **services.msc**, a następnie naciśnij klawisz **Enter**, kliknij prawym przyciskiem myszy pozycję **Usługa łącznika usługi Intune** i kliknij polecenie **Uruchom ponownie**.

Aby sprawdzić, czy usługa jest uruchomiona, otwórz przeglądarkę i wprowadź następujący adres URL, co powinno spowodować zwrócenie błędu **403** :

**http://&lt;nazwa_FQDN_serwera_usługi_NDES&gt;/certsrv/mscep/mscep.dll**

### Następne kroki
Teraz można skonfigurować profile certyfikatów zgodnie z opisem w sekcji [Konfigurowanie profilów certyfikatów](Configure-Intune-certificate-profiles.md).



<!--HONumber=Jul16_HO4-->


