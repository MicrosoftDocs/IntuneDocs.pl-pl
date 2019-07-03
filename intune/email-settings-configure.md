---
title: Konfigurowanie ustawień poczty e-mail w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Utwórz profil poczty e-mail w usłudze Microsoft Intune i wdróż go w urządzeniach z rozwiązaniem Android Enterprise oraz z systemami iOS i Windows. Profil poczty e-mail pozwala skonfigurować wspólne ustawienia poczty e-mail, w tym serwer poczty e-mail i metodę uwierzytelniania połączenia z firmową pocztą e-mail w urządzeniach, którymi zarządzasz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b579849d9afdb50470b7a772e003cc616e1f94a0
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67530047"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Dodawanie ustawień poczty e-mail do urządzeń przy użyciu usługi Intune

Usługa Microsoft Intune obejmuje różne ustawienia poczty e-mail, które można wdrożyć w urządzeniach w organizacji. Administrator IT tworzy profile poczty e-mail z konkretnymi ustawieniami połączenia z serwerem poczty, takim jak usługa Office 365 lub Gmail. Użytkownicy końcowi mogą nawiązywać połączenia, uwierzytelniać się i synchronizować konta e-mail organizacji w swoich urządzeniach przenośnych. Utworzenie i wdrożenie profilu poczty e-mail umożliwia używanie standardowych ustawień w wielu urządzeniach. Pomaga też zmniejszyć liczbę zgłoszeń od użytkowników końcowych, którzy nie znają prawidłowych ustawień poczty e-mail.

Profile poczty e-mail mogą służyć do konfigurowania wbudowanych ustawień poczty e-mail dla następujących urządzeń:

- System Android Samsung Knox Standard 4.0 i nowsze wersje
- Android Enterprise
- System iOS 8.0 i nowsze
- System Windows Phone 8.1 lub nowszy
- System Windows 10 Mobile Desktop i Windows 10 Mobile

W tym artykule przedstawiono sposób tworzenia profilu poczty e-mail w usłudze Microsoft Intune. Zawiera on też linki dotyczące bardziej szczegółowych ustawień na innych platformach.

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź **nazwę** i **opis** profilu poczty e-mail.
4. Wybierz **platformę** z listy rozwijanej. Dostępne opcje:

    - **Android** (tylko system Samsung Android Knox Standard)
    - **Android enterprise**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 lub nowszy**

5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Poczta e-mail**.
6. Ustawienia, które można skonfigurować, mogą różnić się zależnie od platformy. Aby uzyskać konkretne ustawienia, wybierz platformę:

    - [Ustawienia systemu Android Samsung Knox Standard](email-settings-android.md)
    - [Ustawienia systemu Android Enterprise](email-settings-android-enterprise.md)
    - [Ustawienia systemu iOS](email-settings-ios.md)
    - [Ustawienia systemu Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Windows 10 settings](email-settings-windows-10.md) (Ustawienia systemu Windows 10)

