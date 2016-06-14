---
# required metadata

title: Portal Azure — zasady zarządzania aplikacjami mobilnymi | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Portal Azure — zasady zarządzania aplikacjami mobilnymi
## Dostęp do portalu Azure
**Portal Azure** pozwala tworzyć zasady zarządzania aplikacjami mobilnymi oraz zarządzać tymi zasadami.

Portal Azure obsługuje tworzenie zasad zarządzania aplikacjami mobilnymi dla następujących składników:
- Aplikacje działające na urządzeniach **zarejestrowanych w usłudze Intune i zarządzanych przez nią**.
- Aplikacje działające na urządzeniach, które **nie są zarejestrowane** w żadnym rozwiązaniu do zarządzania aplikacjami mobilnymi
- Aplikacje działające na urządzeniach, które **są zarejestrowane w rozwiązaniu do zarządzania aplikacjami mobilnymi innej firmy**..

Jeśli obecnie korzystasz z **konsoli administracyjnej usługi Intune** do zarządzania urządzeniami, możesz utworzyć zasady zarządzania aplikacjami mobilnym obsługujące aplikacje dla urządzeń zarejestrowanych w usłudze Intune przy użyciu [konsoli administracyjnej usługi Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
>[!IMPORTANT]
> W konsoli administracyjnej usługi Intune mogą nie być wyświetlane wszystkie ustawienia zasad zarządzania aplikacjami mobilnymi. Portal Azure to nowa konsola administracyjna do tworzenia zasad zarządzania aplikacjami mobilnymi.

## Zaloguj się do portalu Azure i dostosuj swoją stronę początkową

1.  Przejdź do [portalu Azure](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Zrzut ekranu przedstawiający stronę logowania się do portalu Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po pomyślnym zalogowaniu pojawi się strona **Pulpit nawigacyjny**. Na stronie **Pulpit nawigacyjny** znajduje się zestaw kafelków domyślnych, które można usunąć i dodać nowe w celu dostosowania strony.

    ![Zrzut ekranu pulpitu nawigacyjnego portalu Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  W menu **Przeglądaj** znajdź pozycję **Intune**.![Zrzut ekranu przedstawiający menu Przeglądaj z wyróżnioną pozycją Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Kliknij pozycje **Intune > Zarządzanie aplikacjami mobilnymi w usłudze Intune > Ustawienia**..

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Aby przypiąć blok do strony **Start** , możesz użyć opcji **przypinania** w bloku.  Kliknij ikonę przypinania w **bloku zarządzania aplikacjami mobilnymi usługi Intune**, aby przypiąć go do strony **Start** .

    ![Zrzut ekranu przedstawiający blok zarządzania aplikacjami mobilnymi usługi Intune z wyróżnioną ikoną przypinania](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Zrzut ekranu pulpitu nawigacyjnego z przypiętym kafelkiem usługi Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Następne kroki
[Przygotowywanie się do konfigurowania zasad zarządzania aplikacjami mobilnymi](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


