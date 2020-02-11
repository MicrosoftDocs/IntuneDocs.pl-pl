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
ms.openlocfilehash: 0872eef38e3ea5a70ebb64d3ae3c62069045fa97
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754636"
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

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz kolejno pozycje **Urządzenia** > **iOS** > **Rejestracja urządzeń z systemem iOS** > **Typy rejestracji (wersja zapoznawcza)**  > **Utwórz profil** > **iOS/iPadOS**. W tym profilu wskazuje się, które środowisko rejestracji użytkownicy końcowi systemu iOS i iPadOS będą mieli na urządzeniach, które nie zostały zarejestrowane za pomocą firmowej metody firmy Apple. Ten profil można edytować po jego utworzeniu w razie potrzeby wprowadzenia zmian.

    ![Tworzenie profilu rejestracji firmy Apple](./media/ios-user-enrollment/create-profile.png)

2. Na stronie **Podstawy** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis** dla profilu. Informacje te będą używane do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices).

    ![Strona Podstawy](./media/ios-user-enrollment/basics-page.png)


3. Wybierz pozycję **Dalej**.

4. Na stronie **Ustawienia** wybierz jedną z następujących opcji **typu rejestracji**:

    ![Strona Ustawienia](./media/ios-user-enrollment/settings-page.png)

    - **Rejestrowanie urządzenia**: wszyscy użytkownicy w tym profilu będą korzystać z opcji rejestrowania urządzenia.
    - **Rejestrowanie użytkownika**: wszyscy użytkownicy w tym profilu będą korzystać z opcji rejestrowania użytkownika.
    - **Określ na podstawie wyboru użytkownika**: wszyscy użytkownicy w tej grupie będą mieć wybór typu rejestracji do użycia. Podczas rejestrowania urządzeń użytkownicy będą widzieć następujące opcje do wyboru: **To urządzenie należy do mnie** i **Firma (nazwa firmy) jest właścicielem tego urządzenia**. Jeśli wybiorą drugą opcję, urządzenie zostanie zarejestrowane przy użyciu funkcji rejestracji urządzenia. Jeśli użytkownik wybierze opcję **To urządzenie należy do mnie**, będzie mógł wybrać opcję zabezpieczenia całego urządzenia lub zabezpieczenia tylko aplikacji i danych związanych z pracą. Od wyboru właściciela urządzenia przez użytkownika końcowego zależy typ rejestracji zaimplementowany na urządzeniu tego użytkownika. Ten wybór użytkownika jest również odzwierciedlony w atrybucie własności urządzenia w usłudze Intune. Aby dowiedzieć się więcej na temat środowiska użytkownika, zobacz [Set up iOS device access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) (Konfigurowanie dostępu urządzenia z systemem iOS do zasobów firmowych).
    
5. Wybierz pozycję **Dalej**.

6. Na stronie **Przypisania** wybierz grupy użytkowników zawierające użytkowników, którym chcesz przypisać ten profil. Możesz przypisać profil do wszystkich użytkowników lub do określonych grup. Wszyscy użytkownicy w wybranych grupach będą korzystać z wybranego powyżej typu rejestracji. Grupy urządzeń nie są obsługiwane w scenariuszach rejestracji użytkownika, ponieważ ta funkcja jest oparta na tożsamościach użytkowników, a nie urządzeń. Możesz przypisać profil do wszystkich użytkowników lub do określonych grup.

    ![Strona Przypisania](./media/ios-user-enrollment/assignments-page.png)

7. Wybierz pozycję **Dalej**.

8. Na stronie **Przejrzyj i utwórz** przejrzyj wybrane opcje, a następnie wybierz pozycję **Utwórz**, aby przypisać profil do użytkowników.

    ![Strona Przypisania](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Priorytet profilu

Po utworzeniu więcej niż jednego profilu typu rejestracji można zmienić kolejność priorytetów, w których profile są stosowane.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz kolejno pozycje **Urządzenia** > **iOS** > **Rejestracja urządzeń z systemem iOS** > **Typy rejestracji (wersja zapoznawcza)** .
2. Przeciągnij i upuść profile na liście w kolejności, w jakiej chcesz je zastosować.

Jeśli w przypadku jakiegoś użytkownika wystąpią konflikty między profilami, do tego użytkownika zostanie zastosowany profil o wyższym priorytecie.


