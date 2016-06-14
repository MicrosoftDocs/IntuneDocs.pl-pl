---
# required metadata

title: Dodawanie aplikacji | Usługa Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Dodawanie aplikacji za pomocą usługi Microsoft Intune
Przed rozpoczęciem wdrażania aplikacji za pomocą usługi Microsoft Intune poświęć trochę czasu na zapoznanie się z pojęciami opisanymi w tym temacie. Informacje te ułatwią zrozumienie, które aplikacje można wdrożyć na poszczególnych platformach, a także zrozumienie koniecznych do spełnienia wymagań wstępnych.

## Typy aplikacji, które można wdrożyć za pomocą usługi Intune
Aplikacje można wdrażać na wszystkich typach urządzeń obsługiwanych przez usługę Intune. W zależności od typu aplikacji do wdrożenia różnić się będzie sam proces wdrożenia i obsługiwane urządzenia. W poniższej tabeli opisano aplikacje, które można i których nie można wdrożyć.


### **Instalator Windows (&#42;.exe, &#42;.msi)**
- Ten typ aplikacji musi obsługiwać instalację dyskretną bez udziału użytkownika. Dokumentacja aplikacji powinna zawierać odpowiednie opcje wiersza polecenia do przeprowadzenia instalacji dyskretnej aplikacji (na przykład **/q**).).
- Wszelkie dodatkowe pliki i foldery, które są wymagane przez program instalacyjny aplikacji, muszą być dostępne w lokalizacji określonej dla plików instalacyjnych aplikacji.
- W większości przypadków pliki Instalatora Windows (msi) i pliki poprawek Instalatora Windows (msp) nie wymagają żadnych argumentów wiersza polecenia do zainstalowania przez usługę Intune. Zajrzyj do dokumentacji aplikacji. Jeśli argumenty wiersza polecenia są wymagane, muszą zostać wprowadzone jako pary nazwa=wartość (na przykład TRANSFORMS=custom_transform.mst).

Ten typ aplikacji jest przekazywany do magazynu w chmurze.
### **Pakiet aplikacji dla systemu Android (plik &#42;.apk)**
Ten typ aplikacji jest przekazywany do magazynu w chmurze.
### **Pakiet aplikacji dla systemu iOS (plik &#42;.ipa)**
- Do wdrożenia aplikacji dla systemu iOS potrzebny jest prawidłowy plik pakietu ipa.
- Pakiet ipa musi być podpisany przez firmę Apple, a data wygaśnięcia wskazana w profilu inicjowania obsługi administracyjnej musi być ważna. Usługa Intune może dystrybuować aplikacje dla systemu iOS z certyfikatem przedsiębiorstwa. Nie wszystkie aplikacje z certyfikatem deweloperów firmy Apple są obsługiwane.
- Firma musi być zarejestrowana w programie dla deweloperów aplikacji systemu iOS dla przedsiębiorstw (iOS Developer Enterprise Program).
- Upewnij się, że zapora organizacji zezwala na dostęp do witryn sieci Web obsługi administracyjnej i certyfikacji systemu iOS.
- Plik manifestu (plist) nie jest wymagany do wdrożenia z aplikacją.

Ten typ aplikacji jest przekazywany do magazynu w chmurze.

Obecnie użytkownicy końcowi nie mogą instalować aplikacji firmowych za pomocą aplikacji Portal firmy usługi Intune dla systemu iOS. Jest to spowodowane ograniczeniami dotyczącymi aplikacji opublikowanych w sklepie App Store dla systemu iOS. Zobacz [App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/) (Wytyczne dotyczące sklepu App Store). Użytkownicy mają dostęp do aplikacji firmowych (w tym aplikacji zarządzanych ze sklepu App Store oraz pakietów aplikacji biznesowych) przez uruchomienie aplikacji Portal firmy na urządzeniu. W tym celu należy nacisnąć kafelek Company Apps (Aplikacje firmowe), co spowoduje uruchomienie przeglądarki i przekierowanie do portalu sieci Web usługi Intune.

### **Pakiet aplikacji systemu Windows Phone (&#42;.xap, .appx, .appxbundle)**
- Aby wdrożyć aplikacje, wymagany jest firmowy mobilny certyfikat podpisywania kodu. Aby uzyskać więcej szczegółów, zobacz [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)..

Ten typ aplikacji jest przekazywany do magazynu w chmurze.

Poniżej dostępne są informacje dotyczące instalowania aplikacji biznesowych platformy uniwersalnej systemu Windows za pomocą usługi Intune.

