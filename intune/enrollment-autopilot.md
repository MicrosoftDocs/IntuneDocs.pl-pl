---
title: "Rejestrowanie urządzeń z systemem Windows za pomocą programu Windows AutoPilot Deployment"
description: "Dowiedz się, jak zarejestrować nowe urządzenia z systemem Windows 10 za pomocą programu Windows AutoPilot Deployment."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 1e6052c914406c9cd2fe9dc72597ee4dbe5b8902
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>Rejestrowanie urządzeń z systemem Windows za pomocą programu Windows AutoPilot Deployment
Program Windows AutoPilot Deployment upraszcza aprowizowanie urządzeń. Tworzenie i konserwacja niestandardowych obrazów systemów operacyjnych zajmuje dużo czasu. Trzeba również poświęcić czas na stosowanie tych niestandardowych obrazów systemów operacyjnych na nowych urządzeniach w celu przygotowania ich do użycia przed przekazaniem użytkownikom końcowym. Dzięki usłudze Microsoft Intune i rozwiązaniu AutoPilot można przekazać nowe urządzenia użytkownikom końcowym bez konieczności tworzenia, konserwowania i stosowania niestandardowych obrazów systemów operacyjnych do urządzeń. Jeśli do zarządzania urządzeniami z rozwiązaniem AutoPilot używasz usługi Intune, możesz zarządzać zasadami, profilami, aplikacjami itp. na urządzeniach po ich zarejestrowaniu. Aby zapoznać się z korzyściami, scenariuszami i wymaganiami wstępnymi, zobacz [Overview of Windows AutoPilot (Przegląd rozwiązania Windows AutoPilot)](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot).

