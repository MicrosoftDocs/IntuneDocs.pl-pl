---
title: Konfiguracja integracji z programem SEP Mobile w usłudze Intune
titleSuffix: Intune on Azure
description: Sposób konfigurowania rozwiązania Sophos Mobile w usłudze Microsoft Intune w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67f3f329cb66716a2126f47eb2984ca26854b6de
ms.sourcegitcommit: b1ad73f5c9fd0ad8026c572aef8d15e258951c8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2019
ms.locfileid: "64880759"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Integracja usługi Sophos Mobile z usługą Intune  

Aby zintegrować rozwiązanie Sophos Mobile Threat Defense z usługą Intune, wykonaj kroki opisane poniżej.  

## <a name="before-you-begin"></a>Przed rozpoczęciem  

Przed rozpoczęciem procesu integracji rozwiązania Sophos Mobile z usługą Intune upewnij się, że przygotowano następujące elementy:  
- Subskrypcja usługi Microsoft Intune  
- Poświadczenia administratora usługi Azure Active Directory umożliwiające przyznanie następujących uprawnień:  
  - Logowanie i odczyt profilu użytkownika  
  - Dostęp do katalogu jako zalogowany użytkownik  
  - Odczyt danych katalogu  
  - Wysyłanie informacji o urządzeniu do usługi Intune  
- Poświadczenia administratora umożliwiające dostęp do konsoli administracyjnej rozwiązania Sophos Mobile  


### <a name="sophos-mobile-app-authorization"></a>Autoryzacja aplikacji Sophos Mobile  
  
Przebieg procesu autoryzacji aplikacji Sophos Mobile jest następujący:  
- Zezwól usłudze Sophos Mobile na przekazywanie informacji związanych z kondycją urządzenia z powrotem do usługi Intune.  
- Usługa Sophos Mobile synchronizuje się z członkostwem w grupie rejestracji usługi Azure AD, aby wypełnić bazę danych urządzeń.  
- Zezwól konsoli administracyjnej Sophos Mobile na używanie logowania jednokrotnego usługi Azure AD.  
- Zezwól aplikacji Sophos Mobile na logowanie się przy użyciu logowania jednokrotnego usługi Azure AD.  


## <a name="to-set-up-sophos-mobile-integration"></a>Aby skonfigurować integrację aplikacji Sophos Mobile  

1. Zaloguj się do witryny [Azure Portal]( https://portal.azure.com/), przejdź do pozycji **Intune** > **Zgodność urządzenia** > **Mobile Threat Defense** i wybierz pozycję **Dodaj**.  
2. Na stronie **Dodawanie łącznika** użyj listy rozwijanej i wybierz pozycję **Sophos**. Następnie wybierz pozycję **Utwórz**.  
3. Wybierz link *Otwórz konsolę administracyjną Sophos*.  
4. Zaloguj się do [konsoli administracyjnej Sophos](https://central.sophos.com/) przy użyciu swoich poświadczeń Sophos.  
5. Przejdź do pozycji **Mobile (Urządzenie przenośne)** > **Settings (Ustawienia)** > **Setup (Konfiguracja)** > **Sophos Setup (Konfiguracja rozwiązania Sophos)**.  
6. Na stronie **Sophos setup (Konfiguracja rozwiązania Sophos)** wybierz kartę **Intune MTD**.  
   ![Konfiguracja rozwiązania Sophos](./media/sophos-mtd-connector-integration/sophos-setup.png) 
 
7. Wybierz pozycję **Bind (Powiąż)**, a następnie wybierz pozycję **Yes (Tak)**. Rozwiązanie Sophos nawiąże połączenie z usługą Intune i poprosi o zalogowanie się do subskrypcji usługi Intune. 
8. W oknie uwierzytelniania usługi Microsoft Intune wprowadź swoje poświadczenia usługi Intune i **zaakceptuj** żądanie uprawnień do usługi *Sophos Mobile Thread Defense*.  
   ![Uwierzytelnianie w usłudze Intune](./media/sophos-mtd-connector-integration/intune-authentication.png)

9. Na stronie **Sophos setup (Konfiguracja rozwiązania Sophos)** wybierz opcję **Save (Zapisz)** w celu zakończenia konfiguracji dla usługi Intune:  
   ![Zapisywanie konfiguracji rozwiązania Sophos](./media/sophos-mtd-connector-integration/save-sophos-configuration.png)  

1. Gdy zostanie wyświetlony komunikat **Successful Integration** (Pomyślna integracja), integracja będzie zakończona.  
1. W konsoli usługi Intune będzie od teraz dostępna usługa Sophos.  


## <a name="next-steps"></a>Następne kroki  
[Konfigurowanie aplikacji klienckich usługi Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
