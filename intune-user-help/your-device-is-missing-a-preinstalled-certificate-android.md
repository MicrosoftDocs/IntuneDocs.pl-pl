---
title: Brak certyfikatu urządzenia | Dokumentacja firmy Microsoft
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: NOINDEX, NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 753fce1e37014e0ad4dac44f1eeb9284482e8f83
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72500173"
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Urządzenie z systemem Android nie ma certyfikatu, który zazwyczaj jest zainstalowany na telefonie

Jeśli urządzenie nie jest zarejestrowane w usłudze Intune i nie ma certyfikatu, który zazwyczaj jest zainstalowany w telefonie, nie można zalogować się do aplikacji Portal firmy. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Można rozwiązać ten problem, uzyskując wymagane certyfikaty ze [strony certyfikatów firmy Digicert](https://www.digicert.com/digicert-root-certificates.htm).

1. Znajdź i pobierz __Certyfikat główny firmy Baltimore CyberTrust__. Możesz również pobrać go bezpośrednio [stąd](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

2. Przeciągnij z góry na dół ekranu, aby wyświetlić listę ostatnich powiadomień, a następnie dotknij pozycji **BaltimoreCyberTrustRoot.crt**.

3. W urządzeniu zostanie wyświetlony monit o **nadanie nazwy certyfikatowi**. Nie należy zmieniać wyświetlonej domyślnej nazwy certyfikatu.

4. Upewnij się, że ustawienie **Credential Use** (Użycie poświadczeń) ma wartość **Used for VPN and apps** (Używane dla sieci VPN i aplikacji), a następnie naciśnij przycisk **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. Zamknij przeglądarkę i aplikację Portal firmy.

6. Otwórz ponownie aplikację Portal firmy. Zalogowanie się do aplikacji Portal firmy powinno być teraz możliwe. Jeśli korzystanie z aplikacji Portal firmy nadal nie jest możliwe, skontaktuj się z działem pomocy technicznej Twojej firmy, korzystając z informacji podanych w [witrynie internetowej aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980) w celu uzyskania szczegółowych instrukcji.

>[!NOTE]
> Jeśli zainstalowanie certyfikatu nie rozwiąże problemu i jeśli zostanie wyświetlony inny komunikat informujący o „braku certyfikatu”, niezbędne będzie wykonanie dodatkowych czynności w celu [zainstalowania brakującego certyfikatu](your-device-is-missing-an-IT-required-certificate-android.md).

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
