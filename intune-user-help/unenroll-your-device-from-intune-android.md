---
title: Jak usunąć urządzenie z systemem Android z usługi Intune | Microsoft Docs
description: Opis sposobu wyrejestrowania urządzenia z systemem Android z usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ec3c0a1c8ce4e04f4d23fb01e7c2525d8f2eed5b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-remove-your-android-device-from-intune"></a>Jak usunąć urządzenie z systemem Android z usługi Intune

Po usunięciu z usługi Intune urządzenie z systemem Android nie może uzyskiwać dostępu do zasobów firmy.  Aby uzyskać więcej informacji o tym, co się stanie po usunięciu urządzenia z zarządzania, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

## <a name="removing-the-device-from-the-company-portal-app"></a>Usuwanie urządzenia przy użyciu aplikacji Portal firmy

Aby usunąć urządzenie z usługi Intune i usunąć aplikację Portal firmy, wykonaj poniższe kroki:

1. Aby otworzyć **menu akcji**, naciśnij przycisk z trzema pionowo ułożonymi kropkami w prawym górnym rogu aplikacji Portal firmy.

   ![Obraz aplikacji Portal firmy dla systemu Android z otwartym menu akcji w prawym górnym rogu. Nowa opcja „usuń portal firmy” jest dostępna jako trzecia opcja poniżej opcji „mój profil” i „ustawienia”, powyżej pozycji „warunki i postanowienia”, „pomoc i opinie” oraz „informacje”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Naciśnij pozycję **Usuń Portal firmy**.

3. W oknie wyskakującym zostanie wyświetlona prośba o potwierdzenie, czy na pewno aplikacja Portal firmy ma zostać usunięta. Będzie ona zawierała pewne informacje o tym, co się stanie po wyrejestrowaniu urządzenia. Po zapoznaniu się z tym komunikatem naciśnij przycisk **OK**, aby usunąć aplikację.

   ![Obraz okna dialogowego potwierdzenia, które jest dostępne po wybraniu w menu akcji nowej opcji „usuń portal firmy”. Okno dialogowe informuje użytkownika, że „po usunięciu portalu firmy urządzenie przestanie być zarządzane przez dział pomocy technicznej Twojej firmy, a dostęp do firmowych danych, aplikacji i poczty e-mail może zostać utracony”. Następnie użytkownik jest proszony o potwierdzenie za pomocą przycisku „Tak”, że chce usunąć aplikację Portal firmy.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Usuwanie danych zebranych przez aplikację Portal firmy

Aby usunąć wszystkie dane przechowywane przez aplikację Portal firmy dla systemu Android z urządzenia:

-   Wyczyść dane aplikacji: przejdź do obszaru Aplikacje, a następnie kliknij aplikację i przycisk „Wyczyść dane”
-   Usuń folder „\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal”

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
