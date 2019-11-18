---
title: Rejestrowanie urządzeń z systemem iOS — rejestracja użytkownika
titleSuffix: Microsoft Intune
description: Informacje o konfigurowaniu rejestracji użytkownika w systemach iOS oraz iPadOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e538204306ce80d6a13739fc981edf2748a622de
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713466"
---
# <a name="set-up-ios-and-ipados-user-enrollment-preview"></a>Konfigurowanie rejestracji użytkownika w systemach iOS oraz iPadOS (wersja zapoznawcza)

Usługę Intune można skonfigurować do rejestrowania urządzeń z systemem iOS i iPadOS przy użyciu procesu rejestracji użytkownika firmy Apple. Rejestracja użytkownika zapewnia administratorom uproszczony podzbiór opcji zarządzania w porównaniu z innymi metodami rejestracji.

Aby uzyskać więcej informacji na temat opcji dostępnych w przypadku rejestracji użytkownika, zobacz [akcje obsługiwane przez rejestrację użytkownika, hasła i inne opcje](ios-user-enrollment-supported-actions.md).

> [!NOTE]
> Obsługa rejestracji użytkownika firmy Apple w usłudze Intune jest obecnie dostępna w wersji zapoznawczej.

## <a name="prerequisites"></a>Wymagania wstępne
- [Urząd zarządzania urządzeniami przenośnymi (MDM)](../fundamentals/mdm-authority-set.md)
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- [Zarządzane identyfikatory Apple ID](https://support.apple.com/guide/apple-business-manager/mdm1c9622977/web)

## <a name="create-a-user-enrollment-profile-in-intune"></a>Tworzenie profilu rejestracji użytkownika w usłudze Intune

Profil rejestracji określa ustawienia stosowane do grupy urządzeń podczas rejestracji. 

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Typy rejestracji (wersja zapoznawcza)**  > **Utwórz profil** > **iOS**. W tym profilu wskazuje się, które środowisko rejestracji użytkownicy końcowi systemu iOS i iPadOS będą mieli na urządzeniach, które nie zostały zarejestrowane za pomocą firmowej metody firmy Apple. Ten profil można edytować po jego utworzeniu w razie potrzeby wprowadzenia zmian.

    ![Tworzenie profilu rejestracji firmy Apple](./media/ios-user-enrollment/create-profile.png)

2. Na stronie **Podstawy** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis** dla profilu. Informacje te będą używane do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices).

    ![Strona Podstawy](./media/ios-user-enrollment/basics-page.png)


3. Wybierz pozycję **Dalej**.

4. Na stronie **Ustawienia** można wybrać opcję nadania użytkownikom prawa wyboru typu rejestracji, którego będą używać. Alternatywnie można ustawić wartość domyślną.

    ![Strona Ustawienia](./media/ios-user-enrollment/settings-page.png)

    - Jeśli chcesz, aby wszyscy użytkownicy w tym profilu używali rejestracji użytkownika, wykonaj następujące kroki:
        1. Dla opcji **Wymagaj, aby użytkownik wybrał typ urządzenia** wybierz ustawienie **Nie skonfigurowano**.
        2. Dla opcji **Domyślny typ rejestracji** wybierz ustawienie **Rejestracja użytkownika**.
    - Jeśli chcesz, aby wszyscy użytkownicy w tym profilu używali rejestracji urządzenia, wykonaj następujące kroki:
        1. Dla opcji **Wymagaj, aby użytkownik wybrał typ urządzenia** wybierz ustawienie **Nie skonfigurowano**.
        2. Dla opcji **Domyślny typ rejestracji** wybierz ustawienie **Rejestracja urządzenia**.
    - Jeśli chcesz nadać wszystkim użytkownikom w tej grupie prawo wyboru typu rejestracji, wybierz ustawienie **Wymagane** dla opcji **Wymagaj, aby użytkownik wybrał typ urządzenia**. Gdy użytkownicy rejestrują swoje urządzenia, otrzymają możliwość wyboru między opcjami **To urządzenie należy do mnie** i **Firma [nazwa firmy] jest właścicielem tego urządzenia**. Jeśli wybiorą pierwszą z nich, urządzenie zostanie zarejestrowane przy użyciu funkcji rejestracji użytkownika. Jeśli wybiorą drugą opcję, urządzenie zostanie zarejestrowane przy użyciu funkcji rejestracji urządzenia. Jeśli użytkownik wybierze opcję **To urządzenie należy do mnie**, będzie mógł wybrać opcję zabezpieczenia całego urządzenia lub zabezpieczenia tylko aplikacji i danych związanych z pracą. Od wyboru właściciela urządzenia przez użytkownika końcowego zależy tylko typ rejestracji zaimplementowany na urządzeniu tego użytkownika. Ten wybór użytkownika nie zostanie odzwierciedlony w atrybucie własności urządzenia w usłudze Intune. Aby dowiedzieć się więcej na temat środowiska użytkownika, zobacz [Set up iOS device access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) (Konfigurowanie dostępu urządzenia z systemem iOS do zasobów firmowych).
    
    > [!NOTE]
    > Następujące powiadomienie jest niedokładne i zostanie usunięte z interfejsu użytkownika.
    > „Aby dostęp warunkowy działał na urządzeniach docelowych z rejestracją użytkownika, musisz wypchnąć aplikację Azure Authenticator jako wymaganą dla tej grupy użytkowników w celu włączenia logowania jednokrotnego i dołączania w miejscu pracy”.
    > Jako administrator nie musisz podejmować żadnych działań w celu wypchnięcia aplikacji Authenticator do użytkowników. Użytkownicy zostaną poinstruowani w Portalu firmy, aby zainstalować aplikację Authenticator w celu ukończenia procesu rejestracji użytkownika i zapewnienia poprawnego działania tych scenariuszy.

5. Wybierz pozycję **Dalej**.

6. Na stronie **Przypisania** wybierz grupy użytkowników zawierające użytkowników, którym chcesz przypisać ten profil. Możesz przypisać profil do wszystkich użytkowników lub do określonych grup. Wszyscy użytkownicy w wybranych grupach będą korzystać z wybranego powyżej typu rejestracji. Grupy urządzeń nie są obsługiwane w scenariuszach rejestracji użytkownika, ponieważ ta funkcja jest oparta na tożsamościach użytkowników, a nie urządzeń. Możesz przypisać profil do wszystkich użytkowników lub do określonych grup.

    ![Strona Przypisania](./media/ios-user-enrollment/assignments-page.png)

7. Wybierz pozycję **Dalej**.

8. Na stronie **Przejrzyj i utwórz** przejrzyj wybrane opcje, a następnie wybierz pozycję **Utwórz**, aby przypisać profil do użytkowników.

    ![Strona Przypisania](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Priorytet profilu

Po utworzeniu więcej niż jednego profilu typu rejestracji można zmienić kolejność priorytetów, w których profile są stosowane.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Typy rejestracji (wersja zapoznawcza)** .
2. Przeciągnij i upuść profile na liście w kolejności, w jakiej chcesz je zastosować.

Jeśli w przypadku jakiegoś użytkownika wystąpią konflikty między profilami, do tego użytkownika zostanie zastosowany profil o wyższym priorytecie.


