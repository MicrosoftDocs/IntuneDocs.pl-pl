---
title: Jak zintegrować usługę Windows Hello dla firm z usługą Microsoft Intune
titleSuffix: ''
description: Tworzenie zasad umożliwiających kontrolę sposobu korzystania z funkcji Windows Hello dla firm na urządzeniach zarządzanych.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e701f1b9cddf5b5b2d7a864da1f5d286a6872c3f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="integrate-windows-hello-for-business-with-microsoft-intune"></a>Integracja usługi Windows Hello dla firm z usługą Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługę Windows Hello dla firm (poprzednio Microsoft Passport for Work) można zintegrować z usługą Microsoft Intune.

 Usługa Hello dla firm to alternatywna metoda logowania korzystająca z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej. Pozwala ona używać do logowania *gestu użytkownika* zamiast hasła. Gestem użytkownika może być prosty numer PIN, uwierzytelnianie biometryczne, takie jak Windows Hello, lub urządzenie zewnętrzne, np. czytnik linii papilarnych.

Integracja usługi Intune z usługą Hello dla firm następuje na dwa sposoby:

-   Za pomocą zasad usługi Intune można określać gesty, przy użyciu których użytkownicy mogą się logować.

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> W systemie Windows 10 w wersji Desktop i Mobile przed aktualizacją Anniversary Update można było ustawić dwa różne numery PIN służące do uwierzytelniania zasobów:
> - **Numer PIN urządzenia** umożliwiał odblokowanie urządzenia i nawiązanie połączenia z zasobami w chmurze.
> - **Służbowy numer PIN** służył do uzyskiwania dostępu do zasobów usługi Azure AD na urządzeniach osobistych użytkownika (BYOD).
> 
> W aktualizacji Anniversary Update te dwa numery PIN zostały scalone w jeden numer PIN urządzenia.
> Wszystkie ustawione zasady konfiguracji usługi Intune służące do kontrolowania numeru PIN urządzenia oraz wszystkie skonfigurowane zasady usługi Windows Hello dla firm ustawiają teraz tę nową wartość numeru PIN.
> Jeśli ustawiono kontrolę numeru PIN przy użyciu obu typów zasad, zasady usługi Windows Hello dla firm są stosowane zarówno na komputerach stacjonarnych, jak i na urządzeniach przenośnych z systemem Windows 10.
> Aby zapewnić rozwiązywanie konfliktów i prawidłowe stosowanie zasad dotyczących numeru PIN, zaktualizuj zasady usługi Windows Hello dla firm, aby były zgodne z ustawieniami w zasadach konfiguracji i poproś użytkowników o zsynchronizowanie swoich urządzeń w aplikacji Portal firmy.



## <a name="create-a-windows-hello-for-business-policy"></a>Tworzenie zasad usługi Windows Hello dla firm

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > **Monitorowanie + zarządzanie** > **Intune**.

2. W okienku usługi Intune wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Rejestracja w systemie Windows** > **Windows Hello dla firm**.

3. W otwartym okienku wybierz ustawienia **Domyślne**.

4. W okienku **Wszyscy użytkownicy** kliknij pozycję **Właściwości**, a następnie uzupełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do ustawień usługi Windows Hello dla firm.

5. W okienku **Wszyscy użytkownicy** kliknij pozycję **Ustawienia**, a następnie wybierz jedną z następujących wartości pozycji **Skonfiguruj usługę Windows Hello dla firm**:

    - **Wyłączony**. Wybierz to ustawienie, jeśli nie chcesz używać usługi Windows Hello dla firm. Wszystkie inne ustawienia na ekranie będą wtedy niedostępne.
    - **Włączony**. Wybierz to ustawienie, jeśli chcesz skonfigurować ustawienia usługi Windows Hello dla firm.
    - **Nieskonfigurowane**. Wybierz to ustawienie, jeśli nie chcesz używać usługi Intune do kontrolowania ustawień usługi Windows Hello dla firm. Żadne z istniejących ustawień usługi Windows Hello dla firm na urządzeniach z systemem Windows 10 nie są zmieniane. Wszystkie inne ustawienia w okienku są niedostępne.

