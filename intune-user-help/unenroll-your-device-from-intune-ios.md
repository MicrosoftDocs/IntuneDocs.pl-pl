---
title: Usuwanie urządzenia z systemem iOS z usługi Intune | Microsoft Docs
description: Opis sposobu usunięcia urządzenia z systemem iOS z usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 28914db1-3e62-45f5-9632-b0d2a808a44d
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 0a90cace32edb33293ba0b0b89d272465ea32418
ms.sourcegitcommit: 07528df71460589522a2e1b3e5f9ed63eb773eea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34547492"
---
# <a name="remove-your-ios-device-from-intune"></a>Usuwanie urządzenia z systemem iOS z usługi Intune

Po usunięciu urządzenia z systemem iOS z usługi Intune urządzenie nie będzie już mogło uzyskiwać dostępu do zasobów firmy i nie będzie już zarządzane przez usługę Intune.


## <a name="removing-the-device-from-my-devices"></a>Usuwanie urządzenia z pozycji Moje urządzenia

Aby usunąć urządzenie z usługi Intune, wykonaj następujące czynności lub obejrzyj ten film:


1.  W aplikacji Portal firmy naciśnij pozycję **Urządzenia** i wybierz urządzenie, które chcesz wyrejestrować. Jeśli masz tylko jedno urządzenie, naciśnięcie opcji **Urządzenia** spowoduje przejście bezpośrednio do ekranu szczegółów urządzenia.

2.  Obok pozycji **ZMIEŃ NAZWĘ** naciśnij przycisk wielokropka > **Usuń urządzenie** > **Usuń**.  

    |![Zrzut ekranu przedstawiający ekran Urządzenia aplikacji Portal firmy, na którym wyświetlono opcje dostępne po kliknięciu pozycji Usuń przez użytkownika. Przedstawia przycisk „Usuń urządzenie”, przycisk „Reset do ustawień fabrycznych” oraz przycisk „Anuluj”.](/intune-user-help/media/cp_ios_unenroll_after_1804_001.png)|

    |![Zrzut ekranu przedstawiający ekran Urządzenia aplikacji Portal firmy, na którym wyświetlono opcje dostępne po kliknięciu przycisku Usuń urządzenie przez użytkownika. Przedstawia podświetlony na czerwono przycisk „Usuń” oraz podświetlone na niebiesko przyciski „Dowiedz się więcej” i „Anuluj”.](/intune-user-help/media/cp_ios_unenroll_after_1804_002.png)|


  Po wyrejestrowaniu urządzenia z usługi Intune:

  -   Urządzenie nie będzie już wyświetlane w Portalu firmy.

  -   Nie będzie już można instalować aplikacji z poziomu Portalu firmy.

  -   Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go, np. wyłączenie aparatu lub wymaganie hasła o określonej długości, nie będą miały dłużej zastosowania.

  -   Użytkownik może utracić dostęp za pośrednictwem urządzenia do niektórych zasobów firmy, takich jak udziały plików lub wewnętrzne witryny sieci Web.

  -   Nie będzie można dłużej korzystać z aplikacji oraz danych firmy na urządzeniu.

  -   Nawiązanie połączenia z siecią firmową za pośrednictwem sieci Wi-Fi lub VPN (Virtual Private Network) może być niemożliwe.

  -   Profile firmowej poczty e-mail zostaną usunięte z urządzenia.

  -   Urządzenia, które są skonfigurowane tylko do obsługi poczty e-mail, nie będą wyświetlane w aplikacji Portal firmy ani w witrynie sieci Web Portalu firmy.
  
  -   Aplikacje zostaną odinstalowane. Dane aplikacji firmowych zostaną usunięte.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Usuwanie danych zebranych przez aplikację Portal firmy

Istnieją trzy miejsca, w których aplikacja Portal firmy przechowuje dane lokalne na urządzeniu.

-   **Dzienniki informacyjne**: standardowe dane o aktywności aplikacji, które zbiera firma Microsoft, np. czas otwarcia aplikacji lub informacje o awarii — są automatycznie usuwane w przypadku usunięcia urządzenia z aplikacji Portal firmy.

-   **Analizy firmy Apple**: standardowe dane o aktywności awarii aplikacji zbierane przez firmę Apple. Te informacje można usunąć tylko poprzez zresetowanie urządzenia z powrotem do ustawień fabrycznych. Spowoduje to wymazanie wszystkich danych osobowych na urządzeniu. Aby to zrobić, otwórz pozycję **Ustawienia** > **Ogólne** > **Resetuj** > **Wymaż zawartość i ustawienia**.

-   **Pęk kluczy**: urządzenie przechowuje hasła i inne informacje używane do logowania w pęku kluczy. Aplikacje firmy Microsoft udostępniają informacje logowania innym aplikacjom opracowanym przez firmę Microsoft na urządzeniu, w tym programom Microsoft Outlook i Microsoft Authenticator. Podobnie jak w przypadku analiz firmy Apple te informacje można usunąć wyłącznie poprzez zresetowanie urządzenia do ustawień fabrycznych. Spowoduje to wymazanie wszystkich danych osobowych na urządzeniu. Aby to zrobić, otwórz pozycję **Ustawienia** > **Ogólne** > **Resetuj** > **Wymaż zawartość i ustawienia**.


Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
