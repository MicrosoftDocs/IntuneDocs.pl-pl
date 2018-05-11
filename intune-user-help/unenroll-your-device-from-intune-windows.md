---
title: Usuwanie urządzenia z systemem Windows z usługi Intune | Microsoft Docs
description: Opis sposobu usunięcia urządzenia z systemem Windows z usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 89a69f7d5cda31658cc9faf068a2a37698fdd93c
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
---
# <a name="remove-your-windows-device-from-intune"></a>Usuwanie urządzenia z systemem Windows z usługi Intune

Jeśli Twoje urządzenie zostało zarejestrowane w usłudze Intune, ale nie chcesz już używać go do dostępu do służbowych wiadomości e-mail, aplikacji oraz innych zasobów, musisz usunąć je z zarządzania. Po usunięciu urządzenia z usługi Intune nie będzie można uzyskiwać dostępu do tych zasobów. Aby uzyskać więcej informacji o tym, co się stanie po usunięciu urządzenia z zarządzania, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Usuwanie urządzenia z systemem Windows 10

1.  Na liście aplikacji naciśnij aplikację **Portal firmy** .

2.  Zaloguj się przy użyciu poświadczeń konta służbowego.

3.  Na stronie **Moje urządzenia**wybierz urządzenie, które chcesz wyrejestrować.

4.  Naciśnij pozycję **Usuń** &gt; **Usuń**.

## <a name="remove-your-windows-81-computer"></a>Usuwanie komputera z systemem Windows 8.1

1.  Przejdź do pozycji **Ustawienia komputera** &gt; **Sieć** &gt; **Miejsce pracy**.

2.  W obszarze **Dołącz do miejsca pracy** wybierz pozycję **Opuść**.

3.  W obszarze **Włączanie zarządzania urządzeniami** wybierz pozycję **Wyłącz**.

4.  W otwartym oknie podręcznym wybierz pozycję **Wyłącz**.

## <a name="remove-your-windows-phone-81-mobile-device"></a>Usuwanie urządzenia przenośnego z systemem Windows Phone 8.1

1.  Przejdź do pozycji **Ustawienia** &gt; **Miejsce pracy**.

2.  Naciśnij konto firmowe, które chcesz wyrejestrować.

3.  W dolnej części ekranu naciśnij pozycję **Usuń**.

4.  W oknie dialogowym **Usuń konto** naciśnij opcję **Usuń**.

## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Usuwanie danych osobowych po usunięciu aplikacji Portal firmy

Istnieją dwa rodzaje danych, które aplikacja Portal firmy przechowuje na urządzeniu z systemem Windows:

-   **Dzienniki diagnostyczne**: standardowe dane o aktywności aplikacji, które zbiera firma Microsoft, na przykład czas otwarcia aplikacji lub informacje o awarii — są automatycznie usuwane w przypadku odinstalowania aplikacji Portal firmy.
-   **Pamięć podręczna aplikacji**: przechowywanie wybranych plików pomocniczych wymaganych do działania aplikacji, np. ikon i ustawień.

Istnieje kilka kroków, które należy podjąć, aby całkowicie usunąć te informacje.

### <a name="uninstall-the-company-portal"></a>Odinstalowanie aplikacji Portal firmy  

[Odinstalowanie aplikacji Portal firmy](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) spowoduje usunięcie niektórych danych aplikacji przechowywanych na urządzeniu.  

### <a name="reset-the-company-portal"></a>Resetowanie aplikacji Portal firmy

Możesz zresetować pozostałe dane aplikacji Portal firmy poprzez zresetowanie aplikacji w ustawieniach. Otwórz pozycję **Ustawienia** > **Aplikacje i funkcje** > **Portal firmy** > **Opcje zaawansowane** > **Resetuj**.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
