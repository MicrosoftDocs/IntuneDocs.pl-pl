---
title: Ustawienia kiosku dla systemu Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Konfigurowanie kiosków z systemem Android jako kiosków z jedną aplikacją i z wieloma aplikacjami.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9158893b3ae2c2f70b08682a61cbba4d55b43710
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909154"
---
# <a name="kiosk-settings-for-android-devices-in-intune"></a>Ustawienia kiosku dla urządzeń z systemem Android w usłudze Intune

Urządzenie można skonfigurować w trybie kiosku z jedną lub wieloma aplikacjami przy użyciu ustawień konfiguracji urządzenia. Gdy urządzenie jest w trybie kiosku, użycie urządzenia jest ograniczone do aplikacji lub linków internetowych zdefiniowanych przez profil ograniczeń. 

## <a name="restrict-an-android-kiosk-device-to-a-single-app"></a>Ograniczanie kiosku z systemem Android do pojedynczej aplikacji

Jeśli profil ograniczeń urządzenia kiosku jest ustawiony na **Tryb kiosku** = **kiosk z pojedynczą aplikacją**, użytkownicy mogą uzyskać dostęp tylko do jednej aplikacji. Podczas uruchamiania urządzenia skonfigurowanego w tym trybie jest uruchamiana konkretna aplikacja. Użytkownicy nie mogą otwierać nowych aplikacji ani zmieniać uruchomionej aplikacji.

1. Upewnij się, że aplikacja, która ma być używana na urządzeniu kiosku została [wdrożona na urządzeniu](apps-deploy.md) i przypisana do grupy urządzeń utworzonej dla kiosków.
2. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. W bloku **Tworzenie profilu** skonfiguruj następujące pola:
     - **Nazwa**
     - **Platforma**: Android enterprise
     - **Typ profilu**: Tylko właściciel urządzenia > Ograniczenia dotyczące urządzeń
4. Wybierz pozycję **Ustawienia** > **Kiosk**.
5. W polu **Tryb kiosku** wybierz **Kiosk z pojedynczą aplikacją**.
6. Wybierz pozycję **Wybierz zarządzaną aplikację**, a następnie wybierz zarządzaną aplikację ze sklepu Google Play, która ma być jedyną aplikacją dostępną dla urządzeń używających tego profilu.
7. Wybierz przyciski **OK** > **OK** > **OK** > **Utwórz**.
8. Wybierz utworzony profil, a następnie pozycję **Przypisania**.
9. W obszarze **Przypisz do** wybierz pozycję **Wybrane grupy**.
10. Wybierz pozycję **Wybierz grupy do uwzględnienia**, wybierz grupę urządzeń utworzoną dla urządzeń kiosków, a następnie opcję **Wybierz**.

## <a name="restrict-a-kiosk-device-to-a-set-of-apps-or-web-links"></a>Ograniczanie kiosku do zestawu aplikacji lub linków internetowych

Jeśli profil ograniczeń urządzenia kiosku jest ustawiony na **Tryb kiosku** = **Kiosk z wieloma aplikacjami**, użytkownicy mogą uzyskiwać dostęp tylko do ograniczonego zestawu aplikacji, który można skonfigurować. Możesz również zdefiniować zestaw linków internetowych, które użytkownicy mogą odwiedzać. Po zastosowaniu zasad użytkownicy widzą ikony dozwolonych aplikacji na ekranie głównym.

Aby ustawić kiosk z systemem Android dla wielu aplikacji, wykonaj następujące główne kroki:

