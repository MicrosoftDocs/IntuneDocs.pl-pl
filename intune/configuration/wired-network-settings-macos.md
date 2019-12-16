---
title: Konfigurowanie ustawień sieci przewodowej dla urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń sieci przewodowej z systemem macOS. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/4/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dba36d03489bcdeee3c3c1f69a4995823dd21ee
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2019
ms.locfileid: "74994335"
---
# <a name="add-wired-network-settings-for-macos-devices-in-microsoft-intune"></a>Dodawanie ustawień sieci przewodowej dla urządzeń macOS w Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Można utworzyć profil z określonymi ustawieniami sieci przewodowej, a następnie wdrożyć ten profil na urządzeniach z systemem macOS. Usługa Microsoft Intune oferuje wiele funkcji, w tym uwierzytelnianie do sieci, dodawanie klucza wstępnego lub protokołu SCEP i inne. 

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](device-profile-create.md).

> [!NOTE]
> Te ustawienia są dostępne dla wszystkich typów rejestracji. Aby uzyskać więcej informacji na temat typów rejestracji, zobacz [Rejestrowanie macOS](../enrollment/macos-enroll.md).

## <a name="profiles"></a>Profile

- **Typ profilu**: Wybierz **sieć przewodową**.
- **Interfejs sieciowy**: 
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje:
  - **EAP-FAST**: wprowadź **ustawienia PAC (Protected Access Credential)**. Ta opcja używa poświadczeń dostępu chronionego do utworzenia uwierzytelnionego tunelu między klientem i serwerem uwierzytelniania. Dostępne opcje:
    - **Nie używaj (PAC)**
    - **Użyj (PAC)**: jeśli plik PAC istnieje, użyj go.
    - **Użyj pliku PAC i aprowizuj go**: tworzenie i aprowizowanie pliku PAC dla urządzeń.
    - **Użyj pliku PAC i aprowizuj go anonimowo**: tworzenie i dodawanie pliku PAC do urządzeń bez uwierzytelniania na serwerze.
  - **EAP-TLS**: wprowadź też następujące ustawienia:
    - **Zaufanie serwera** - **Nazwy serwerów certyfikatów**: **dodaj** co najmniej jedną nazwę pospolitą używaną w certyfikatach wystawionych przez zaufany urząd certyfikacji. W przypadku wprowadzania tych informacji można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników nawiązujących połączenie z siecią Wi-Fi.
    - **Certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przesyłany na serwer, gdy klient łączy się z siecią, i jest używany do uwierzytelniania połączenia.
    - **Uwierzytelnianie klienta** - **certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**: wybierz profil certyfikatu protokołu SCEP lub standardów PKCS, który również został wdrożony do urządzenia. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.
  - **EAP-TTLS**: wprowadź też następujące ustawienia:
    - **Zaufanie serwera** - **Nazwy serwerów certyfikatów**: **dodaj** co najmniej jedną nazwę pospolitą używaną w certyfikatach wystawionych przez zaufany urząd certyfikacji. W przypadku wprowadzania tych informacji można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników nawiązujących połączenie z siecią Wi-Fi.
    - **Certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przesyłany na serwer, gdy klient łączy się z siecią, i jest używany do uwierzytelniania połączenia.
    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:
      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda inna niż EAP (tożsamość wewnętrzna)**: wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi.
          Dostępne opcje: **Hasło nieszyfrowane (PAP)**, **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**, **Microsoft CHAP (MS-CHAP)** i **Microsoft CHAP wersja 2 (MS-CHAP v2)**
      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub standardów PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.
      - **Prywatność tożsamości (tożsamość zewnętrzna)**: wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.
  - **LEAP**
  - **PEAP**: wprowadź też następujące ustawienia:
    - **Zaufanie serwera** - **Nazwy serwerów certyfikatów**: **dodaj** co najmniej jedną nazwę pospolitą używaną w certyfikatach wystawionych przez zaufany urząd certyfikacji. W przypadku wprowadzania tych informacji można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników nawiązujących połączenie z siecią Wi-Fi.
    - **Certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przesyłany na serwer, gdy klient łączy się z siecią, i jest używany do uwierzytelniania połączenia.
    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:
      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. 
      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub standardów PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.
      - **Prywatność tożsamości (tożsamość zewnętrzna)**: wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypisz ten profil](device-profile-assign.md) i [monitoruj jego stan](device-profile-monitor.md).

Konfigurowanie ustawień sieci Wi-Fi na urządzeniach z [systemem Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [iOS](wi-fi-settings-ios.md)i [Windows 10](wi-fi-settings-windows.md) .
