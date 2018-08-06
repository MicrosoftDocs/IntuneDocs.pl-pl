---
title: Podpisywanie i szyfrowanie wiadomości e-mail przy użyciu protokołu S/MIME — Azure | Micrososft Docs
description: Używanie lub włączanie protokołu S/MIME na potrzeby do podpisywania i szyfrowania wiadomości e-mail w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0eac3c1d6739ca70e485b0327e3257ba8d32d2b
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321723"
---
# <a name="smime-email-signing-and-encryption-in-intune"></a>Podpisywanie i szyfrowanie wiadomości e-mail przy użyciu protokołu S/MIME w usłudze Intune

Protokół S/MIME zapewnia dodatkowy poziom zabezpieczeń komunikacji za pośrednictwem poczty e-mail dzięki użyciu szyfrowania i odszyfrowywania. Usługa Microsoft Intune może używać protokołu S/MIME do podpisywania i szyfrowania wiadomości e-mail na urządzeniach przenośnych z systemem iOS, Windows, Windows Phone, Android i macOS.

Na urządzeniach z systemem iOS można utworzyć profil poczty e-mail zarządzany przez usługę Intune, która będzie korzystać z protokołu S/MIME i certyfikatów w przypadku podpisywania i szyfrowania przychodzących i wychodzących wiadomości e-mail. Na innych platformach protokół S/MIME może być obsługiwany lub nie. Jeśli jest obsługiwany, można zainstalować certyfikaty, które używają podpisywania i szyfrowania za pomocą protokołu S/MIME. Następnie użytkownik końcowy może włączyć protokół S/MIME w aplikacjach poczty e-mail.

