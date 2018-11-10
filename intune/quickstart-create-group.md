---
title: Przewodnik Szybki start — tworzenie grupy do zarządzania użytkownikami
titlesuffix: Microsoft Intune
description: W tym przewodniku Szybki start utworzysz za pomocą usługi Microsoft Intune grupę na podstawie istniejących użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2b52265bb9b3df800c0e13450a2154e46098a933
ms.sourcegitcommit: 9d08545727543b434dd270371fa50233470f2bce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50410824"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Przewodnik Szybki start: tworzenie grupy do zarządzania użytkownikami

W tym przewodniku Szybki start utworzysz za pomocą usługi Intune grupę na podstawie istniejącego użytkownika. Grupy służą do zarządzania użytkownikami i sterowania dostępem pracowników do zasobów firmy. Te zasoby mogą być częścią intranetu firmy lub być zasobami zewnętrznymi, takimi jak witryny programu SharePoint, aplikacje SaaS czy aplikacje internetowe.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

>[!NOTE]
>Usługa Intune udostępnia w konsoli wstępnie utworzone grupy **Wszyscy użytkownicy** i **Wszystkie urządzenia** z wbudowanymi optymalizacjami dla wygody użytkownika.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby zrealizować zadania w tym przewodniku Szybki start, musisz [utworzyć użytkownika](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako [administrator globalny lub administrator usługi Intune](users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-group"></a>Tworzenie grupy

Utworzysz grupę, która będzie używana w dalszej części tej serii przewodników Szybki Start.

1. Po otwarciu okienka **Microsoft Intune** wybierz pozycję **Grupy** > **Nowa grupa**.
2. Z listy rozwijanej **Typ grupy** wybierz pozycję **Zabezpieczenia**.
3. W polu **Nazwa** ustaw wartość „Contoso Testers” (Testerzy Contoso) i dodaj tekst w polu **Opis** dla grupy.
4. Ustaw opcję **Typ członkostwa** na wartość **Przypisany**. 
5. Kliknij pozycję **Członkowie** i wybierz co najmniej jednego członka dla grupy z listy istniejących członków.

    ![Zrzut ekranu przedstawiający tworzenie grupy w usłudze Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Kliknij pozycję **Wybierz** > **Utwórz**.

Po pomyślnym utworzeniu grupy zostanie ona wyświetlona na liście **Wszystkie grupy**. 

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono za pomocą usługi Intune grupę na podstawie istniejącego użytkownika.

> [!div class="nextstepaction"]
> [Tworzenie zasad zgodności urządzenia](quickstart-create-policy.md)
