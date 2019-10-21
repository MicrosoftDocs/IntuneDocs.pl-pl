---
title: Tworzenie profilów certyfikatów w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil certyfikatu dla urządzeń poprzez skonfigurowanie środowiska certyfikatu SCEP lub PKCS, wyeksportowanie certyfikatu publicznego, utworzenie profilu w witrynie Azure Portal, a następnie przypisanie środowiska SCEP lub PKCS do profilów certyfikatów w usłudze Microsoft Intune w witrynie Azure Portal
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e993df5c37cfed8d5dd0481543b406dd25ad1a49
ms.sourcegitcommit: b1e97211db7cb949eb39be6776b3a11d434fdab0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "72251566"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Używanie certyfikatów do uwierzytelniania w usłudze Microsoft Intune  

Przy użyciu certyfikatów w usłudze Intune można uwierzytelniać użytkowników w aplikacjach i zasobach firmowych za pośrednictwem sieci VPN, Wi-Fi lub profilów poczty e-mail. W przypadku używania certyfikatów do uwierzytelniania tych połączeń użytkownicy końcowi nie będą musieli wprowadzać nazw użytkowników i haseł, co ułatwia zapewnienie im bezproblemowego dostępu. Certyfikaty są również używane do podpisywania i szyfrowania poczty e-mail przy użyciu protokołu S/MIME.

## <a name="intune-supported-certificates-and-usage"></a>Certyfikaty obsługiwane przez usługę Intune i ich użycie
| Typ              | Uwierzytelnianie | Podpisywanie S/MIME | Szyfrowanie S/MIME  |
|--|--|--|--|
| Zaimportowany certyfikat PKCS |  | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png)|
| PKCS#12 (lub PFX)    | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) |  |
| Prosty protokół rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol)  | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | |

Aby wdrożyć te certyfikaty, należy utworzyć i przypisać profile certyfikatów do urządzeń.  

Każdy utworzony profil certyfikatów obsługuje jedną platformę. Jeśli na przykład używasz certyfikatów PKCS, utworzysz profil certyfikatu PKCS dla systemu Android i oddzielny profil certyfikatu PKCS dla systemu iOS. Jeśli używasz również certyfikatów SCEP dla tych dwóch platform, utworzysz jeden profil certyfikatu SCEP dla systemu Android i drugi dla systemu iOS.  

**Zagadnienia ogólne**:  
- Jeśli nie masz urzędu certyfikacji przedsiębiorstwa, musisz go utworzyć lub skorzystać z [jednego z naszych obsługiwanych partnerów](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners).
- Jeśli używasz profilów certyfikatów SCEP korzystających z usług certyfikatów usługi Microsoft Active Directory, musisz skonfigurować serwer usługi rejestracji urządzeń sieciowych (NDES).
- Jeśli korzystasz z protokołu SCEP z jednym z naszych partnerów urzędu certyfikacji, musisz [zintegrować go z usługą Intune](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).
- Profile certyfikatów SCEP i PKCS wymagają pobrania, zainstalowania i skonfigurowania łącznika certyfikatów usługi Microsoft Intune. 
- Zaimportowane certyfikaty PCKS wymagają pobrania, zainstalowania i skonfigurowania łącznika certyfikatów PFX dla usługi Microsoft Intune.
- Zaimportowane certyfikaty PKCS wymagają wyeksportowania certyfikatów z urzędu certyfikacji i zaimportowania ich do usługi Microsoft Intune. Zobacz [projekt programu PowerShell w narzędziu PFXImport](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)
- Aby urządzenie mogło korzystać z profilów certyfikatu SCEP, PCKS lub zaimportowanego certyfikatu PKCS, musi ufać głównemu urzędowi certyfikacji. Do wdrożenia certyfikatu zaufanego głównego urzędu certyfikacji na urządzeniach używany jest *profil zaufanego certyfikatu*.  

