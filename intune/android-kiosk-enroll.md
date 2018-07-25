---
title: Rejestrowanie urządzeń kiosku z rozwiązaniem Android enterprise w usłudze Intune
titlesuffix: Microsoft Intune
description: Dowiedz się, jak zarejestrować urządzenia kiosku z rozwiązaniem Android enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5a223834eed1b0174c56b5e33ad2140203073d0
ms.sourcegitcommit: 5251a630fb2c7a2e6f86abd84ab887f8eabc1481
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2018
ms.locfileid: "39212039"
---
# <a name="set-up-enrollment-of-android-enterprise-kiosk-devices"></a>Konfigurowanie rejestracji urządzeń kiosku z rozwiązaniem Android enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

System Android obsługuje kioski za pomocą zestawu rozwiązań modelu firmowych urządzeń mających określone zastosowanie dla urządzeń z systemem Android. Takie urządzenia są używane w jednym celu, na przykład do cyfrowego znakowania, drukowania biletów lub zarządzania zapasami. Administratorzy ograniczają użycie urządzenia do zdefiniowanego zestawu aplikacji i linków internetowych. Uniemożliwia to również użytkownikom dodawanie innych aplikacji i wykonywanie innych akcji na urządzeniu.

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na kioskach z systemem Android. Aby uzyskać szczegółowe informacje na temat rozwiązania Android enterprise, zobacz [wymagania dotyczące rozwiązania Android enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Urządzenia zarządzane w ten sposób są zarejestrowane w usłudze Intune bez konta użytkownika i nie są powiązane z żadnym użytkownikiem końcowym. Nie są one przeznaczone dla aplikacji do użytku osobistego ani aplikacji wymagających danych konta określonych dla użytkownika, takich jak program Outlook lub usługa Gmail.

## <a name="device-requirements"></a>Wymagania dotyczące urządzeń

Urządzenia muszą spełniać następujące wymagania, aby mogły być zarządzane jako urządzenia kiosku w ramach rozwiązania Android enterprise:

- System operacyjny Android w wersji 5.1 lub nowszy.
- Na urządzeniach musi działać dystrybucja systemu Android obsługująca łączność z usługami Google Mobile Services (GMS). Urządzenia muszą mieć dostępne usługi GMS i muszą być w stanie połączyć się z usługami GMS.

## <a name="set-up-android-kiosk-management"></a>Konfigurowanie zarządzania kioskiem z systemem Android

Aby skonfigurować zarządzanie kioskiem z systemem Android, wykonaj następujące kroki:

1. Aby przygotować się do zarządzania urządzeniami przenośnymi, należy [ustawić urząd zarządzania urządzeniami przenośnymi (MDM, mobile device management) na **Microsoft Intune**](mdm-authority-set.md) w celu uzyskania instrukcji. Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.
2. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android enterprise](connect-intune-android-enterprise.md).
3. [Utwórz profil rejestracji](#create-an-enrollment-profile).
4. [Utwórz grupę urządzeń](#create-a-device-group).
5. [Zarejestruj urządzenia kiosku](#enroll-the-kiosk-devices).

### <a name="create-an-enrollment-profile"></a>Tworzenie profilu rejestracji

Aby zarejestrować urządzenia kiosku, należy utworzyć profil rejestracji. Po utworzeniu profilu udostępnia on token rejestracji (losowy ciąg) i kod QR. W zależności od systemu operacyjnego Android i wersji urządzenia możesz użyć tokenu lub kodu QR, aby [zarejestrować urządzenie kiosku](#enroll-the-kiosk-devices).

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Rejestracja urządzeń** > **Rejestracja urządzenia z systemem Android** > **Rejestracja urządzenia kiosku i zadań**.
2. Wybierz pozycję **Utwórz** i wypełnij wymagane pola.
    - **Nazwa**: wpisz nazwę, która będzie używana podczas przypisywania profilu do dynamicznej grupy urządzeń.
    - **Data wygaśnięcia tokenu**: data wygaśnięcia tokenu. Firma Google wymusza maksymalnie 30 dni.
3. Wybierz pozycję **Utwórz**, aby zapisać profil.

### <a name="create-a-device-group"></a>Tworzenie grupy urządzeń

Aplikacje i zasady można zastosować do przypisanych albo dynamicznych grup urządzeń. Można skonfigurować dynamiczne grupy urządzeń usługi AAD, aby automatycznie wypełnić listę urządzeń zarejestrowanych przy użyciu określonego profilu rejestracji. W tym celu wykonaj następujące czynności:

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Grupy** > **Wszystkie grupy** > **Nowa grupa**.
2. W bloku **Grupa** wypełnij wymagane pola w następujący sposób:
    - **Typ grupy**: Zabezpieczenia
    - **Nazwa grupy**: wpisz intuicyjną nazwę (na przykład Urządzenia z fabryki 1)
    - **Typ członkostwa**: Urządzenie dynamiczne
3. Wybierz pozycję **Dodaj zapytanie dynamiczne**.
4. W bloku **Reguły członkostwa dynamicznego** wypełnij pola w następujący sposób:
    - **Dodaj dynamiczną regułę członkostwa**: Reguła prosta
    - **Dodaj urządzenia, na których**: enrollmentProfileName
    - W środkowym polu wybierz pozycję **Dopasowanie**.
    - W ostatnim polu wprowadź nazwę profilu rejestracji, który został utworzony wcześniej.
5. Wybierz pozycję **Dodaj zapytanie** > **Utwórz**.

### <a name="replace-or-remove-tokens"></a>Zamiana lub usuwanie tokenów

Tokeny i kody QR można zamienić albo usunąć.

- **Zamień token**: za pomocą opcji Zamień token możesz wygenerować nowy token/kod QR, gdy ten będzie bliski wygaśnięcia.
- **Odwołaj token**: możesz natychmiast unieważnić token/kod QR. Od tego momentu użycie tokenu/kodu QR nie będzie już możliwe. Z tej opcji można skorzystać w następujących przypadkach:
    - Przypadkowo udostępniono token/kod QR nieautoryzowanej osobie
    - Ukończono wszystkie rejestracje i token/kod QR nie jest już potrzebny

Zamiana lub odwołanie tokenu/kodu QR nie będzie miała żadnego wpływu na urządzenia, które są już zarejestrowane.

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Rejestracja urządzeń** > **Rejestracja urządzenia z systemem Android** > **Rejestracja urządzenia kiosku i zadań**.
2. Wybierz profil, z którym chcesz pracować.
3. Wybierz **Token**.
4. Aby zamienić token, wybierz opcję **Zamień token**.
5. Aby odwołać token, wybierz opcję **Odwołaj token**.

## <a name="enroll-the-kiosk-devices"></a>Rejestrowanie urządzeń kiosku

Po utworzeniu profilu rejestracji i dynamicznej grupy urządzeń możesz zarejestrować urządzenia kiosku. Sposób rejestrowania urządzeń z systemem Android zależy od systemu operacyjnego.

| Metoda rejestracji | Minimalna obsługiwana wersja systemu operacyjnego Android |
| ----- | ----- |
| Komunikacja zbliżeniowa | 5.1 |
| Wpis tokenu | 6.0 |
| Kod QR | 7.0 |
| Zero Touch | 8.0, w przypadku producentów uczestniczących w programie |

### <a name="enroll-by-using-near-field-communication-nfc"></a>Rejestracja przy użyciu komunikacji zbliżeniowej (NFC)

W przypadku urządzeń z systemem Android 5.1 lub nowszym obsługujących komunikację zbliżeniową (NFC, Near Field Communication) urządzenia można aprowizować, tworząc specjalnie sformatowany tag NFC. W tym celu możesz użyć własnej aplikacji lub narzędzia kreatora tagu NFC. Aby uzyskać więcej informacji, zobacz [dokumentację interfejsu API zarządzania systemem Android firmy Google](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Rejestracja przy użyciu tokenu

W przypadku urządzeń z systemem Android 6 lub nowszym można użyć tokenu do zarejestrowania urządzenia.

1. Włącz urządzenie zresetowane do ustawień fabrycznych.
2. Na ekranie **powitalnym** wybierz swój język.
3. Połącz się ze swoją **siecią Wi-Fi**, a następnie wybierz przycisk **DALEJ**.
4. Zaakceptuj warunki i postanowienia firmy Google, a następnie wybierz przycisk **DALEJ**.
5. Na ekranie logowania Google wprowadź ciąg **afw#setup** zamiast konta Gmail, a następnie wybierz przycisk **DALEJ**.
6. Wybierz pozycję **ZAINSTALUJ** dla aplikacji **Android Device Policy**.
7. Kontynuuj instalację tych zasad.  Niektóre urządzenia mogą wymagać zaakceptowania dodatkowych warunków. 
8. Na ekranie **Zarejestruj to urządzenie** zezwól urządzeniu na zeskanowanie kodu QR lub wybierz ręczne wprowadzenie tokenu.
9. Postępuj zgodnie z wyświetlanymi instrukcjami, aby ukończyć proces rejestracji. 

### <a name="enroll-by-using-a-qr-code"></a>Rejestracja przy użyciu kodu QR

Na urządzeniach z systemem Android 7 lub nowszym można zeskanować kod QR z profilu rejestracji w celu zarejestrowania urządzenia.

1. Aby uruchomić odczyt kodu QR na urządzeniu z systemem Android, naciśnij wielokrotnie pierwszy ekran, który zostanie wyświetlony po zresetowaniu do ustawień fabrycznych.
2. W przypadku urządzeń z systemem Android 7 i 8 zostanie wyświetlony monit o zainstalowanie czytnika kodów QR. Na urządzeniach z systemem Android 9 lub nowszym czytnik kodów QR jest już zainstalowany.
3. Użyj czytnika kodów QR, aby zeskanować kod QR profilu rejestracji, a następnie postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby ukończyć rejestrację.

### <a name="enroll-by-using-google-zero-touch"></a>Rejestracja przy użyciu programu Google Zero Touch

Aby korzystać z systemu Google Zero Touch, urządzenie musi go obsługiwać i być powiązane z dostawcą, który jest częścią usługi.  Aby uzyskać więcej informacji, zobacz [witrynę internetową programu Google Zero Touch](https://www.android.com/enterprise/management/zero-touch/). 


1. Utwórz nową konfigurację w konsoli Zero Touch.
2. Z listy rozwijanej EMM DPC (Kontroler zasad urządzenia EMM) wybierz pozycję **Microsoft Intune**.
3. W konsoli Zero Touch firmy Google skopiuj i wklej następujący kod JSON do pola dodatków kontrolera DPC. Zastąp ciąg *YourEnrollmentToken* tokenem rejestracji utworzonym jako część profilu rejestracji. Pamiętaj, aby ująć token rejestracji w cudzysłów.

```
{ 
    "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup", 

    "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": { 
        "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken" 
    } 
} 
```
4. Wybierz pozycję **Zastosuj**.

## <a name="managing-apps-on-android-kiosk-devices"></a>Zarządzanie aplikacjami na urządzeniach kiosku z systemem Android

Na urządzeniach kiosku z systemem Android można instalować tylko aplikacje, które mają typ przypisania [ustawiony na Wymagane](apps-deploy.md#to-assign-an-app). Aplikacje są instalowane z zarządzanego sklepu Google Play w taki sam sposób, jak w przypadku urządzeń z profilem służbowym systemu Android.

Aplikacje będą automatycznie aktualizowane na urządzeniach zarządzanych, gdy deweloper aplikacji opublikuje aktualizacje w sklepie Google Play.

Aby usunąć aplikację z urządzenia kiosku z systemem Android, wykonaj jedną z następujących czynności:
-   Usuń wdrożenie wymaganej aplikacji.
-   Utwórz wdrożenie odinstalowania dla aplikacji.


## <a name="next-steps"></a>Następne kroki
- [Wdrażanie aplikacji kiosku dla systemu Android](apps-deploy.md)
- [Dodawanie zasad konfiguracji kiosku z systemem Android](device-profiles.md)