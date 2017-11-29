---
title: "Integrowanie narzędzia Jamf Pro z usługą Intune w celu zachowania zgodności"
titlesuffix: Azure portal
description: "Wykorzystaj zgodność w celu ułatwienia zabezpieczania urządzeń zarządzanych za pomocą narzędzia Jamf."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b37ffd23f8cf8764ba457b0803dfc308cf1c071
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrowanie narzędzia Jamf Pro z usługą Intune w celu zachowania zgodności

|Dotyczy: usługa Intune w witrynie Azure Portal |
|--|
|Szukasz dokumentacji dotyczącej usługi Intune w portalu klasycznym? [Przejdź tutaj](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Aktualnie w prywatnej wersji zapoznawczej|
|--|
|Funkcje opisane w tym temacie są aktualnie dostępne jedynie dla klientów prywatnej wersji zapoznawczej. Ten komunikat zostanie usunięty po udostępnieniu funkcji wszystkim klientom.|
| |

Jeśli do zarządzania użytkownikami końcowymi komputerów Mac Twoja organizacja używa narzędzia [Jamf Pro](https://www.jamf.com), zastosowanie zasad zgodności usługi Microsoft Intune i dostępu warunkowego usługi Azure Active Directory zapewnia, że urządzenia w organizacji będą zgodne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować dostęp warunkowy przy użyciu narzędzia Jamf Pro, wymagane są następujące elementy:

- Dostęp do prywatnej wersji zapoznawczej usługi Intune w celu uzyskania dostępu warunkowego urządzeń z systemem macOS
- Program Jamf Pro 10.1.0 lub nowsza wersja
- [Aplikacja Portal firmy dla systemu macOS](https://aka.ms/macoscompanyportal)
- Urządzenia z systemem macOS (OS X 10.11 Yosemite lub nowszy)

## <a name="connecting-intune-to-jamf-pro"></a>Połączenie usługi Intune z narzędziem Jamf Pro

Usługę Intune można połączyć z narzędziem Jamf Pro poprzez:

1. Utworzenie nowej aplikacji na platformie Azure
2. Włączenie możliwości integracji usługi Intune z narzędziem Jamf Pro
3. Skonfigurowanie dostępu warunkowego w narzędziu Jamf Pro

## <a name="create-a-new-application-in-azure-active-directory"></a>Utworzenie nowej aplikacji w usłudze Azure Active Directory

1. Otwórz opcję **Azure Active Directory** > **Rejestracja aplikacji**.
2. Kliknij przycisk **+Rejestrowanie nowej aplikacji**.
3. Wprowadź **nazwę wyświetlaną**, np. **Dostęp warunkowy Jamf**.
4. Wybierz opcję **Interfejs API/aplikacja sieci Web**.
5. Określ **Adres URL logowania** dla narzędzia Jamf Pro.
6. Kliknij przycisk **Utwórz aplikację**.
7. Zapisz nowo utworzony **Identyfikator aplikacji**, a następnie otwórz opcję **Wszystkie ustawienia** > **Klucze**, aby utworzyć nowy klucz aplikacji. Zapisz klucz aplikacji.

  > [!NOTE]
  > W trakcie tego procesu klucz aplikacji jest wyświetlany tylko raz. Pamiętaj, aby zapisać go w innym miejscu, z którego łatwo można go będzie pobrać.

8. Przejdź do opcji **Wszystkie ustawienia** > **Dostęp do interfejsu API** > **Wymagane uprawnienia** i usuń wszystkie uprawnienia.

  > [!NOTE]
  > Dodaj nowe wymagane uprawnienie. Aplikacja może działać prawidłowo tylko w sytuacji, gdy ma pojedyncze wymagane uprawnienie.

9.  Wybierz opcję **Interfejs API usługi Microsoft Intune** i kliknij przycisk **Wybierz**.
10. Wybierz opcję **Wyślij atrybuty urządzenia do usługi Microsoft Intune** i kliknij przycisk **Wybierz**.
11. Po zapisaniu wymaganych uprawnień dla aplikacji kliknij przycisk **Udziel uprawnień**.

  > [!NOTE]
  > Jeśli klucz aplikacji wygaśnie, należy utworzyć nowy klucz aplikacji na platformie Microsoft Azure, a następnie zaktualizować dane dostępu warunkowego w narzędziu Jamf Pro. Aby uniknąć zakłóceń w świadczeniu usług, platforma Azure umożliwia stosowanie zarówno starego, jak i nowego klucza.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Włączanie możliwości integracji usługi Intune z narzędziem Jamf Pro

1. W portalu Microsoft Azure otwórz opcję **Microsoft Intune** > **Zgodność urządzeń** > **Łącznik zgodności dla oprogramowania Jamf**.
2. Włącz Łącznik zgodności dla narzędzia Jamf poprzez wklejenie identyfikatora aplikacji w polu **Identyfikator aplikacji usługi Azure Active Directory w oprogramowaniu Jamf**.
3. Kliknij polecenie **Zapisz**.

## <a name="configure-conditional-access-in-jamf-pro"></a>Skonfigurowanie dostępu warunkowego w narzędziu Jamf Pro

1. W narzędziu Jamf Pro przejdź do opcji **Globalne zarządzanie** > **Dostęp warunkowy**. Kliknij przycisk **Edytuj** znajdujący się na karcie **Microsoft**.
2. Zaznacz pole wyboru opcji **Włącz dostęp warunkowy Microsoft**.
3. Podaj wymagane informacje o dzierżawie platformy Azure, w tym zapisane w poprzednich krokach wartości pól **Lokalizacja**, **Nazwa domeny**, **Identyfikator aplikacji** i **Klucz aplikacji**.
4. Kliknij polecenie **Zapisz**. Narzędzie Jamf Pro dokona sprawdzenia ustawień i zweryfikuje poprawność konfiguracji.

## <a name="information-shared-from-jamf-pro-to-intune"></a>Informacje przekazywane z narzędzia Jamf Pro do usługi Intune

Narzędzie Jamf Pro przechwytuje informacje dotyczące spisu zarządzanych urządzeń z systemem macOS. Narzędzie Jamf Pro zgłasza do usługi Intune następujące informacje:

* Identyfikator urządzenia w usłudze Azure Active Directory
* Stan spisu JAMF (stan spisu komputera zaewidencjonowanego w oprogramowaniu Jamf Pro w ciągu ostatnich 24 godzin)
* Wersja systemu operacyjnego
* Identyfikator użytkownika w usłudze Azure Active Directory
* Zaszyfrowane (FileVault 2)
* Stan programu Gatekeeper
* Hasło: minimalna liczba zestawów znaków
* Wygaśnięcie hasła (dni)
* Typ hasła — prosty, alfanumeryczny lub nieznany
* Zapobieganie automatycznemu logowaniu
* Wymagana długość kodu dostępu
* Hasło: liczba poprzednich haseł, których nie można użyć ponownie
* Ochrona integralności systemu
* Czas ostatniego zaewidencjonowania
* Typ architektury
* Dostępne gniazda pamięci RAM
* Pojemność baterii
* Pamięć rozruchowa ROM
* Szybkość magistrali
* Rozmiar pamięci podręcznej
* Nazwa urządzenia
* Przyłączanie do domeny
* Identyfikator Jamf
* Adres MAC
* Marka
* Model
* Identyfikator modelu
* Szybkość karty sieciowej
* Liczba rdzeni
* Liczba procesorów
* System operacyjny
* Platforma
* Szybkość procesora
* Typ procesora
* Dodatkowy adres MAC
* Numer seryjny
* Wersja SMC
* Całkowita ilość pamięci RAM
* Identyfikator UDID
* Adres e-mail użytkownika

## <a name="next-steps"></a>Następne kroki

- [Stosowanie zasad zgodności do urządzeń zarządzanych za pomocą narzędzia Jamf](conditional-access-assign-jamf.md)