Aby uzyskać więcej informacji na temat szyfrowania i podpisywania wiadomości e-mail przy użyciu protokołu S/MIME, zobacz [S/MIME for message signing and encryption (Protokół S/MIME na potrzeby podpisywania i szyfrowania wiadomości)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

## <a name="signing-certificates"></a>Certyfikaty podpisywania

Certyfikaty używane do podpisywania umożliwiają aplikacji poczty e-mail klienta bezpieczne komunikowanie się z serwerem poczty e-mail.

Aby korzystać z podpisywania certyfikatów, należy utworzyć szablon w obrębie urzędu certyfikacji skoncentrowany na podpisywaniu. Temat [Configure the server certificate template (Konfigurowanie szablonu certyfikatu serwera)](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) dla urzędu certyfikacji usługi Microsoft Active Directory zawiera instrukcje dotyczące tworzenia szablonów certyfikatów.

Certyfikaty podpisywania w usłudze Intune używają certyfikatów PKCS. W artykule [Konfigurowanie certyfikatów PKCS i korzystanie z nich](certficates-pfx-configure.md) opisano sposób wdrażania i używania certyfikatu PKCS w danym środowisku usługi Intune. Kroki te obejmują:

- Pobieranie i instalowanie łącznika certyfikatów usługi Microsoft Intune na potrzeby obsługi żądań certyfikatów PKCS.
- Tworzenie profilu zaufanego certyfikatu głównego dla urządzeń. Ten krok obejmuje używanie zaufanych certyfikatów głównych i certyfikatów pośrednich dla urzędu certyfikacji, a następnie wdrażanie profilu do urządzeń.
- Tworzenie profilu certyfikatu PKCS przy użyciu utworzonego szablonu certyfikatu. Ten profil wystawia certyfikaty podpisywania dla urządzeń i wdraża profil certyfikatu PKCS na urządzeniach.

Można również zaimportować certyfikat podpisywania dla określonego użytkownika. Certyfikat podpisywania jest wdrażany na dowolnym urządzeniu rejestrowanym przez użytkownika. Aby importować certyfikaty w usłudze Intune, należy używać [poleceń cmdlet programu PowerShell w usłudze GitHub](https://github.com/Microsoft/Intune-Resource-Access). Aby wdrożyć certyfikat PKCS zaimportowany w usłudze Intune w celu używania go do podpisywania wiadomości e-mail, należy wykonać kroki opisane w temacie [Konfigurowanie certyfikatów PKCS i korzystanie z nich za pomocą usługi Intune](certficates-pfx-configure.md). Kroki te obejmują:

- Pobieranie i instalowanie łącznika certyfikatów PFX w usłudze Microsoft Intune. Ten łącznik dostarcza importowane certyfikaty PKCS na urządzenia.
- Importowanie certyfikatów podpisywania wiadomości e-mail w ramach protokołu S/MIME do usługi Intune.
- Tworzenie profilu zaimportowanego certyfikatu PKCS. Ten profil dostarcza zaimportowane certyfikaty PKCS na urządzenia odpowiedniego użytkownika.

## <a name="encryption-certificates"></a>Certyfikaty szyfrowania

Certyfikaty używane do szyfrowania potwierdzają, że zaszyfrowane wiadomości e-mail mogą zostać odszyfrowane tylko przez zamierzonego odbiorcę. Szyfrowanie S/MIME to dodatkowa warstwa zabezpieczeń, która może być używana na potrzeby komunikacji za pośrednictwem wiadomości e-mail.

Podczas wysyłania zaszyfrowanych wiadomości e-mail do innego użytkownika jest uzyskiwany klucz publiczny certyfikatu szyfrowania tego użytkownika, a wysyłana wiadomość e-mail jest szyfrowana. Odbiorca odszyfrowuje wiadomość e-mail przy użyciu klucza prywatnego na swoim urządzeniu. Użytkownicy mogą mieć historię certyfikatów używanych do szyfrowania poczty e-mail. Każdy z tych certyfikatów musi zostać wdrożony do wszystkich urządzeń określonego użytkownika, aby ich adres e-mail mógł być pomyślnie odszyfrowywany.

Zaleca się, aby certyfikaty szyfrowania wiadomości e-mail nie były tworzone w usłudze Intune. Jeśli usługa Intune obsługuje wystawianie certyfikatów PKCS, które obsługują szyfrowanie, tworzy ona unikatowy certyfikat na każdym urządzeniu. Unikatowy certyfikat na poszczególnych urządzeniach nie jest idealnym rozwiązaniem w przypadku scenariusza szyfrowania S/MIME, w którym certyfikat szyfrowania powinien być udostępniany na wszystkich urządzeniach użytkownika.

Aby wdrażać certyfikaty szyfrowania S/MIME przy użyciu usługi Intune, należy zaimportować wszystkie certyfikaty szyfrowania użytkownika do usługi Intune. Usługa Intune następnie wdraża wszystkie te certyfikaty do każdego urządzenia rejestrowanego przez użytkownika. Aby importować certyfikaty w usłudze Intune, należy używać [poleceń cmdlet programu PowerShell w usłudze GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Aby wdrożyć certyfikat PKCS zaimportowany w usłudze Intune i używany do szyfrowania wiadomości e-mail, należy wykonać kroki opisane w temacie [Konfigurowanie certyfikatów PKCS i korzystanie z nich za pomocą usługi Intune](certficates-pfx-configure.md). Kroki te obejmują:

- Pobieranie i instalowanie łącznika certyfikatów PFX w usłudze Microsoft Intune. Ten łącznik dostarcza importowane certyfikaty PKCS na urządzenia.
- Importowanie certyfikatów szyfrowania wiadomości e-mail w ramach protokołu S/MIME do usługi Intune.
- Tworzenie profilu zaimportowanego certyfikatu PKCS. Ten profil dostarcza zaimportowane certyfikaty PKCS na urządzenia odpowiedniego użytkownika.

 > [!NOTE]
 > Zaimportowane certyfikaty szyfrowania S/MIME są usuwane przez usługę Intune po usunięciu danych firmowych lub gdy użytkownicy zostaną wyrejestrowani z zarządzania. Certyfikaty nie są jednak odwoływane w urzędzie certyfikacji.

## <a name="smime-email-profiles"></a>Profile poczty e-mail protokołu S/MIME

Po utworzeniu profilów certyfikatów podpisywania i szyfrowania S/MIME można [włączyć protokół S/MIME na potrzeby natywnej poczty e-mail systemu iOS](email-settings-ios.md).