### **Pakiet aplikacji systemu Windows (.appx, .appxbundle)**
- Aby wdrożyć aplikacje, wymagany jest firmowy mobilny certyfikat podpisywania kodu. Aby uzyskać więcej szczegółów, zobacz [Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)..

Ten typ aplikacji jest przekazywany do magazynu w chmurze.
### **Instalator Windows korzystający z funkcji zarządzania urządzeniami przenośnymi (&#42;.msi)**
Ten typ instalatora umożliwia tworzenie i wdrażanie aplikacji opartych na Instalatorze Windows na zarejestrowanych komputerach z systemem Windows 10.<br /><br />W przypadku korzystania z instalatora tego typu należy wziąć pod uwagę następujące kwestie:
- Możesz przekazać tylko jeden plik z rozszerzeniem msi.
- Kod i wersja produktu pliku są używane do wykrywania aplikacji.
- Zostanie zastosowane domyślne zachowanie dotyczące ponownego uruchamiania Nie jest to kontrolowane przez usługę Intune.
- Pakiety MSI dla użytkownika zostaną zainstalowane dla pojedynczego użytkownika.
- Pakiety MSI dla maszyny zostaną zainstalowane dla wszystkich użytkowników urządzenia.
- Obecnie pakiety MSI w trybie podwójnym są instalowane dla wszystkich użytkowników urządzenia.
- Aktualizacje aplikacji są obsługiwane, jeśli kod produktu MSI jest taki sam dla każdej wersji.

Ten typ aplikacji jest przekazywany do magazynu w chmurze.
### **Link zewnętrzny**
Używany w przypadku, gdy posiadasz:
- **Adres URL**, który umożliwia użytkownikom pobieranie aplikacji ze sklepu App Store.
- **Link** do aplikacji sieci Web uruchamianej w przeglądarce sieci Web.

Aplikacje oparte na linkach zewnętrznych nie są przechowywane w magazynie w chmurze usługi Intune.
### **Zarządzana aplikacja systemu iOS ze sklepu App Store**
Umożliwia zarządzanie bezpłatnymi aplikacjami ze sklepu App Store dla systemu iOS i zarządzanie nimi. Umożliwia również skojarzenie [zasad zarządzania aplikacjami mobilnymi](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) ze [zgodnymi aplikacjami](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) i sprawdzanie ich stanu w konsoli administratora.<br /><br />Zarządzane aplikacje dla systemu iOS nie są przechowywane w magazynie w chmurze usługi Intune.
> [!TIP]
> Opcje dla urządzeń przenośnych nie są dostępne, dopóki usługa Intune [nie zostanie ustawiona jako Źródło zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md).

## Obsługa aplikacji platformy uniwersalnej systemu Windows
Urządzenia z systemem Windows 10 nie wymagają klucza ładowania bezpośredniego, aby zainstalować aplikacje biznesowe. Jednak klucz rejestru **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** musi mieć wartość **1**, aby umożliwić ładowanie bezpośrednie.

Jeśli ten klucz rejestru nie jest skonfigurowany, usługa Intune automatycznie ustawi tę wartość na **1** podczas pierwszego wdrożenia aplikacji na urządzeniu. Jeśli tę wartość ustawiono na **0**, usługa Intune nie może automatycznie zmienić wartości i wdrożenie aplikacji biznesowych zakończy się niepowodzeniem.

Aplikacje biznesowe platformy uniwersalnej systemu Windows muszą być podpisane przy użyciu certyfikatu podpisywania kodu, który jest zaufany na każdym urządzeniu, na którym aplikacja jest wdrożona. Można użyć certyfikatów z wewnętrznej infrastruktury kluczy publicznych (PKI) lub certyfikatu z głównego certyfikatu publicznego innej firmy zainstalowanego na urządzeniu.

Na urządzeniach z systemem Windows 10 Mobile do podpisywania uniwersalnych aplikacji **appx** można użyć certyfikatu podpisywania kodu innego niż certyfikat firmy Symantec. Dla aplikacji **xap**, a także pakietów **appx** utworzonych dla systemu Windows Phone 8.1, które chcesz zainstalować na urządzeniach z systemem Windows 10 Mobile, należy korzystać z certyfikatu podpisywania kodu firmy Symantec.

## Następne kroki 

Następnie należy dodać aplikacje w konsoli usługi Intune przed ich wdrożeniem. Aplikacje można dodawać dla [zarejestrowanych urządzeń](add-apps-for-mobile-devices-in-microsoft-intune.md) lub [komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)..

<!--HONumber=May16_HO1-->


