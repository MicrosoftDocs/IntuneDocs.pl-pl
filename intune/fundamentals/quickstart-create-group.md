---
title: Przewodnik Szybki start — tworzenie grupy do zarządzania użytkownikami
titleSuffix: Microsoft Intune
description: W tym przewodniku Szybki start utworzysz za pomocą usługi Microsoft Intune grupę na podstawie istniejących użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/22/2019
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
ms.openlocfilehash: d73cc367e6c3308b34c2d2dd14c9fed94d80ba74
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813405"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Szybki start: tworzenie grupy do zarządzania użytkownikami

W tym przewodniku Szybki start utworzysz za pomocą usługi Intune grupę na podstawie istniejącego użytkownika. Grupy służą do zarządzania użytkownikami i sterowania dostępem pracowników do zasobów firmy. Te zasoby mogą być częścią intranetu firmy lub być zasobami zewnętrznymi, takimi jak witryny programu SharePoint, aplikacje SaaS czy aplikacje internetowe.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

>[!NOTE]
>Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby zrealizować zadania w tym przewodniku Szybki start, musisz [utworzyć użytkownika](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-group"></a>Tworzenie grupy

Utworzysz grupę, która będzie używana w dalszej części tej serii przewodników Szybki Start. Aby utworzyć grupę:

1. Po otwarciu okienka **Microsoft Intune** wybierz pozycję **Grupy** > **Nowa grupa**.
2. Z listy rozwijanej **Typ grupy** wybierz pozycję **Zabezpieczenia**.
3. W polu **Nazwa grupy** wprowadź nazwę nowej grupy (na przykład **Testerzy firmy Contoso**).
4. Dodaj **opis** grupy.
5. Ustaw opcję **Typ członkostwa** na wartość **Przypisany**. 
6. Kliknij pozycję **Członkowie** i wybierz z listy co najmniej jednego członka dla grupy.

    ![Zrzut ekranu przedstawiający tworzenie grupy w usłudze Microsoft Intune](./media/quickstart-create-group/quickstart-use-groups-01.png)

7. Kliknij pozycję **Wybierz** > **Utwórz**.

Po pomyślnym utworzeniu grupy zostanie ona wyświetlona na liście **Wszystkie grupy**. 

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono za pomocą usługi Intune grupę na podstawie istniejącego użytkownika. Aby uzyskać więcej informacji na temat dodawania grup do usługi Intune, zobacz [Dodawanie grup w celu zorganizowania użytkowników i urządzeń](../groups-add.md).

Aby zapoznać się kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: konfigurowanie automatycznego rejestrowania urządzeń z systemem Windows 10](../enrollment/quickstart-setup-auto-enrollment.md)
