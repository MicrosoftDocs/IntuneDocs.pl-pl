---
title: Konfigurowanie rejestracji w usłudze Intune dla dedykowanych urządzeń z systemem Android Enterprise
titleSuffix: Microsoft Intune
description: Dowiedz się, jak zarejestrować dedykowane urządzenia z systemem Android Enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4ff9126fec182d1e0d2f3eb75297ede8a632e2e
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390724"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Konfigurowanie rejestracji w usłudze Intune dla dedykowanych urządzeń z systemem Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

System Android Enterprise obsługuje należące do firmy kioski jednego przeznaczenia za pomocą zestawu rozwiązań urządzeń dedykowanych. Takie urządzenia są używane w jednym celu, na przykład do cyfrowego znakowania, drukowania biletów lub zarządzania zapasami. Administratorzy ograniczają użycie urządzenia do zdefiniowanego zestawu aplikacji i linków internetowych. Uniemożliwia to również użytkownikom dodawanie innych aplikacji i wykonywanie innych akcji na urządzeniu.

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na dedykowanych urządzeniach z systemem Android Enterprise. Aby uzyskać szczegółowe informacje na temat systemu Android Enterprise, zapoznaj się z [wymaganiami dotyczącymi systemu Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Urządzenia zarządzane w ten sposób są zarejestrowane w usłudze Intune bez konta użytkownika i nie są powiązane z żadnym użytkownikiem końcowym. Nie są one przeznaczone dla aplikacji do użytku osobistego ani aplikacji wymagających danych konta określonych dla użytkownika, takich jak program Outlook lub usługa Gmail.

## <a name="device-requirements"></a>Wymagania dotyczące urządzeń

Urządzenia muszą spełniać następujące wymagania, aby mogły być zarządzane jako dedykowane urządzenia z systemem Android Enterprise:

- System operacyjny Android w wersji 5.1 lub nowszy.
- Na urządzeniach musi działać dystrybucja systemu Android obsługująca łączność z usługami Google Mobile Services (GMS). Urządzenia muszą mieć dostępne usługi GMS i muszą być w stanie połączyć się z usługami GMS.

## <a name="set-up-android-enterprise-dedicated-device-management"></a>Konfigurowanie zarządzania dedykowanymi urządzeniami z systemem Android Enterprise

Aby skonfigurować zarządzanie dedykowanymi urządzeniami z systemem Android Enterprise, wykonaj następujące kroki:

1. Aby przygotować się do zarządzania urządzeniami przenośnymi, należy [ustawić urząd zarządzania urządzeniami przenośnymi (MDM, mobile device management) na **Microsoft Intune**](../fundamentals/mdm-authority-set.md) w celu uzyskania instrukcji. Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.
2. [Połącz konto dzierżawy usługi Intune z kontem zarządzanego sklepu Google Play](connect-intune-android-enterprise.md).
3. [Utwórz profil rejestracji](#create-an-enrollment-profile).
4. [Utwórz grupę urządzeń](#create-a-device-group).
5. [Zarejestruj urządzenia dedykowane](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Tworzenie profilu rejestracji

> [!NOTE]
> Jeśli token wygasł, skojarzony z nim profil nie będzie wyświetlany w sekcjach **Rejestrowanie urządzeń** > **Rejestracja systemu Android** > **Dedykowane urządzenia należące do firmy**. Aby wyświetlić wszystkie profile skojarzone zarówno z tokenami aktywnym, jak i nieaktywnym, kliknij pozycję **Filtruj** i zaznacz pola wyboru dla stanów zasad „Aktywne” i „Nieaktywne”. 

Aby zarejestrować urządzenia dedykowane, należy utworzyć profil rejestracji. Po utworzeniu profilu udostępnia on token rejestracji (losowy ciąg) i kod QR. W zależności od systemu operacyjnego Android i wersji urządzenia możesz użyć tokenu lub kodu QR, aby [zarejestrować urządzenie dedykowane](#enroll-the-dedicated-devices).

1. Zaloguj się w [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) i wybierz pozycje **Rejestrowanie urządzenia** > **Rejestracja systemu Android** > **Dedykowane urządzenia należące do firmy**.
2. Wybierz pozycję **Utwórz** i wypełnij wymagane pola.
    - **Nazwa**: wpisz nazwę, która będzie używana podczas przypisywania profilu do dynamicznej grupy urządzeń.
    - **Data wygaśnięcia tokenu**: Data, kiedy wygasa token. Firma Google wymusza maksymalnie 90 dni.
3. Wybierz pozycję **Utwórz**, aby zapisać profil.

### <a name="create-a-device-group"></a>Tworzenie grupy urządzeń

Aplikacje i zasady można zastosować do przypisanych albo dynamicznych grup urządzeń. Można skonfigurować dynamiczne grupy urządzeń usługi AAD, aby automatycznie wypełnić listę urządzeń zarejestrowanych przy użyciu określonego profilu rejestracji. W tym celu wykonaj następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) i wybierz pozycję **Grupy** > **Wszystkie grupy** > **Nowa grupa**.
2. W bloku **Grupa** wypełnij wymagane pola w następujący sposób:
    - **Typ grupy**: Zabezpieczenia
    - **Nazwa grupy**: wpisz intuicyjną nazwę (na przykład Urządzenia z fabryki 1)
    - **Typ członkostwa**: urządzenie dynamiczne
3. Wybierz pozycję **Dodaj zapytanie dynamiczne**.
4. W bloku **Reguły członkostwa dynamicznego** wypełnij pola w następujący sposób:
    - **Dodaj dynamiczną regułę członkostwa**: reguła prosta
    - **Dodaj urządzenia, na których**: enrollmentProfileName
    - W środkowym polu wybierz pozycję **Równa się**.
    - W ostatnim polu wprowadź nazwę profilu rejestracji, który został utworzony wcześniej.
    Aby uzyskać więcej informacji na temat reguł członkostwa dynamicznego, zobacz [Dynamic membership rules for groups in AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) (Reguły członkostwa dynamicznego dla grup w usłudze AAD). 
5. Wybierz pozycję **Dodaj zapytanie** > **Utwórz**.

### <a name="replace-or-remove-tokens"></a>Zamiana lub usuwanie tokenów

- **Zamień token**: za pomocą opcji Zamień token możesz wygenerować nowy token/kod QR, gdy ten będzie bliski wygaśnięcia.
- **Odwołaj token**: możesz natychmiast unieważnić token/kod QR. Od tego momentu użycie tokenu/kodu QR nie będzie już możliwe. Z tej opcji można skorzystać w następujących przypadkach:
  - Przypadkowo udostępniono token/kod QR nieautoryzowanej osobie
  - Ukończono wszystkie rejestracje i token/kod QR nie jest już potrzebny

Zamiana lub odwołanie tokenu/kodu QR nie będzie miała żadnego wpływu na urządzenia, które są już zarejestrowane.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) i wybierz pozycje **Rejestrowanie urządzenia** > **Rejestracja systemu Android** > **Dedykowane urządzenia należące do firmy**.
2. Wybierz profil, z którym chcesz pracować.
3. Wybierz **Token**.
4. Aby zamienić token, wybierz opcję **Zamień token**.
5. Aby odwołać token, wybierz opcję **Odwołaj token**.

## <a name="enroll-the-dedicated-devices"></a>Rejestrowanie urządzeń dedykowanych

Teraz możesz [zarejestrować swoje urządzenia dedykowane](android-dedicated-devices-fully-managed-enroll.md).

> [!NOTE]
> Aplikacja **Microsoft Intune** zostanie zainstalowana automatycznie podczas rejestrowania dedykowanego urządzenia.  Ta aplikacja jest wymagana w celu rejestracji i nie można jej odinstalować. 

## <a name="managing-apps-on-android-enterprise-dedicated-devices"></a>Zarządzanie aplikacjami na dedykowanych urządzeniach z systemem Android Enterprise

Na dedykowanych urządzeniach z systemem Android Enterprise można instalować tylko aplikacje, które mają typ przypisania [ustawiony na Wymagane](../apps/apps-deploy.md#assign-an-app). Aplikacje są instalowane z zarządzanego sklepu Google Play w taki sam sposób, jak w przypadku urządzeń z profilem służbowym systemu Android Enterprise.

Aplikacje będą automatycznie aktualizowane na urządzeniach zarządzanych, gdy deweloper aplikacji opublikuje aktualizacje w sklepie Google Play.

Aby usunąć aplikację z dedykowanych urządzeń z systemem Android Enterprise, wykonaj jedną z następujących czynności:
- Usuń wdrożenie wymaganej aplikacji.
- Utwórz wdrożenie odinstalowania dla aplikacji.

## <a name="next-steps"></a>Następne kroki
- [Wdrażanie aplikacji dla systemu Android](../apps/apps-deploy.md)
- [Dodawanie zasad konfiguracji systemu Android](../configuration/device-profiles.md)