## <a name="supported-platforms-and-certificate-profiles"></a>Obsługiwane platformy i profile certyfikatów  
| Platforma              | Profil zaufanego certyfikatu | Profil certyfikatu PKCS | Profil certyfikatu SCEP | Profil zaimportowanego certyfikatu PKCS  |
|--|--|--|--|---|
| Administrator urządzenia z systemem Android | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png)|  ![Obsługiwane](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> — W pełni zarządzane (właściciel urządzenia)   | ![Obsługiwane](./media/certificates-configure/green-check.png) |   | ![Obsługiwane](./media/certificates-configure/green-check.png) |   |
| Android Enterprise <br> — Dedykowane (właściciel urządzenia)   |  |   |  |   |
| Android Enterprise <br> — Profil służbowy    | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) |
| iOS                   | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) |
| macOS                 | ![Obsługiwane](./media/certificates-configure/green-check.png) |   |![Obsługiwane](./media/certificates-configure/green-check.png)|![Obsługiwane](./media/certificates-configure/green-check.png)|
| Windows Phone 8,1     |![Obsługiwane](./media/certificates-configure/green-check.png)  |  | ![Obsługiwane](./media/certificates-configure/green-check.png)| ![Obsługiwane](./media/certificates-configure/green-check.png) |
| Windows 8.1 i nowsze |![Obsługiwane](./media/certificates-configure/green-check.png)  |  |![Obsługiwane](./media/certificates-configure/green-check.png) |   |
| System Windows 10 lub nowszy  | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) | ![Obsługiwane](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji  
Aby używać certyfikatów PKCS, SCEP i zaimportowanych certyfikatów PKCS, urządzenia muszą ufać głównemu urzędowi certyfikacji. Aby ustanowić to zaufanie, należy wyeksportować certyfikat zaufanego głównego urzędu certyfikacji (CA), a także certyfikaty wszystkich pośrednich lub wystawiających urzędów certyfikacji, jako certyfikat publiczny (plik CER). Te certyfikaty można pobrać z wystawiającego urzędu certyfikacji lub z dowolnego urządzenia, które ufa wystawiającemu urzędowi certyfikacji.  

Aby wyeksportować certyfikat, zapoznaj się z dokumentacją Twojego urzędu certyfikacji. Musisz wyeksportować certyfikat publiczny jako plik CER.  Nie eksportuj klucza prywatnego (plik PFX).  

Ten plik CER będzie używany podczas [tworzenia profilów zaufanych certyfikatów](#create-trusted-certificate-profiles) do wdrażania tego certyfikatu na urządzeniach.  

## <a name="create-trusted-certificate-profiles"></a>Tworzenie profilów zaufanych certyfikatów  
Utwórz profil zaufanego certyfikatu, aby móc utworzyć profil certyfikatu SCEP, PKCS lub zaimportowanego certyfikatu PKCS. Wdrożenie profilu zaufanego certyfikatu zapewnia, że każde urządzenie rozpoznaje urząd certyfikacji jako wiarygodny. Profile certyfikatów SCEP odwołują się bezpośrednio do profilu zaufanego certyfikatu. Profile certyfikatów PKCS nie odwołują się bezpośrednio do profilu zaufanego certyfikatu, ale bezpośrednio odwołują się do serwera, który hostuje urząd certyfikacji. Profile zaimportowanych certyfikatów PKCS nie odwołują się bezpośrednio do profilu zaufanego certyfikatu, ale mogą korzystać z niego na urządzeniu. Wdrożenie profilu zaufanego certyfikatu na urządzeniach gwarantuje, że to zaufanie zostało ustanowione. Jeśli urządzenie nie ufa głównemu urzędowi certyfikacji, zasady profilu certyfikatu SCEP lub PKCS nie będą działać.  

Dla każdej platformy urządzenia, która ma być obsługiwana, utwórz oddzielny profil zaufanego certyfikatu tak samo jak w przypadku profilów certyfikatów SCEP, PCKS i importowanych certyfikatów PKCS.  


### <a name="to-create-a-trusted-certificate-profile"></a>Aby utworzyć profil zaufanego certyfikatu  

1. Zaloguj się do [portalu usługi Intune](https://aka.ms/intuneportal).  
2. Wybierz pozycję **Konfiguracja urządzenia** > **Zarządzaj** > **Profile** > **Utwórz profil**.  
3. Wypełnij pola **Nazwa i Opis** dla profilu zaufanego certyfikatu.  
4. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego zaufanego certyfikatu.  
5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Zaufany certyfikat**.  
6. Przejdź do pliku CER certyfikatu zaufanego głównego urzędu certyfikacji, który został wyeksportowany do użycia z tym profilem certyfikatu, a następnie wybierz przycisk **OK**.  
7. Dotyczy wyłącznie urządzeń z systemem Windows 8.1 i Windows 10: wybierz dla zaufanego certyfikatu **magazyn docelowy** spośród wymienionych poniżej:  
   - **Magazyn certyfikatów komputera — główny**
   - **Magazyn certyfikatów komputera — pośredni**
   - **Magazyn certyfikatów użytkownika — pośredni**
8. Gdy skończysz, wybierz opcję **OK**, wróć do okienka **Utwórz profil** i wybierz pozycję **Utwórz**.
Profil zostanie wyświetlony na liście profilów w okienku *Konfiguracja urządzenia — Profile*, z typem profilu **Certyfikat zaufany**.  Należy przypisać ten profil do urządzeń, które będą używały certyfikatów SCEP lub PCKS. Aby przypisać profil do grup, zobacz [przypisywanie profilów urządzeń](../configuration/device-profile-assign.md).

> [!NOTE]  
> Na urządzeniach z systemem Android może zostać wyświetlony komunikat o zainstalowaniu zaufanego certyfikatu przez osobę trzecią.  

## <a name="additional-resources"></a>Dodatkowe zasoby  
- [Przypisywanie profilów urządzeń](../configuration/device-profile-assign.md)  
- [Używanie protokołu S/MIME do podpisywania i szyfrowania wiadomości e-mail](certificates-s-mime-encryption-sign.md)  
- [Używanie urzędu certyfikacji innej firmy](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Następne kroki  
Po utworzeniu i przypisaniu profilów zaufanych certyfikatów należy utworzyć profile certyfikatów SCEP, PKCS lub zaimportowanych certyfikatów PKCS dla wszystkich platform, które będą używane. Aby kontynuować, zobacz następujące artykuły:  
- [Konfigurowanie infrastruktury do obsługi certyfikatów SCEP przy użyciu usługi Intune](certificates-scep-configure.md)  
- [Konfigurowanie certyfikatów PKCS i zarządzanie nimi za pomocą usługi Intune](certficates-pfx-configure.md)  
- [Tworzenie profilu zaimportowanego certyfikatu PKCS](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)  

