---
title: Konfigurowanie protokołu S/MIME z programem Outlook dla systemu iOS w usłudze Microsoft Intune
description: Omówienie protokołu S/MIME z programem Outlook dla systemu iOS w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lance
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b2f483415d050486ae9979899d9308154a9b131
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74411362"
---
# <a name="configure-smime-with-outlook-for-ios"></a>Konfigurowanie protokołu S/MIME z programem Outlook dla systemu iOS

Protokół Secure/Multipurpose Internet Mail Extensions (S/MIME) zapewnia dodatkową warstwę zabezpieczeń dla wiadomości e-mail wysyłanych do i z konta programu Exchange ActiveSync (EAS). Program [Microsoft Outlook](https://aka.ms/omsmime) może korzystać z protokołu S/MIME, aby umożliwić użytkownikom szyfrowanie wiadomości wychodzących i załączników, dzięki czemu tylko zamierzony adresat może odczytać i uzyskać dostęp do zawartości wiadomości przy użyciu kont usługi Office 365. Użytkownicy mogą również cyfrowo podpisywać wiadomości, co umożliwia adresatom zweryfikowanie tożsamości nadawcy i potwierdzenie, że wiadomość nie została naruszona. Jest to możliwe dzięki użyciu certyfikatów. Aby uzyskać więcej informacji, zobacz [Omówienie protokołu S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)?redirectedfrom=MSDN).

> [!NOTE]
> W tym temacie opisano sposób wdrażania zaufanych certyfikatów głównych za pośrednictwem programu [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). Microsoft Endpoint Manager to pojedyncza, zintegrowana platforma zarządzania punktami końcowymi służąca do zarządzania wszystkimi punktami końcowymi. To centrum administracyjne programu Microsoft Endpoint Manager integruje program ConfigMgr i usługę Microsoft Intune.

## <a name="about-message-encryption"></a>Informacje o szyfrowaniu komunikatów
Użytkownicy mogą wysyłać zaszyfrowane wiadomości do osób w swojej organizacji i do osób spoza organizacji, jeśli mają publiczną część certyfikatów szyfrowania. Klucze prywatne skojarzone z certyfikatami szyfrowania powinny być zawsze chronione i zabezpieczone przez adresata zaszyfrowanej wiadomości. Klucz prywatny certyfikatu szyfrowania jest używany do odszyfrowywania wiadomości przez adresata.

Zaszyfrowane wiadomości mogą być odczytywane tylko przez adresatów, którzy posiadają certyfikat odpowiadający temu, za pomocą którego zaszyfrowano wiadomość. Jeśli spróbujesz wysłać zaszyfrowaną wiadomość do adresatów, których certyfikat szyfrowania jest niedostępny, aplikacja wyświetli monit o usunięcie tych adresatów przed wysłaniem wiadomości e-mail.

## <a name="about-digital-signatures"></a>Informacje o podpisach cyfrowych
Podpisana cyfrowo wiadomość daje pewność adresatowi, że wiadomość nie została naruszona i że tożsamość nadawcy jest autentyczna. Adresaci mogą zweryfikować podpis cyfrowy tylko wtedy, gdy używają klienta poczty e-mail obsługującego protokół S/MIME.

## <a name="prerequisites"></a>Wymagania wstępne
- Program Outlook dla systemu iOS obsługuje protokół S/MIME na kontach usługi Office 365.
- Protokół S/MIME należy skonfigurować dla usługi Office 365. Aby uzyskać więcej informacji, zobacz [Jak skonfigurować protokół S/MIME w usłudze Office 365](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/How-to-Configure-S-MIME-in-Office-365/ba-p/584516).
- Musisz mieć urząd certyfikacji, który może wystawiać certyfikaty, które mogą być używane do podpisywania i szyfrowania.
- Wdróż zaufane certyfikaty główne za pośrednictwem programu Endpoint Manager. Aby uzyskać więcej informacji, zobacz [Tworzenie profili certyfikatów zaufanych](~/protect/certificates-configure.md#create-trusted-certificate-profiles).
- Certyfikaty szyfrowania należy zaimportować do programu Endpoint Manager. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zaimportowanych certyfikatów PKCS i korzystanie z nich w usłudze Intune](~/protect/certificates-imported-pfx-configure.md).
- Zainstaluj i skonfiguruj łącznik PFX dla usługi Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Pobieranie, instalowanie i konfigurowanie programu Łącznik certyfikatów PFX dla usługi Microsoft Intune](~/protect/certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
- Urządzenia muszą być zarejestrowane w usłudze MDM, aby automatycznie otrzymywać zaufane certyfikaty główne i certyfikaty S/MIME z programu Endpoint Manager.

> [!IMPORTANT]
> Należy pobrać i zainstalować zaktualizowany łącznik PFX (w wersji 6.1911.11.0 lub nowszej), aby usługa Microsoft Intune mogła używać certyfikatów szyfrowania S/MIME w programie Outlook dla systemu iOS.

## <a name="smime-support-in-outlook-for-ios"></a>Obsługa protokołu S/MIME w programie Outlook dla systemu iOS
Program Outlook dla systemu iOS obsługuje podpisywanie i szyfrowanie wiadomości za pomocą protokołu S/MIME przy użyciu certyfikatów. Wielu klientów ma oddzielne certyfikaty podpisywania i szyfrowania, w przeciwieństwie do posiadania pojedynczego certyfikatu, który obsługuje podpisywanie i szyfrowanie. Certyfikaty podpisywania są zwykle unikatowe na zarejestrowanych urządzeniach poszczególnych użytkowników, natomiast certyfikaty szyfrowania są wspólne na zarejestrowanych urządzeniach poszczególnych użytkowników. Często użytkownicy korzystają z protokołu S/MIME przez lata, używając różnych certyfikatów szyfrowania w miarę upływu czasu, ponieważ certyfikaty są odnawiane. Historie certyfikatów szyfrowania, w tym ich klucze prywatne, muszą być obecne na urządzeniu użytkownika, aby można było odczytać wiadomości e-mail, które mogły zostać zaszyfrowane za pomocą dowolnego z tych certyfikatów w przeszłości. Można również posiadać jeden certyfikat obsługujący podpisywanie i szyfrowanie.

Program Outlook dla systemu iOS obsługuje dwa sposoby dostarczania certyfikatów na urządzenia, aby można było ich używać na potrzeby protokołu S/MIME:

- **Użytkownicy** mogą wysłać do siebie certyfikaty S/MIME pocztą e-mail i zainstalować je z załączników w programie Outlook dla systemu iOS na urządzeniach przenośnych.
- **Administratorzy** mogą zaimportować historie certyfikatu szyfrowania z dowolnego urzędu certyfikacji do programu Endpoint Manager. Program Endpoint Manager automatycznie dostarczy te certyfikaty na wszystkie urządzenia zarejestrowane przez użytkownika. Na ogół do podpisywania certyfikatów jest używany prosty protokół rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol). W przypadku protokołu SCEP klucz prywatny jest generowany i przechowywany na zarejestrowanym urządzeniu, a do każdego urządzenia zarejestrowanego przez użytkownika jest dostarczany unikatowy certyfikat, co można wykorzystać na potrzeby niemożności wyparcia się. Administratorzy importują historie certyfikatu szyfrowania dla swoich użytkowników do programu Endpoint Manager, który następnie dostarcza wszystkie certyfikaty szyfrowania użytkownika do dowolnego zarejestrowanego przez niego urządzenia. Ponadto program Endpoint Manager obsługuje poświadczenia pochodne dla klientów, którzy potrzebują obsługi dla standardu NIST 800-157. W systemie iOS certyfikaty podpisywania i szyfrowania są pobierane z usługi Intune przy użyciu aplikacji Portal firmy.

