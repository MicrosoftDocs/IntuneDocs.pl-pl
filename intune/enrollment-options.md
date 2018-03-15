---
title: "Opcje rejestracji dla urządzeń zarządzanych przez usługę Microsoft Intune"
titleSuffix: 
description: "Lista opcji rejestracji, które administratorzy mogą ustawić dla urządzeń zarządzanych przez usługę Microsoft Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: 67805253f432098736e0fb96776e8f7f0ff44cc3
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2018
---
# <a name="enrollment-options-for-devices-managed-by-intune"></a>Opcje rejestracji dla urządzeń zarządzanych przez usługę Intune

Jako administrator usługi Intune możesz skonfigurować rejestrację urządzeń, aby pomóc użytkownikom i włączyć możliwości usługi Intune.  Usługa Intune obejmuje następujące opcje rejestracji:

## <a name="terms-and-conditions"></a>Warunki i postanowienia

Możesz wymagać, aby użytkownicy zaakceptowali warunki i postanowienia obowiązujące w firmie, zanim rozpoczną korzystanie z aplikacji Portal firmy w celu zarejestrowania swoich urządzeń oraz uzyskania dostępu do zasobów firmowych, takich jak aplikacje i wiadomości e-mail. Konfiguracja warunków i postanowień jest opcjonalna. Dowiedz się więcej o [warunkach i postanowieniach](terms-and-conditions-create.md).

## <a name="enrollment-restrictions"></a>Ograniczenia rejestracji

Możesz ograniczyć rejestrację urządzeń według następujących parametrów:
- Platforma urządzeń
- Liczba urządzeń na użytkownika
- Blokowanie urządzeń osobistych

Dowiedz się więcej o [ograniczeniach rejestracji](enrollment-restrictions-set.md).

## <a name="enable-apple-device-enrollment"></a>Włączanie rejestracji urządzeń firmy Apple

Aby zarządzać rejestracją urządzeń z systemem iOS i macOS, wymagany jest certyfikat usługi wypychania MDM. Dowiedz się więcej na temat [certyfikatów usługi wypychania MDM](apple-mdm-push-certificate-get.md).

## <a name="corporate-identifiers"></a>Identyfikatory firmy

Możesz wyświetlić listę numerów międzynarodowych identyfikatorów urządzeń przenośnych (IMEI) oraz numerów seryjnych, aby zidentyfikować urządzenia stanowiące własność firmy. Dowiedz się więcej o [identyfikatorach firmy](corporate-identifiers-add.md).
## <a name="multi-factor-authentication"></a>Uwierzytelnianie wieloskładnikowe

Można wymagać od użytkowników, aby podczas rejestracji urządzenia korzystali z dodatkowej metody weryfikacji, takiej jak telefon, kod PIN lub dane biometryczne. Dowiedz się więcej o [uwierzytelnianiu wieloskładnikowym](multi-factor-authentication.md).

## <a name="device-enrollment-manager"></a>Menedżer rejestracji urządzeń
Możesz uczynić użytkowników menedżerami rejestracji urządzeń.  Użytkownicy DEM mogą rejestrować duże liczby urządzeń przenośnych za pomocą jednego konta użytkownika. Konto menedżera rejestracji urządzeń (DEM) umożliwia rejestrację do 1000 urządzeń. Dowiedz się więcej o [menedżerach rejestracji urządzeń](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Kategorie urządzeń

Kategorie urządzeń służą do automatycznego dodawania urządzeń do grup opartych na zdefiniowanych przez Ciebie kategoriach. Zorganizowanie urządzeń w grupy ułatwia zarządzanie tymi urządzeniami. Dowiedz się więcej o[ kategoriach urządzeń](device-group-mapping.md).
