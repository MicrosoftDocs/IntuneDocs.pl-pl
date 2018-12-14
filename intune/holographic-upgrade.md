---
title: Uaktualnienie do systemu Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Dowiedz się, jak uaktualnić urządzenia z systemem Windows Holographic do systemu Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 4839206db5e34a039c9e99dd74f5ab1bad328418
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112344"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Uaktualnianie urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business


Aby zarządzać urządzeniami z systemem Windows Holographic za pomocą usługi Microsoft Intune, musisz uaktualnić urządzenia z systemem Windows Holographic do systemu Windows Holographic for Business. W celu przeprowadzenia tego uaktualnienia możesz utworzyć profil uaktualniania wersji. W przypadku urządzeń Microsoft HoloLens możesz kupić wersję Commercial Suite, aby uzyskać wymaganą licencję na uaktualnienie. Aby uzyskać więcej informacji, zobacz [Unlock Windows Holographic for Business features](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise) (Odblokowanie funkcji systemu Windows Holographic for Business).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Aby skonfigurować profil konfiguracji urządzenia dla uaktualnienia wersji

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com) przy użyciu konta administratora.


2.  Kliknij pozycje **Konfiguracja urządzeń**, **Profile**, a następnie kliknij przycisk **+ Utwórz profil**.

    ![Utwórz profil](media/Holographic-create-profile.png)

3.  Na stronie **Utwórz profil** wpisz nazwę profilu, wybierz pozycję **Windows 10 i nowsze** dla platformy, a następnie wybierz pozycję **Uaktualnienie wersji** dla typu profilu. Kliknij przycisk **Konfiguruj ustawienia**.

5. Na stronie **Uaktualnienie wersji** dla pozycji **Docelowa wersja uaktualnienia** wybierz pozycję **Windows 10 Holographic for Business**. W polu **Plik licencji** wyszukaj i wybierz plik licencji XML, który został udostępniony.

    ![Wprowadzanie nazwy pliku XML](media/Holographic-edition-upgrade.png)
 
5.  Kliknij przycisk **OK**, a następnie kliknij przycisk **Utwórz**, aby utworzyć profil.


## <a name="deploy-the-edition-upgrade-policy"></a>Wdrażanie zasad uaktualniania wersji

Następnie przypisz profil uaktualniania wersji do wybranych grup lub urządzeń.

1. W profilu, który został utworzony w poprzednich krokach, kliknij przycisk **Przypisania**.

2. Na stronie **Przypisania** wybierz grupy użytkowników i urządzeń, które chcesz dołączać i wykluczać za pomocą zasad.

![Dołączanie i wykluczanie grup](media/Holographic-groups.PNG)

Profil uaktualnienia wersji jest stosowany, gdy ci użytkownicy lub urządzenia są zarejestrowane w usłudze Intune. 

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat grup, zobacz [Wprowadzenie do grup](get-started-groups.md).


