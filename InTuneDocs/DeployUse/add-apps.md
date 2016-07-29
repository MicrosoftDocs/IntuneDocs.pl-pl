---
title: "Dodawanie aplikacji | Usługa Microsoft Intune"
description: "Przed rozpoczęciem wdrażania aplikacji za pomocą usługi Intune poświęć trochę czasu na zapoznanie się z pojęciami opisanymi w tym temacie."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 3b35e835634733f542b7ddaf2ede2ad2464721fd


---

# Dodawanie aplikacji za pomocą usługi Microsoft Intune
Przed rozpoczęciem wdrażania aplikacji za pomocą usługi Microsoft Intune poświęć trochę czasu na zapoznanie się z pojęciami opisanymi w tym temacie. Informacje te ułatwią zrozumienie, które aplikacje można wdrożyć na poszczególnych platformach, a także zrozumienie koniecznych do spełnienia wymagań wstępnych.

## Typy aplikacji, które można wdrożyć

### Instalator oprogramowania

|Typ aplikacji|Szczegóły|
|----------------|-------|
|**Instalator Windows (&#42;.exe, &#42;.msi)**|Ten typ aplikacji musi obsługiwać instalację dyskretną bez udziału użytkownika. Dokumentacja aplikacji powinna zawierać odpowiednie opcje wiersza polecenia do przeprowadzenia instalacji dyskretnej aplikacji (na przykład **/q**).<br>Listę typowych opcji wiersza polecenia można znaleźć [tutaj](https://support.microsoft.com/en-us/kb/227091).<br><br>Wszelkie dodatkowe pliki i foldery, które są wymagane przez program instalacyjny aplikacji, muszą być dostępne w lokalizacji określonej dla plików instalacyjnych aplikacji.<br><br>W większości przypadków pliki Instalatora Windows (msi) i pliki poprawek Instalatora Windows (msp) nie wymagają żadnych argumentów wiersza polecenia do zainstalowania przez usługę Intune. Zajrzyj do dokumentacji aplikacji.<br><br>Jeśli argumenty wiersza polecenia są wymagane, muszą zostać wprowadzone jako pary nazwa=wartość (na przykład TRANSFORMS=custom_transform.mst).|
|**Pakiet aplikacji dla systemu Android (plik &#42;.apk)**|Do wdrożenia aplikacji dla systemu Android potrzebny jest prawidłowy plik pakietu apk|
|**Pakiet aplikacji dla systemu iOS (plik &#42;.ipa)**|Do wdrożenia aplikacji dla systemu iOS potrzebny jest prawidłowy plik pakietu ipa.<br><br>Pakiet ipa musi być podpisany przez firmę Apple, a data wygaśnięcia wskazana w profilu inicjowania obsługi administracyjnej musi być ważna. Usługa Intune może dystrybuować aplikacje dla systemu iOS z certyfikatem przedsiębiorstwa.<br>Nie wszystkie aplikacje z certyfikatem deweloperów firmy Apple są obsługiwane.<br><br>Firma musi być zarejestrowana w programie dla deweloperów aplikacji systemu iOS dla przedsiębiorstw (iOS Developer Enterprise Program).<br><br>Upewnij się, że zapora organizacji zezwala na dostęp do witryn sieci Web obsługi administracyjnej i certyfikacji systemu iOS.<br><br>Nie musisz wdrażać pliku manifestu (plist) z aplikacją.|
|**Pakiet aplikacji systemu Windows Phone (&#42;.xap, .appx, .appxbundle)**|Aby wdrożyć aplikacje, wymagany jest firmowy mobilny certyfikat podpisywania kodu.<br>Aby uzyskać więcej szczegółów, zobacz [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).|
|**Pakiet aplikacji systemu Windows (.appx, .appxbundle)**|Aby wdrożyć aplikacje, wymagany jest firmowy mobilny certyfikat podpisywania kodu.<br>Aby uzyskać więcej szczegółów, zobacz [Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Instalator Windows korzystający z funkcji zarządzania urządzeniami przenośnymi (&#42;.msi)**|Umożliwia tworzenie i wdrażanie aplikacji opartych na Instalatorze Windows na zarejestrowanych komputerach z systemem Windows 10 (zarządzanych przez funkcję MDM).<br /><br />Możesz przekazać tylko jeden plik z rozszerzeniem msi.<br><br>Kod i wersja produktu pliku są używane do wykrywania aplikacji.<br><br>Zostanie zastosowane domyślne zachowanie dotyczące ponownego uruchamiania Nie jest to kontrolowane przez usługę Intune.<br><br>Pakiety MSI dla użytkownika zostaną zainstalowane dla pojedynczego użytkownika.<br><br>Pakiety MSI dla maszyny zostaną zainstalowane dla wszystkich użytkowników urządzenia.<br><br>Obecnie pakiety MSI w trybie podwójnym są instalowane dla wszystkich użytkowników urządzenia.<br><br>Aktualizacje aplikacji są obsługiwane, jeśli kod produktu MSI jest taki sam dla każdej wersji.<br>
Wszystkie typy aplikacji instalatora oprogramowania są przekazywane do magazynu w chmurze.

### **Link zewnętrzny**
Używany w przypadku, gdy posiadasz:
- **Adres URL**, który umożliwia użytkownikom pobieranie aplikacji ze sklepu App Store.
- **Link** do aplikacji sieci Web uruchamianej w przeglądarce sieci Web.

Aplikacje oparte na linkach zewnętrznych nie są przechowywane w magazynie w chmurze usługi Intune.
### **Zarządzana aplikacja systemu iOS ze sklepu App Store**
Umożliwia zarządzanie bezpłatnymi aplikacjami ze sklepu App Store dla systemu iOS i zarządzanie nimi. Umożliwia również skojarzenie [zasad zarządzania aplikacjami mobilnymi](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) ze [zgodnymi aplikacjami](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) i sprawdzanie ich stanu w konsoli administratora.<br /><br />Zarządzane aplikacje dla systemu iOS nie są przechowywane w magazynie w chmurze usługi Intune.

> [!TIP]
> Opcje dla urządzeń przenośnych nie są dostępne, dopóki usługa Intune [nie zostanie ustawiona jako Źródło zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md).

## Wydawca oprogramowania usługi Intune
**Wydawca oprogramowania usługi Microsoft Intune** jest uruchamiany podczas dodawania lub modyfikowania aplikacji w konsoli administratora usługi Intune. Za pomocą wydawcy należy wybrać i skonfigurować typ instalatora oprogramowania, który przekaże aplikacje (programy dla komputerów lub aplikacje dla urządzeń przenośnych) do przechowywania w magazynie w chmurze usługi Intune albo utworzy link do aplikacji w sklepie online lub aplikacji internetowej.

Przed rozpoczęciem korzystania z wydawcy oprogramowania należy zainstalować pełną wersję programu [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Po zainstalowaniu może być konieczne ponowne uruchomienie komputera, aby wydawca oprogramowania został poprawnie otwarty.

## Miejsce do magazynowania w chmurze
Wszystkie aplikacje tworzone przy użyciu instalatora oprogramowania (na przykład aplikacje biznesowe) zostają spakowane i przekazane do magazynu w chmurze usługi Microsoft Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Pełna subskrypcja obejmuje 20 GB miejsca do magazynowania.

Sprawdzenia ilości wykorzystanego miejsca można dokonać w węźle **Użycie magazynu** w obszarze roboczym **Administrator**.

### Wymagania dotyczące miejsca do magazynowania w chmurze

-   Upewnij się, że wszystkie pliki instalacyjne aplikacji znajdują się w tym samym folderze.

-   Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.


## Obsługa aplikacji platformy uniwersalnej systemu Windows
Komputery z systemem Windows 10 nie wymagają klucza ładowania bezpośredniego, aby zainstalować aplikacje biznesowe. Jednak klucz rejestru **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** musi mieć wartość **1**, aby umożliwić ładowanie bezpośrednie.

Jeśli ten klucz rejestru nie jest skonfigurowany, usługa Intune automatycznie ustawi tę wartość na **1** podczas pierwszego wdrożenia aplikacji na urządzeniu. Jeśli tę wartość ustawiono na **0**, usługa Intune nie może automatycznie zmienić wartości i wdrożenie aplikacji biznesowych zakończy się niepowodzeniem.

Aplikacje biznesowe platformy uniwersalnej systemu Windows muszą być podpisane przy użyciu certyfikatu podpisywania kodu, który jest zaufany na każdym urządzeniu, na którym aplikacja jest wdrożona. Można użyć certyfikatów z wewnętrznej infrastruktury kluczy publicznych (PKI) lub certyfikatu z głównego certyfikatu publicznego innej firmy zainstalowanego na urządzeniu.

Na urządzeniach z systemem Windows 10 Mobile do podpisywania uniwersalnych aplikacji **appx** można użyć certyfikatu podpisywania kodu innego niż certyfikat firmy Symantec. Dla aplikacji **xap**, a także pakietów **appx** utworzonych dla systemu Windows Phone 8.1, które chcesz zainstalować na urządzeniach z systemem Windows 10 Mobile, należy korzystać z certyfikatu podpisywania kodu firmy Symantec.

## Następne kroki 

Następnie należy dodać aplikacje w konsoli usługi Intune przed ich wdrożeniem. Aplikacje można dodawać dla [zarejestrowanych urządzeń](add-apps-for-mobile-devices-in-microsoft-intune.md) lub [komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


