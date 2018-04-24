---
title: Uzyskiwanie certyfikatu wypychania MDM firmy Apple
titlesuffix: Microsoft Intune
description: Opis czynności niezbędnych w celu uzyskania certyfikatu wypychania MDM firmy Apple przeznaczonego do zarządzania urządzeniami z systemem iOS za pomocą usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28eb86a1924dc72df4c77cc3f8a05aacd61e0fbd
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Uzyskiwanie certyfikatu wypychania MDM firmy Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz komputerami Mac i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i macOS, wymagany jest certyfikat usługi wypychania MDM firmy Apple. Po dodaniu certyfikatu do usługi Intune użytkownicy mogą rejestrować swoje urządzenia przy użyciu następujących sposobów:

- Aplikacja Portal firmy.

- Metody rejestracji zbiorczej firmy Apple, np. program Device Enrollment Program, Apple School Manager lub Apple Configurator.

Aby uzyskać więcej informacji o opcjach rejestracji, zobacz [Wybieranie sposobu rejestracji urządzenia z systemem iOS](enrollment-method-choose-ios.md).

Po wygaśnięciu certyfikatu wypychania należy go odnowić. Podczas odnawiania upewnij się, że używasz tego samego identyfikatora Apple ID, który został użyty podczas pierwszego utworzenia certyfikatu wypychania.


## <a name="steps-to-get-your-certificate"></a>Procedura uzyskiwania certyfikatu
W witrynie [Azure Portal](https://portal.azure.com) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Certyfikat wypychania Apple MDM**, a następnie wykonaj poniższe kroki w witrynie [Azure Portal](https://portal.azure.com).

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>Krok 1. Udzielanie firmie Microsoft uprawnień do wysłania informacji o użytkowniku i urządzeniu do firmy Apple
Wybierz opcję **Zgadzam się**, aby udzielić firmie Microsoft uprawnień do wysyłania danych do firmy Apple.

![Ekran konfigurowania certyfikatu wypychania Apple MDM z nieskonfigurowanym wypychaniem MDM.](./media/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>Krok 2. Pobieranie żądania podpisania certyfikatu usługi Intune wymaganego do utworzenia certyfikatu wypychania MDM firmy Apple
Wybierz pozycję **Pobierz żądanie CSR**, aby pobrać plik żądania i zapisać go lokalnie. Ten plik jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

  ### <a name="step-3-create-an-apple-mdm-push-certificate"></a>Krok 3. Tworzenie certyfikatu wypychania MDM firmy Apple
Wybierz pozycję **Utwórz swój certyfikat push MDM**, aby przejść do portalu Apple Push Certificates. Zaloguj się przy użyciu identyfikatora firmy Apple Twojej firmy, a następnie kliknij pozycję **Utwórz certyfikat**. Wybierz pozycję **Wybierz plik** i przejdź do pliku żądania podpisania certyfikatu, a następnie wybierz pozycję **Przekaż**. Na stronie Potwierdzenie wybierz pozycję **Pobierz**, aby pobrać plik certyfikatu (pem), i zapisz plik lokalnie.

> [!NOTE]
> Certyfikat jest skojarzony z identyfikatorem firmy Apple użytym do jego utworzenia. Najlepszym rozwiązaniem jest używanie identyfikatora Apple ID dla zadań zarządzania i upewnienie się, że skrzynka pocztowa jest monitorowana przez więcej niż jedną osobę, na przykład przez listę dystrybucyjną. Nigdy nie należy używać osobistego identyfikatora firmy Apple.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>Krok 4. Wprowadzenie identyfikatora firmy Apple użytego do utworzenia certyfikatu wypychania MDM firmy Apple
Zanotuj ten identyfikator na wypadek, gdyby konieczne było odnowienie tego certyfikatu.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>Krok 5. Przejście do pliku certyfikatu wypychania MDM firmy Apple w celu jego przekazania
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Przy użyciu certyfikatu wypychania usługa Intune może rejestrować urządzenia firmy Apple i zarządzać nimi.

## <a name="renew-apple-mdm-push-certificate"></a>Odnawianie certyfikatu wypychania MDM firmy Apple
Certyfikat wypychania MDM firmy Apple jest ważny przez rok i musi być odnawiany co roku, aby zachować możliwość zarządzania urządzeniami z systemami iOS i macOS. Jeśli certyfikat wygaśnie, nie będzie można skontaktować się z zarejestrowanymi urządzeniami firmy Apple.

Certyfikat jest skojarzony z identyfikatorem firmy Apple użytym do jego utworzenia. Certyfikat wypychania MDM odnów przy użyciu tego samego identyfikatora firmy Apple, którego użyto do jego utworzenia.

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple**, a następnie wybierz kafelek **Certyfikat wypychania Apple MDM** w obszarze szczegółów.
2. Wybierz pozycję **Pobierz żądanie CSR**, aby pobrać plik żądania i zapisać go lokalnie. Ten plik jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.
3. Wybierz pozycję **Utwórz swój certyfikat push MDM**, aby przejść do portalu Apple Push Certificates. Znajdź certyfikat, który chcesz odnowić, i wybierz opcję **Odnów**.
4. Na ekranie **Odnawianie certyfikatu wypychania** wpisz notatki, aby w przyszłości łatwiej zidentyfikować certyfikat, wybierz pozycję **Wybierz plik**, aby wskazać nowo pobrany plik żądania, a następnie wybierz opcję **Przekaż**.
   > [!TIP]
   > Certyfikat można zidentyfikować na podstawie jego identyfikatora UID. Sprawdź **Identyfikator podmiotu** w szczegółach certyfikatu, aby znaleźć fragment identyfikatora UID będący identyfikatorem GUID. Alternatywnie na zarejestrowanym urządzeniu z systemem iOS wybierz pozycję **Ustawienia** > **Ogólne** > **Urządzenie****Zarządzanie** > **Profil zarządzania** > **Więcej szczegółów** > **Profil zarządzania**. Element w drugim wierszu, **Temat**, zawiera unikatowy identyfikator GUID, który można dopasować do certyfikatu w portalu Apple Push Certificates.
 
6. Na ekranie **Potwierdzenie** wybierz pozycję **Pobierz** i zapisz plik pem na urządzeniu lokalnym.
7. W witrynie [Azure Portal](https://portal.azure.com) wybierz ikonę przeglądania w obszarze **Certyfikat wypychania Apple MDM**, wybierz plik .pem pobrany od firmy Apple, a następnie wybierz opcję **Przekaż**.

Twój certyfikat wypychania MDM firmy Apple będzie mieć stan **Aktywny** i 365 dni do wygaśnięcia.
