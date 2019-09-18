---
title: Rejestracja zbiorcza urządzeń z systemem Windows 10
titleSuffix: Microsoft Intune
description: Tworzenie pakietu rejestracji zbiorczej dla usługi Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: spshumwa
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8344184a9d5f6957c815259c41835311d953e05
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2019
ms.locfileid: "71080096"
---
# <a name="bulk-enrollment-for-windows-devices"></a>Rejestracja zbiorcza urządzeń z systemem Windows

Jako administrator możesz dołączyć dużą liczbę nowych urządzeń z systemem Windows do usługi Azure Active Directory i Intune. W celu umożliwienia zbiorczego rejestrowania urządzeń dla dzierżawy usługi Azure AD utwórz pakiet aprowizacyjny przy użyciu aplikacji Windows Configuration Designer (WCD). Zastosowanie pakietu aprowizacyjnego do urządzeń stanowiących własność firmy powoduje ich dołączenie do dzierżawy usługi Azure AD i zarejestrowanie w usłudze Intune w celu umożliwienia zarządzania nimi. Po zastosowaniu pakietu użytkownicy usługi Azure AD mogą się zalogować.

Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady usługi Intune oraz wymagane aplikacje. Urządzenia z systemem Windows zarejestrowane w usłudze Intune przy użyciu rejestracji zbiorczej systemu Windows mogą instalować dostępne aplikacje przy użyciu aplikacji Portal firmy. 

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Wymagania wstępne dotyczące rejestracji zbiorczej urządzeń z systemem Windows

