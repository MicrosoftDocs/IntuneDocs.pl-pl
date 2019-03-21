---
title: Sprawdzanie dostępu urządzeń | Microsoft Docs
description: Sprawdź dostęp urządzenia, aby dowiedzieć się, czy spełnia ono wymagania i jest w stanie uzyskać dostęp do zasobów służbowych.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b4c1575c72e0563c4c55e262756c9b4aa0eddde
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "55848206"
---
# <a name="check-access-from-company-portal-app-for-windows"></a>Sprawdzanie dostępu z poziomu aplikacji Portal firmy dla systemu Windows

Sprawdź, czy urządzenie ma dostęp do zasobów służbowych. 

Organizacje wymuszają wymagania, takie jak szyfrowanie i limity haseł, aby mieć pewność, że tylko zabezpieczone, zaufane urządzenia uzyskują dostęp do ich danych. Urządzenia zarządzane muszą spełniać i obsługiwać te wymagania, aby mogły uzyskać dostęp do zasobów organizacji.

Akcja **Sprawdź dostęp** ocenia ustawienia Twojego urządzenia i jego stan dostępu. Na stronie **Szczegóły urządzenia** znajduje się lista ustawień, które musisz dostosować, aby odzyskać dostęp. 

Wykonaj kroki opisane w tym artykule, aby sprawdzić dostęp z poziomu aplikacji Portal firmy dla systemu Windows.  

## <a name="check-access-from-device-details-page"></a>Sprawdzanie dostępu z poziomu strony Szczegóły urządzenia  
1. Otwórz aplikację Portal firmy dla systemu Windows i przejdź do sekcji **Moje urządzenia**.  

    ![Przykładowy zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona główna z wyróżnieniem sekcji Moje urządzenia.](./media/1809_CheckAccess_Context_Select_Device.png)  
2. Wybierz urządzenie.  
3. Na stronie **Szczegóły urządzenia** wybierz pozycję **Sprawdź dostęp**. Aplikacja zsynchronizuje Twoje urządzenie z bieżącymi wymaganiami organizacji, aby upewnić się, że urządzenie je spełnia. Sprawdzanie może potrwać kilka minut.  

    ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem przycisku Sprawdź dostęp.](./media/1809_CheckAccess_Checking_Status.png) 

4. Spójrz na aktualizację stanu. Będzie ona zawierała informację, czy Twoje urządzenie **Ma dostęp do zasobów organizacji**, czy **Nie ma dostępu do zasobów organizacji**.  

   ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem sekcji Stan.](./media/1809_CheckAccess_Device_details_status1.png)  
   
5. Jeśli urządzenie nie ma dostępu do zasobów, przejdź do alertu w górnej części strony. Kliknij pozycję **Więcej**, aby rozwinąć jego szczegóły. Kliknij pozycję **Mniej**, aby je zwinąć.  

    ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem alertu w górnej części strony.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Jeśli to możliwe, komunikat zawiera dodatkowe linki pomocy i akcje korygowania. Wybierz co najmniej jedną z tych opcji, aby od razu rozpocząć rozwiązywanie problemów. Opisane poniżej akcje rozwiązywania, synchronizacji i kontaktu są widoczne tylko w przypadku korzystania z aplikacji Portal firmy na urządzeniu, którego dotyczy problem.  

     * **Jak to rozwiązać** otwiera odpowiedni artykuł pomocy, jeśli jest dostępny.  
     * **Rozwiąż** przekierowuje Cię do ustawienia na urządzeniu.  
     * **Synchronizuj** ocenia, czy urządzenie spełnia wymagania organizacji.  
     * **Kontakt z działem IT** przekierowuje Cię do informacji kontaktowych Twojego zespołu IT.   
 
6. Po zaktualizowaniu ustawień kliknij pozycję **Sprawdź dostęp**, aby potwierdzić stan Twojego urządzenia.  

    ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem sekcji Stan.](./media/1809_CheckAccess_Device_details_status1.png)  

## <a name="check-access-from-device-context-menu"></a>Sprawdzanie dostępu z poziomu menu kontekstowego urządzenia  
1. Otwórz aplikację Portal firmy dla systemu Windows i przejdź do sekcji **Moje urządzenia**.  

    ![Przykładowy zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona główna z wyróżnieniem sekcji Moje urządzenia.](./media/1809_CheckAccess_Context_Select_Device.png)  

2. Kliknij prawym przyciskiem myszy lub naciśnij i przytrzymaj urządzenie, aby otworzyć jego [menu kontekstowe](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus).  

    ![Przykładowy zrzut ekranu aplikacji Portal firmy dla systemu Windows, strona główna. Menu kontekstowe urządzenia jest widoczne w sekcji **Moje urządzenia** strony i przedstawia akcje „Zmień nazwę”, „Usuń” oraz „Sprawdź dostęp”.](./media/1809_DeviceContextMenu_Windows_CP.png)  
3. Wybierz pozycję **Sprawdź dostęp**. Aplikacja zsynchronizuje Twoje urządzenie z bieżącymi wymaganiami organizacji, aby upewnić się, że urządzenie je spełnia. Sprawdzanie może potrwać kilka minut.  
 
4. W obszarze urządzenia zostanie wyświetlony komunikat informujący o tym, że urządzenie **Ma dostęp do zasobów firmy** lub **Nie ma dostępu do zasobów firmy**. 

    ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem sekcji Stan.](./media/1809_CheckAccess_Context_Menu_Alert2.png) 

5. Jeśli urządzenie nie ma dostępu do zasobów, wybierz je.  
6. Na stronie **Szczegóły urządzenia** przejdź do alertu w górnej części strony. Kliknij pozycję **Więcej**, aby rozwinąć jego szczegóły. Kliknij pozycję **Mniej**, aby je zwinąć.  

    ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem alertu w górnej części strony.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Jeśli to możliwe, komunikat zawiera dodatkowe linki pomocy i akcje korygowania. Wybierz co najmniej jedną z tych opcji, aby od razu rozpocząć rozwiązywanie problemów. Opisane poniżej akcje rozwiązywania, synchronizacji i kontaktu są widoczne tylko w przypadku korzystania z aplikacji Portal firmy na urządzeniu, którego dotyczy problem.  

     * **Jak to rozwiązać** otwiera odpowiedni artykuł pomocy, jeśli jest dostępny.  
     * **Rozwiąż** przekierowuje Cię do ustawienia na urządzeniu.  
     * **Synchronizuj** ocenia, czy urządzenie spełnia wymagania organizacji.  
     * **Kontakt z działem IT** przekierowuje Cię do informacji kontaktowych Twojego zespołu IT.    

7. Po zaktualizowaniu ustawień kliknij pozycję **Sprawdź dostęp** w dolnej części strony.  

    ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona Szczegóły urządzenia z wyróżnieniem akcji Sprawdź dostęp.](./media/1809_CheckAccess_Device_details_button.png) 


Potrzebujesz dodatkowej pomocy? Znajdź informacje kontaktowe działu pomocy technicznej Twojej firmy w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
