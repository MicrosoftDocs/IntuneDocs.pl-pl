---
title: Tworzenie profilów certyfikatów w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil certyfikatu dla urządzeń poprzez skonfigurowanie środowiska certyfikatu SCEP lub PKCS, wyeksportowanie certyfikatu publicznego, utworzenie profilu w witrynie Azure Portal, a następnie przypisanie środowiska SCEP lub PKCS do profilów certyfikatów w usłudze Microsoft Intune w witrynie Azure Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89f8ddc105787bc7ff4f7cfc1e226d28589ecbbf
ms.sourcegitcommit: 9536300a6211bac4bdc733593a40c1ae47611de3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2018
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Konfigurowanie profilu certyfikatu dla urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Po zapewnieniu użytkownikom dostępu do zasobów firmowych za pośrednictwem sieci VPN, sieci Wi-Fi lub profilów poczty e-mail możesz uwierzytelnić te połączenia przy użyciu certyfikatów. Nie musisz wprowadzać nazw użytkownika i haseł, aby uwierzytelnić połączenia, jeśli używasz certyfikatów

Możesz użyć usługi Intune w celu przypisania tych certyfikatów do zarządzanych urządzeń. Usługa Intune obsługuje przypisywanie następujących typów certyfikatów i zarządzanie nimi:

- Prosty protokół rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol)
- PKCS#12 (lub PFX)

Każdy z tych typów certyfikatów ma własne wymagania wstępne i wymagania dotyczące infrastruktury.

## <a name="overview"></a>Przegląd

1. Upewnij się, że dysponujesz odpowiednią infrastrukturą certyfikatów. Możesz użyć [certyfikatów protokołu SCEP](certificates-scep-configure.md) i [certyfikatów protokołu PKCS](certficates-pfx-configure.md).

2. Zainstaluj certyfikat główny lub certyfikat pośredniego urzędu certyfikacji (CA) na każdym urządzeniu, aby urządzenia rozpoznawały urząd certyfikacji jako wiarygodny. W tym celu należy utworzyć i przypisać **profil zaufanego certyfikatu**. Po przypisaniu tego profilu urządzenia zarządzane przy użyciu usługi Intune zażądają certyfikatu głównego i otrzymają go. Dla każdej platformy należy utworzyć oddzielny profil. Profile zaufanego certyfikatu są dostępne dla następujących platform:

    - System iOS 8.0 i nowsze
    - System macOS 10.11 i nowsze
    - Android 4.0 i nowsze
    - Program Android for Work
    - Windows 8.1 i nowsze
    - System Windows Phone 8.1 lub nowszy
    - System Windows 10 lub nowszy

3. Utwórz profile certyfikatów, aby mieć pewność, że poszczególne urządzenia żądają certyfikatu w celu jego użycia do uwierzytelniania dostępu do poczty e-mail, sieci VPN i sieci Wi-Fi. Na potrzeby urządzeń korzystających z następujących platform można tworzyć i przypisywać profile certyfikatów protokołów **PKCS** i **SCEP**:

   - System iOS 8.0 i nowsze
   - Android 4.0 i nowsze
   - Program Android for Work
   - System Windows 10 (Desktop i Mobile) i nowsze

   Profilu certyfikatu protokołu **SCEP** możesz użyć wyłącznie na urządzeniach z następującymi platformami:

   - System macOS 10.9 i nowsze
   - System Windows Phone 8.1 lub nowszy

Dla każdej platformy urządzenia należy utworzyć oddzielny profil. Po utworzeniu certyfikatu należy go skojarzyć z utworzonym profilem zaufanego certyfikatu głównego.

### <a name="further-considerations"></a>Dodatkowe uwagi

- Jeśli nie masz urzędu certyfikacji przedsiębiorstwa, musisz go utworzyć
- Jeśli używasz profilów SCEP, skonfiguruj serwer usługi rejestracji urządzeń sieciowych
- Niezależnie od tego, czy zamierzasz używać profilów certyfikatów protokołu SCEP, czy PKCS, pobierz i skonfiguruj łącznik certyfikatów usługi Microsoft Intune


## <a name="step-1-configure-your-certificate-infrastructure"></a>Krok 1 — Konfigurowanie infrastruktury certyfikatów

Aby uzyskać pomoc dotyczącą konfigurowania infrastruktury dla każdego z typów profilów certyfikatu, zobacz następujące tematy:

- [Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune](certificates-scep-configure.md)
- [Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Krok 2 — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji

Wyeksportuj certyfikat zaufanego głównego urzędu certyfikacji w formacie certyfikatu publicznego (cer) z wystawiającego urzędu certyfikacji lub dowolnego urządzenia traktującego wystawiający urząd certyfikacji jako zaufany. Nie eksportuj klucza prywatnego (pfx).

Ten certyfikat zostanie zaimportowany podczas konfigurowania profilu zaufanego certyfikatu.

## <a name="step-3-create-trusted-certificate-profiles"></a>Krok 3 — Tworzenie profilów zaufanych certyfikatów
Aby móc utworzyć profil certyfikatu protokołu SCEP lub PKCS, utwórz profil zaufanego certyfikatu. Dla każdej platformy urządzenia wymagany jest profil zaufanego certyfikatu oraz profil SCEP lub PKCS. Kroki związane z tworzeniem zaufanych certyfikatów są podobne dla każdej platformy urządzeń.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** wybierz pozycję **Zarządzaj** > **Profile**.
3. W okienku profilów wybierz pozycję **Utwórz profil**.
4. W okienku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu zaufanego certyfikatu.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego zaufanego certyfikatu. Obecnie dla ustawień certyfikatu można wybrać jedną z następujących platform:

    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**

6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Zaufany certyfikat**.
7. Przejdź do lokalizacji certyfikatu zapisanego w zadaniu 1, a następnie kliknij przycisk **OK**.
8. Dotyczy wyłącznie urządzeń z systemem Windows 8.1 i Windows 10: wybierz dla zaufanego certyfikatu **magazyn docelowy** spośród wymienionych poniżej:
    - **Magazyn certyfikatów komputera — główny**
    - **Magazyn certyfikatów komputera — pośredni**
    - **Magazyn certyfikatów użytkownika — pośredni**
8. Gdy skończysz, wybierz opcję **OK**, wróć do okienka **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na liście. Aby przypisać ten profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).

Na urządzeniach z systemem Android może zostać wyświetlony komunikat o przeprowadzeniu instalacji zaufanego certyfikatu przez osobę trzecią.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Krok 4 — Tworzenie profilów certyfikatów protokołu SCEP lub PKCS

Aby uzyskać pomoc dotyczącą konfigurowania i przypisywania każdego z typów profilów certyfikatu, zobacz odpowiednio tematy:

- [Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune](certificates-scep-configure.md)
- [Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune](certficates-pfx-configure.md)

Po utworzeniu profilu zaufanego certyfikatu należy utworzyć profile certyfikatów protokołu SCEP lub PKCS dla wszystkich platform, które będą używane. Podczas tworzenia profilu certyfikatu protokołu SCEP należy wskazać profil zaufanego certyfikatu dla danej platformy. W ten sposób oba profile certyfikatów zostaną połączone, niemniej jednak każdy profil należy przypisać osobno.

## <a name="next-steps"></a>Następne kroki
Ogólne informacje dotyczące sposobu przypisywania profilów urządzeń znajdują się w temacie [How to assign device profiles](device-profile-assign.md) (Jak przypisywać profile urządzeń).
