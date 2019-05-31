---
title: Ustawienia funkcji Windows Hello dla firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień numeru PIN, biometrii i ochrony przed fałszowaniem w profilu usługi Identity Protection na potrzeby używania i konfigurowania funkcji Windows Hello dla firm na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 158840a73784516d13defa04785ca5990a9874cf
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041825"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Ustawienia urządzeń z systemem Windows 10 służące do włączania funkcji Windows Hello dla firm w usłudze Intune

W tym artykule wymieniono i opisano ustawienia funkcji Windows Hello dla firm, które można kontrolować na urządzeniach z systemem Windows 10 w usłudze Intune. Jako administrator usługi Intune możesz skonfigurować i przypisać te ustawienia do urządzeń z systemem Windows 10 w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management). 

Dodatkowe informacje na temat tych ustawień znajdziesz w części [Configure Windows Hello for Business Policy settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings) (Konfigurowanie funkcji Windows Hello dla ustawień zasad biznesowych) w dokumentacji funkcji Windows Hello.


Aby dowiedzieć się więcej na temat profilów funkcji Windows Hello dla firm w usłudze Intune, zobacz artykuł [Konfigurowanie ochrony tożsamości](identity-protection-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello for Business

- **Skonfiguruj funkcję Windows Hello dla firm**: aby korzystać z tej funkcji i konfigurować jej ustawienia, wybierz pozycję **Włącz**.
- **Minimalna długość numeru PIN**: podaj minimalną długość numeru PIN, na którą chcesz zezwolić na urządzeniach. Domyślna długość numeru PIN to sześć znaków. Minimalna długość numeru PIN to cztery (4) znaki.
- **Maksymalna długość numeru PIN**: podaj maksymalną długość numeru PIN, na którą chcesz zezwolić na urządzeniach. Domyślna długość numeru PIN to sześć (6) znaków. Maksymalna długość numeru PIN to 127 znaków.  
- **Małe litery w numerze PIN**: można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania małych liter. Dostępne opcje:

  - **Niedozwolone** (domyślnie): użytkownicy nie mogą używać małych liter w PIN-ie. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
  - **Dozwolone**: użytkownicy mogą używać małych liter w numerze PIN, ale nie jest to wymagane.
  - **Wymagane**: użytkownicy muszą użyć co najmniej jednej małej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

- **Wielkie litery w numerze PIN**: można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania wielkich liter. Dostępne opcje:

  - **Niedozwolone** (domyślnie): użytkownicy nie mogą używać wielkich liter w PIN-ie. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
  - **Dozwolone**: użytkownicy mogą używać wielkich liter w numerze PIN, ale nie jest to wymagane.
  - **Wymagane**: użytkownicy muszą użyć co najmniej jednej wielkiej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

- **Znaki specjalne w numerze PIN**: można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania znaków specjalnych. Dostępne opcje:

  - **Niedozwolone** (domyślnie): użytkownicy nie mogą używać znaków specjalnych w PIN-ie. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
    Znaki specjalne obejmują: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Dozwolone**: użytkownicy mogą używać wielkich liter w numerze PIN, ale nie jest to wymagane.
  - **Wymagane**: użytkownicy muszą użyć co najmniej jednej wielkiej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

- **Wygaśnięcie numeru PIN (dni)** : dobrze jest ustalić okres ważności dla numeru PIN, po którym użytkownicy muszą go zmienić. Wartość domyślna to 41 dni.

- **Pamiętaj historię numerów PIN**: ogranicza ponowne używanie wcześniej stosowanych PIN-ów. Domyślnie nie jest dozwolone ponowne użycie żadnego z 5 ostatnich numerów PIN.  
- **Włącz odzyskiwanie numeru PIN**: umożliwia użytkownikowi zmianę numeru PIN przy użyciu usługi odzyskiwania numeru PIN usługi Windows Hello dla firm.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Używaj modułu TPM (Trusted Platform Module)** : moduł TPM zapewnia dodatkową warstwę zabezpieczeń danych. Wybierz jedną z następujących opcji:  
  - **Włącz**: tylko urządzenia z dostępnym modułem TPM mogą aprowizować usługę Windows Hello dla firm.
  - **Nie skonfigurowano**: wszystkie urządzenia mogą aprowizować usługę Windows Hello dla firm nawet wtedy, gdy nie ma modułu TPM, którego można używać. Urządzenia najpierw spróbują użyć modułu TPM, ale jeśli jest on niedostępny, urządzenia mogą używać szyfrowania programowego.  

- **Zezwalaj na uwierzytelnianie biometryczne**: umożliwia użycie uwierzytelniania biometrycznego, takiego jak rozpoznawanie twarzy lub linii papilarnych, zamiast numeru PIN na potrzeby funkcji Windows Hello dla firm. Użytkownicy nadal muszą skonfigurować służbowy numer PIN na wypadek niepowodzenia uwierzytelniania biometrycznego. Wybierz spośród opcji:

  - **Włącz**: usługa Windows Hello dla firm pozwala na użycie uwierzytelniania biometrycznego.
  - **Nie skonfigurowano** (wartość domyślna): funkcja Windows Hello dla firm nie pozwala na użycie uwierzytelniania biometrycznego (dotyczy wszystkich typów kont).

- **Użyj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**: wybierz tę pozycję, jeśli funkcje ochrony przed fałszowaniem funkcji Windows Hello są używane na obsługujących je urządzeniach. Jest to na przykład wykrywanie fotografii twarzy zamiast prawdziwej twarzy.

  - **Włącz**: system Windows wymaga od wszystkich użytkowników używania ochrony przed fałszowaniem na potrzeby rozpoznawania twarzy, jeśli jest obsługiwane.  
  - **Nieskonfigurowane** (domyślnie): system Windows uwzględnia konfiguracje ochrony przed fałszowaniem na urządzeniu.

- **Certyfikat dla zasobów lokalnych**: 

  - **Włącz**: umożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych.
  - **Nie skonfigurowano** (wartość domyślna): uniemożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych. Zamiast tego urządzenia używają zachowania domyślnego *uwierzytelniania lokalnego zaufania klucza*. Więcej informacji znajdziesz w części [User certificate for on-premises authentication](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) (Certyfikat użytkownika do uwierzytelniania lokalnego) w dokumentacji funkcji Windows Hello.  
## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
