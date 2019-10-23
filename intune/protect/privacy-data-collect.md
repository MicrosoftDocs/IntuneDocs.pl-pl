---
title: Zbieranie danych w usłudze Intune
titleSuffix: Microsoft Intune
description: Informacje o tym, jak są zbierane dane osobowe w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e93e69b5cce2c54ae07410309b33870dd828f563
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509085"
---
# <a name="data-collection-in-intune"></a>Zbieranie danych w usłudze Intune

Gdy użytkownicy rejestrują swoje firmowe lub osobiste urządzenia za pomocą usługi Intune, usługa Intune zbiera i udostępnia niektóre dane osobowe. Usługa Intune zbiera dane osobowe z następujących źródeł:

- Użycie usługi Intune przez administratora w witrynie Azure Portal.
- Urządzenia użytkownika końcowego (podczas rejestracji na potrzeby zarządzania za pomocą usługi Intune i podczas używania).
- Konta klientów w usługach innych firm (zgodnie z instrukcjami administratora).
- Informacje diagnostyczne dotyczące wydajności i użycia.

Z tych źródeł usługa Intune zbiera informacje należące do następujących trzech kategorii: [identyfikujące](#identified-data), [pseudonimizowane](#pseudonymized-data) i [zagregowane](#aggregated-data).

> [!NOTE]
> Danych zebranych przez naszą usługę nie sprzedajemy z jakiegokolwiek powodu żadnym osobom trzecim.

## <a name="identified-data"></a>Dane identyfikujące

Większość danych osobowych zbieranych przez usługę Intune to dane identyfikujące. Te dane są powiązane z użytkownikiem, urządzeniem lub aplikacją i stanowią sedno natury zarządzania. Dane identyfikujące są używane do zarządzania urządzeniami i aplikacjami użytkownika oraz do aprowizowania usługi Intune.

Dane identyfikujące zebrane przez usługę Intune obejmują między innymi: 

- Informacje o użytkowniku
  - Wyświetlana nazwa właściciela/użytkownika (zarejestrowana na platformie Azure nazwa użytkownika określona za pomocą identyfikatora użytkownika platformy Azure)
  - Główna nazwa użytkownika lub adres e-mail
  - Identyfikatory użytkownika w innych firmach (na przykład identyfikator AppleID)
- Informacje dotyczące spisu sprzętu
  - Nazwa urządzenia
  - Producent
  - System operacyjny
  - Numer seryjny
  - Numer IMEI
  - Adres IP
  - Adres Mac karty Wi-Fi
  - Identyfikator ICCID
  - Numer telefonu
- Informacje dziennika inspekcji, w tym dane o następujących działaniach
  - Zarządzanie programem Endpoint Protection usługi
  - Utwórz
  - Aktualizowanie (edytowanie)
  - Usuwanie
  - Przypisywanie
  - Zadania zdalne
- Informacje dotyczące pomocy technicznej
  - Informacje kontaktowe (nazwisko, numer telefonu, adres e-mail)
  - Korespondencja e-mail z pomocą techniczną firmy Microsoft oraz członkami zespołu obsługi klienta i zespołów produktów
- Informacje dotyczące kontroli dostępu (usługa Intune używa tych danych do zarządzania dostępem do zadań i ról administracyjnych za pośrednictwem funkcji takich jak [kontrola dostępu na podstawie ról](../fundamentals/role-based-access-control.md).
  - Statyczni wystawcy uwierzytelnienia (hasło klienta)
  - Klucze prywatności dla certyfikatów 
- Informacje o administratorze i o koncie
  - Imię i nazwisko administratora
  - Nazwa użytkownika administratora
  - Nazwa UPN (e-mail)
  - Numer telefonu
  - Adres e-mail właściciela konta
  - Identyfikator usługi Active Directory administratora IT każdego klienta
  - Dane płatności dla rozliczeń klienta
  - Klucz subskrypcji
- Spis aplikacji, na przykład
  - Nazwa aplikacji
  - Wersja
  - Identyfikator aplikacji
  - rozmiar
  - Miejsce instalacji
  - Dane spisu aplikacji są zbierane tylko wtedy, gdy urządzenie zostanie oznaczone przez administratora jako należące do firmy lub gdy jest włączona funkcja zgodnych aplikacji.  
- Identyfikatory dzierżawy innej firmy klienta, na przykład identyfikator Apple ID. 

## <a name="pseudonymized-data"></a>Dane pseudonimizowane

Dane pseudonimizowane są skojarzone z unikatowym identyfikatorem, zwykle liczbą wygenerowaną przez system, która nie może samodzielnie zidentyfikować określonej osoby, ale jest używana na potrzeby dostarczania usług korporacyjnych użytkownikom. 

Dane pseudonimizowane zebrane przez usługę Intune obejmują między innymi: 

- Dane diagnostyczne oraz dotyczące wydajności i użycia powiązane z użytkownikiem i/lub urządzeniem
  - Liczba użyć funkcji
  - Polecenia dostarczane do funkcji
  - Czas odpowiedzi usługi
  - Współczynniki powodzeń instalacji i innych procesów
  - Błędy aplikacji Portal firmy usługi Intune
  - Identyfikatory użytkownika i urządzeń
  - Identyfikatory na potrzeby odwołania, korelacji i zarządzania 
- Dane urządzenia niepowiązane z określonym urządzeniem lub użytkownikiem (jeśli dane są powiązane z urządzeniem lub użytkownikiem, usługa Intune traktuje je jako dane identyfikujące)
  - Identyfikator urządzenia w usłudze Intune
  - Identyfikator urządzenia w usłudze Azure Active Directory
  - Identyfikator zarządzania urządzeniem w usłudze Intune
  - Identyfikator dzierżawy
  - Identyfikator konta
  - Identyfikator urządzenia protokołu EAS
  - Identyfikatory specyficzne dla platformy
  - Identyfikator AppleID dla urządzeń z systemem iOS
  - Adres Mac dla urządzeń Mac
  - Identyfikator systemu Windows dla urządzeń z systemem Windows
- Informacje o aplikacji zarządzanej
  - Identyfikator aplikacji zarządzanej
  - Tag urządzenia aplikacji zarządzanej
  - Identyfikator zarządzania urządzeniem w usłudze Intune
  - Identyfikator urządzenia w usłudze Azure Active Directory
  - Klucze szyfrowania

## <a name="aggregated-data"></a>Dane zagregowane

Dane zagregowane są używane w celu aprowizowania i ulepszania usługi Intune. 

Dane zagregowane zebrane przez usługę Intune obejmują między innymi: 

- Dane użycia administratora ze wszystkich dzierżaw usługi Intune (na przykład kontrolki administratora wybrane podczas korzystania z konsoli administracyjnej)
- Informacje o koncie dzierżawy (te dane są dostępne w bloku usługi Intune)
  - Liczba zarejestrowanych urządzeń lub użytkowników
  - Liczba zidentyfikowanych platform urządzeń  
  - Liczba zainstalowanych urządzeń
  - installedDeviceCount: Liczba urządzeń, na których zainstalowano aplikację.
  - notApplicableDeviceCount: Liczba urządzeń, dla których aplikacja nie jest przeznaczona.
  - notInstalledDeviceCount: Liczba urządzeń, dla których aplikacja jest przeznaczona, ale nie jest na nich zainstalowana.
  - pendingInstallDeviceCount: Liczba urządzeń, dla których aplikacja jest przeznaczona i które oczekują na jej instalację.

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej na temat tego, jak usługa Intune [przechowuje i przetwarza](privacy-data-store-process.md) oraz [udostępnia](privacy-data-secure-share.md) dane osobowe. 
