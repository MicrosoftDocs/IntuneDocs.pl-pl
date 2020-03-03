---
title: Podpisywanie i szyfrowanie poczty e-mail przy użyciu protokołu S/MIME — Microsoft Intune — Azure | Microsoft Docs
description: Dowiedz się, jak podpisywać i szyfrować wiadomości e-mail w urządzeniach za pomocą certyfikatów cyfrowych w usłudze Microsoft Intune. Są to certyfikaty protokołu S/MIME skonfigurowane przy użyciu profili konfiguracji urządzeń. Certyfikaty podpisywania i szyfrowania używają protokołu PKCS (certyfikatów prywatnych) oraz umożliwiają importowanie certyfikatów za pomocą łącznika.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/10/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15147a1d9ffd82e2f900d15c4a9d2b4d23ad23e3
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515156"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>Omówienie protokołu S/MIME w zakresie podpisywania i szyfrowania wiadomości e-mail w usłudze Intune

Certyfikaty poczty e-mail, nazywane też certyfikatami S/MIME, zapewniają dodatkowe zabezpieczenia wiadomości e-mail przy użyciu szyfrowania i odszyfrowywania. Usługa Microsoft Intune może używać certyfikatów S/MIME do podpisywania i szyfrowania wiadomości e-mail w urządzeniach przenośnych korzystających z następujących platform:

- Android
- iOS/iPadOS
- macOS
- Windows 10 lub nowszym
- Windows Phone

Na urządzeniach z systemem iOS/iPadOS można utworzyć profil poczty e-mail zarządzany przez usługę Intune, która będzie korzystać z protokołu S/MIME i certyfikatów w przypadku podpisywania i szyfrowania przychodzących i wychodzących wiadomości e-mail. Na innych platformach protokół S/MIME może być obsługiwany lub nie. Jeśli jest obsługiwany, zainstaluj certyfikaty, które używają podpisywania i szyfrowania za pomocą protokołu S/MIME. Następnie użytkownik końcowy włącza protokół S/MIME w aplikacjach poczty e-mail.

