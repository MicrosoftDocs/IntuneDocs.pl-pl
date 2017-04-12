---
title: Dodawanie aplikacji | Microsoft Docs
description: "Przed rozpoczęciem wdrażania aplikacji za pomocą usługi Intune poświęć trochę czasu na zapoznanie się z pojęciami opisanymi w tym temacie."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a85b9f603e022b3296cb16754effd06087074a72
ms.openlocfilehash: c294a0abaf69017b6c098a95870fc035f28d0787
ms.lasthandoff: 04/01/2017


---

# <a name="add-apps-with-microsoft-intune"></a>Dodawanie aplikacji za pomocą usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Przed rozpoczęciem wdrażania aplikacji za pomocą usługi Microsoft Intune poświęć trochę czasu na zapoznanie się z pojęciami opisanymi w tym temacie. Te pojęcia ułatwiają zrozumienie aplikacji, które można wdrożyć na poszczególnych platformach. Ułatwiają także zrozumienie wymagań wstępnych, które należy spełnić przed wdrożeniem aplikacji.

## <a name="app-types-that-you-can-deploy"></a>Typy aplikacji, które można wdrożyć

### <a name="software-installer"></a>Instalator oprogramowania

|Typ aplikacji|Szczegóły|
|----------------|-------|
|**Instalator Windows (&#42;.exe, &#42;.msi)**|Ten typ aplikacji musi obsługiwać instalację dyskretną bez udziału użytkownika. Dokumentacja aplikacji powinna zawierać odpowiednie opcje wiersza polecenia do przeprowadzenia instalacji dyskretnej aplikacji (na przykład **/q**). Listę typowych opcji wiersza polecenia można znaleźć w artykule [Przełączniki wiersza polecenia dla narzędzia Instalatora Microsoft Windows](https://support.microsoft.com/en-us/kb/227091).<br><br>Wszelkie dodatkowe pliki i foldery wymagane przez program instalacyjny aplikacji muszą być dostępne w lokalizacji określonej dla plików instalacyjnych aplikacji.<br><br>W większości przypadków pliki Instalatora systemu Windows (msi) i pliki poprawek Instalatora Windows (msp) nie wymagają instalacji żadnych argumentów wiersza polecenia przez usługę Intune. Zajrzyj do dokumentacji aplikacji.<br><br>Jeśli argumenty wiersza polecenia są wymagane, muszą zostać wprowadzone jako pary nazwa=wartość (na przykład TRANSFORMS=custom_transform.mst).<br><br>Ten typ aplikacji dotyczy tylko komputerów, na których uruchomiono oprogramowanie klienckie usługi Intune.|
|**Pakiet aplikacji dla systemu Android (&#42;.apk)**|Do wdrożenia aplikacji dla systemu Android potrzebny jest prawidłowy pakiet apk.|
|**Pakiet aplikacji dla systemu iOS (&#42;.ipa)**|Do wdrożenia aplikacji dla systemu iOS potrzebny jest prawidłowy plik pakietu ipa.<br><br>Pakiet ipa musi być podpisany przez firmę Apple, a data wygaśnięcia w profilu inicjowania obsługi administracyjnej musi być ważna. Usługa Intune może dystrybuować aplikacje dla systemu iOS z certyfikatem przedsiębiorstwa.<br><br>Nie wszystkie aplikacje z certyfikatem deweloperów firmy Apple są obsługiwane.<br><br>Firma musi być zarejestrowana w programie dla deweloperów aplikacji systemu iOS dla przedsiębiorstw (iOS Developer Enterprise Program).<br><br>Upewnij się, że zapora organizacji zezwala na dostęp do witryn sieci Web obsługi administracyjnej i certyfikacji systemu iOS.<br><br>Nie musisz wdrażać pliku manifestu (plist) z aplikacją.|
|**Pakiet aplikacji systemu Windows Phone (&#42;.xap, .appx, .appxbundle)**|Aby wdrożyć aplikacje, wymagany jest firmowy mobilny certyfikat podpisywania kodu. Aby uzyskać więcej szczegółów, zobacz [Konfigurowanie zarządzania systemem Windows Phone przy użyciu usługi Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Pakiet aplikacji systemu Windows (.appx, .appxbundle)**|Aby wdrożyć aplikacje, wymagany jest firmowy mobilny certyfikat podpisywania kodu. Aby uzyskać więcej szczegółów, zobacz [Konfigurowanie zarządzania urządzeniami z systemem Windows przy użyciu usługi Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Instalator Windows przy użyciu systemu MDM (&#42;.msi)**|Aplikacja umożliwia tworzenie i wdrażanie aplikacji opartych na Instalatorze Windows na zarejestrowanych komputerach z systemem Windows 10. Te komputery są zarządzane przy użyciu funkcji zarządzania urządzeniami przenośnymi (MDM).<br /><br />Możesz przekazać tylko jeden plik z rozszerzeniem msi.<br><br>Kod i wersja produktu pliku są używane do wykrywania aplikacji.<br><br>Zostanie zastosowane domyślne zachowanie dotyczące ponownego uruchamiania Nie jest to kontrolowane przez usługę Intune.<br><br>Pakiety MSI dla użytkownika zostaną zainstalowane dla pojedynczego użytkownika.<br><br>Pakiety MSI dla maszyny zostaną zainstalowane dla wszystkich użytkowników urządzenia.<br><br>Obecnie pakiety MSI w trybie podwójnym są instalowane dla wszystkich użytkowników urządzenia.<br><br>Aktualizacje aplikacji są obsługiwane, jeśli kod produktu MSI jest taki sam dla każdej wersji.<br>
Wszystkie typy aplikacji instalatora oprogramowania są przekazywane do magazynu w chmurze.

### <a name="external-link"></a>**Link zewnętrzny**
Użyj linku zewnętrznego, jeśli masz:
- Adres URL, który umożliwia użytkownikom pobieranie aplikacji ze sklepu App Store.
- Link do aplikacji sieci Web uruchamianej w przeglądarce sieci Web.

Aplikacje oparte na linkach zewnętrznych nie są przechowywane w magazynie w chmurze usługi Intune.
### <a name="managed-ios-app-from-the-app-store"></a>**Zarządzana aplikacja systemu iOS ze sklepu App Store**
Zarządzane aplikacje systemu iOS umożliwiają zarządzanie bezpłatnymi aplikacjami ze sklepu App Store dla systemu iOS i ich wdrażanie. Zarządzane aplikacje systemu iOS można również wykorzystać do skojarzenia [zasad zarządzania aplikacjami mobilnymi](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) ze [zgodnymi aplikacjami](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) i sprawdzać ich stan w konsoli administracyjnej.<br /><br />Zarządzane aplikacje dla systemu iOS nie są przechowywane w magazynie w chmurze usługi Intune.

> [!TIP]
> Opcje dla urządzeń przenośnych nie są dostępne, dopóki usługa Intune [nie zostanie ustawiona jako źródło MDM](prerequisites-for-enrollment.md).

## <a name="intune-software-publisher"></a>Wydawca oprogramowania usługi Intune
Wydawca oprogramowania usługi Microsoft Intune jest uruchamiany podczas dodawania lub modyfikowania aplikacji w konsoli administratora usługi Intune. Wydawca umożliwia wybranie i skonfigurowanie typu instalatora oprogramowania, który:

- Przekazuje aplikacje (programy komputerowe lub aplikacje dla urządzeń mobilnych) do zapisania w magazynie w chmurze usługi Intune.
- Zawiera link do sklepu online lub aplikacji sieci Web.

Przed rozpoczęciem korzystania z wydawcy oprogramowania należy zainstalować pełną wersję programu [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Po zainstalowaniu może być konieczne ponowne uruchomienie komputera, aby wydawca oprogramowania został poprawnie otwarty.

## <a name="cloud-storage-space"></a>Miejsce do magazynowania w chmurze
Wszystkie aplikacje tworzone przy użyciu instalatora oprogramowania (na przykład aplikacje biznesowe) zostają spakowane i przekazane do magazynu w chmurze usługi Microsoft Intune. Subskrypcja próbna usługi Intune obejmuje 2 GB magazynu opartego na chmurze, który jest używany do przechowywania zarządzanych aplikacji i aktualizacji. Pełna subskrypcja obejmuje 20 GB miejsca do magazynowania.

Sprawdzenia ilości wykorzystanego miejsca można dokonać w węźle **Użycie magazynu** w obszarze roboczym **Administrator**. Możesz kupić dodatkowy magazyn dla usługi Intune przy użyciu pierwotnej metody zakupu.  Jeśli zakupu dokonano przy użyciu faktury lub karty kredytowej, odwiedź [portal zarządzania subskrypcją](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  W przeciwnym razie skontaktuj się ze swoim partnerem lub współpracownikiem ds. sprzedaży.

Wymagania dotyczące miejsca do magazynowania w chmurze są następujące:

-   Wszystkie pliki instalacyjne aplikacji muszą znajdować się w tym samym folderze.
-   Maksymalny rozmiar dowolnego przekazywanego pliku wynosi 2 GB.


## <a name="support-for-universal-windows-platform-uwp-apps"></a>Obsługa aplikacji platformy uniwersalnej systemu Windows
Komputery z systemem Windows 10 nie wymagają klucza ładowania bezpośredniego, aby zainstalować aplikacje biznesowe. Jednak klucz rejestru **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** musi mieć wartość **1**, aby umożliwić ładowanie bezpośrednie.

Jeśli ten klucz rejestru nie jest skonfigurowany, usługa Intune automatycznie ustawi tę wartość na **1** podczas pierwszego wdrożenia aplikacji na urządzeniu. Jeśli tę wartość ustawiono na **0**, usługa Intune nie może automatycznie zmienić wartości i wdrożenie aplikacji biznesowych zakończy się niepowodzeniem.

Aplikacje biznesowe platformy uniwersalnej systemu Windows muszą być podpisane przy użyciu certyfikatu podpisywania kodu, który jest zaufany na każdym urządzeniu, na którym aplikacja jest wdrożona. Można użyć certyfikatu z wewnętrznej infrastruktury kluczy publicznych (PKI) lub certyfikatu z głównego certyfikatu publicznego innej firmy zainstalowanego na urządzeniu.

Na urządzeniach z systemem Windows 10 Mobile do podpisywania uniwersalnych aplikacji **appx** można użyć certyfikatu podpisywania kodu innego niż certyfikat firmy Symantec. Dla aplikacji **xap**, a także pakietów **appx** utworzonych dla systemu Windows Phone 8.1, które chcesz zainstalować na urządzeniach z systemem Windows 10 Mobile, należy korzystać z certyfikatu podpisywania kodu firmy Symantec.

### <a name="dependencies-for-uwp-apps"></a>Zależności dotyczące aplikacji platformy UWP

Po dodaniu uniwersalnego pakietu appxbundle systemu Windows 10 do usługi Intune upewnij się, że przekazane zostały wszystkie zależności aplikacji.
W tym celu zapewnij, aby folder **Zależności** utworzony podczas kompilowania aplikacji znajdował się w tym samym folderze, co plik .appxbundle.
W ten sposób podczas przekazywania aplikacji do usługi Intune zostaną również przekazane wszystkie pliki folderu **Zależności**. Tę sytuację ilustruje poniższy zrzut ekranu:


![Jak wybrać zależności appxbundle platformy UWP systemu Windows 10](./media/w10-dependencies.png)


## <a name="next-steps"></a>Następne kroki

Należy dodać aplikacje w konsoli usługi Intune przed ich wdrożeniem. Aplikacje można dodawać dla [zarejestrowanych urządzeń](add-apps-for-mobile-devices-in-microsoft-intune.md) lub [komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

