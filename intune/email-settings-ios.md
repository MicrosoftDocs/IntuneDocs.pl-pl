---
title: Ustawienia poczty e-mail dla urządzeń z systemem iOS w usłudze Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej o ustawieniach usługi Microsoft Intune, których możesz użyć do konfigurowania ustawień poczty e-mail na urządzeniach z systemem iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe791dce88878fdbde7c62e59452a53ac08ef06b
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190489"
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>Ustawienia profilu poczty e-mail w usłudze Microsoft Intune dla urządzeń z systemem iOS 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia profilu poczty e-mail, które możesz skonfigurować dla urządzeń z systemem iOS.

## <a name="email-settings"></a>Ustawienia poczty e-mail

- **Serwer poczty e-mail** — nazwa hosta serwera programu Exchange.
- **Nazwa konta** — nazwa wyświetlana dla konta e-mail, jaka będzie wyświetlana użytkownikom na ich urządzeniach.
- **Atrybut nazwy użytkownika z usługi AAD** — jest to atrybut usługi Active Directory (AD) lub Azure AD, który jest używany do generowania nazwy użytkownika dla danego profilu e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład **user1@contoso.com**, lub **Główna nazwa użytkownika**, na przykład **użytkownik1** lub **user1@contoso.com**.
- **Atrybut adresu e-mail z usługi AAD** — określa, jak adres e-mail użytkownika jest generowany na poszczególnych urządzeniach. Wybierz pozycję **Podstawowy adres SMTP**, aby użyć podstawowego adresu SMTP do logowania do programu Exchange, lub wybierz pozycję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Nazwa użytkownika i hasło** lub **Certyfikaty** (**Uwaga**: usługa Azure Multi-factor Authentication nie jest obsługiwana).
    - W przypadku wybrania pozycji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który jest używany do uwierzytelniania połączenia z programem Exchange.
- **Protokół SSL** — użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i otrzymywania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **S/MIME** — wysyłaj wychodzącą pocztę e-mail przy użyciu podpisywania S/MIME.
    - W przypadku wybrania opcji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu PKCS, który będzie używany do uwierzytelniania połączenia z programem Exchange.
- **Liczba wiadomości e-mail do synchronizacji** — wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Zezwalaj na przenoszenie wiadomości na inne konta poczty e-mail** — umożliwia użytkownikom przenoszenie wiadomości e-mail między różnymi kontami skonfigurowanymi na ich urządzeniu.
- **Zezwalaj na wysyłanie wiadomości e-mail przy użyciu aplikacji innych firm** — zezwalaj użytkownikowi na wybranie jego profilu jako domyślnego konta wysyłania poczty e-mail i zezwalaj aplikacjom innych firm na otwieranie poczty e-mail w natywnej aplikacji poczty e-mail, na przykład w celu dołączania plików do wiadomości e-mail.
- **Synchronizuj ostatnio używane adresy e-mail** — ta funkcja pozwala użytkownikom zsynchronizować listę adresów e-mail, które były ostatnio używane na urządzeniu, z serwerem.
