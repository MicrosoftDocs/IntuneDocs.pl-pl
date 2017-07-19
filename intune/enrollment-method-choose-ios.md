---
title: "Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące rejestrowania urządzeń z systemem iOS w usłudze Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Wybieranie sposobu rejestrowania urządzeń z systemem iOS i macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W tym temacie opisano metody, z których administrator IT może skorzystać w celu włączenia w usłudze Intune rejestracji urządzeń z systemem iOS.

Poniższe informacje pomogą zdecydować, której metody rejestracji urządzeń z systemem iOS użyć. Wszystkie poniższe metody, z wyjątkiem BYOD, służą do rejestrowania urządzeń firmowych.

**Wymaganie wstępne:** wymagany jest [certyfikat usługi Apple Push Notification Service](apple-mdm-push-certificate-get.md).

## <a name="user-owned-ios-devices-byod"></a>Urządzenia z systemem iOS należące do użytkownika (BYOD)

Jeśli użytkownik chce zarejestrować własne urządzenie (BYOD, Bring Your Own Device), może pobrać aplikację Portal firmy dla systemu iOS ze sklepu App Store i postępować zgodnie z zawartymi w aplikacji instrukcjami. Po zarejestrowaniu użytkownicy mogą nawiązać połączenie z siecią firmową, przyłączyć się do domeny lub usługi Azure Active Directory i uzyskać dostęp do zasobów firmy. Jedynym wymaganiem do włączenia modelu BYOD jest [certyfikat usługi Apple Push Notification Service](apple-mdm-push-certificate-get.md). Można także zablokować możliwość rejestrowania urządzeń z systemem iOS będących własnością użytkowników. Instrukcje zawiera temat [Ustawianie ograniczeń typu urządzeń](enrollment-restrictions-set.md).

## <a name="user-owned-macos-devices-byod"></a>Urządzenia z systemem macOS należące do użytkownika (BYOD)

Można włączyć rejestrowanie urządzeń z systemem macOS. Jedynym wymaganiem do włączenia rejestrowania urządzeń z systemem macOS jest [certyfikat usługi Apple Push Notification Service](apple-mdm-push-certificate-get.md). Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem macOS](./macos-enroll.md).

## <a name="enrollment-program-with-apple"></a>Program rejestracji firmy Apple
Firma Apple oferuje programy zakupu urządzeń, które obejmują rejestrację urządzeń i infrastrukturę zarządzania nimi. Urządzenia kupione w ramach jednego z tych programów można bezprzewodowo rejestrować zbiorczo, przypisując numery seryjne urządzeń do zarządzania w usłudze Intune.

- **Device Enrollment Program (DEM)** — program rejestracji urządzeń firmy Apple dla organizacji i przedsiębiorstw. Aby uzyskać więcej informacji, zobacz artykuł [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md) (Rejestracja urządzeń z systemem iOS przy użyciu programu Device Enrollment Program).
- **Apple School Manager** — program rejestracji urządzeń firmy Apple dla szkół. Aby uzyskać więcej informacji, zobacz [Włączanie rejestracji urządzeń z systemem iOS za pomocą usługi Apple School Manager](apple-school-manager-set-up-ios.md)

## <a name="apple-configurator"></a>Program Apple Configurator

W celu zarejestrowania urządzeń z systemem iOS można wyeksportować firmowy profil wdrażania, a następnie połączyć te urządzenia przenośne z komputerem Mac, na którym działa program Apple Configurator. Program Apple Configurator obsługuje dwa rodzaje rejestracji:

- **Rejestracja przy użyciu Asystenta ustawień**: przywracanie ustawień fabrycznych urządzenia i przygotowanie do konfiguracji przez nowego użytkownika. Ta metoda wymaga od administratora podłączenia urządzenia z systemem iOS przez port USB do komputera Mac z programem Apple Configurator w celu wstępnego skonfigurowania rejestracji. Urządzenia są następnie dostarczane do użytkowników, którzy przy pierwszym uruchomieniu korzystają z Asystenta ustawień. W ramach tego procesu następuje konfiguracja urządzenia z poświadczeniami firmy lub szkoły użytkownika i ukończenie procesu rejestracji. Aby uzyskać więcej informacji, zobacz artykuł [Rejestracja urządzeń z systemem iOS za pomocą narzędzia Apple Configurator przy użyciu Asystenta ustawień](apple-configurator-setup-assistant-enroll-ios.md).

- **Rejestracja bezpośrednia**: tworzenie pliku zgodnego z programem Apple Configurator do użytku podczas przygotowywania urządzenia. Zarejestrowane urządzenie nie jest resetowane do ustawień fabrycznych i nie ma określonej przynależności do użytkownika. Aby zarejestrować urządzenia, administrator musi podłączyć urządzenie z systemem iOS przez port USB do komputera Mac z uruchomionym programem Apple Configurator. Aby uzyskać więcej informacji, zobacz artykuł [Bezpośrednie rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Użycie programu Device Enrollment Program (DEP)

Program DEP wdraża bezprzewodowo profil rejestracji na urządzeniach zakupionych w ramach tego programu. Gdy użytkownik otwiera Asystenta ustawień przy pierwszym uruchomieniu, urządzenie jest rejestrowane w usłudze Intune. Aby uzyskać więcej informacji, zobacz artykuł [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md) (Rejestracja urządzeń z systemem iOS przy użyciu programu Device Enrollment Program).

## <a name="use-the-device-enrollment-manager-dem"></a>Korzystanie z menedżera rejestracji urządzeń (DEM)
Menedżer rejestracji urządzeń to ogólne konto użytkownika, które umożliwia rejestrację maksymalnie 1000 urządzeń oraz zarządzanie nimi. Urządzenia zarządzane przez menedżera rejestracji urządzeń nie mają koligacji użytkownika, dlatego urządzenie nigdy nie ma właściciela. Użytkownicy usługi Intune otrzymują uprawnienia menedżera rejestracji urządzeń w celu udostępnienia im tych funkcji. Każde urządzenie rejestrowane przez użytkownika menedżera rejestracji urządzeń korzysta z licencji usługi Intune. Aby uzyskać więcej informacji, zobacz artykuł [Enroll devices using device enrollment manager](device-enrollment-manager-enroll.md) (Rejestracja urządzeń przy użyciu menedżera rejestracji urządzeń).
