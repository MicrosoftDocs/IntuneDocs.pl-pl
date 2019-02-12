---
title: Włączanie zgodności z funkcją Google Play Protect przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Informacje dotyczące tworzenia zasad zgodności dla urządzeń z systemem Android w celu włączenia funkcji Google Play Protect.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5963cb7de2994feb41c4679e87970aec4f127de5
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848831"
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Jak utworzyć zasady zgodności urządzenia w celu włączenia funkcji Google Play Protect

Można utworzyć nowe zasady zgodności dla platformy systemu Android, aby sprawdzić zgodność z funkcją Google Play Protect (GPP).

Zasady zgodności, które wymagają tych ustawień, można następnie zastosować do grupy użytkowników systemu Android lub urządzeń z tym systemem. Jeśli w urządzeniu nie włączono tych ustawień, nie jest ono zgodne.

## <a name="create-a-compliance-policy"></a>Tworzenie zasad zgodności

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
2. Wybierz pozycję **Zgodność urządzenia** w grupie **Zarządzanie**. 
3. Wybierz pozycję **Zasady**, a następnie wybierz pozycję **Utwórz zasady**.
4. Wpisz informacje w następujących polach zasad: **Nazwa** i **Opis**.
5. Wybierz platformę **Android**.
6. Wybierz kolejno pozycje **Ustawienia** > **Kondycja urządzenia**.
7. Skonfiguruj ustawienia funkcji **Google Play Protect**.
8. Po zdefiniowaniu ustawień funkcji Google Play Protect określ ustawienia w obszarach **Zabezpieczenia systemu** i **Właściwości urządzenia**. Gdy wszystko będzie gotowe, wybierz pozycję **OK**.

## <a name="configure-the-google-play-protect-settings"></a>Konfigurowanie ustawień funkcji Google Play Protect

 - **Skonfigurowano Usługi Google Play**  
   Wymagaj zainstalowania i włączenia aplikacji usług Google Play. Usługi Google Play umożliwiają aktualizacje zabezpieczeń i stanowią zależność na poziomie podstawowym dla wielu funkcji zabezpieczeń w urządzeniach certyfikowanych przez firmę Google.
 - **Aktualny dostawca zabezpieczeń**  
   Wymagaj, aby aktualny dostawca zabezpieczeń mógł chronić urządzenie przed znanymi lukami w zabezpieczeniach.
 - **Skanowanie aplikacji pod kątem zagrożeń**  
   Wymagaj włączenia funkcji **Weryfikuj aplikacje** w systemie Android.
    > [!Note]  
    > Na platformie systemu Android w starszej wersji ta funkcja jest ustawieniem zgodności. Usługa Intune może tylko sprawdzić, czy to ustawienie zostało włączone na poziomie urządzenia. Na urządzeniach z profilami służbowymi systemu Android to ustawienie można znaleźć w obszarze ustawień zasad konfiguracji. Umożliwia to administratorom włączenie ustawienia dla urządzenia.

    Jeśli w przedsiębiorstwie są używane profile służbowe systemu Android, można włączyć opcję **Skanowanie aplikacji pod kątem zagrożeń** dla zarejestrowanych urządzeń. Ustanów profil urządzenia i wymagaj ustawienia zabezpieczeń systemu. Aby uzyskać więcej informacji, zobacz [Ustawienia ograniczeń urządzenia z profilem służbowym systemu Android w usłudze Microsoft Intune](device-restrictions-android-for-work.md).

 - **Zaświadczanie urządzeń SafetyNet**  
   Ustaw poziom integralności zaświadczania urządzenia SafetyNet, którego warunki muszą zostać spełnione. Dostępne poziomy to **Nie skonfigurowano**, **Sprawdź podstawową integralność** i **Sprawdź podstawową integralność i certyfikowane urządzenia**.




## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się więcej na temat pracy z zasadami zgodności urządzeń usługi Intune, zobacz [Wprowadzenie do zasad zgodności urządzeń usługi Intune](device-compliance-get-started.md).
