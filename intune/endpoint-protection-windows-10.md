---
title: "Ustawienia programu Endpoint Protection usługi Intune dla systemu Windows 10"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień programu Endpoint Protection, na przykład funkcji BitLocker, na urządzeniach z systemem Windows 10."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 19c20ac5dd73b45dc06d1df6a7d08cc6bac42982
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil programu Endpoint Protection umożliwia kontrolowanie funkcji zabezpieczeń na urządzeniach z systemem Windows 10, takich jak funkcja BitLocker i usługa Windows Defender.

Skorzystaj z informacji w tym temacie, aby dowiedzieć się, jak tworzyć profile programu Endpoint Protection.

## <a name="create-an-endpoint-protection-profile"></a>Tworzenie profilu programu Endpoint Protection

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** wprowadź wartości pól **Nazwa** i **Opis** odnoszące się do profilu funkcji urządzenia.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Endpoint Protection**.
7. W bloku **Szyfrowanie systemu Windows** skonfiguruj odpowiednie ustawienia. Zapoznaj się ze szczegółowymi informacjami w tym temacie, aby lepiej zrozumieć działanie poszczególnych ustawień. Gdy skończysz, wybierz przycisk **OK**.
8. Wróć do bloku **Tworzenie profilu**, a następnie wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="windows-defender-smartscreen-settings"></a>Ustawienia filtru Windows Defender SmartScreen

- **Filtr SmartScreen dla aplikacji i plików** — Włącz filtr Windows SmartScreen na potrzeby wykonywania plików i uruchamiania aplikacji.
- **Wykonywanie niezweryfikowanych plików** — Blokuj użytkownikowi końcowemu możliwość uruchamiania plików, które nie zostały zweryfikowane przez filtr Windows SmartScreen.

## <a name="windows-encryption-settings"></a>Ustawienia szyfrowania systemu Windows

### <a name="windows-settings"></a>Ustawienia systemu Windows

- **Wymagaj, aby urządzenie było zaszyfrowane (tylko na komputerach)** — jeśli to ustawienie jest włączone, użytkownicy są monitowani o włączenie szyfrowania urządzenia. Ponadto użytkownicy zostaną poproszeni o potwierdzenie, że nie zostało włączone szyfrowanie od innego dostawcy. Jeśli szyfrowanie systemu Windows jest włączone, gdy inna metoda szyfrowania jest aktywna, urządzenie może pracować niestabilnie.
- **Wymagaj, aby karta pamięci była zaszyfrowana (tylko na urządzeniach przenośnych)** — włącz to ustawienie, aby zaszyfrować wszystkie wymienne karty pamięci używane przez urządzenie.


### <a name="bitlocker-base-settings"></a>Podstawowe ustawienia funkcji BitLocker

- **Konfiguruj metody szyfrowania** — włącz to ustawienie, aby skonfigurować algorytmy szyfrowania na potrzeby systemu operacyjnego, danych i dysków wymiennych.
    - **Szyfrowanie dla dysków z systemami operacyjnymi** — wybierz metodę szyfrowania dla dysków z systemami operacyjnymi. Zaleca się użycie algorytmu XTS-AES.
    - **Szyfrowanie dla stałych dysków danych** — wybierz metodę szyfrowania dla stałych (wbudowanych) dysków danych. Zaleca się użycie algorytmu XTS-AES.
    - **Szyfrowanie dla wymiennych dysków danych** — wybierz metodę szyfrowania dla wymiennych dysków danych. Jeśli dysk wymienny jest używany z urządzeniami z systemem innym niż Windows 10, zaleca się użycie algorytmu AES-CBC.


### <a name="bitlocker-os-drive-settings"></a>Ustawienia funkcji BitLocker dla dysku z systemem operacyjnym

- **Wymagaj dodatkowego uwierzytelniania przy uruchamianiu** -
    - **Funkcja BitLocker z niezgodnym modułem TPM** -
    - **Uruchomienie modułu TPM** — pozwala określić, czy mikroukład TPM jest dozwolony, niedozwolony, czy wymagany.
    - **Numer PIN uruchomienia modułu TPM** — pozwala określić, czy użycie numeru PIN uruchomienia dla mikroukładu TPM ma być dozwolone, niedozwolone, czy wymagane.
    - **Klucz uruchomienia modułu TPM** — pozwala określić, czy użycie klucza uruchomienia dla mikroukładu TPM ma być dozwolone, niedozwolone, czy wymagane.
    - **Klucz uruchomienia i numer PIN modułu TPM** — pozwala określić, czy użycie klucza uruchomienia i numeru PIN dla mikroukładu TPM ma być dozwolone, niedozwolone, czy wymagane.
- **Minimalna długość numeru PIN** — włącz to ustawienie, aby skonfigurować minimalną długość numeru PIN uruchomienia modułu TPM.
    - **Minimalna liczba znaków** — wprowadź liczbę znaków wymaganą dla numeru PIN uruchomienia z przedziału **4**-**20** znaków.
