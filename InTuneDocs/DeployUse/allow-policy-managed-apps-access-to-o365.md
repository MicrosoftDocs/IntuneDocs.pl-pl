---
title: "Dostęp warunkowy do usług O365 oparty na aplikacji | Microsoft Intune"
description: "Poznaj sposób, w jaki dostęp warunkowy zarządzania aplikacjami mobilnymi może pomóc w kontrolowaniu tego, które aplikacje mogą mieć dostęp do usług O365."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Tworzenie zasad zezwalających na dostęp do usług Office 365 wyłącznie aplikacjom mobilnym obsługującym zasady zarządzania aplikacjami mobilnymi usługi Intune
[Zasady zarządzania aplikacjami mobilnymi usługi Intune](protect-apps-and-data-with-microsoft-intune.md) pomagają chronić dane firmy na urządzeniach zarejestrowanych na potrzeby zarządzania przez usługę Intune. Możesz również korzystać z zasad zarządzania aplikacjami mobilnymi na **urządzeniach należących do pracowników, które nie zostały zarejestrowane na potrzeby zarządzania przez usługę Intune**.  W takim przypadku, nawet jeśli nie zarządzasz danym urządzeniem, musisz upewnić się, że dane i zasoby firmy zostały odpowiednio zabezpieczone. Przy użyciu dostępu warunkowego do zarządzania aplikacjami mobilnymi możesz utworzyć zasady, które zezwalają na dostęp do usług O365, takich jak usługa Exchange Online, tylko tym aplikacjom mobilnym, które obsługują zasady zarządzania aplikacjami mobilnymi usługi Intune.

Na przykład zezwalając na dostęp do usługi Exchange Online wyłącznie **aplikacji Microsoft Outlook**, możesz **blokować wbudowane aplikacje poczty e-mail w systemach iOS i Android**, które nie zapewniają ochrony danych pochodzącej z zasad zarządzania aplikacjami mobilnymi usługi Intune, aby nie mogły odbierać wiadomości z usługi **Exchange Online**.

## Wymagania wstępne
**Przed** skonfigurowaniem zasad dostępu warunkowego do zarządzania aplikacjami mobilnymi musisz mieć **subskrypcję pakietu Enterprise Mobility + Security lub usługi Azure Active Directory w warstwie Premium**, a użytkownicy muszą mieć licencję usług EMS lub Azure AD. Aby uzyskać więcej szczegółowych informacji, zobacz [Cennik pakietu Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) lub [Cennik usługi Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Obsługiwane aplikacje
**Exchange Online**
* Microsoft Outlook dla systemów Android i iOS

## Nakładanie się z innymi metodami dostępu warunkowego i uwierzytelniania
### Dostęp warunkowy do zarządzania aplikacjami mobilnymi z uwierzytelnianiem na podstawie certyfikatu usługi Azure Active Directory

Dostęp warunkowy do zarządzania aplikacjami mobilnymi nie może być używany za pomocą uwierzytelniania na podstawie certyfikatu usługi Azure Active Directory (Azure AD). Użytkownik może mieć skonfigurowaną tylko jedną z tych opcji.
### Dostęp warunkowy do zarządzania aplikacjami mobilnymi z dostępem warunkowym opartym na zgodności urządzeń  

[Dostęp warunkowy oparty na zgodności urządzeń](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**dostęp warunkowy do urządzenia**) można skonfigurować przy użyciu [konsoli administratora usługi Intune](https://manage.microsoft.com) lub [konsoli zarządzania usługi Azure AD Premium] (https://manage.windowsazure.com). Dostęp warunkowy do urządzenia wymaga od użytkowników nawiązania połączenia z usługą Exchange Online tylko za pośrednictwem urządzeń zarządzanych przez usługę Intune, które są zgodne z zasadami zgodności urządzeń usługi Intune, lub komputerów połączonych z domeną.  Jeśli użytkownik należy do co najmniej jednej grupy zabezpieczeń, w której stosowane są zasady dostępu warunkowego do zarządzania aplikacjami mobilnymi oraz zasady dostępu warunkowego do urządzeń, musi spełnić jedno z poniższych wymagań:
* Aplikacja używana do uzyskiwania dostępu do usługi jest aplikacją mobilną obsługiwaną przez dostęp warunkowy do zarządzania aplikacjami mobilnymi, a urządzenie, na którym działa aplikacja, ma zainstalowane narzędzie **iOS Authenticator (w przypadku urządzeń z systemem iOS)** lub aplikację **Portal firmy (w przypadku urządzeń z systemem Android)**.
* Urządzenie używane do uzyskiwania dostępu do usługi jest **zarządzane przez usługę Intune i zgodne** z zasadami zgodności urządzeń usługi Intune lub jest **komputerem połączonym z domeną**.  Oto kilka przykładów ilustrujących tę sytuację:
  * W przypadku próby nawiązania połączenia z poziomu **natywnej aplikacji poczty e-mail w systemie iOS** wymagane będzie, aby użytkownik korzystał z **zarządzanego i zgodnego urządzenia**, ponieważ natywna aplikacja poczty e-mail nie jest obsługiwana przez dostęp warunkowy do zarządzania aplikacjami mobilnymi.
  * W przypadku próby nawiązania połączenia z **komputera domowego z systemem Windows** zostaną zastosowane **zasady dostępu warunkowego do urządzenia**, które wymagają, aby użytkownik użył komputera połączonego z domeną.


## Oczekiwany przebieg korzystania z aplikacji z dostępem warunkowym do zarządzania aplikacjami mobilnymi
Dostęp warunkowy do zarządzania aplikacjami mobilnymi weryfikuje tożsamość zatwierdzonych aplikacji za pomocą aplikacji brokera, która musi być obecna na urządzeniu:
*  W systemie **iOS** aplikacją brokera jest **aplikacja Azure Authenticator**.
* W systemie **Android** aplikacją brokera jest aplikacja **Portal firmy usługi Intune**. 

Użytkownicy końcowi, którzy logują się po raz pierwszy do aplikacji obsługiwanej przez dostęp warunkowy do zarządzania aplikacjami mobilnymi, takiej jak OneDrive lub Outlook, zostaną poproszeni o zainstalowanie aplikacji brokera i zarejestrowanie urządzenia w usłudze Azure AD. Rejestracja urządzenia w usłudze Azure AD (znana wcześniej jako funkcja dołączania w miejscu pracy) spowoduje utworzenie rekordu urządzenia i certyfikatu, względem którego wydawane są tokeny.  To **nie** jest to samo, co **rejestracja w usłudze zarządzania urządzeniami przenośnymi**. Nie ma żadnych profilów zarządzania ani stosowanych zasad, nie jest także tworzony spis aplikacji na urządzeniu.  Proces instalacji aplikacji brokera i rejestracji urządzenia nastąpi tylko przy pierwszym użyciu zarządzanej aplikacji.


## Następne kroki
[Tworzenie zasad usługi Exchange Online dla aplikacji zarządzania aplikacjami mobilnymi](mam-ca-for-exchange-online.md)

[Blokowanie aplikacji bez nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)

### Zobacz także

[Ochrona danych aplikacji za pomocą zasad zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


