---
title: Szybki start — tworzenie i przypisywanie zasad ochrony aplikacji
titlesuffix: Microsoft Intune
description: W tym przewodniku Szybki start utworzysz i przypiszesz za pomocą usługi Microsoft Intune zasady ochrony aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e3057009eb758e37a4b42cddc4673bd721d1bce
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576636"
---
# <a name="quickstart-create-and-assign-an-app-protection-policy"></a>Szybki start: tworzenie i przypisywanie zasad ochrony aplikacji

W tym przewodniku Szybki start użyjesz usługi Intune do utworzenia i przypisania zasad ochrony aplikacji do aplikacji klienckiej na urządzeniu użytkownika końcowego. Usługa Intune używa zasad ochrony aplikacji, aby sprawdzać, czy Twoje aplikacje spełniają wymagania organizacji w zakresie ochrony danych.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Aby ukończyć ten przewodnik Szybki start, musisz [utworzyć użytkownika](quickstart-create-user.md), [utworzyć grupę](quickstart-create-group.md), [zarejestrować urządzenie](quickstart-setup-auto-enrollment.md) oraz [dodać i przypisać aplikację](quickstart-add-assign-app.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-an-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji

Użyj następujących kroków, aby utworzyć zasady ochrony aplikacji:

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji** > **Utwórz zasady**. 
2. Wprowadź następujące informacje: 

    - **Nazwa**: *Ochrona zawartości w systemie Windows 10*
    - **Opis**: *Użytkownicy skojarzeni z tymi zasadami nie będą mogli wycinać, kopiować ani wklejać żadnej zawartości między przypisaną aplikacją a innymi niezarządzanymi aplikacjami na urządzeniu.*
    - **Platforma**: *Windows 10*
    - **Stan rejestracji**: *Z rejestracją*

3. Wybierz pozycję **Chronione aplikacje**, aby wybrać aplikacje, które muszą stosować się do tych zasad.
4. Kliknij pozycję **Dodaj aplikacje**.
5. W obszarze **Zalecane aplikacje** wybierz pozycję **Word Mobile**.
5. Kliknij przycisk **OK** > **OK**. 
6. Wybierz pozycję **Wymagane ustawienia**, aby skonfigurować aplikację.
7. Kliknij pozycję **Zezwalaj na przesłonięcia**, aby ustawić tryb usługi Windows Information Protection. Wybranie tej opcji spowoduje, że dane przedsiębiorstwa nie będą mogły opuszczać chronionej aplikacji.
8. Kliknij przycisk **OK** > **Utwórz**.

Zobaczysz zasady ochrony aplikacji w usłudze Intune.

### <a name="assign-the-app-protection-policy"></a>Przypisywanie zasad ochrony aplikacji

Po utworzeniu zasad ochrony aplikacji w usłudze Intune można je przypisać do grup. 

Aby przypisać zasady ochrony aplikacji, wykonaj następujące kroki:

1.  W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycje **Intune** > **Aplikacje klienckie** > **Zasady ochrony aplikacji**. 
2.  Wybierz zasady ochrony aplikacji utworzone wcześniej. W tym przewodniku Szybki start są to zasady **Ochrona zawartości w systemie Windows 10**.
3.  Wybierz pozycję **Przypisania**.
4.  Na karcie **Dołączanie** wybierz pozycję **Wybierz grupy do uwzględnienia**.
5.  Jako grupę do dołączenia wybierz grupę **Testerzy firmy Contoso**.
6.  Kliknij pozycję **Wybierz**. 

Zasady ochrony aplikacji zostały przypisane.

> [!NOTE]
> Zasady ochrony aplikacji można zastosować tylko do grup zawierających użytkowników, nie do grup zawierających urządzenia.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start zostały utworzone i przypisane zasady ochrony aplikacji. Użytkownicy aplikacji, którzy mają przypisane te zasady, nie będą w stanie wycinać, kopiować ani wklejać żadnej zawartości między przypisaną aplikacją i innymi, niezarządzanymi aplikacjami na urządzeniu. Ten typ ochrony pomoże chronić dane Twojej organizacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji w usłudze Intune, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: tworzenie i przypisywanie roli niestandardowej](quickstart-create-custom-role.md)
