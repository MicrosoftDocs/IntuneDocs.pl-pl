---
title: Konfiguracja rejestracji w usłudze Intune dla dedykowanych urządzeń z rozwiązaniem Android enterprise
titlesuffix: Microsoft Intune
description: Dowiedz się, jak zarejestrować dedykowane urządzenia z rozwiązaniem Android enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 4a6818f67ab4e3b04364b412fb8ecf71227328d4
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54386916"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Konfiguracja rejestracji w usłudze Intune dla dedykowanych urządzeń z rozwiązaniem Android enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

System Android obsługuje należące do firmy kioski jednego przeznaczenia za pomocą zestawu rozwiązań urządzeń dedykowanych. Takie urządzenia są używane w jednym celu, na przykład do cyfrowego znakowania, drukowania biletów lub zarządzania zapasami. Administratorzy ograniczają użycie urządzenia do zdefiniowanego zestawu aplikacji i linków internetowych. Uniemożliwia to również użytkownikom dodawanie innych aplikacji i wykonywanie innych akcji na urządzeniu.

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na dedykowanych urządzeniach z systemem Android. Aby uzyskać szczegółowe informacje na temat rozwiązania Android enterprise, zobacz [wymagania dotyczące rozwiązania Android enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Urządzenia zarządzane w ten sposób są zarejestrowane w usłudze Intune bez konta użytkownika i nie są powiązane z żadnym użytkownikiem końcowym. Nie są one przeznaczone dla aplikacji do użytku osobistego ani aplikacji wymagających danych konta określonych dla użytkownika, takich jak program Outlook lub usługa Gmail.

## <a name="device-requirements"></a>Wymagania dotyczące urządzeń

Urządzenia muszą spełniać następujące wymagania, aby mogły być zarządzane jako dedykowane urządzenia w ramach rozwiązania Android enterprise:

- System operacyjny Android w wersji 5.1 lub nowszy.
- Na urządzeniach musi działać dystrybucja systemu Android obsługująca łączność z usługami Google Mobile Services (GMS). Urządzenia muszą mieć dostępne usługi GMS i muszą być w stanie połączyć się z usługami GMS.

## <a name="set-up-android-dedicated-device-management"></a>Konfigurowanie zarządzania dedykowanymi urządzeniami z systemem Android

Aby skonfigurować zarządzanie dedykowanymi urządzeniami z systemem Android, wykonaj następujące kroki:

1. Aby przygotować się do zarządzania urządzeniami przenośnymi, należy [ustawić urząd zarządzania urządzeniami przenośnymi (MDM, mobile device management) na **Microsoft Intune**](mdm-authority-set.md) w celu uzyskania instrukcji. Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.
2. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android enterprise](connect-intune-android-enterprise.md).
3. [Utwórz profil rejestracji](#create-an-enrollment-profile).
4. [Utwórz grupę urządzeń](#create-a-device-group).
5. [Zarejestruj urządzenia dedykowane](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Tworzenie profilu rejestracji

Aby zarejestrować urządzenia dedykowane, należy utworzyć profil rejestracji. Po utworzeniu profilu udostępnia on token rejestracji (losowy ciąg) i kod QR. W zależności od systemu operacyjnego Android i wersji urządzenia możesz użyć tokenu lub kodu QR, aby [zarejestrować urządzenie dedykowane](#enroll-the-dedicated-devices).

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Rejestracja urządzeń** > **Rejestracja urządzenia z systemem Android** > **Rejestracja urządzenia kiosku i zadań**.
2. Wybierz pozycję **Utwórz** i wypełnij wymagane pola.
    - **Nazwa**: wpisz nazwę, która będzie używana podczas przypisywania profilu do dynamicznej grupy urządzeń.
    - **Data wygaśnięcia tokenu**: Data, kiedy wygasa token. Firma Google wymusza maksymalnie 90 dni.
3. Wybierz pozycję **Utwórz**, aby zapisać profil.

### <a name="create-a-device-group"></a>Tworzenie grupy urządzeń

Aplikacje i zasady można zastosować do przypisanych albo dynamicznych grup urządzeń. Można skonfigurować dynamiczne grupy urządzeń usługi AAD, aby automatycznie wypełnić listę urządzeń zarejestrowanych przy użyciu określonego profilu rejestracji. W tym celu wykonaj następujące czynności:

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Grupy** > **Wszystkie grupy** > **Nowa grupa**.
2. W bloku **Grupa** wypełnij wymagane pola w następujący sposób:
    - **Typ grupy**: Zabezpieczenia
    - **Nazwa grupy**: wpisz intuicyjną nazwę (na przykład Urządzenia z fabryki 1)
    - **Typ członkostwa**: urządzenie dynamiczne
3. Wybierz pozycję **Dodaj zapytanie dynamiczne**.
4. W bloku **Reguły członkostwa dynamicznego** wypełnij pola w następujący sposób:
    - **Dodaj dynamiczną regułę członkostwa**: reguła prosta
    - **Dodaj urządzenia, na których**: enrollmentProfileName
    - W środkowym polu wybierz pozycję **Dopasowanie**.
    - W ostatnim polu wprowadź nazwę profilu rejestracji, który został utworzony wcześniej.
    Aby uzyskać więcej informacji na temat reguł członkostwa dynamicznego, zobacz [Dynamic membership rules for groups in AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) (Reguły członkostwa dynamicznego dla grup w usłudze AAD). 
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

## <a name="enroll-the-dedicated-devices"></a>Rejestrowanie urządzeń dedykowanych

Teraz możesz [zarejestrować swoje urządzenia dedykowane](android-dedicated-devices-fully-managed-enroll.md).

## <a name="managing-apps-on-android-dedicated-devices"></a>Zarządzanie aplikacjami na dedykowanych urządzeniach z systemem Android

Na dedykowanych urządzeniach z systemem Android można instalować tylko aplikacje, które mają typ przypisania [ustawiony na Wymagane](apps-deploy.md#to-assign-an-app). Aplikacje są instalowane z zarządzanego sklepu Google Play w taki sam sposób, jak w przypadku urządzeń z profilem służbowym systemu Android.

Aplikacje będą automatycznie aktualizowane na urządzeniach zarządzanych, gdy deweloper aplikacji opublikuje aktualizacje w sklepie Google Play.

Aby usunąć aplikację z dedykowanego urządzenia z systemem Android, wykonaj jedną z następujących czynności:
-   Usuń wdrożenie wymaganej aplikacji.
-   Utwórz wdrożenie odinstalowania dla aplikacji.

## <a name="next-steps"></a>Następne kroki
- [Wdrażanie aplikacji dla systemu Android](apps-deploy.md)
- [Dodawanie zasad konfiguracji systemu Android](device-profiles.md)