- Urządzenia z aktualizacją systemu Windows 10 dla twórców (kompilacja 1703) lub nowszą wersją
- [Automatyczne rejestrowanie urządzeń z systemem Windows](windows-enroll.md#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Tworzenie pakietu aprowizacyjnego

1. Pobierz aplikację [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) ze Sklepu Microsoft.
   ![Zrzut ekranu przedstawiający aplikację Windows Configuration Designer ze sklepu App Store](media/bulk-enroll-store.png)

2. Otwórz aplikację **Windows Configuration Designer** i wybierz opcję **Provision desktop devices** (Aprowizuj urządzenia stacjonarne).
   ![Zrzut ekranu przedstawiający wybór opcji aprowizacji urządzeń stacjonarnych w aplikacji Windows Configuration Designer](media/bulk-enroll-select.png)

3. Zostanie wyświetlone okno dialogowe **New project** (Nowy projekt), w którym należy podać następujące dane:
   - **Name** (Nazwa) — nazwa projektu
   - **Project folder** (Folder projektu) — lokalizacja zapisu dla projektu
   - **Description** (Opis) — opcjonalny opis projektu ![Zrzut ekranu przedstawiający proces wpisywania nazwy, folderu projektu i opisu w aplikacji Windows Configuration Designer](media/bulk-enroll-name.png)

4. Wprowadź unikatową nazwę dla każdego z urządzeń. Nazwy mogą zawierać numer seryjny (%SERIAL%) lub losowy zestaw znaków. Opcjonalnie można także wprowadzić klucz produktu (w przypadku uaktualniania wersji systemu Windows), skonfigurować urządzenie pod kątem współużytkowania i usunąć wstępnie zainstalowane oprogramowanie.
   
   ![Zrzut ekranu przedstawiający proces określania nazwy i klucza produktu w aplikacji Windows Configuration Designer](media/bulk-enroll-device.png)

5. Opcjonalnie można skonfigurować sieć Wi-Fi, z którą urządzenia połączą się po pierwszym uruchomieniu.  Jeśli urządzenia sieciowe nie zostaną skonfigurowane, podczas pierwszego uruchomienia urządzenia wymagane będzie połączenie sieci przewodowej.
   ![Zrzut ekranu przedstawiający włączanie w aplikacji Windows Configuration Designer obsługi sieci Wi-Fi, w tym ustawienia SSID sieci i typu sieci](media/bulk-enroll-network.png)

6. Wybierz opcję **Enroll in Azure AD** (Zarejestruj w usłudze Azure AD), wypełnij pole **Bulk Token Expiry** (Data wygaśnięcia tokenu zbiorczego), a następnie wybierz przycisk **Get Bulk Token** (Uzyskaj token zbiorczy).
   ![Zrzut ekranu przedstawiający zarządzanie kontem w aplikacji Windows Configuration Designer](media/bulk-enroll-account.png)

7. Wprowadź swoje poświadczenia usługi Azure AD, aby uzyskać token zbiorczy.
   ![Zrzut ekranu przedstawiający logowanie się do aplikacji Windows Configuration Designer](media/bulk-enroll-cred.png)

8. Po pomyślnym pobraniu **tokenu zbiorczego** kliknij przycisk **Dalej**.

9. Opcjonalnie możesz wybrać pozycję **Add applications** (Dodaj aplikacje) i **Add certificates** (Dodaj certyfikaty). Te aplikacje i certyfikaty są aprowizowane na urządzeniu.

10. Opcjonalnie możesz objąć pakiet aprowizacyjny ochroną hasłem.  Kliknij przycisk **Utwórz**.
    ![Zrzut ekranu przedstawiający ochronę pakietu w aplikacji Windows Configuration Designer](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Aprowizowanie urządzeń

1. Uzyskaj dostęp do pakietu aprowizacyjnego w lokalizacji określonej w ustawieniu **Project folder** (Folder projektu) w aplikacji.

2. Określ, jak użytkownik może zastosować pakiet aprowizacyjny do urządzenia.  Pakiet aprowizacyjny może zostać zastosowany do urządzenia na jeden z następujących sposobów:
   - Umieść pakiet aprowizacyjny na dysku USB, podłącz dysk USB do urządzenia, które ma zostać poddane rejestrowaniu zbiorczemu i zastosuj go podczas konfiguracji wstępnej
   - Umieść pakiet aprowizacyjny w folderze sieciowym i zastosuj go do po konfiguracji wstępnej

   Aby uzyskać instrukcje krok po kroku dotyczące stosowania pakietu aprowizacyjnego, zobacz artykuł [Apply a provisioning package](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package) (Stosowanie pakietu aprowizacyjnego).

3. Po zastosowaniu pakietu urządzenie zostanie automatycznie uruchomione ponownie w ciągu jednej minuty.
   ![Zrzut ekranu przedstawiający proces określania nazwy, folderu projektu i opisu w aplikacji Windows Configuration Designer](media/bulk-enroll-add.png)

4. Po ponownym uruchomieniu urządzenie nawiązuje połączenie z usługą Azure Active Directory i zostaje zarejestrowane w usłudze Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Rozwiązywanie problemów dotyczących rejestrowania zbiorczego w systemie Windows

### <a name="provisioning-issues"></a>Problemy z aprowizacją
Aprowizacja to funkcja przeznaczona do użycia na nowych urządzeniach z systemem Windows. Problemy z aprowizowaniem mogą wymagać wyczyszczenia urządzenia lub odzyskania urządzenia z obrazu rozruchowego. Poniżej opisano przykładowe przyczyny niepowodzeń aprowizacji:

- Pakiet aprowizacyjny, który próbuje przyłączyć urządzenie do domeny usługi Active Directory lub dzierżawy usługi Azure Active Directory, która nie tworzy konta lokalnego, może spowodować, że urządzenie będzie nieosiągalne w przypadku niepowodzenia procesu przyłączania do domeny w wyniku braku łączności sieciowej.
- Skrypty są uruchamiane przez pakiet aprowizacyjny w kontekście systemu. Skrypty mogą wprowadzać dowolne zmiany w systemie plików i konfiguracji urządzenia. Złośliwy lub nieprawidłowy skrypt może spowodować, że urządzenie znajdzie się w stanie, którego naprawienie będzie wymagać odtwarzania z obrazu lub wyczyszczenia danych z urządzenia.

### <a name="bulk-enrollment-with-wi-fi"></a>Rejestrowanie zbiorcze za pomocą sieci Wi-Fi 

W przypadku urządzeń zarejestrowanych zbiorczo nie można używać certyfikatów ukierunkowanych na użytkowników i wdrożenia sieci Wi-Fi. Aby zarządzać tymi połączeniami, trzeba użyć [certyfikatów na poziomie urządzeń](certificates-configure.md). 

### <a name="conditional-access"></a>Dostęp warunkowy
Dostęp warunkowy nie jest dostępny dla urządzeń z systemem Windows zarejestrowanych zbiorczo.