## <a name="configuring-outlook-for-ios-smime-in-endpoint-manager"></a>Konfigurowanie protokołu S/MIME programu Outlook dla systemu iOS w programie Endpoint Manager
Aby skonfigurować protokół S/MIME programu Outlook dla systemu iOS w programie Endpoint Manager, w tym automatyczne dostarczanie certyfikatów S/MIME, których może używać program Outlook dla systemu iOS, wykonaj następujące czynności:

### <a name="add-the-microsoft-outlook-app"></a>Dodawanie aplikacji Microsoft Outlook
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Dodaj aplikację Microsoft Outlook dla systemu iOS ze sklepu App Store do programu Endpoint Manager lub zsynchronizuj aplikację Outlook dla systemu iOS z programu Apple Volume Purchase Program. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji ze sklepu dla systemu iOS do usługi Microsoft Intune](~/apps/store-apps-ios.md) lub [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemów iOS i macOS, które zostały zakupione w ramach programu zakupów zbiorczych firmy Apple](~/apps/vpp-apps-ios.md).

### <a name="create-the-outlook-for-ios-smime-configuration-policy"></a>Tworzenie zasad konfiguracji protokołu S/MIME programu Outlook dla systemu iOS

Poniższe kroki umożliwiają utworzenie i skonfigurowanie zasad protokołu S/MIME programu Outlook dla systemu iOS w programie Endpoint Manager. Te ustawienia zapewniają zautomatyzowane dostarczanie certyfikatów podpisywania i szyfrowania.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj**.<br>
Zostanie wyświetlone okienko **Dodawanie zasad konfiguracji**.
2. Wprowadź odpowiednie dane w polach **Nazwa** i **Opis** dla zasad konfiguracji.
3. Wybierz pozycję **Urządzenia zarządzane** w polu **Typ rejestracji urządzenia**.
4. Wybierz pozycję **iOS/iPadOS** w polu **Platforma**.
5. Kliknij pozycję **Wybierz wymaganą aplikację**, aby znaleźć i skojarzyć aplikację Microsoft Outlook dla systemu iOS, która została wcześniej dodana. 
6. Kliknij pozycję **Ustawienia konfiguracji**, aby dodać ustawienia konfiguracji. 
    - Wybierz pozycję **Użyj projektanta konfiguracji** obok pozycji **Format ustawień konfiguracji** i zaakceptuj ustawienia domyślne. Aby uzyskać więcej informacji, zobacz [ustawienia konfiguracji programu Microsoft Outlook](~/apps/app-configuration-policies-outlook.md).
