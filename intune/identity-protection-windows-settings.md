---
title: Ustawienia funkcji Windows Hello dla firm w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień numeru PIN, biometrii i ochrony przed fałszowaniem w profilu usługi Identity Protection na potrzeby używania i konfigurowania funkcji Windows Hello dla firm na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 1cbf45fc337cbe7d7a45081a3b9e05002ca126d8
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402936"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Ustawienia urządzeń z systemem Windows 10 służące do włączania funkcji Windows Hello dla firm w usłudze Intune

W tym artykule wymieniono i opisano ustawienia funkcji Windows Hello dla firm, które można kontrolować na urządzeniach z systemem Windows 10 w usłudze Intune. Jako administrator usługi Intune możesz skonfigurować i przypisać te ustawienia do urządzeń z systemem Windows 10 w ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management). 

Dodatkowe informacje na temat tych ustawień znajdziesz w części [Configure Windows Hello for Business Policy settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings) (Konfigurowanie funkcji Windows Hello dla ustawień zasad biznesowych) w dokumentacji funkcji Windows Hello.


Aby dowiedzieć się więcej na temat profilów funkcji Windows Hello dla firm w usłudze Intune, zobacz artykuł [Konfigurowanie ochrony tożsamości](identity-protection-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello for Business
- **Skonfiguruj usługę Windows Hello dla firm**:
  - **Nieskonfigurowane** — wybierz to ustawienie, jeśli nie chcesz używać usługi Intune do kontrolowania ustawień usługi Windows Hello dla firm. Żadne z istniejących ustawień usługi Windows Hello dla firm na urządzeniach z systemem Windows 10 nie są zmieniane. Wszystkie inne ustawienia w okienku są niedostępne.

  - **Wyłączone** — wybierz to ustawienie, jeśli nie chcesz używać usługi Windows Hello dla firm. Wszystkie inne ustawienia na ekranie będą wtedy niedostępne.
  - **Włączone** — wybierz to ustawienie, jeśli chcesz skonfigurować ustawienia usługi Windows Hello dla firm.  
  
  **Domyślnie**: Nie skonfigurowano

  Po ustawieniu *włączone*, dostępne są następujące ustawienia:

    - **Minimalna długość numeru PIN**  
     Określ minimalną długość numeru PIN urządzenia, aby ułatwić bezpiecznego logowania. Ustawienia domyślne urządzenia Windows to sześć znaków, ale ustawienie to można wymusić co najmniej 4 do 127 znaków. 
  
      **Domyślne**: *Nieskonfigurowane*

    - **Maksymalna długość numeru PIN**  
    Określ maksymalną długość numeru PIN urządzenia, aby ułatwić bezpiecznego logowania. Ustawienia domyślne urządzenia Windows to sześć znaków, ale ustawienie to można wymusić co najmniej 4 do 127 znaków.  

      **Domyślne**: *Nieskonfigurowane*  

    - **Małe litery w numerze PIN**  
      można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania małych liter. Dostępne opcje:

      - **Niedozwolone** — użytkownicy nie mogą używać małych liter w numerze PIN. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
      - **Dozwolone** — użytkownicy mogą używać małych liter w numerze PIN, ale nie jest to wymagane.
      - **Wymagane** — użytkownicy muszą użyć co najmniej jednej małej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

    - **Wielkie litery w numerze PIN**  
    można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania wielkich liter. Dostępne opcje:

      - **Niedozwolone** — użytkownicy nie mogą używać wielkich liter w numerze PIN. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
      - **Dozwolone** — użytkownicy mogą używać wielkich liter w numerze PIN, ale nie jest to wymagane.
      - **Wymagane** — użytkownicy muszą użyć co najmniej jednej wielkiej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

    - **Znaki specjalne w numerze PIN**  
    można wymusić stosowanie silniejszych numerów PIN, wymagając od użytkowników końcowych zastosowania znaków specjalnych. Znaki specjalne obejmują: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  
 
      Dostępne opcje:
      - **Niedozwolone** — użytkownicy nie mogą używać znaków specjalnych w numerze PIN. To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane.
      - **Dozwolone** — użytkownicy mogą używać wielkich liter w numerze PIN, ale nie jest to wymagane.
      - **Wymagane** — użytkownicy muszą użyć co najmniej jednej wielkiej litery w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

      **Domyślne**: niedozwolone

  - **Wygaśnięcie numeru PIN (dni)**  
      Dobrze jest ustalić okres ważności dla numeru PIN, po którym użytkownicy końcowi muszą go zmienić. Ustawienia domyślne urządzenia Windows to 41 dni.

    **Domyślne**: nieskonfigurowane

  - **Pamiętaj historię numerów PIN**  
    Ogranicza ponowne używanie wcześniej stosowanych numerów PIN. Domyślnie urządzenia Windows uniemożliwia ponowne użycie pięć ostatnich numerów PIN.  

    **Domyślne**: nieskonfigurowane  

  - **Włącz odzyskiwanie kodu PIN**   
    Zezwala użytkownikowi na korzystanie z usługi Windows Hello dla firm numer PIN odzyskiwania usługi. 
    
    - **Włączone** — numer PIN odzyskiwania hasła są przechowywane na urządzeniu, a użytkownik może zmienić numer PIN, jeśli to konieczne.  
    - **Wyłączone** -secret odzyskiwania nie jest tworzone lub przechowywane.

    **Domyślnie**: Nie skonfigurowano

  - **Używaj modułu TPM (Trusted Platform Module)**    
    Moduł TPM zapewnia dodatkową warstwę zabezpieczeń danych.  

    - **Włączone** — tylko urządzenia z dostępnym modułem TPM mogą aprowizować usługę Windows Hello dla firm.
    - **Nieskonfigurowane** — urządzenia najpierw próbują użyć modułu TPM. Jeśli nie jest on dostępny, mogą używać szyfrowania programowego.
    
    **Domyślnie**: Nie skonfigurowano

  - **Zezwalaj na uwierzytelnianie biometryczne**  
     Umożliwia użycie uwierzytelniania biometrycznego, takiego jak rozpoznawanie twarzy lub linii papilarnych, zamiast numeru PIN na potrzeby usługi Windows Hello dla firm. Użytkownicy nadal muszą skonfigurować służbowy numer PIN na wypadek niepowodzenia uwierzytelniania biometrycznego. Wybierz spośród opcji:

    - **Włącz** — usługa Windows Hello dla firm pozwala na użycie uwierzytelniania biometrycznego.
    - **Nieskonfigurowane** — funkcja Windows Hello dla firm nie pozwala na użycie uwierzytelniania biometrycznego (dotyczy wszystkich typów kont).

    **Domyślnie**: Nie skonfigurowano

  - **Użyj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**  
    Określa, czy funkcje ochrony przed fałszowaniem usługi Windows Hello są używane na obsługujących je urządzeniach (np. wykrywanie fotografii twarzy zamiast prawdziwej twarzy).  
    - **Włącz** — system Windows wymaga od wszystkich użytkowników używania ochrony przed fałszowaniem na potrzeby rozpoznawania twarzy, jeśli jest obsługiwane.
    - **Nieskonfigurowane** — system Windows uwzględnia konfiguracje ochrony przed fałszowaniem na urządzeniu.

    **Domyślnie**: Nie skonfigurowano

  - **Certyfikat dla zasobów lokalnych**  

    - **Włącz** — umożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych.
    - **Nieskonfigurowane** — uniemożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych. Zamiast tego urządzenia używają zachowania domyślnego *uwierzytelniania lokalnego zaufania klucza*. Więcej informacji znajdziesz w części [User certificate for on-premises authentication](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) (Certyfikat użytkownika do uwierzytelniania lokalnego) w dokumentacji funkcji Windows Hello.  

  **Domyślnie**: Nie skonfigurowano

- **Użyj kluczy zabezpieczeń podczas logowania**  
  To ustawienie jest dostępne dla urządzeń z systemem Windows 10 w wersji 1903 lub nowszej. Przy jego użyciu zarządzać obsługę logowania przy użyciu kluczy zabezpieczeń Windows Hello.  

  - **Włączone** — użytkownicy mogą używać klucza zabezpieczeń Windows Hello, ponieważ poświadczenia logowania dla komputerów docelowych z tymi zasadami. 
  - **Wyłączone** — kluczy zabezpieczeń są wyłączone, a użytkownicy nie mogą ich używać do logowania na komputerach z systemem.   

  **Domyślnie**: Nie skonfigurowano

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
