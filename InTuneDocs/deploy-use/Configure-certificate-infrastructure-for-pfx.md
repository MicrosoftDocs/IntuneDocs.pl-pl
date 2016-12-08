---
title: "Konfigurowanie infrastruktury certyfikatów dla profilu PFX | Microsoft Intune"
description: "Tworzenie i wdrażanie profilów certyfikatów PFX."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7d1f37a2ba2e634fb75058d33eaaccf3aa5845b0
ms.openlocfilehash: 8fc1cc718fd0edae8b8ec4a0a8dc25487eafda2b



---
# <a name="configure-certificate-infrastructure"></a>Konfigurowanie infrastruktury certyfikatu
W tym temacie opisano elementy potrzebne do utworzenia i wdrożenia profilów certyfikatów PFX.

Aby przeprowadzać uwierzytelnianie oparte na certyfikatach w organizacji, należy zastosować urząd certyfikacji przedsiębiorstwa.

Do korzystania z profilów certyfikatu PFX w połączeniu z urzędem certyfikacji przedsiębiorstwa są wymagane również następujące elementy:

-   Komputer, który może komunikować się z urzędem certyfikacji, lub komputer urzędu certyfikacji.

-  Łącznik certyfikatów usługi Intune uruchamiany na komputerze, który może komunikować się z urzędem certyfikacji.

## <a name="onpremises-infrastructure-description"></a>Opis infrastruktury lokalnej


-    **Domena usługi Active Directory:** wszystkie serwery wymienione w tej części (z wyjątkiem serwera proxy aplikacji sieci Web) muszą należeć do Twojej domeny usługi Active Directory.

