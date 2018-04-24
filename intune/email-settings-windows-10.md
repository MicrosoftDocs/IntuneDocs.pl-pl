---
title: Niestandardowe ustawienia poczty e-mail w usłudze Microsoft Intune dla urządzeń z systemem Windows 10
titleSuffix: ''
description: Dowiedz się więcej na temat ustawień usługi Microsoft Intune, których możesz użyć do konfigurowania ustawień poczty e-mail na urządzeniach z systemem Windows 10.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4a0c3eaf0643ede02b8c084d172b7a51d251b3a3
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-windows-10"></a>Ustawienia profilu poczty e-mail w usłudze Microsoft Intune dla urządzeń z systemem Windows 10

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia profilu poczty e-mail, które możesz skonfigurować dla urządzeń z systemem Windows 10.


- **Serwer poczty e-mail** — nazwa hosta serwera programu Exchange.
- **Nazwa konta** — nazwa wyświetlana dla konta e-mail, jaka będzie wyświetlana użytkownikom na ich urządzeniach.
- **Atrybut nazwy użytkownika z usługi AAD** — jest to atrybut usługi Active Directory (AD) lub Azure AD, który jest używany do generowania nazwy użytkownika dla danego profilu e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład **user1@contoso.com**, lub **Główna nazwa użytkownika**, na przykład **użytkownik1** lub **user1@contoso.com**.
- **Atrybut adresu e-mail z usługi AAD** — określa, jak adres e-mail użytkownika jest generowany na poszczególnych urządzeniach. Wybierz pozycję **Podstawowy adres SMTP**, aby użyć podstawowego adresu SMTP do logowania do programu Exchange, lub wybierz pozycję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail.


## <a name="security-settings"></a>Ustawienia zabezpieczeń

- **Protokół SSL** — użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i otrzymywania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.



## <a name="synchronization-settings"></a>Ustawienia synchronizacji

- **Liczba wiadomości e-mail do synchronizacji** — wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Harmonogram synchronizacji** — wybierz harmonogram, według którego urządzenia będą synchronizować dane z serwera programu Exchange. Możesz również wybrać pozycję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie zaraz po odebraniu, lub pozycję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.

## <a name="content-sync-settings"></a>Ustawienia synchronizacji zawartości

- **Typ zawartości do zsynchronizowania** — wybierz typ zawartości, który chcesz zsynchronizować z urządzeniem:
    - **Kontakty**
    - **Kalendarz**
    - **Zadania**