- **Włącz odzyskiwanie dysku systemu operacyjnego** — włącz to ustawienie, aby określić sposób odzyskiwania dysków z systemem operacyjnym chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.
    - **Agent odzyskiwania danych oparty na certyfikatach** — Włącz to ustawienie, aby możliwe było używanie agentów odzyskiwania danych względem dysków z systemem operacyjnym chronionych przez funkcję BitLocker.
    - **Tworzenie hasła odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Tworzenie klucza odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Ukryj opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom wyświetlanie lub zmianę opcji odzyskiwania po włączeniu funkcji BitLocker.
    - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS** — umożliwia zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Active Directory.
    - **Konfiguruj zapisywanie informacji odzyskiwania funkcji BitLocker w usługach AD DS** — pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Active Directory. Wybierz spośród opcji:
        - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
        - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
    - **Wymagaj zapisania informacji odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom włączenie funkcji BitLocker, chyba że urządzenie jest przyłączone do domeny, a informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Active Directory.
- **Włącz komunikat i adres URL dotyczący odzyskiwania przed rozruchem** — włącz to ustawienie, aby skonfigurować komunikat i adres URL wyświetlane na ekranie odzyskiwania kluczy przed rozruchem.
    - **Komunikat odzyskiwania przed rozruchem** — pozwala określić sposób wyświetlania użytkownikom komunikatu odzyskiwania przed rozruchem. Wybierz spośród opcji:
        - **Użyj domyślnego komunikatu i adresu URL dotyczącego odzyskiwania**
        - **Użyj pustego komunikatu i adresu URL dotyczącego odzyskiwania**
        - **Użyj niestandardowego komunikatu dotyczącego odzyskiwania**
        - **Użyj niestandardowego adresu URL odzyskiwania**


### <a name="bitlocker-fixed-data-drive-settings"></a>Ustawienia stałych dysków danych w funkcji BitLocker

- **Zabroń dostępu do zapisu dla stałych dysków danych, które nie są chronione przez funkcję BitLocker** — jeśli to ustawienie jest włączone, ochrona za pomocą funkcji BitLocker musi być włączona na wszystkich stałych lub wbudowanych dyskach danych, aby możliwy był na nich zapis.
- **Włącz odzyskiwanie dysku stałego** — włącz to ustawienie, aby określić sposób odzyskiwania dysków stałych chronionych przez funkcję BitLocker, jeśli wymagane informacje dotyczące uruchamiania nie są dostępne.
    - **Agent odzyskiwania danych** — Włącz to ustawienie, aby możliwe było używanie agentów odzyskiwania danych względem dysków stałych chronionych przez funkcję BitLocker.
    - **Tworzenie hasła odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 48-cyfrowego hasła odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.  
    - **Tworzenie klucza odzyskiwania przez użytkownika** — pozwala określić, czy wygenerowanie przez użytkowników 256-bitowego klucza odzyskiwania ma być dozwolone, wymagane, czy niedozwolone.
    - **Ukryj opcje odzyskiwania w kreatorze konfiguracji funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom wyświetlanie lub zmianę opcji odzyskiwania po włączeniu funkcji BitLocker.
    - **Zapisz informacje o odzyskiwaniu funkcji BitLocker w usługach AD DS** — umożliwia zapisywanie informacji odzyskiwania funkcji BitLocker w usłudze Active Directory.
    - **Konfiguruj zapisywanie informacji odzyskiwania funkcji BitLocker w usługach AD DS** — pozwala określić, które części informacji odzyskiwania funkcji BitLocker są zapisywane w usłudze Active Directory. Wybierz spośród opcji:
        - **Wykonaj kopie zapasowe haseł odzyskiwania i pakietów kluczy**
        - **Wykonaj kopie zapasowe tylko haseł odzyskiwania**
    - **Wymagaj zapisania informacji odzyskiwania w usługach AD DS przed włączeniem funkcji BitLocker** — włącz to ustawienie, aby uniemożliwić użytkownikom włączenie funkcji BitLocker, chyba że urządzenie jest przyłączone do domeny, a informacje odzyskiwania funkcji BitLocker zostały pomyślnie zapisane w usłudze Active Directory.


### <a name="bitlocker-removable-data-drive-settings"></a>Ustawienia wymiennych dysków danych w funkcji BitLocker

- **Zabroń dostępu do zapisu dla wymiennych dysków danych, które nie są chronione przez funkcję BitLocker** — określ, czy dla wymiennych dysków magazynu wymagane jest szyfrowanie za pomocą funkcji BitLocker.
    - **Blokuj dostęp do zapisu dla urządzeń skonfigurowanych w innej organizacji** — określ, czy możliwy ma być zapis na wymiennych dyskach danych, które należą do innej organizacji.



## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).