Aby uzyskać więcej informacji na temat szyfrowania i podpisywania wiadomości e-mail przy użyciu protokołu S/MIME w programie Exchange, zobacz [S/MIME for message signing and encryption (Protokół S/MIME na potrzeby podpisywania i szyfrowania wiadomości)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

W tym artykule omówiono, jak podpisywać i szyfrować wiadomości e-mail w urządzeniach przy użyciu certyfikatów S/MIME.

## <a name="signing-certificates"></a>Certyfikaty podpisywania

Certyfikaty używane do podpisywania umożliwiają aplikacji poczty e-mail klienta bezpieczne komunikowanie się z serwerem poczty e-mail.

Aby korzystać z podpisywania certyfikatów, należy utworzyć szablon w obrębie urzędu certyfikacji skoncentrowany na podpisywaniu. Temat [Configure the server certificate template (Konfigurowanie szablonu certyfikatu serwera)](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) dla urzędu certyfikacji usługi Microsoft Active Directory zawiera instrukcje dotyczące tworzenia szablonów certyfikatów.

Certyfikaty podpisywania w usłudze Intune używają certyfikatów PKCS. W artykule [Konfigurowanie certyfikatów PKCS i korzystanie z nich](certficates-pfx-configure.md) opisano sposób wdrażania i używania certyfikatu PKCS w danym środowisku usługi Intune. Te kroki to:

- Pobieranie i instalowanie łącznika certyfikatów usługi Microsoft Intune na potrzeby obsługi żądań certyfikatów PKCS.
- Tworzenie profilu zaufanego certyfikatu głównego dla urządzeń. Ten krok obejmuje używanie zaufanych certyfikatów głównych i certyfikatów pośrednich dla urzędu certyfikacji, a następnie wdrażanie profilu do urządzeń.
- Tworzenie profilu certyfikatu PKCS przy użyciu utworzonego szablonu certyfikatu. Ten profil wystawia certyfikaty podpisywania dla urządzeń i wdraża profil certyfikatu PKCS na urządzeniach.

Można również zaimportować certyfikat podpisywania dla określonego użytkownika. Certyfikat podpisywania jest wdrażany na dowolnym urządzeniu rejestrowanym przez użytkownika. Aby importować certyfikaty w usłudze Intune, należy używać [poleceń cmdlet programu PowerShell w usłudze GitHub](https://github.com/Microsoft/Intune-Resource-Access). Aby wdrożyć certyfikat PKCS zaimportowany w usłudze Intune w celu używania go do podpisywania wiadomości e-mail, należy wykonać kroki opisane w temacie [Konfigurowanie certyfikatów PKCS i korzystanie z nich za pomocą usługi Intune](certficates-pfx-configure.md). Te kroki to:

- Pobieranie i instalowanie łącznika certyfikatów PFX w usłudze Microsoft Intune. Ten łącznik dostarcza importowane certyfikaty PKCS na urządzenia.
- Importowanie certyfikatów podpisywania wiadomości e-mail w ramach protokołu S/MIME do usługi Intune.
- Tworzenie profilu zaimportowanego certyfikatu PKCS. Ten profil dostarcza zaimportowane certyfikaty PKCS na urządzenia odpowiedniego użytkownika.

## <a name="encryption-certificates"></a>Certyfikaty szyfrowania

Certyfikaty używane do szyfrowania potwierdzają, że zaszyfrowane wiadomości e-mail mogą zostać odszyfrowane tylko przez zamierzonego odbiorcę. Szyfrowanie S/MIME to dodatkowa warstwa zabezpieczeń, która może być używana na potrzeby komunikacji za pośrednictwem wiadomości e-mail.

Podczas wysyłania zaszyfrowanych wiadomości e-mail do innego użytkownika jest uzyskiwany klucz publiczny certyfikatu szyfrowania tego użytkownika, a wysyłana wiadomość e-mail jest szyfrowana. Odbiorca odszyfrowuje wiadomość e-mail przy użyciu klucza prywatnego na swoim urządzeniu. Użytkownicy mogą mieć historię certyfikatów używanych do szyfrowania poczty e-mail. Każdy z tych certyfikatów musi zostać wdrożony do wszystkich urządzeń określonego użytkownika, aby ich adres e-mail mógł być pomyślnie odszyfrowywany.

Zaleca się, aby certyfikaty szyfrowania wiadomości e-mail nie były tworzone w usłudze Intune. Jeśli usługa Intune obsługuje wystawianie certyfikatów PKCS, które obsługują szyfrowanie, tworzy ona unikatowy certyfikat na każdym urządzeniu. Unikatowy certyfikat na poszczególnych urządzeniach nie jest idealnym rozwiązaniem w przypadku scenariusza szyfrowania S/MIME, w którym certyfikat szyfrowania powinien być udostępniany na wszystkich urządzeniach użytkownika.

Aby wdrażać certyfikaty szyfrowania S/MIME przy użyciu usługi Intune, należy zaimportować wszystkie certyfikaty szyfrowania użytkownika do usługi Intune. Usługa Intune następnie wdraża wszystkie te certyfikaty do każdego urządzenia rejestrowanego przez użytkownika. Aby importować certyfikaty w usłudze Intune, należy używać [poleceń cmdlet programu PowerShell w usłudze GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Aby wdrożyć certyfikat PKCS zaimportowany w usłudze Intune i używany do szyfrowania wiadomości e-mail, należy wykonać kroki opisane w temacie [Konfigurowanie certyfikatów PKCS i korzystanie z nich za pomocą usługi Intune](certficates-pfx-configure.md). Te kroki to:

- Pobieranie i instalowanie łącznika certyfikatów PFX w usłudze Microsoft Intune. Ten łącznik dostarcza importowane certyfikaty PKCS na urządzenia.
- Importowanie certyfikatów szyfrowania wiadomości e-mail w ramach protokołu S/MIME do usługi Intune.
- Tworzenie profilu zaimportowanego certyfikatu PKCS. Ten profil dostarcza zaimportowane certyfikaty PKCS na urządzenia odpowiedniego użytkownika.

 > [!NOTE]
 > Zaimportowane certyfikaty szyfrowania S/MIME są usuwane przez usługę Intune po usunięciu danych firmowych lub gdy użytkownicy zostaną wyrejestrowani z zarządzania. Certyfikaty nie są jednak odwoływane w urzędzie certyfikacji.

## <a name="smime-email-profiles"></a>Profile poczty e-mail protokołu S/MIME

Po utworzeniu profilów certyfikatów podpisywania i szyfrowania S/MIME można [włączyć protokół S/MIME na potrzeby natywnej poczty e-mail systemu iOS/iPadOS](../configuration/email-settings-ios.md).

## <a name="next-steps"></a>Następne kroki

- [Używanie protokołu SCEP dla certyfikatów](certificates-scep-configure.md)
- [Używanie certyfikatów PKCS](certficates-pfx-configure.md)
- [Używanie urzędu certyfikacji partnera](certificate-authority-add-scep-overview.md)
- [Wystawianie certyfikatów PKCS z poziomu usługi internetowej Symantec PKI Manager](certificates-digicert-configure.md)
