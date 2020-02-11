---
title: Przewodnik Szybki start — tworzenie grupy do zarządzania użytkownikami
titleSuffix: Microsoft Intune
description: W tym przewodniku Szybki start utworzysz za pomocą usługi Microsoft Intune grupę na podstawie istniejących użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/17/2020
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9b06043dd10f92b6176d4b2e9f90f1b7c87aac9
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540960"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Szybki start: tworzenie grupy do zarządzania użytkownikami

W tym przewodniku Szybki start utworzysz za pomocą usługi Intune grupę na podstawie istniejącego użytkownika. Grupy służą do zarządzania użytkownikami i sterowania dostępem pracowników do zasobów firmy. Te zasoby mogą być częścią intranetu firmy lub być zasobami zewnętrznymi, takimi jak witryny programu SharePoint, aplikacje SaaS czy aplikacje internetowe.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

>[!NOTE]
>Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika.

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja usługi Intune: [utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).
- Aby zrealizować zadania w tym przewodniku Szybki start, musisz [utworzyć użytkownika](quickstart-create-user.md).

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Logowanie do usługi Intune w programie Microsoft Endpoint Manager

Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-group"></a>Tworzenie grupy

Utworzysz grupę, która będzie używana w dalszej części tej serii przewodników Szybki Start. Aby utworzyć grupę:

1. Po otwarciu **centrum administracyjnego programu Microsoft Endpoint Manager** wybierz pozycję **Grupy** > **Nowa grupa**.
2. Z listy rozwijanej **Typ grupy** wybierz pozycję **Zabezpieczenia**.
3. W polu **Nazwa grupy** wprowadź nazwę nowej grupy (na przykład **Testerzy firmy Contoso**).
4. Dodaj **opis grupy**.
5. Ustaw opcję **Typ członkostwa** na wartość **Przypisany**. 
6. W obszarze **Członkowie** wybierz link i dodaj co najmniej jednego członka dla grupy z listy.

    ![Zrzut ekranu przedstawiający tworzenie grupy w usłudze Microsoft Intune](./media/quickstart-create-group/quickstart-use-groups-01.png)

7. Kliknij pozycję **Wybierz** > **Utwórz**.

Po pomyślnym utworzeniu grupy zostanie ona wyświetlona na liście **Wszystkie grupy**. 

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono za pomocą usługi Intune grupę na podstawie istniejącego użytkownika. Aby uzyskać więcej informacji na temat dodawania grup do usługi Intune, zobacz [Dodawanie grup w celu zorganizowania użytkowników i urządzeń](../groups-add.md).

Aby zapoznać się z kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10](../enrollment/quickstart-setup-auto-enrollment.md)
