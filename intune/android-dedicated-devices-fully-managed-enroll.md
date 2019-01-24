---
title: Rejestrowanie dedykowanych lub w pełni zarządzanych urządzeń z systemem Android w usłudze Intune
titlesuffix: Microsoft Intune
description: Dowiedz się, jak rejestrować dedykowane lub w pełni zarządzane urządzenia z systemem Android Enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 9f9f95c42be252e0b2be515344e01a1d93e2cc6c
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54387221"
---
# <a name="enroll-your-android-dedicated-devices-or-fully-managed-devices-preview"></a>Rejestrowanie dedykowanych lub w pełni zarządzanych urządzeń z systemem Android (wersja zapoznawcza)

Po skonfigurowaniu [dedykowanych](android-kiosk-enroll.md) lub [w pełni zarządzanych](android-fully-managed-enroll.md) urządzeń z systemem Android w usłudze Intune możesz zarejestrować te urządzenia. Sposób rejestrowania urządzeń z systemem Android zależy od systemu operacyjnego.

| Metoda rejestracji | Minimalna wersja systemu operacyjnego Android dla urządzeń dedykowanych | Minimalna wersja systemu operacyjnego Android dla urządzeń w pełni zarządzanych |
| ----- | ----- | ----- |
| Komunikacja zbliżeniowa | 5.1 | 6.0 |
| Wpis tokenu | 6.0 | 6.0 |
| Kod QR | 7.0 | 7.0 |
| Zero Touch  | 8.0\* | 8.0\* |

\* W przypadku producentów uczestniczących w programie.

### <a name="enroll-by-using-near-field-communication-nfc"></a>Rejestracja przy użyciu komunikacji zbliżeniowej (NFC)

W przypadku urządzeń obsługujących komunikację zbliżeniową (NFC, Near Field Communication) urządzenia można aprowizować, tworząc specjalnie sformatowany tag NFC. W tym celu możesz użyć własnej aplikacji lub narzędzia kreatora tagu NFC. Aby uzyskać więcej informacji, zobacz temat [Oparta na technologii NFC rejestracja urządzeń z systemem Android Enterprise w usłudze Microsoft Intune](https://blogs.technet.microsoft.com/cbernier/2018/10/15/nfc-based-android-enterprise-device-enrollment-with-microsoft-intune/) i zapoznaj się z [dokumentacją interfejsu API zarządzania systemem Android firmy Google](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Rejestracja przy użyciu tokenu

W przypadku urządzeń z systemem Android 6 lub nowszym można użyć tokenu do zarejestrowania urządzenia. System Android 6.1 i jego nowsze wersje mogą również używać skanowania kodu QR w przypadku korzystania z metody rejestracji **aft#setup**.

1. Włącz wyczyszczone urządzenie.
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

> [!Note]
> Powiększenie w przeglądarce może spowodować, że urządzenie nie będzie mogło zeskanować kodu QR. Aby rozwiązać problem, można zwiększyć powiększenie.

1. Aby uruchomić odczyt kodu QR na urządzeniu z systemem Android, naciśnij wielokrotnie pierwszy ekran, który zostanie wyświetlony po wyczyszczeniu.
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


## <a name="next-steps"></a>Następne kroki
- [Wdrażanie aplikacji dla systemu Android](apps-deploy.md)
- [Dodawanie zasad konfiguracji systemu Android](device-profiles.md)