1. [Importowanie i wdrażanie aplikacji Managed Home Screen z zarządzanego sklepu Google Play](#import-and -deploy-the-managed-home-screen-app)
2. [Dodawanie i przypisywanie aplikacji, które mogą być używane w trybie kiosku](#add-and-assign-apps-that-can-be-used-in-kiosk-mode)
3. (Opcjonalnie) [Dodawanie linków internetowych, które mogą być używane w trybie kiosku](#add-web-links-that-can-be-used-in-kiosk-mode)

### <a name="import-and-deply-the-managed-home-screen-app"></a>Importowanie i wdrażanie aplikacji Managed Home Screen

1. Przejdź do [strony Managed Home Screen w sklepie Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) i zaloguj się przy użyciu konta, które jest używane dla innych aplikacji zarządzanych ze sklepu Google Play.
2. Wybierz pozycję **Zatwierdź**.
3. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Aplikacje mobilne** > **Zarządzany sklep Google Play** > **Synchronizuj**.
4. Wybierz pozycję **Aplikacje** > **Managed Home Screen** > **Przypisania** > **Dodaj grupę**.
5. W obszarze **Typ przypisania** wybierz pozycję **Wymagane**.
6. Wybierz pozycję **Dołączone grupy** > **Wybierz grupy do uwzględnienia** > wybierz grupę urządzeń utworzoną dla urządzeń kiosków > **Wybierz** > **OK** > **OK** > **Zapisz**.

### <a name="add-and-assign-apps-that-can-be-used-in-kiosk-mode"></a>Dodawanie i przypisywanie aplikacji, które mogą być używane w trybie kiosku

Dla każdej aplikacji, która ma być dostępna na urządzeniach kiosku, wykonaj następujące kroki:

1. [Dodaj aplikację do usługi Intune](store-apps-android.md).
2. Wybierz pozycję **Aplikacje mobilne** > **Aplikacje** > wybierz aplikację > **Przypisania** > **Dodaj grupę**.
3. W obszarze **Typ przypisania** wybierz pozycję **Wymagane**.
4. Wybierz pozycję **Dołączone grupy** > **Wybierz grupy do uwzględnienia** > wybierz grupę urządzeń utworzoną dla urządzeń kiosków > **Wybierz** > **OK** > **OK** > **Zapisz**.

### <a name="add-web-links-that-can-be-used-in-kiosk-mode"></a>Dodawanie linków internetowych, które mogą być używane w trybie kiosku

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Aplikacje mobilne** > **Aplikacje** > **Dodaj**.
2. W obszarze **Typ aplikacji** wybierz pozycję **Link internetowy**.
3. Wybierz pozycję **Konfiguruj** i podaj wymagane informacje. Nie trzeba dodawać obrazu logo, ponieważ zostanie on automatycznie pobrany z obrazu favicon.ico witryny internetowej.
4. Wybierz przycisk **OK** > **Dodaj**.

Upewnij się, że aplikacja przeglądarki internetowej została wdrożona na urządzeniach kiosku przy użyciu usługi [Mobile Apps](apps-add.md).

### <a name="create-a-multi-app-kiosk-profile"></a>Tworzenie profilu kiosku z wieloma aplikacjami

1. Przejdź do [portalu usługi Intune](https://portal.azure.com) i wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. W bloku **Tworzenie profilu** skonfiguruj następujące pola:
     - **Nazwa**: wpisz intuicyjną nazwę
     - **Platforma**: Android enterprise
     - **Typ profilu**: Tylko właściciel urządzenia > Ograniczenia dotyczące urządzeń
4. Wybierz pozycję **Ustawienia** > **Kiosk**.
5. W polu **Tryb kiosku** wybierz pozycję **Kiosk z wieloma aplikacjami**.
6. Wybierz pozycję **Dodaj**, a następnie wybierz aplikacje lub linki internetowe, które mają być dostępne dla urządzeń używających tego profilu.
7. Wybierz przyciski **OK** > **OK** > **OK** > **Utwórz**.
8. Wybierz utworzony profil, a następnie pozycję **Przypisania**.
9. W obszarze **Przypisz do** wybierz pozycję **Wybrane grupy**.
10. Wybierz pozycję **Wybierz grupy do uwzględnienia**, wybierz grupę urządzeń utworzoną dla urządzeń kiosków, a następnie opcję **Wybierz** > **Zapisz**.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
