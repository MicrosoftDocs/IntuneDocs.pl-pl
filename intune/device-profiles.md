---
title: "Co to są profile urządzeń w usłudze Microsoft Intune?"
titlesuffix: Azure portal
description: "Więcej informacji na temat profilów urządzeń w usłudze Intune i ich przydatności w Twojej firmie do zarządzania urządzeniami i ich ochrony."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c745f9f745802e0de7a58e3dd7570c0e363ab5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Co to są profile urządzeń w usłudze Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W celu zarządzania ustawieniami i funkcjami na wszystkich zarządzanych urządzeniach użyj obciążenia **Konfiguracja urządzeń** w usłudze Microsoft Intune. To obciążenie służy głównie do tworzenia profilów urządzeń, które umożliwiają zarządzanie całym szeregiem różnych funkcji na urządzeniach.

Po otwarciu tego obciążenia zostaną wyświetlone następujące opcje:

- **Przegląd** — ta strona udostępnia stan i raporty pomagające w monitorowaniu konfiguracji urządzeń, które zostały przypisane do użytkowników i urządzeń.
- **Zarządzanie profilami** — w tej sekcji można utworzyć profile konfiguracji urządzenia. Listę wszystkich typów profilów, które można utworzyć, można znaleźć w dalszej części tego tematu.
- **Konfiguracja urzędu certyfikacji** — ten przepływ pracy przeprowadza przez kroki wymagane do skonfigurowania profilów certyfikatów usługi Intune.

## <a name="getting-started"></a>Wprowadzenie

Przepływ pracy związany z tworzeniem profilów urządzeń jest podobny dla wszystkich profilów. Informacje o sposobie tworzenia profilów można znaleźć w temacie [How to create Microsoft Intune device configuration profiles (Sposoby tworzenia profilów konfiguracji urządzeń w usłudze Microsoft Intune)](device-profile-create.md). W dalszej kolejności należy zapoznać się z konkretnymi informacjami na temat tworzenia ustawień dla każdego typu profilu.

Na urządzeniach można zarządzać następującymi możliwościami:

## <a name="device-features"></a>Funkcje urządzenia

Funkcje urządzenia pozwalają sterować funkcjami urządzeń z systemami iOS i macOS, takimi jak AirPrint, powiadomienia i udostępniane konfiguracje urządzeń.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure device feature settings](device-features-configure.md) (Sposób konfigurowania ustawień funkcji urządzenia) Obsługuje systemy iOS i macOS.

## <a name="device-restrictions"></a>Ograniczenia dotyczące urządzeń
Ograniczenia dotyczące urządzeń pozwalają na kontrolę wielu ustawień na zarządzanych urządzeniach, dotyczących zabezpieczeń, sprzętu i ustawień związanych z udostępnianiem danych. Na przykład można utworzyć profil ograniczenia dotyczącego urządzeń, który uniemożliwia użytkownikom urządzeń z systemem iOS dostęp do aparatu urządzenia.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure device restriction settings (Sposoby konfigurowania ustawień ograniczeń urządzenia)](device-restrictions-configure.md) Dotyczy systemów: Android, iOS, macOS, Windows 10 i Windows 10 Team.

## <a name="email"></a>Poczta e-mail
Profile poczty e-mail pozwalają na tworzenie, przypisywanie i monitorowanie ustawień poczty e-mail protokołu Exchange ActiveSync na urządzeniach zarządzanych. Profile poczty e-mail zapewniają spójność i zmniejszają liczbę interwencji obsługi oraz umożliwiają użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure email settings (Konfigurowanie ustawień poczty e-mail)](email-settings-configure.md) Dotyczy systemów: Android, iOS, Windows Phone 8.1 i Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Aby przypisać ustawienia sieci bezprzewodowej do użytkowników i urządzeń w organizacji, użyj profilów sieci Wi-Fi. W przypadku przypisania profilu sieci Wi-Fi użytkownicy uzyskają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure Wi-Fi settings (Konfigurowanie ustawień sieci Wi-Fi)](wi-fi-settings-configure.md) Dotyczy systemów: Android, iOS, macOS i Windows 8.1 (tylko import).

