---
title: "Korzystanie z aplikacji z dostępem warunkowym zarządzania aplikacjami mobilnymi | Microsoft Docs"
description: "Poznaj sposób, w jaki dostęp warunkowy zarządzania aplikacjami mobilnymi może pomóc w kontrolowaniu tego, które aplikacje mogą mieć dostęp do usług O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 22746475bf50f8e4775c81e6833428c7f2ef9eba


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>Oczekiwany przebieg korzystania z aplikacji z dostępem warunkowym do zarządzania aplikacjami mobilnymi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dostęp warunkowy do zarządzania aplikacjami mobilnymi weryfikuje tożsamość zatwierdzonych aplikacji za pomocą aplikacji brokera, która musi być obecna na urządzeniu:
*  W systemie **iOS** aplikacją brokera jest **aplikacja Azure Authenticator**.
* W systemie **Android** aplikacją brokera jest aplikacja **Portal firmy usługi Intune**. 

Użytkownicy końcowi, którzy logują się po raz pierwszy do aplikacji obsługiwanej przez dostęp warunkowy do zarządzania aplikacjami mobilnymi, takiej jak OneDrive lub Outlook, zostaną poproszeni o zainstalowanie aplikacji brokera i zarejestrowanie urządzenia w usłudze Azure AD. Rejestracja urządzenia w usłudze Azure AD (znana wcześniej jako funkcja dołączania w miejscu pracy) spowoduje utworzenie rekordu urządzenia i certyfikatu, względem którego wydawane są tokeny.  To **nie** jest to samo, co **rejestracja w usłudze zarządzania urządzeniami przenośnymi**. Nie ma żadnych profilów zarządzania ani stosowanych zasad, nie jest także tworzony spis aplikacji na urządzeniu.  Proces instalacji aplikacji brokera i rejestracji urządzenia nastąpi tylko przy pierwszym użyciu zarządzanej aplikacji.

Poniżej przedstawiono listę właściwości, które pochodzą bezpośrednio z urządzenia:

* alternativeSecurityIds (skrót klucza publicznego i odcisk palca certyfikatu usługi Azure Active Directory)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Aby usunąć urządzenie zarejestrowane w usłudze Azure AD
Zarejestrowane urządzenie można usunąć na przykład za pomocą konsoli administracyjnej usługi Azure AD, co zazwyczaj jest wykonywane przez administratora IT.  Usunąć urządzenie może także użytkownik końcowy za pomocą swojego urządzenia.

* **Konsola administracyjna usługi Azure AD**: w konsoli administracyjnej usługi Azure AD** usuń odpowiednie urządzenie.
* **Urządzenie z systemem iOS**: otwórz aplikację Azure Authenticator, przesuń w lewo na koncie i wybierz opcję wyrejestrowania.  
* **Urządzenie z systemem Android**: odinstaluj aplikację portalu firmy lub usuń konto w obszarze **Ustawienia systemu**.



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>Dostęp warunkowy do zarządzania aplikacjami mobilnymi z dostępem warunkowym opartym na zgodności urządzeń  

[Dostęp warunkowy oparty na zgodności urządzeń](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**dostęp warunkowy do urządzenia**) można skonfigurować przy użyciu [konsoli administratora usługi Intune](https://manage.microsoft.com) lub [konsoli zarządzania usługi Azure AD Premium] (https://manage.windowsazure.com). Dostęp warunkowy do urządzenia wymaga od użytkowników nawiązania połączenia z usługą Exchange Online tylko za pośrednictwem urządzeń zarządzanych przez usługę Intune, które są zgodne z zasadami zgodności urządzeń usługi Intune, lub komputerów połączonych z domeną.  Jeśli użytkownik należy do co najmniej jednej grupy zabezpieczeń, w której stosowane są zasady dostępu warunkowego do zarządzania aplikacjami mobilnymi oraz zasady dostępu warunkowego do urządzeń, musi spełnić jedno z poniższych wymagań:
* Aplikacja używana do uzyskiwania dostępu do usługi jest aplikacją mobilną obsługiwaną przez dostęp warunkowy do zarządzania aplikacjami mobilnymi, a urządzenie, na którym działa aplikacja, ma zainstalowane narzędzie **iOS Authenticator (w przypadku urządzeń z systemem iOS)** lub aplikację **Portal firmy (w przypadku urządzeń z systemem Android)**.
* Urządzenie używane do uzyskiwania dostępu do usługi jest **zarządzane przez usługę Intune i zgodne** z zasadami zgodności urządzeń usługi Intune lub jest **komputerem połączonym z domeną**.  Oto kilka przykładów ilustrujących tę sytuację:
  * W przypadku próby nawiązania połączenia z poziomu **natywnej aplikacji poczty e-mail w systemie iOS** wymagane będzie, aby użytkownik korzystał z **zarządzanego i zgodnego urządzenia**, ponieważ natywna aplikacja poczty e-mail nie jest obsługiwana przez dostęp warunkowy do zarządzania aplikacjami mobilnymi.
  * W przypadku próby nawiązania połączenia z **komputera domowego z systemem Windows** zostaną zastosowane **zasady dostępu warunkowego do urządzenia**, które wymagają, aby użytkownik użył komputera połączonego z domeną.




## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad usługi Exchange Online dla aplikacji z obsługą zarządzania aplikacjami mobilnymi](mam-ca-for-exchange-online.md)

[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji za pomocą zasad zarządzania aplikacjami mobilnymi](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