-  **Urząd certyfikacji**: wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. Instrukcje dotyczące sposobu konfigurowania urzędu certyfikacji znajdują się w temacie [Instalacja urzędu certyfikacji](http://technet.microsoft.com/library/jj125375.aspx).
    Jeśli na serwerze urzędu certyfikacji jest zainstalowany system Windows Server 2008 R2, należy najpierw [zainstalować poprawkę z tematu KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Komputer, który może komunikować się z urzędem certyfikacji**: alternatywnie można użyć komputera urzędu certyfikacji.
-  **Łącznik certyfikatów usługi Microsoft Intune**: używając konsoli administracyjnej usługi Intune, możesz pobrać instalatora **łącznika certyfikatów** (**ndesconnectorssetup.exe**). Następnie możesz uruchomić plik **ndesconnectorssetup.exe** na komputerze, na którym chcesz zainstalować łącznik certyfikatów. W przypadku profilów certyfikatów PFX zainstaluj łącznik certyfikatów na komputerze, który komunikuje się z urzędem certyfikacji.
-  **Serwer proxy aplikacji sieci Web** (opcjonalnie): jako serwera proxy aplikacji sieci Web (WAP) można użyć serwera z systemem Windows Server 2012 R2 lub nowszym. Ta konfiguracja:
    -  Umożliwia urządzeniom otrzymywanie certyfikatów przy użyciu połączenia internetowego.
    -  Jest zalecana ze względów bezpieczeństwa w przypadku używania połączenia internetowego do pobierania i odnawiania certyfikatów przez urządzenia.

 > [!NOTE]           
> -    Serwer proxy aplikacji sieci Web [wymaga instalacji aktualizacji](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) umożliwiającej obsługę długich adresów URL używanych przez usługę rejestracji urządzeń sieciowych (NDES). Ta aktualizacja jest dostępna w ramach [zbiorczego pakietu aktualizacji z grudnia 2014 r.](http://support.microsoft.com/kb/3013769)lub osobno w temacie [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Ponadto serwer, który hostuje serwer proxy aplikacji sieci Web, musi mieć certyfikat SSL odpowiadający nazwie opublikowanej dla klientów zewnętrznych oraz uznawać certyfikat SSL używany na serwerze usługi NDES za zaufany. Te certyfikaty umożliwiają serwerowi proxy aplikacji sieci Web zakończenie połączenia SSL od klientów i utworzenie nowego połączenia SSL z serwerem usługi NDES.
    Informacje na temat certyfikatów dla serwera proxy aplikacji sieci Web zawiera sekcja **Planowanie certyfikatów** w temacie [Planowanie publikowania aplikacji przy użyciu serwera proxy aplikacji sieci Web](https://technet.microsoft.com/library/dn383650.aspx). Ogólne informacje na temat serwerów proxy aplikacji sieci Web znajdują się w temacie [Praca z serwerem proxy aplikacji sieci Web](http://technet.microsoft.com/library/dn584113.aspx).|


### <a name="certificates-and-templates"></a>Certyfikaty i szablony

|Obiekt|Szczegóły|
|----------|-----------|
|**Szablon certyfikatu**|Ten szablon należy skonfigurować na serwerze wystawiającego urzędu certyfikacji.|
|**Certyfikat zaufanego głównego urzędu certyfikacji**|Ten certyfikat należy wyeksportować w pliku w formacie **.cer** z urzędu wystawiającego certyfikaty lub dowolnego urządzenia traktującego urząd wystawiający certyfikaty jako zaufany, a następnie wdrożyć go na urządzeniach, korzystając z profilu certyfikatu zaufanego urzędu certyfikacji.<br /><br />Należy użyć jednego certyfikatu zaufanego głównego urzędu certyfikacji dla każdej platformy systemu operacyjnego i powiązać te certyfikaty z poszczególnymi utworzonymi profilami zaufanych certyfikatów głównych.<br /><br />W razie potrzeby można użyć dodatkowych certyfikatów zaufanego głównego urzędu certyfikacji. Można na przykład zrobić to, aby urząd certyfikacji podpisujący certyfikaty uwierzytelniania serwera dla punktów dostępowych Wi-Fi był traktowany jako zaufany.|


## <a name="configure-your-infrastructure"></a>Konfigurowanie infrastruktury
Aby można było skonfigurować profile certyfikatów, należy najpierw wykonać poniższe zadania. Te zadania wymagają znajomości systemu Windows Server 2012 R2 oraz usług certyfikatów Active Directory (ADCS):

- **Zadanie 1** — Konfigurowanie szablonów certyfikatu w urzędzie certyfikacji.
- **Zadanie 2** — Włączanie, instalacja i konfiguracja łącznika certyfikatów dla usługi Intune.

### <a name="task-1-configure-certificate-templates-on-the-certification-authority"></a>Zadanie 1 — Konfigurowanie szablonów certyfikatu w urzędzie certyfikacji
To zadanie obejmuje publikowanie szablonu certyfikatu.

##### <a name="to-configure-the-certification-authority"></a>Aby skonfigurować urząd certyfikacji

1.  Za pomocą przystawki Szablony certyfikatów dla wystawiającego urzędu certyfikacji utwórz nowy szablon niestandardowy lub skopiuj i zmodyfikuj istniejący szablon (na przykład szablon użytkownika), aby używać go z profilem PFX.

    Dla szablonu należy uwzględnić następujące kwestie:

    -   Określ przyjazną **nazwę wyświetlaną szablonu** .

    -   Na karcie **Nazwa podmiotu** zaznacz opcję **Dostarcz w żądaniu**. 

    -   Na karcie **Rozszerzenia** upewnij się, że **Opis zasad aplikacji** obejmuje pozycję **Uwierzytelnianie klienta**.

        > [!IMPORTANT]
        > W przypadku szablonów certyfikatów dla systemu iOS i Mac OS X na karcie **Rozszerzenia** edytuj pozycję **Użycie klucza** i upewnij się, że opcja **Podpis jest dowodem pochodzenia** nie jest zaznaczona.

2.  Sprawdź **Okres ważności** na karcie **Ogólne** szablonu. Domyślnie usługa Intune używa wartości skonfigurowanej w szablonie. Można jednak skonfigurować urząd certyfikacji tak, aby umożliwiał żądającemu określenie innej wartości, którą można następnie ustawić przy użyciu konsoli administratora w usłudze Intune. Jeśli chcesz, aby zawsze była używana wartość określona w szablonie, pomiń pozostałe czynności w tym kroku.

    > [!IMPORTANT]
    > W przypadku platform iOS i Mac OS X wartość ustawiona w szablonie jest używana zawsze, niezależnie od innych ustawień.

    W celu skonfigurowania urzędu certyfikacji tak, aby umożliwiał żądającemu określenie okresu ważności, uruchom następujące polecenia w urzędzie certyfikacji:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Użyj przystawki Urząd certyfikacji dla wystawiającego urzędu certyfikacji, aby opublikować szablon certyfikatu.

    a.  Zaznacz węzeł **Szablony certyfikatów**, kliknij pozycję **Akcja**-&gt; **Nowy** &gt; **Szablon certyfikatu do wystawienia**, a następnie wybierz szablon utworzony w kroku 2.

    b.  Sprawdź, czy certyfikat został opublikowany, wyświetlając go w folderze **Szablony certyfikatów** .

4.  Na komputerze urzędu certyfikacji sprawdź, czy komputer hostujący łącznik certyfikatów usługi Intune ma uprawnienia do rejestracji, dzięki czemu może uzyskiwać dostęp do szablonu używanego podczas tworzenia profilu PFX. Ustaw to uprawnienie na karcie **Zabezpieczenia** właściwości komputera urzędu certyfikacji.

### <a name="task-2-enable-install-and-configure-the-intune-certificate-connector"></a>Zadanie 2 — Włączanie, instalacja i konfiguracja łącznika certyfikatów dla usługi Intune
To zadanie obejmuje:

Pobieranie, instalowanie i konfigurowanie łącznika certyfikatów.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Aby włączyć obsługę łącznika certyfikatów

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com) i wybierz pozycję **Administracja** &gt; **Łącznik certyfikatów**.

2.  Wybierz pozycję **Skonfiguruj lokalny łącznik certyfikatów**.

3.  Wybierz pozycję **Włącz łącznik certyfikatów**, a następnie kliknij przycisk **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Aby pobrać, zainstalować i skonfigurować łącznik certyfikatów

1.  Otwórz [konsolę administracyjną usługi Intune](https://manage.microsoft.com), a następnie wybierz pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Łącznik certyfikatów** &gt; **Pobierz łącznik certyfikatów**.

2.  Po zakończeniu uruchom pobrany program instalacyjny (**ndesconnectorssetup.exe**).

  Uruchom instalatora na komputerze, który może połączyć się z urzędem certyfikacji. Wybierz opcję dystrybucji certyfikatu PFX, a następnie wybierz pozycję **Zainstaluj**. Po ukończeniu instalacji utwórz profil certyfikatu zgodnie z opisem w sekcji [Konfigurowanie profilów certyfikatów](configure-intune-certificate-profiles.md).

   <!-- Not sure about step 3 below -->

3.  Gdy zostanie wyświetlony monit o certyfikat klienta dla łącznika certyfikatów, wybierz pozycję **Wybierz**, a następnie wybierz certyfikat **uwierzytelniania klienta** zainstalowany w zadaniu 3.

    Po wybraniu certyfikatu uwierzytelniania klienta nastąpi powrót do widoku **Certyfikat klienta dla łącznika certyfikatów w usłudze Microsoft Intune** . Chociaż wybrany certyfikat nie jest wyświetlany, wybierz przycisk **Dalej** , aby wyświetlić właściwości certyfikatu. Następnie wybierz przycisk **Dalej**, a następnie pozycję **Zainstaluj**.

4.  Po zakończeniu działania kreatora, ale przed jego zamknięciem, kliknij pozycję **Uruchom interfejs użytkownika łącznika certyfikatów**.

    > [!TIP]
    > Jeśli kreator zostanie zamknięty przed uruchomieniem interfejsu użytkownika łącznika certyfikatów, możesz uruchomić go za pomocą następującego polecenia:
    >
    > **&lt;ścieżka_instalacji&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  W interfejsie użytkownika **łącznika certyfikatów** :

    a. Wybierz pozycję **Zaloguj** i wprowadź swoje poświadczenia administratora usługi Intune lub poświadczenia administratora dzierżawy z uprawnieniami administratora globalnego.

    b. Wybierz kartę **Zaawansowane** , wprowadź poświadczenia konta, do którego przypisano uprawnienia **Wystawianie certyfikatów i zarządzanie nimi** w urzędzie wystawiającym certyfikaty.

    c. Wybierz pozycję **Zastosuj**.

    Teraz możesz zamknąć interfejs użytkownika łącznika certyfikatów.

6.  Otwórz wiersz polecenia i wpisz **services.msc**. Naciśnij klawisz **Enter**, kliknij prawym przyciskiem myszy pozycję **Usługa łącznika usługi Intune** i wybierz polecenie **Uruchom ponownie**.


### <a name="next-steps"></a>Następne kroki
Teraz można skonfigurować profile certyfikatów zgodnie z opisem w sekcji [Konfigurowanie profilów certyfikatów](Configure-Intune-certificate-profiles.md).



<!--HONumber=Nov16_HO3-->


