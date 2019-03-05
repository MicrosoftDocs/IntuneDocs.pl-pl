---
title: Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung
titlesuffix: Microsoft Intune
description: Informacje o sposobie rejestrowania urządzeń z systemem Android przy użyciu rozwiązania Samsung KME
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7bb2b8c57c8aa3f53a04150ce0ad692b0149dee8
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235955"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung

Ten temat zawiera informacje pomocne w przypadku konfigurowania usługi Intune do rejestrowania obsługiwanych urządzeń z systemem Android przy użyciu rozwiązania Samsung Knox Mobile Enrollment (KME). Używając usługi Intune razem z rozwiązaniem Samsung KME, można rejestrować wiele należących do firmy urządzeń z systemem Android, gdy użytkownicy końcowi włączą swoje urządzenia po raz pierwszy i połączą się z siecią Wi-Fi lub siecią komórkową. Ponadto w przypadku korzystania z aplikacji Knox Deployment App urządzenia mogą być rejestrowane za pomocą funkcji Bluetooth lub NFC.

Aby włączyć rejestrację w usłudze Intune przy użyciu rozwiązania Samsung KME, należy użyć portali usługi Intune i rozwiązania Samsung Knox w następującej kolejności:

1. W portalu rozwiązania Knox:
    1. [Utwórz profil oprogramowania MDM](#create-mdm-profile)
    2. [Dodaj urządzenia](#add-devices)
    3. [Przypisz profil oprogramowania MDM do urządzeń](#assign-an-mdm-profile-to-devices)
2. W portalu rozwiązania Knox [skonfiguruj logowanie użytkownika końcowego](#configure-how-end-users-sign-in).
3. [Rozdystrybuuj urządzenia](#distribute-devices).


Lista identyfikatorów urządzeń (numery seryjne i numery IMEI) jest automatycznie dodawana do portalu rozwiązania Knox w przypadku zakupu urządzeń od autoryzowanego odsprzedawcy biorącego udział w programie wdrażania rozwiązania Knox.


## <a name="prerequisites"></a>Wymagania wstępne

Aby rejestrować w usłudze Intune przy użyciu rozwiązania KME, musisz najpierw zarejestrować firmę w portalu Samsung Knox. W tym celu wykonaj następujące czynności:
1.  [Upewnij się, że rozwiązanie KME jest dostępne w Twoim regionie](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): rozwiązanie KME jest dostępne w ponad 55 krajach. Upewnij się, że kraj wdrożenia jest obsługiwany.

2.  [Obsługiwane urządzenia](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): rozwiązanie KME jest dostępne na wszystkich urządzeniach firmy Samsung z platformą Knox co najmniej w wersji 2.4 w przypadku rejestracji urządzeń z systemem Android i z platformą Knox co najmniej w wersji 2.8 w przypadku rejestracji urządzeń z systemem Android Enterprise.

3.  [Wymagania dotyczące sieci](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): upewnij się, że niezbędne reguły zapory i dostępu do sieci są dozwolone w sieci.

4.  [Zarejestruj się, aby założyć konto Samsung](https://www2.samsungknox.com/en/user/register): konto Samsung jest wymagane do rejestrowania i włączania rozwiązania KME oraz zarządzania wszystkimi uprawnieniami rozwiązania Knox Enterprise w jednym miejscu.

5.  Przegląd rejestracji: po ukończeniu i przesłaniu profilu firma Samsung przeprowadza przegląd zgłoszenia i natychmiast je zatwierdza lub przenosi je do stanu oczekiwania na przegląd w celu wykonania dalszych czynności. Po zatwierdzeniu konta można przejść do dalszych czynności.

## <a name="create-mdm-profile"></a>Tworzenie profilu oprogramowania MDM

Po pomyślnym zarejestrowaniu firmy można utworzyć profil oprogramowania MDM dla usługi Microsoft Intune w portalu platformy Knox, korzystając z poniższych informacji. Profile MDM dla systemów Android i Android Enterprise można tworzyć w portalu platformy Knox. 

### <a name="for-android-enterprise"></a>Dla systemu Android Enterprise

| Pola profilu oprogramowania MDM| Wymagane? | Wartości | 
|-------------------|-----------|-------| 
|MDM Server URI (Identyfikator URI serwera MDM)     | Nie        |Pozostaw to pole puste. 
|Profile Name (Nazwa profilu)       | Tak       |Wprowadź wybraną nazwę profilu. 
|Opis        | Nie        |Wprowadź tekst opisujący profil. 
|MDM Agent APK (Plik APK oprogramowania MDM)      | Tak       |https://aka.ms/intune_kme_deviceowner 
|Włącz tę aplikację jako właściciela urządzenia Google | Tak | Wybierz tę opcję, aby zarejestrować się w systemie Android Enterprise. 
|Obsługiwane zarządzanie urządzeniami przenośnymi      | Tak       |Microsoft Intune 
|Pozostaw wszystkie aplikacje systemowe włączone | Nie | Wybierz tę opcję, aby upewnić się, że wszystkie aplikacje są włączone i dostępne dla tego profilu. Jeśli ta opcja nie jest zaznaczona, na pasku aplikacji urządzenia będzie wyświetlany tylko bardzo ograniczony zestaw aplikacji systemowych. Aplikacje takie jak aplikacja poczty e-mail pozostaną ukryte. 
|Custom JSON (Niestandardowa notacja JSON)        | Nie        |{"com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "Wprowadź ciąg tokenu rejestracji usługi Intune"}. Dowiedz się, jak [utworzyć profil rejestracji](android-kiosk-enroll.md). 
| Dodaj umowy prawne | Nie | Pozostaw to pole puste. 

### <a name="for-android"></a>Dla systemu Android

Szczegółowe wskazówki można znaleźć w instrukcjach podanych w artykule [Samsung Knox Profile Setup Wizard](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) (Kreator konfiguracji profilu rozwiązania Samsung Knox).

| Pola profilu oprogramowania MDM| Wymagane? | Wartości |
|-------------------|-----------|-------|
|MDM Server URI (Identyfikator URI serwera MDM)     | Nie        |Pozostaw to pole puste.
|Profile Name (Nazwa profilu)       | Tak       |Wprowadź wybraną nazwę profilu.
|description        | Nie        |Wprowadź tekst opisujący profil.
|MDM Agent APK (Plik APK oprogramowania MDM)      | Tak       |https://aka.ms/intune_kme
|Włącz tę aplikację jako właściciela urządzenia Google | Nie | Pozostaw tę opcję niezaznaczoną w przypadku systemu Android. Dotyczy to tylko systemu Android Enterprise.
|Skip Setup wizard (Pomiń kreatora instalacji)  | Nie        |Wybierz tę opcję, aby pomijać monity dotyczące standardowej instalacji urządzenia w imieniu użytkownika końcowego.
|Allow End User to Cancel Enrollment (Zezwalaj użytkownikowi końcowemu na anulowanie rejestracji) | Nie | Wybierz tę opcję, aby użytkownicy mogli anulować rozwiązanie KME.
|Custom JSON (Niestandardowa notacja JSON)        | Nie        |Pozostaw to pole puste.
| Dodaj umowy prawne | Nie | Pozostaw to pole puste.
Associate a Knox license with this profile (Skojarz licencję rozwiązania Knox z tym profilem) | Nie | Pozostaw tę opcję niezaznaczoną. Rejestrowanie w usłudze Intune przy użyciu rozwiązania KME nie wymaga licencji platformy Knox.

## <a name="add-devices"></a>Dodawanie urządzeń

Aby przypisywać profile oprogramowania MDM do urządzeń, należy dodać obsługiwane urządzenia rozwiązania Samsung Knox do portalu Knox za pomocą jednej z następujących metod:
- **Przy użyciu odsprzedawców zatwierdzonych przez firmę Samsung:** użyj tej metody w przypadku kupowania urządzeń od jednego z zatwierdzonych odsprzedawców firmy Samsung. Zatwierdzeni odsprzedawcy mogą automatycznie przekazywać Twoje urządzenia. [Odwiedź stronę podręcznika użytkownika rozwiązania Samsung Knox Enrollment, aby dowiedzieć się, jak dodawać odsprzedawców](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Przy użyciu aplikacji Knox Deployment App (KDA):** użyj tej metody, jeśli masz urządzenia, które musisz zarejestrować przy użyciu rozwiązania KME. W celu dodania urządzeń do portalu Knox za pomocą tej metody możesz użyć funkcji Bluetooth lub NFC. [Odwiedź stronę podręcznika użytkownika rozwiązania Samsung Knox Enrollment, aby dowiedzieć się, jak używać aplikacji KDA](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Przypisywanie profilu oprogramowania MDM do urządzeń
Przed rozpoczęciem rejestrowania dodanych urządzeń musisz przypisać do nich profil oprogramowania MDM w portalu rozwiązania Knox. [Odwiedź stronę podręcznika użytkownika rozwiązania Samsung Knox Enrollment, aby dowiedzieć się więcej na temat konfiguracji urządzeń](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Konfigurowanie sposobu logowania użytkowników końcowych

W przypadku urządzeń zarejestrowanych w usłudze Intune przy użyciu rozwiązania KME dla systemu Android można skonfigurować sposób logowania użytkownika końcowego w następujący sposób:

- **Bez skojarzenia nazwy użytkownika:** w portalu rozwiązania Knox w obszarze **Szczegóły urządzenia** dla dodawanych urządzeń pozostaw puste pola **Identyfikator użytkownika** i **Hasło**. W tej sytuacji użytkownicy końcowi będą musieli wprowadzić nazwę użytkownika i hasło podczas rejestrowania w usłudze Intune.

- **Ze skojarzeniem nazwy użytkownika:** w portalu rozwiązania Knox w obszarze **Szczegóły urządzenia** dla dodawanych urządzeń wypełnij pole **Identyfikator użytkownika** (na przykład nazwa przypisanego użytkownika lub konto [menedżera rejestracji urządzeń](https://docs.microsoft.com/intune/device-enrollment-manager-enroll)). Spowoduje to wstępne wypełnienie nazwy użytkownika, a użytkownik końcowy będzie musiał wprowadzić hasło podczas rejestrowania w usłudze Intune.

> [!NOTE]
>
>Skojarzenie z użytkownikiem ma zastosowanie tylko w przypadku rejestracji urządzeń z systemem Android. Po zdefiniowaniu skojarzenia użytkownika tylko skojarzony użytkownik będzie mógł zarejestrować urządzenie przy użyciu rozwiązania KME. Ta reguła będzie obowiązywać nawet po zresetowaniu urządzenia do ustawień fabrycznych. W przypadku braku zdefiniowanych skojarzeń użytkownika w portalu rozwiązania Knox każdy użytkownik z ważną licencją usługi Intune może rejestrować urządzenia przy użyciu rozwiązania KME.
>

## <a name="distribute-devices"></a>Dystrybuowanie urządzeń

Po utworzeniu i przypisaniu profilu oprogramowania MDM, skojarzeniu nazwy użytkownika i zidentyfikowaniu urządzeń jako należących do firmy w usłudze Intune można dystrybuować urządzenia do użytkowników.

Nadal potrzebujesz pomocy? Zapoznaj się z pełną wersją [podręcznika użytkownika rozwiązania Mobile Knox Enrollment](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

- **Obsługa właściciela urządzenia:** Usługa Intune obsługuje rejestrowanie urządzeń tylko do trybu kiosku przy użyciu systemu Android Enterprise. Inne tryby właściciela urządzenia systemu Android Enterprise będą obsługiwane, gdy staną się dostępne w usłudze Intune.

- **Brak obsługi profilów roboczych:** rozwiązanie KME jest metodą rejestracji urządzeń firmowych. Na urządzeniach osobistych zarejestrowanych w profilu roboczym systemu Android dane służbowe i dane osobiste są od siebie oddzielone. Z tego powodu rejestracja urządzenia w profilu roboczym przy użyciu rozwiązania KME nie jest scenariuszem obsługiwanym przez usługę Intune.

- **Resetowanie do ustawień fabrycznych w celu zarejestrowania w systemie Android Enterprise:** jeśli ma miejsce zmiana zastosowania urządzeń, które zostały już skonfigurowane, podczas rejestracji w systemie Android Enterprise muszą one zostać zresetowane do ustawień fabrycznych.

- **Konto Google Play:** konto Google Play nie jest niezbędne do rejestracji urządzenia w usłudze Microsoft Intune. Przyszłe aktualizacje aplikacji Portal firmy w usłudze Intune mogą jednak wymagać konta Google Play na urządzeniu. Konto Google Play nie jest wymagane podczas rejestracji jako właściciel urządzenia Google.

- **Pole „Hasło” jest ignorowane:** jeśli w obszarze **Szczegóły urządzenia** w portalu rozwiązania Knox zostało wypełnione pole **Hasło**, jest ono ignorowane przez aplikację Portal firmy w usłudze Intune podczas rejestracji urządzeń z systemem Android. Użytkownik końcowy musi wprowadzić hasło na urządzeniu, aby ukończyć rejestrację tego urządzenia.


## <a name="getting-support"></a>Uzyskiwanie pomocy technicznej
Dowiedz się więcej na temat [uzyskiwania pomocy technicznej dotyczącej rozwiązania Samsung KME](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).