## <a name="prerequisites"></a>Wymagania wstępne
- [Urządzenia zarejestrowane w Twojej organizacji](https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/windows-10-autopilot#device-registration-and-oobe-customization)
- [Włączona funkcja automatycznej rejestracji w systemie Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Subskrypcja usługi Azure Active Directory — wersja Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>Synchronizowanie urządzeń
Zsynchronizuj swoje zarejestrowane urządzenia z usługą Intune, aby można je było skonfigurować.

1. Zaloguj się do platformy [Azure](https://portal.azure.com/).
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W obszarze **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
4. W obszarze **Rejestracja w systemie Windows** w sekcji **Program wdrażania rozwiązania Windows AutoPilot** wybierz pozycję **Urządzenia**.
5. Kliknij pozycję **Synchronizuj**, aby zaimportować swoje zarejestrowane urządzenia. Zostanie wyświetlony komunikat o synchronizacji w toku.
6. Odśwież widok, aby zobaczyć nowe urządzenia. Proces może potrwać kilka minut, w zależności od tego, ile urządzeń jest synchronizowanych.  

## <a name="create-an-autopilot-deployment-profile"></a>Tworzenie profilu wdrażania rozwiązania AutoPilot
Profile wdrażania rozwiązania AutoPilot służą do konfigurowania urządzeń z rozwiązaniem AutoPilot.
1. Zaloguj się do platformy [Azure](https://portal.azure.com/). 
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W obszarze **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
4. W obszarze **Rejestracja w systemie Windows** w sekcji **Program wdrażania rozwiązania Windows AutoPilot** wybierz pozycję **Profile wdrażania**.
5. Kliknij pozycję **Utwórz profil** i wybierz nazwę oraz opcjonalny opis. 
6. Jako **Typ sprzężenia** wybierz pozycję **Dołączono do usługi Azure AD**.
7. Dla pozycji **Środowisko gotowe do użycia (OOBE, Out-of-box experience)** skonfiguruj następujące opcje, a następnie kliknij przycisk **OK**: 
   - **Ustawienia prywatności**: wybierz, czy ustawienia prywatności mają być pokazywane użytkownikom. 
   - **Umowa licencyjna użytkownika oprogramowania (EULA, End User License Agreement)**: określ, czy umowa licencyjna użytkownika oprogramowania ma być pokazywana użytkownikom.
   - **Typ konta użytkownika**: wybierz typ konta użytkownika: **Administrator** lub **Standardowe** konto użytkownika.

     > [!Note]    
     > To ustawienie nie ma zastosowania w przypadku konta administratora globalnego ani konta administratora firmy. Te konta nie mogą odpowiadać użytkownikom standardowym, ponieważ mają dostęp do wszystkich funkcji administracyjnych w usłudze Azure AD.
8. Kliknij pozycję **Utwórz**, aby utworzyć profil. Profil wdrażania rozwiązania AutoPilot jest teraz dostępny do przypisania do urządzeń.
     
> [!Note]    
> Następujące ustawienia są konfigurowane dla wszystkich profilów wdrażania rozwiązania AutoPilot:
> - Pomijanie stron konfiguracji funkcji Cortana, usługi OneDrive i rejestracji OEM
> - Automatyczne konfigurowanie pod kątem firmy lub szkoły
> - Środowisko logowania z oznaczeniami firmy lub szkoły    

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alerty dla urządzeń nieprzypisanych w programie Windows AutoPilot <!-- 163236 -->
Możesz wyświetlić alert dla urządzeń nieprzypisanych w programie Windows AutoPilot, aby sprawdzić, ile urządzeń z programu AutoPilot nie ma przypisanych profilów wdrażania rozwiązania AutoPilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń w programie Windows AutoPilot. 
1. Zaloguj się do platformy [Azure](https://portal.azure.com/). 
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W obszarze **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
4. Aby wyświetlić alert, wybierz pozycję **Przegląd**. Kliknij alert, aby wyświetlić listę urządzeń w programie AutoPilot.  

## <a name="assign-an-autopilot-deployment-profile"></a>Przypisywanie profilu wdrażania rozwiązania AutoPilot
Po utworzeniu profilów wdrażania rozwiązania AutoPilot można przypisać je do wybranych urządzeń.

1. Zaloguj się do platformy [Azure](https://portal.azure.com/). 
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W obszarze **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
4. W bloku **Rejestracja w systemie Windows** w sekcji **Program wdrażania rozwiązania Windows AutoPilot** wybierz pozycję **Urządzenia**.
5. Wybierz urządzenia, do których chcesz przypisać profil wdrażania. Aby łatwo znaleźć urządzenia bez przypisanego profilu, możesz przefiltrować listę według kolumny **Stan**. 
6. Kliknij pozycję **Przypisz profil**, wybierz profil wdrażania rozwiązania AutoPilot, a następnie kliknij pozycję **Przypisz**. Zostanie wyświetlony komunikat o przypisywaniu w toku.
7. Odśwież widok, aby zobaczyć, że profil został przypisany do urządzeń. Proces może potrwać kilka minut, w zależności od tego, ile urządzeń zostało wybranych. 

> [!Note]
> Nowy profil zostanie przypisany do urządzenia. W przypadku urządzeń już zarejestrowanych w usłudze Intune profil zostaje zastosowany po zresetowaniu i ponownym zarejestrowaniu urządzenia.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Przypisywanie innego profilu wdrażania rozwiązania AutoPilot
Jeśli po przypisaniu do urządzenia profilu wdrażania rozwiązania AutoPilot zdecydujesz, że chcesz do niego przypisać inny profil, przypisz nowy profil do urządzenia.  

## <a name="edit-an-autopilot-deployment-profile"></a>Edytowanie profilu wdrażania rozwiązania AutoPilot 
Po utworzeniu profilu wdrażania rozwiązania AutoPilot możesz edytować niektóre jego części.   
1. Zaloguj się do platformy [Azure](https://portal.azure.com/). 
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W obszarze **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
4. W obszarze **Rejestracja w systemie Windows** w sekcji **Program wdrażania rozwiązania Windows AutoPilot** wybierz pozycję **Profile wdrażania**. 
5. Wybierz profil, który chcesz edytować. 
6. Kliknij pozycję **Właściwości** po lewej stronie, aby zmienić nazwę lub opis profilu wdrażania. Po wprowadzeniu zmian kliknij pozycję **Zapisz**. 
7. Kliknij pozycję **Ustawienia**, aby wprowadzić zmiany do ustawień trybu OOBE. Po wprowadzeniu zmian kliknij pozycję **Zapisz**. 

> [!NOTE]
> Zaktualizowany profil zostanie przypisany do urządzeń. Zaktualizowany profil nie zostanie jednak zastosowany do urządzenia już zarejestrowanego w usłudze Intune, dopóki nie zostanie zresetowane i ponownie zarejestrowane. 

## <a name="using-autopilot-in-other-portals"></a>Używanie rozwiązania AutoPilot w innych portalach
Jeśli nie interesuje Cię zarządzanie urządzeniami przenośnymi, z rozwiązania AutoPilot możesz korzystać na przykład w połączeniu ze Sklepem Microsoft dla Firm. Używanie innych portali jest opcjonalne. My zalecamy, aby do zarządzania wdrożeniami rozwiązania AutoPilot używać samej usługi Intune. Jeśli używasz usługi Intune i innego portalu, usługa Intune nie może:
- Wyświetlać zmian w profilach utworzonych w usłudze Intune, ale edytowanych w innym portalu.
- Synchronizować profilów utworzonych w innym portalu.
- Wyświetlać zmian w przypisaniach profilów wykonanych w innym portalu.
- Synchronizować przypisań profilów wykonanych w innym portalu.
- Wyświetlać zmian wprowadzonych na liście urządzeń w innym portalu

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu rozwiązania Windows AutoPilot dla zarejestrowanych urządzeń z systemem Windows 10 dowiedz się, jak zarządzać tymi urządzeniami. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](https://docs.microsoft.com/intune/device-management)