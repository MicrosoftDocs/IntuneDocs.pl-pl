---
title: "Ustawienia poczty e-mail w usłudze Intune dla urządzeń z systemem Android | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń poczty e-mail na urządzeniach z systemem Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f16c9dfb41cb2cfe07ce473a131dac767dee9c74
ms.openlocfilehash: 38858170e50add07f41138848e49e97bde8ac1b2


---

# <a name="email-profile-settings-for-android-devices-in-intune-azure-preview"></a>Ustawienia profilów e-mail dla urządzeń z systemem Android w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **Serwer poczty e-mail** — nazwa hosta serwera programu Exchange.
- **Nazwa konta** — nazwa wyświetlana konta e-mail, jaka będzie wyświetlana użytkownikom na ich urządzeniach.
- **Atrybut nazwy użytkownika z usługi AAD** — jest to atrybut usługi Active Directory (AD) lub Azure AD, który będzie używany do generowania nazwy użytkownika dla danego profilu e-mail. Uzupełnij pole **Podstawowy adres SMTP**, na przykład user1@contoso.com, lub **Główna nazwa użytkownika**, na przykład użytkownik1 lub user1@contoso.com.
- **Atrybut adresu e-mail z usługi AAD** — określa, jak adres e-mail użytkownika jest generowany na poszczególnych urządzeniach. Wybierz pozycję **Podstawowy adres SMTP**, aby użyć podstawowego adresu SMTP do logowania do programu Exchange, lub wybierz pozycję **Główna nazwa użytkownika**, aby użyć pełnej głównej nazwy jako adresu e-mail.
- **Metoda uwierzytelniania** — wybierz metodę uwierzytelniania stosowaną w profilu e-mail: **Certyfikaty** lub **Nazwa użytkownika i hasło**.
    - W przypadku wybrania pozycji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

## <a name="security-settings"></a>Ustawienia zabezpieczeń

- **Protokół SSL** — użyj komunikacji SSL (Secure Sockets Layer) podczas wysyłania i otrzymywania wiadomości e-mail oraz komunikacji z serwerem programu Exchange.
- **S/MIME** — umożliwia wysyłanie wychodzącej poczty e-mail przy użyciu szyfrowania S/MIME.
    - W przypadku wybrania pozycji **Certyfikat** wybierz wcześniej utworzony profil certyfikatu SCEP lub PKCS klienta, który będzie używany do uwierzytelniania połączenia z programem Exchange.

## <a name="synchronization-settings"></a>Ustawienia synchronizacji

- **Liczba wiadomości e-mail do synchronizacji** — wybierz liczbę dni, z których chcesz zsynchronizować pocztę e-mail, lub wybierz pozycję **Nieograniczone**, aby synchronizować wszystkie dostępne wiadomości e-mail.
- **Harmonogram synchronizacji** — wybierz harmonogram, według którego urządzenia będą synchronizować dane z serwera programu Exchange. Możesz również wybrać pozycję **W momencie nadejścia nowych wiadomości**, która powoduje synchronizowanie zaraz po odebraniu, lub pozycję **Ręcznie**, jeśli użytkownik urządzenia ma inicjować synchronizację.

## <a name="content-sync-settings"></a>Ustawienia synchronizacji zawartości

- **Typ zawartości do zsynchronizowania** — wybierz typ zawartości, który chcesz zsynchronizować z urządzeniem:
    - **Kontakty**
    - **Kalendarz**
    - **Zadania**



<!--HONumber=Feb17_HO1-->


