---
title: Ustawienia funkcji Windows Hello dla firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień numeru PIN, biometrii i ochrony przed fałszowaniem w profilu usługi Identity Protection na potrzeby używania i konfigurowania funkcji Windows Hello dla firm na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bbdb56770c154a482ad004f1f3f980809424caf
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848512"
---
# <a name="windows-10-and-newer-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Ustawienia urządzeń z systemem Windows 10 (lub nowszym) służące do włączania funkcji Windows Hello dla firm w usłudze Intune

W tym artykule wymieniono i opisano ustawienia funkcji Windows Hello dla firm, które można kontrolować na urządzeniach z systemem Windows 10 w usłudze Intune. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby korzystać z numeru PIN lub odcisku palca podczas do logowania i nie tylko.

Jako administrator usługi Intune możesz tworzyć i przypisywać te ustawienia do urządzeń z systemem Windows 10 lub nowszym.

Aby dowiedzieć się więcej na temat profilów funkcji Windows Hello dla firm w usłudze Intune, zobacz artykuł [Konfigurowanie ochrony tożsamości](identity-protection-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello for Business

- **Skonfiguruj usługę Windows Hello dla firm**: aby korzystać z tej funkcji i konfigurować jej ustawienia, wybierz pozycję **Włącz**.
- **Minimalna długość numeru PIN**: wprowadź minimalną długość numeru PIN, na który chcesz zezwolić na urządzeniach. Domyślna długość numeru PIN to sześć znaków. Minimalna długość numeru PIN to cztery (4) znaki.
- **Maksymalna długość numeru PIN**: wprowadź maksymalną długość numeru PIN, na który chcesz zezwolić na urządzeniach. Domyślna długość numeru PIN to sześć (6) znaków. Maksymalna długość numeru PIN to 127 znaków.  
- **Małe litery w numerze PIN**: można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania małych liter. Dostępne opcje:

  - **Niedozwolone** (ustawienie domyślne): użytkownicy nie mogą używać małych liter w numerze PIN. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
  - **Dozwolone**: użytkownicy mogą używać małych liter w numerze PIN, ale nie jest to wymagane.
  - **Wymagane**: użytkownicy muszą użyć co najmniej jednej małej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

- **Wielkie litery w numerze PIN**: można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania wielkich liter. Dostępne opcje:

  - **Niedozwolone** (ustawienie domyślne): użytkownicy nie mogą używać wielkich liter w numerze PIN. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
  - **Dozwolone**: użytkownicy mogą używać wielkich liter w numerze PIN, ale nie jest to wymagane.
  - **Wymagane**: użytkownicy muszą użyć co najmniej jednej wielkiej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

- **Znaki specjalne w numerze PIN**: można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania znaków specjalnych. Dostępne opcje:

  - **Niedozwolone** (ustawienie domyślne): użytkownicy nie mogą używać znaków specjalnych w numerze PIN. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
    Znaki specjalne obejmują: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Dozwolone**: użytkownicy mogą używać wielkich liter w numerze PIN, ale nie jest to wymagane.
  - **Wymagane**: użytkownicy muszą użyć co najmniej jednej wielkiej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

- **Wygaśnięcie numeru PIN (dni)**: Dobrze jest ustalić okres ważności dla numeru PIN, po którym użytkownicy końcowi muszą go zmienić. Wartość domyślna to 41 dni.

- **Pamiętaj historię numerów PIN**: Ogranicza ponowne używanie wcześniej stosowanych numerów PIN. Domyślnie nie jest dozwolone ponowne użycie żadnego z 5 ostatnich numerów PIN.  
- **Włącz odzyskiwanie kodu PIN**: umożliwia użytkownikowi zmianę numeru PIN przy użyciu usługi odzyskiwania numeru PIN usługi Windows Hello dla firm.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Używaj modułu TPM (Trusted Platform Module)**: Moduł TPM zapewnia dodatkową warstwę zabezpieczeń danych. Wybierz jedną z następujących opcji:  
  - **Włącz**: Tylko urządzenia z dostępnym modułem TPM mogą aprowizować usługę Windows Hello dla firm.
  - **Nieskonfigurowane**: Wszystkie urządzenia mogą aprowizować usługę Windows Hello dla firm nawet wtedy, gdy nie ma modułu TPM, którego można używać. Urządzenia najpierw spróbują użyć modułu TPM, ale jeśli jest on niedostępny, urządzenia mogą używać szyfrowania programowego.  

- **Zezwalaj na uwierzytelnianie biometryczne**: Umożliwia użycie uwierzytelniania biometrycznego, takiego jak rozpoznawanie twarzy lub linii papilarnych, zamiast numeru PIN na potrzeby usługi Windows Hello dla firm. Użytkownicy nadal muszą skonfigurować służbowy numer PIN na wypadek niepowodzenia uwierzytelniania biometrycznego. Wybierz spośród opcji:

  - **Włącz**: Usługa Windows Hello dla firm pozwala na użycie uwierzytelniania biometrycznego.
  - **Nieskonfigurowane** (wartość domyślna): Usługa Windows Hello dla firm nie pozwala na użycie uwierzytelniania biometrycznego (dotyczy wszystkich typów kont).

- **Użyj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**: wybierz tę pozycję, jeśli funkcje ochrony przed fałszowaniem usługi Windows Hello są używane na obsługujących je urządzeniach. Jest to na przykład wykrywanie fotografii twarzy zamiast prawdziwej twarzy.

  - **Włącz**: System Windows wymaga od wszystkich użytkowników używania ochrony przed fałszowaniem na potrzeby rozpoznawania twarzy, jeśli jest obsługiwane.  
  - **Nieskonfigurowane** (wartość domyślna): System Windows uwzględnia konfiguracje ochrony przed fałszowaniem na urządzeniu.

- **Certyfikat dla zasobów lokalnych**: 

  - **Włącz**: Umożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych.
  - **Nieskonfigurowane** (wartość domyślna): Uniemożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych.  

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