6. W przypadku wybrania w poprzednim kroku pozycji **Włączony** należy skonfigurować wymagane ustawienia, które są stosowane do wszystkich zarejestrowanych urządzeń z systemami Windows 10 i Windows 10 Mobile.

   - **Używaj modułu TPM (Trusted Platform Module)**. Moduł TPM zapewnia dodatkową warstwę zabezpieczeń danych.<br>Wybierz jedną z następujących opcji:

     - **Wymagane** (domyślnie). Tylko urządzenia z dostępnym modułem TPM mogą aprowizować usługę Windows Hello dla firm.
     - **Preferowane**. Urządzenia najpierw próbują użyć modułu TPM. Jeśli nie jest on dostępny, mogą używać szyfrowania programowego.

   - **Minimalna długość numeru PIN**/**Maksymalna długość numeru PIN**. Konfiguruje urządzenia do używania określonych minimalnych i maksymalnych długości numeru PIN, co pomaga zapewnić bezpieczne logowanie. Domyślna długość numeru PIN to sześć znaków, ale można wymusić stosowanie numerów o długości minimalnej czterech znaków. Maksymalna długość numeru PIN to 127 znaków.

   - **Małe litery w numerze PIN**/**Wielkie litery w numerze PIN**/**Znaki specjalne w numerze PIN**. Można wymusić stosowanie silniejszych numerów PIN poprzez wymaganie użycia wielkich liter, małych liter i znaków specjalnych w numerze PIN. Wybierz spośród opcji:

     - **Dozwolone**. Użytkownicy mogą używać typu znaków w numerze PIN, ale nie jest to konieczne.

     - **Wymagane**. Użytkownicy muszą zawrzeć co najmniej jeden z typów znaków w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

     - **Niedozwolone** (ustawienie domyślne). Użytkownicy nie mogą używać tego typu znaków w numerach PIN. (Ta wartość jest stosowana także w przypadku, gdy parametr nie zostanie skonfigurowany).<br>Znaki specjalne obejmują: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Wygaśnięcie numeru PIN (dni)**. Dobrze jest ustalić okres ważności dla numeru PIN, po którym użytkownicy końcowi muszą go zmienić. Wartość domyślna to 41 dni.

   - **Pamiętaj historię numerów PIN**. Ogranicza ponowne używanie wcześniej stosowanych numerów PIN. Domyślnie nie jest dozwolone ponowne użycie żadnego z 5 ostatnich numerów PIN.

   - **Zezwalaj na uwierzytelnianie biometryczne**. Umożliwia użycie uwierzytelniania biometrycznego, takiego jak rozpoznawanie twarzy lub linii papilarnych, zamiast numeru PIN na potrzeby usługi Windows Hello dla firm. Użytkownicy nadal muszą skonfigurować służbowy numer PIN na wypadek niepowodzenia uwierzytelniania biometrycznego. Wybierz spośród opcji:

     - **Tak**. Usługa Windows Hello dla firm pozwala na użycie uwierzytelniania biometrycznego.
     - **Nie**. Usługa Windows Hello dla firm nie pozwala na użycie uwierzytelniania biometrycznego (dotyczy wszystkich typów kont).

   - **Użyj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**. Określa, czy funkcje ochrony przed fałszowaniem usługi Windows Hello są używane na obsługujących je urządzeniach (np. wykrywanie fotografii twarzy zamiast prawdziwej twarzy).<br>W przypadku wybrania opcji **Tak** system Windows wymaga od wszystkich użytkowników używania ochrony przed fałszowaniem na potrzeby rozpoznawania twarzy, jeśli jest obsługiwana.

   - **Zezwalaj na logowanie za pomocą telefonu**. W przypadku wybrania opcji **Tak** użytkownicy mogą używać paszportu zdalnego jako przenośnego urządzenia towarzyszącego w celu uwierzytelniania komputerów stacjonarnych. Komputer stacjonarny musi być przyłączony do usługi Azure Active Directory, a urządzenie towarzyszące musi mieć skonfigurowany numer PIN usługi Windows Hello dla firm.

## <a name="windows-holographic-for-business-support"></a>Obsługa systemu Windows Holographic for Business

System Windows Holographic for Business obsługuje następujące ustawienia usługi Windows Hello dla firm:

- Używaj modułu TPM (Trusted Platform Module)
- Minimalna długość numeru PIN
- Maksymalna długość numeru PIN
- Małe litery w numerze PIN
- Wielkie litery w numerze PIN
- Znaki specjalne w numerze PIN
- Wygaśnięcie numeru PIN (dni)
- Pamiętaj historię numerów PIN

## <a name="further-information"></a>Dodatkowe informacje
Aby uzyskać więcej informacji na temat usługi Microsoft Passport, zobacz [przewodnik](https://technet.microsoft.com/library/mt589441.aspx) w dokumentacji systemu Windows 10.
