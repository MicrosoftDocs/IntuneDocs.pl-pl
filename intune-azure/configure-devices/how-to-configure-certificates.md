---
title: "Jak skonfigurować certyfikaty z użyciem usługi Intune | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Usługa Intune Azure w wersji zapoznawczej: Dowiedz się, jak tworzyć i przypisywać certyfikaty, które pozwolą zabezpieczyć sieci Wi-Fi i VPN oraz inne połączenia, korzystając z usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: ecb6a806e7870fd2b1986c4247607c9374431151
ms.contentlocale: pl-pl
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Jak skonfigurować certyfikaty z użyciem usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Po zapewnieniu użytkownikom dostępu do zasobów firmowych za pośrednictwem sieci VPN, sieci Wi-Fi lub profilów poczty e-mail możesz uwierzytelnić te połączenia przy użyciu certyfikatów. Pozwalają one wyeliminować potrzebę wprowadzania nazw użytkownika i haseł w celu uwierzytelniania połączeń.

Możesz użyć usługi Intune w celu przypisania tych certyfikatów do zarządzanych urządzeń. Usługa Intune obsługuje przypisywanie następujących typów certyfikatów i zarządzanie nimi:

- Prosty protokół rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol)
- PKCS#12 (lub PFX)

Każdy z tych typów certyfikatów ma własne wymagania wstępne i wymagania dotyczące infrastruktury.

## <a name="general-workflow"></a>Informacje ogólne dotyczące przepływu pracy

1. Upewnij się, że dysponujesz odpowiednią infrastrukturą certyfikatów. Możesz użyć [certyfikatów protokołu SCEP](configure-certificate-infrastructure-for-scep.md) i [certyfikatów protokołu PKCS](configure-certificate-infrastructure-for-pfx.md).
2. Zainstaluj certyfikat główny lub certyfikat pośredniego urzędu certyfikacji (CA) na każdym urządzeniu, aby urządzenia rozpoznawały urząd certyfikacji jako wiarygodny. W tym celu należy utworzyć i przypisać **profil zaufanego certyfikatu**. Po przypisaniu tego profilu urządzenia zarządzane przy użyciu usługi Intune zażądają certyfikatu głównego i otrzymają go. Należy utworzyć oddzielny profil dla każdej platformy. Profile zaufanego certyfikatu są dostępne dla następujących platform:
    - System iOS 8.0 i nowsze
    - System macOS 10.9 i nowsze
    - Android 4.0 i nowsze
    - Program Android for Work
    - Windows 8.1 i nowsze
    - System Windows Phone 8.1 lub nowszy
    - System Windows 10 lub nowszy
3. Utwórz profile certyfikatów, aby mieć pewność, że poszczególne urządzenia żądają certyfikatu w celu jego użycia do uwierzytelniania dostępu do poczty e-mail, sieci VPN i sieci Wi-Fi. Do urządzeń korzystających z następujących platform można tworzyć i przypisywać profile certyfikatów protokołów **PKCS** i **SCEP**:
    - System iOS 8.0 i nowsze
    - Android 4.0 i nowsze
    - Program Android for Work
    - System Windows 10 (Desktop i Mobile) i nowsze

    Na urządzeniach korzystających z następujących platform można używać wyłącznie profilów certyfikatów protokołu SCEP:

-     System macOS 10.9 i nowsze
-     System Windows Phone 8.1 lub nowszy

Dla każdej platformy urządzenia należy utworzyć oddzielny profil. Po utworzeniu certyfikatu należy go skojarzyć z utworzonym profilem zaufanego certyfikatu głównego.

### <a name="further-considerations"></a>Dodatkowe uwagi

- Jeśli nie masz urzędu certyfikacji przedsiębiorstwa, musisz go utworzyć.
- Jeśli na podstawie platform urządzeń zdecydujesz się na użycie uproszczonego protokołu rejestrowania certyfikatów (SCEP), musisz również skonfigurować serwer usługi rejestracji urządzeń sieciowych (NDES).
- Niezależnie od tego, czy zamierzasz używać profilów certyfikatów protokołu SCEP czy PKCS, musisz pobrać i skonfigurować łącznik certyfikatów usługi Microsoft Intune.


## <a name="step-1--configure-your-certificate-infrastructure"></a>Krok 1 — Konfigurowanie infrastruktury certyfikatów

Aby uzyskać pomoc dotyczącą konfigurowania infrastruktury dla każdego z typów profilów certyfikatu, zobacz następujące tematy:

- [Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune](configure-certificate-infrastructure-for-scep.md)
- [Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune](configure-certificate-infrastructure-for-pfx.md)


## <a name="step-2---export-your-trusted-root-ca-certificate"></a>Krok 2 — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji

Wyeksportuj certyfikat zaufanego głównego urzędu certyfikacji w formacie pliku **.cer** z wystawiającego urzędu certyfikacji lub dowolnego urządzenia traktującego wystawiający urząd certyfikacji jako zaufany. Nie należy eksportować klucza prywatnego.

Ten certyfikat zostanie zaimportowany podczas konfigurowania profilu zaufanego certyfikatu.

## <a name="step-3-create-trusted-certificate-profiles"></a>Krok 3 — Tworzenie profilów zaufanych certyfikatów
Aby móc utworzyć profil certyfikatu protokołu SCEP lub PKCS, należy utworzyć profil zaufanego certyfikatu. Dla każdej platformy urządzenia wymagany jest profil zaufanego certyfikatu oraz profil SCEP lub PKCS. Przepływ pracy związany z tworzeniem zaufanych certyfikatów przedstawia się podobnie dla każdej platformy urządzeń.

### <a name="to-create-a-trusted-certificate-profile"></a>Aby utworzyć profil zaufanego certyfikatu

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu zaufanego certyfikatu.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego zaufanego certyfikatu. Obecnie dla ustawień certyfikatu można wybrać jedną z następujących platform:
    - **Android**
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
8. Gdy skończysz, wybierz opcję **OK**, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).


> [!Note]
> Na urządzeniach z systemem Android zostanie wyświetlone powiadomienie o przeprowadzeniu instalacji zaufanego certyfikatu przez osobę trzecią.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Krok 4 — Tworzenie profilów certyfikatów protokołu SCEP lub PKCS

Aby uzyskać pomoc dotyczącą konfigurowania i przypisywania każdego z typów profilów certyfikatu, zobacz odpowiednio tematy:

- [Konfigurowanie certyfikatów protokołu SCEP i zarządzanie nimi za pomocą usługi Intune](configure-certificate-infrastructure-for-scep.md)
- [Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune](configure-certificate-infrastructure-for-pfx.md)

Po utworzeniu profilu zaufanego certyfikatu należy utworzyć profile certyfikatów protokołu SCEP lub PKCS dla wszystkich platform, które będą używane. Podczas tworzenia profilu certyfikatu protokołu SCEP należy wskazać profil zaufanego certyfikatu dla danej platformy. W ten sposób oba profile certyfikatów zostaną połączone, niemniej jednak każdy profil należy przypisać osobno.


## <a name="next-steps"></a>Następne kroki
Ogólne informacje dotyczące sposobu przypisywania profilów urządzeń znajdują się w temacie [How to assign device profiles](how-to-assign-device-profiles.md) (Jak przypisywać profile urządzeń).

