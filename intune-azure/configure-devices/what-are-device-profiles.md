---
title: "Co to są profile urządzeń w usłudze Microsoft Intune? | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: więcej informacji na temat profilów urządzeń w usłudze Intune i sposobu, w jaki mogą one być pomocne w zarządzaniu urządzeniami w Twojej firmie i ich ochronie."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 0e126c067b5c212ae5bfe1cf69e01128a00b1c8e


---

# <a name="what-are-device-profiles"></a>Co to są profile urządzeń?
<!--- This topic doesn't really answer the topic title: What are device profiles?" It needs to answer that question, then it can go on to discuss what profiles are in Intune and how to use them. Linda--->

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Użyj obciążenia **Konfigurowanie urządzeń** w usłudze Microsoft Intune do zarządzania ustawieniami i funkcjami na wszystkich urządzeniach zarządzanych.

Po otwarciu tego obciążenia zostaną wyświetlone następujące opcje:

- **Przegląd** — ta strona udostępnia stan i raporty pomagające w monitorowaniu konfiguracji urządzeń, które zostały przypisane do użytkowników i urządzeń.
- **Zarządzanie profilami** — w tej sekcji można utworzyć profile konfiguracji urządzenia. Poniższa lista zawiera wszystkie typy profilów, które można utworzyć.
- **Konfiguracja urzędu certyfikacji** — ten przepływ pracy przeprowadza przez kroki wymagane do skonfigurowania certyfikatów. Wykonanie tych czynności jest niezbędne do pracy z profilami certyfikatów usługi Intune.

## <a name="getting-started"></a>Wprowadzenie

Przepływ pracy związany z tworzeniem profilów urządzeń jest podobny dla wszystkich profilów. Informacje o sposobie tworzenia profilów można znaleźć w temacie [How to create Microsoft Intune device configuration profiles (Sposoby tworzenia profilów konfiguracji urządzeń w usłudze Microsoft Intune)](/intune-azure/configure-devices/how-to-create-device-profiles). W dalszej kolejności należy zapoznać się z konkretnymi informacjami na temat tworzenia ustawień dla każdego typu profilu.

Na urządzeniach można zarządzać następującymi możliwościami:

## <a name="device-restrictions"></a>Ograniczenia dotyczące urządzeń
Ograniczenia dotyczące urządzeń pozwalają na kontrolę szerokiego zakresu ustawień i funkcji, którymi można zarządzać w ramach wielu kategorii, w tym dotyczących zabezpieczeń, przeglądarki, sprzętu i ustawień związanych z udostępnianiem danych. Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure device restriction settings (Sposoby konfigurowania ustawień ograniczeń urządzenia)](how-to-configure-device-restrictions.md) Dotyczy systemów: Android, iOS, macOS, Windows 10 i Windows 10 Team.

## <a name="email"></a>Poczta e-mail
Profile poczty e-mail pozwalają na tworzenie, wdrażanie i monitorowanie ustawień poczty e-mail protokołu Exchange ActiveSync na urządzeniach zarządzanych. Wdrożenie tych ustawień zapewnia spójność, zmniejszenie liczby interwencji obsługi i umożliwia użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure email settings (Konfigurowanie ustawień poczty e-mail)](how-to-configure-email-settings.md) Dotyczy systemów: Android, iOS, Windows Phone 8.1 i Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Aby wdrożyć ustawienia sieci bezprzewodowej dla użytkowników i urządzeń w organizacji, użyj profilów sieci Wi-Fi. W przypadku wdrożenia profilu sieci Wi-Fi użytkownicy będą mieli dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure Wi-Fi settings (Konfigurowanie ustawień sieci Wi-Fi)](how-to-configure-wi-fi-settings.md) Dotyczy systemów: Android, iOS, macOS i Windows 8.1 (tylko import).

## <a name="vpn"></a>VPN
Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. Aby wdrożyć ustawienia sieci VPN dla użytkowników i urządzeń w organizacji w taki sposób, aby łączenie się z siecią było łatwe i bezpieczne, użyj profilów sieci VPN.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure VPN settings (Sposoby konfigurowania ustawień sieci VPN)](how-to-configure-vpn-settings.md).
Dotyczy systemów: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 i Windows 10.

## <a name="certificates"></a>Certyfikaty
Ten typ profilu umożliwia skonfigurowanie zaufanych certyfikatów oraz certyfikatów SCEP i PKCS, które mogą zostać przypisane do urządzeń i być używane do uwierzytelniania sieci Wi-Fi, sieci VPN oraz profilów poczty e-mail.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure certificates (Sposoby konfigurowania certyfikatów)](how-to-configure-certificates.md) Dotyczy systemów: Android, iOS, Windows Phone 8.1, Windows 8.1 i Windows 10.

## <a name="education"></a>Edukacja
Pomaga w określeniu prawidłowych certyfikatów do użycia w urządzeniach z systemem iOS w środowisku edukacyjnym.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure Intune education settings for iOS devices (Sposoby konfigurowania ustawień edukacyjnych w usłudze Intune dla urządzeń z systemem iOS)](education-settings-for-ios.md) Dotyczy tylko systemu iOS.

## <a name="edition-upgrade"></a>Zasady uaktualniania wersji
Ten typ profilu umożliwia automatyczne uaktualnianie do nowszej wersji urządzeń, na których są uruchomione niektóre wersje systemu Windows 10. Aby uzyskać więcej informacji, zobacz artykuł [How to configure Windows 10 edition upgrades (Sposoby konfigurowania uaktualnień wersji systemu Windows 10)](how-to-configure-windows-10-edition-upgrade.md) Dotyczy tylko systemu Windows 10.

## <a name="windows-information-protection"></a>Rozwiązanie Windows Information Protection
Funkcja Windows Information Protection ułatwia ochronę przed wyciekami danych bez zakłócania pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, które pracownik zabiera ze sobą do pracy — wszystko to bez konieczności wprowadzania zmian w środowisku lub innych aplikacjach.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure Windows Information Protection (Sposoby konfigurowania funkcji Windows Information Protection)](how-to-configure-windows-information-protection.md) Dotyczy tylko systemu Windows 10.

## <a name="custom"></a>Niestandardowy
Ustawienia niestandardowe umożliwiają przypisywanie ustawień urządzenia, które nie są wbudowane w usługę Intune. Na przykład dla urządzeń z systemem Android można określić wartości OMA-URI, które służą do skonfigurowania urządzenia. W przypadku urządzeń z systemem iOS można zaimportować plik konfiguracyjny utworzony za pomocą programu Apple Configurator.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure custom settings (Sposoby konfigurowania ustawień niestandardowych)](how-to-configure-custom-settings.md) Dotyczy systemów: Android, iOS, macOS i Windows Phone 8.1.



<!--HONumber=Feb17_HO1-->


