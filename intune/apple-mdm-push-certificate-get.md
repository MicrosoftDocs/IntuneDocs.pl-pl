---
title: Uzyskiwanie certyfikatu wypychania MDM firmy Apple
titlesuffix: Microsoft Intune
description: "Opis czynności niezbędnych w celu uzyskania certyfikatu wypychania MDM firmy Apple przeznaczonego do zarządzania urządzeniami z systemem iOS za pomocą usługi Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 504f2431754aa88ddf79bef4a201cbf7aa032834
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Uzyskiwanie certyfikatu wypychania MDM firmy Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi typu iPad, iPhone oraz komputerami Mac i zapewnia użytkownikom dostęp do poczty e-mail oraz aplikacji firmy. Aby zarządzać urządzeniami z systemem iOS i komputerami Mac, wymagany jest certyfikat usługi wypychania MDM. Po dodaniu certyfikatu do usługi Intune użytkownicy mogą zainstalować aplikację Portal firmy, aby zarejestrować swoje urządzenia. Możesz również skonfigurować zarządzanie urządzeniami iOS należącymi do firmy za pomocą programu rejestracji urządzeń firmy Apple lub zarejestrować urządzenia, na przykład przy użyciu programu Apple Configurator. Aby uzyskać więcej informacji o opcjach rejestracji, zobacz [Wybieranie sposobu rejestracji urządzenia z systemem iOS](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Procedura uzyskiwania certyfikatu
W witrynie [Azure Portal](https://portal.azure.com) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Certyfikat wypychania Apple MDM**, a następnie wykonaj poniższe kroki w witrynie [Azure Portal](https://portal.azure.com).

**Krok 1. Pobierz żądanie podpisania certyfikatu usługi Intune wymagane do utworzenia certyfikatu wypychania MDM firmy Apple.**<br>
Wybierz pozycję **Pobierz żądanie CSR**, aby pobrać plik żądania i zapisać go lokalnie. Ten plik jest używany na potrzeby żądania certyfikatu relacji zaufania w portalu Apple Push Certficates.

  ![Ekran konfigurowania certyfikatu wypychania Apple MDM z nieskonfigurowanym wypychaniem MDM.](./media/create-mdm-push-certificate.png)

**Krok 2. Tworzenie certyfikatu wypychania MDM firmy Apple**<br>
Wybierz pozycję **Utwórz swój certyfikat push MDM**, aby przejść do portalu Apple Push Certificates. Zaloguj się przy użyciu identyfikatora firmy Apple Twojej firmy, a następnie kliknij pozycję **Utwórz certyfikat**. Wybierz pozycję **Wybierz plik** i przejdź do pliku żądania podpisania certyfikatu, a następnie wybierz pozycję **Przekaż**. Na stronie Potwierdzenie wybierz pozycję **Pobierz**, aby pobrać plik certyfikatu (pem), i zapisz plik lokalnie.

> [!NOTE]
> Certyfikat jest skojarzony z identyfikatorem firmy Apple użytym do jego utworzenia. Najlepszym rozwiązaniem jest używanie identyfikatora Apple ID dla zadań zarządzania i upewnienie się, że skrzynka pocztowa jest monitorowana przez więcej niż jedną osobę, na przykład przez listę dystrybucyjną. Nigdy nie należy używać osobistego identyfikatora firmy Apple.

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia certyfikatu wypychania MDM firmy Apple.**<br>
Zanotuj ten identyfikator na wypadek, gdyby konieczne było odnowienie tego certyfikatu.

**Krok 4. Przejdź do pliku certyfikatu wypychania MDM firmy Apple, aby go przekazać.**<br>
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