Gdy wprowadzisz ustawienia i utworzysz profil, profil będzie wyświetlany na liście profilów. Następnie [przypisz ten profil do grup](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>Usuwanie profilu poczty e-mail

Profile poczty e-mail są przypisywane do grup urządzeń, a nie grup użytkowników. Istnieją różne sposoby usuwania profilu poczty e-mail z urządzenia, nawet wtedy, gdy w urządzeniu istnieje tylko jeden profil poczty e-mail:

- **Opcja 1**. Otwórz profil poczty e-mail (**Konfiguracja urządzenia** > **Profile**) i wybierz pozycję **Przypisania**. Karta **Dołączanie** zawiera grupy, które zostały przypisane do profilu. Kliknij prawym przyciskiem myszy grupę > **Usuń**. Pamiętaj o **zapisaniu** zmian.

- **Opcja 2**: [Wyczyść lub wycofaj urządzenie](devices-wipe.md). Tych akcji można używać do selektywnego lub pełnego usuwania danych i ustawień.

## <a name="secure-email-access"></a>Bezpieczny dostęp do poczty e-mail

Profile poczty e-mail można zabezpieczyć przy użyciu następujących metod:

- **Certyfikaty**: podczas tworzenia profilu poczty e-mail wybierasz profil certyfikatu utworzony wcześniej w usłudze Intune. Ten certyfikat jest znany pod nazwą certyfikatu tożsamości. Służy on do uwierzytelniania względem profilu zaufanego certyfikatu lub certyfikatu głównego w celu określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest przypisywany do komputera, który uwierzytelnia połączenie poczty e-mail. Zwykle jest to natywny serwer poczty.

  Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz artykuł [How to configure certificates with Intune](certificates-configure.md) (Jak skonfigurować certyfikaty z użyciem usługi Intune).

- **Nazwa użytkownika i hasło**: użytkownik końcowy jest uwierzytelniany na natywnym serwerze poczty e-mail przez wprowadzenie nazwy użytkownika i hasła. Hasło nie istnieje w profilu poczty e-mail. W takiej sytuacji użytkownik końcowy wprowadza hasło podczas łączenia się z pocztą e-mail.

## <a name="how-intune-handles-existing-email-accounts"></a>Obsługa istniejących kont poczty e-mail przez usługę Intune

Jeśli użytkownik skonfigurował już konto e-mail, może przypisać profil poczty e-mail w sposób odpowiedni dla danej platformy.

- **iOS**: Istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Duplikat profilu poczty e-mail blokuje możliwość przypisywania profilu usługi Intune. W takim przypadku w aplikacji Portal firmy zostanie wyświetlony komunikat dla użytkownika z informacją, że profil nie jest zgodny, oraz monitem dla użytkownika końcowego o ręczne usunięcie skonfigurowanego profilu. Aby uniknąć tego scenariusza, poleć użytkownikom końcowym, aby dokonali rejestracji *przed* zainstalowaniem profilu poczty e-mail — dzięki temu usługa Intune będzie mogła samodzielnie skonfigurować profil.

- **Windows:** Istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie nazwy hosta i adresu e-mail. Usługa Intune zastępuje istniejący profil poczty e-mail utworzony przez użytkownika końcowego.

- **Android Samsung Knox Standard**: Istniejące zduplikowane profile poczty e-mail są wykrywane na podstawie adresu e-mail i nadpisują je profilami usługi Intune. System Android nie identyfikuje profilu przy użyciu nazwy hosta. Nie twórz wielu profilów poczty e-mail przy użyciu tego samego adresu e-mail na różnych hostach. Profile zastępują się nawzajem.

- **Profile służbowe systemu Android**: usługa Intune udostępnia dwa służbowe profile poczty e-mail systemu Android — jeden dla aplikacji Gmail i drugi dla aplikacji Nine Work. Te aplikacje są dostępne w sklepie Google Play i są instalowane w profilu służbowym urządzenia. Nie tworzą one zduplikowanych profilów. Obie aplikacje obsługują połączenia z programem Exchange. Aby użyć połączenia poczty e-mail, wdróż jedną z tych aplikacji poczty e-mail w urządzeniach użytkowników. Następnie utwórz i wdróż odpowiedni profil poczty e-mail. Aplikacje poczty e-mail, takie jak Nine Work, mogą nie być bezpłatne. Sprawdź szczegóły licencji aplikacji lub skontaktuj się z producentem aplikacji, jeśli masz jakieś pytania.

## <a name="changes-to-assigned-email-profiles"></a>Zmiany w przypisanych profilach poczty e-mail

W przypadku wprowadzenia zmian w zakresie przypisanego wcześniej profilu poczty e-mail użytkownicy końcowi mogą zobaczyć monit o zatwierdzenie nowej konfiguracji ich ustawień poczty e-mail.

## <a name="next-steps"></a>Następne kroki

Utworzony profil nie wykonuje jeszcze żadnych czynności. Następnie [przypisz profil do urządzeń](device-profile-assign.md).