## <a name="vpn"></a>VPN
Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. Przypisanie profilów sieci VPN do użytkowników i urządzeń w organizacji pozwala łatwo i bezpiecznie łączyć się z siecią.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure VPN settings (Sposoby konfigurowania ustawień sieci VPN)](vpn-settings-configure.md).
Dotyczy systemów: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 i Windows 10.

## <a name="education"></a>Edukacja
Umożliwia konfigurowanie opcji aplikacji systemu Windows Take a Test. Po skonfigurowaniu tych opcji do czasu ukończenia testu nie można uruchomić na urządzeniu żadnych innych aplikacji.
Aby uzyskać więcej informacji, zobacz artykuł [Jak skonfigurować ustawienia sieci VPN w usłudze Microsoft Intune](education-settings-configure.md)

## <a name="certificates"></a>Certyfikaty
Ten typ profilu umożliwia skonfigurowanie zaufanych certyfikatów oraz certyfikatów SCEP i PKCS, które mogą zostać przypisane do urządzeń i być używane do uwierzytelniania sieci Wi-Fi, sieci VPN oraz profilów poczty e-mail.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure certificates (Sposoby konfigurowania certyfikatów)](certificates-configure.md) Dotyczy systemów: Android, iOS, Windows Phone 8.1, Windows 8.1 i Windows 10.

## <a name="edition-upgrade"></a>Zasady uaktualniania wersji
Ten typ profilu umożliwia automatyczne uaktualnianie urządzeń z niektórymi wersjami systemu Windows 10.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure Windows 10 edition upgrades (Sposoby konfigurowania uaktualnień wersji systemu Windows 10)](edition-upgrade-configure-windows-10.md) Dotyczy tylko systemu Windows 10.

## <a name="endpoint-protection"></a>Program Endpoint Protection
Ten typ profilu umożliwia skonfigurowanie ustawień funkcji BitLocker i usługi Windows Defender dla urządzeń z systemem Windows 10.
Aby uzyskać więcej informacji, zobacz [Endpoint protection settings for Windows 10 (Ustawienia programu Endpoint Protection dla systemu Windows 10)](endpoint-protection-windows-10.md) Dotyczy tylko systemu Windows 10.

## <a name="windows-information-protection"></a>Rozwiązanie Windows Information Protection
Funkcja Windows Information Protection ułatwia ochronę przed wyciekami danych bez zakłócania pracy pracownika. Pomaga również chronić aplikacje i dane przedsiębiorstwa przed przypadkowymi przeciekami danych z urządzeń należących do przedsiębiorstwa oraz urządzeń osobistych, które pracownik zabiera ze sobą do pracy — wszystko to bez konieczności wprowadzania zmian w środowisku lub innych aplikacjach.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure Windows Information Protection (Sposoby konfigurowania funkcji Windows Information Protection)](windows-information-protection-configure.md) Dotyczy tylko systemu Windows 10.

## <a name="custom"></a>Niestandardowy
Ustawienia niestandardowe umożliwiają przypisywanie ustawień urządzenia, które nie są wbudowane w usługę Intune. Na przykład dla urządzeń z systemem Android można określić wartości OMA-URI, które służą do skonfigurowania urządzenia. W przypadku urządzeń z systemem iOS można zaimportować plik konfiguracyjny utworzony za pomocą programu Apple Configurator.
Aby uzyskać więcej informacji, zobacz artykuł [How to configure custom settings (Sposoby konfigurowania ustawień niestandardowych)](custom-settings-configure.md) Dotyczy systemów: Android, iOS, macOS i Windows Phone 8.1.

## <a name="next-steps"></a>Następne kroki
Wybierz typ profilu z listy, aby rozpocząć konfigurowanie urządzeń.