7. Kliknij pozycję **S/MIME**, aby wyświetlić stronę **Ustawienia S/MIME programu Outlook**.

    ![Zrzut ekranu ustawień S/MIME programu Outlook dla systemu iOS](./media/app-configuration-policies-outlook-smime/app-configuration-policies-outlook-smime-01.png)

8. Dla pozycji **Włącz protokół S/MIME** ustaw wartość **Tak**.
9. Dla pozycji **Wdróż certyfikaty S/MIME z usługi Intune** ustaw wartość **Tak**.
10. W obszarze **Certyfikaty podpisywania** obok pozycji **Typ profilu certyfikatu** wybierz jedną z następujących opcji:
    - **SCEP** — Tworzy certyfikat, który jest unikatowy dla urządzenia i użytkownika i którego program Microsoft Outlook może używać do podpisywania. Aby uzyskać powiązane informacje, zobacz [Konfigurowanie infrastruktury do obsługi protokołu SCEP w usłudze Intune](~/protect/certificates-scep-configure.md) i [Tworzenie profilu certyfikatu SCEP](~/protect/certificates-profile-scep.md#create-a-scep-certificate-profile). 
    - **Zaimportowane certyfikaty PKCS** — Używa certyfikatu, który jest unikatowy dla użytkownika, ale może być udostępniany między urządzeniami, i został zaimportowany do programu Endpoint Manager przez administratora w imieniu użytkownika. Certyfikat jest dostarczany do każdego urządzenia zarejestrowanego przez użytkownika. Program Endpoint Manager automatycznie wybierze zaimportowany certyfikat obsługujący podpisywanie w celu dostarczenia do urządzenia odpowiadającego zarejestrowanemu użytkownikowi.
    - **Poświadczenia pochodne** — Używa certyfikatu znajdującego się już na urządzeniu, którego można użyć na potrzeby podpisywania. Certyfikat musi zostać pobrany na urządzeniu przy użyciu przepływów poświadczeń pochodnych w usłudze Intune.
11. W obszarze **Certyfikaty szyfrowania** obok pozycji **Typ profilu certyfikatu** wybierz jedną z następujących opcji:
    - **Zaimportowane certyfikaty PKCS** — Dostarcza wszystkie certyfikaty szyfrowania, które zostały zaimportowane do programu Endpoint Manager przez administratora, na wszystkie urządzenia zarejestrowane przez użytkownika. Program Endpoint Manager automatycznie wybierze zaimportowane certyfikaty, które obsługują szyfrowanie, aby dostarczyć je do urządzenia odpowiadającego zarejestrowanemu użytkownikowi.
    - **Poświadczenia pochodne** — Używa certyfikatu znajdującego się już na urządzeniu, którego można użyć na potrzeby podpisywania. Certyfikat musi zostać pobrany na urządzeniu przy użyciu przepływów poświadczeń pochodnych w usłudze Intune.
12. Obok pozycji **Powiadomienia użytkowników końcowych** wybierz powiadamianie użytkowników końcowych przez wybranie pozycji **Portal firmy** lub **E-mail** na potrzeby pobierania certyfikatów S/MIME dla programu Outlook dla systemu iOS.

    W systemie iOS użytkownicy muszą używać aplikacji Portal firmy w celu pobierania certyfikatów S/MIME. Program Endpoint Manager poinformuje użytkownika, że musi on uruchomić aplikację Portal firmy, aby pobrać swoje certyfikaty S/MIME, za pośrednictwem sekcji Powiadomienia aplikacji Portal firmy, powiadomienia push i/lub wiadomości e-mail. Kliknięcie jednego z powiadomień spowoduje przejście do strony docelowej, która informuje o postępie pobierania certyfikatów. Po pobraniu certyfikatów użytkownik może używać protokołu S/MIME z poziomu programu Microsoft Outlook dla systemu iOS, aby podpisywać i szyfrować wiadomości e-mail.
    
    Powiadomienia użytkowników końcowych obejmują następujące opcje:
       - **Portal firmy** — W przypadku wybrania tej opcji użytkownicy otrzymają powiadomienie push na swoim urządzeniu, które spowoduje przejście do strony docelowej w aplikacji Portal firmy, gdzie zostaną pobrane certyfikaty S/MIME.
        - **E-mail** — Wysyła wiadomość e-mail do użytkownika końcowego z informacją o konieczności uruchomienia aplikacji Portal firmy w celu pobrania certyfikatów S/MIME. Jeśli użytkownik podczas klikania linku w wiadomości e-mail korzysta z zarejestrowanego urządzenia z systemem iOS, zostanie przekierowany do aplikacji Portal firmy w celu pobrania certyfikatów.
    
13. Wybierz pozycję **Przypisania**, aby przypisać zasady konfiguracji aplikacji do grup usługi Azure AD. Aby uzyskać więcej informacji, zobacz [Przypisywanie aplikacji do grup w usłudze Microsoft Intune](~/apps/apps-deploy.md).

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji, zobacz [Zasady konfiguracji aplikacji usługi Microsoft Intune](app-configuration-policies-overview.md).
