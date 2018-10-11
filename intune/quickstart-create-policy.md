---
title: 'Przewodnik Szybki start: dodawanie zasad zgodności urządzeń dla urządzenia z systemem Windows 10'
description: Ten przewodnik Szybki start ułatwia utworzenie zasad, aby chronić dane firmowe i zarządzać urządzeniami, za pomocą których użytkownicy końcowi uzyskują dostęp do zasobów firmy. Następnie przypisz te zasady do grup.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73e1e0a27d128d567a924e6f2b343026b11f1a44
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581782"
---
# <a name="quickstart-add-a-device-compliance-policy-for-a-windows-10-device"></a>Przewodnik Szybki start: dodawanie zasad zgodności urządzeń dla urządzenia z systemem Windows 10
Zasady zgodności urządzeń w usłudze Intune dla systemu Windows określają reguły i ustawienia, które urządzenia z systemem Windows muszą spełnić, aby zostały uznane za zgodne. Można je wykorzystać do stosowania [dostępu warunkowego](https://docs.microsoft.com/intune/conditional-access), aby zezwolić na dostęp do zasobów firmy lub go zablokować. Można również pobrać raporty urządzeń i podjąć akcje w przypadku niezgodności.

W tym przewodniku Szybki start utworzysz zasady zgodności urządzeń dla urządzenia z systemem Windows 10, a następnie przypiszesz do tych zasad grupę urządzeń.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
- Aby zrealizować zadania w tym przewodniku Szybki start, musisz najpierw [utworzyć użytkownika](quickstart-create-user.md) i [utworzyć grupę](quickstart-create-group.md).


## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune
Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune.

## <a name="create-a-device-compliance-policy"></a>Tworzenie zasad zgodności urządzenia
1. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
2. Wprowadź tekst **Windows 10 compliance** (Zgodność systemu Windows 10) w polu **Nazwa** i tekst **Sample compliance policy for Windows 10** (Przykładowe zasady zgodności dla systemu Windows 10) w polu **Opis**.
3. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
4. W obszarze **Ustawienia** wybierz pozycję **Zabezpieczenia systemu**, a następnie dla opcji **Wymagaj hasła do odblokowania urządzeń przenośnych** ustaw wartość **Wymagaj**. Po zakończeniu konfigurowania zasad wybierz przycisk **OK**.
   ![Zasady zgodności](/intune/media/quickstart-create-policy/compliance-policy.png)
5. Zamknij okienko **Zasady dotyczące zgodności dla systemu Windows 10**. 
6. W okienku **Tworzenie zasad** wybierz pozycję **Utwórz**. Ta czynność powoduje utworzenie zasad i wymienienie ich w obszarze **Zgodność urządzeń** > **Zasady**.
7. Wybierz swoje nowe zasady i wybierz pozycję **Przypisania**. Możesz włączyć lub wyłączyć grupy zabezpieczeń usługi Azure Active Directory (AD).
8. Wybierz pozycję **Wybrane grupy**, aby wyświetlić istniejące grupy zabezpieczeń usługi Azure AD. Wybierz pozycję **Contoso Testers** (Testerzy Contoso) i pozycję **Zapisz**, aby wdrożyć zasady dla użytkowników w grupie. Jeśli ta grupa nie została utworzona w [przewodniku dotyczącym tworzenia grupy](quickstart-create-group.md), możesz użyć dowolnej grupy. 

## <a name="clean-up-resources"></a>Oczyszczanie zasobów
Gdy te zasady nie będą już potrzebne, usuń je. Aby to zrobić, wybierz zasady **Windows 10 compliance** (Zgodność systemu Windows 10) i kliknij przycisk **Usuń**. 

## <a name="next-steps"></a>Następne kroki
W tym przewodniku Szybki start utworzono i przypisano proste zasady zgodności urządzeń. Aby zarejestrować urządzenie z systemem Windows 10, które otrzyma te zasady, przejdź do przewodnika Szybki start dotyczącego konfigurowania automatycznego rejestrowania. 
 
> [!div class="nextstepaction"]
> [Konfigurowanie automatycznego rejestrowania](quickstart-setup-auto-enrollment.md)