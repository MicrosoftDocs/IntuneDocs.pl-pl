---
title: Pobierz klucz odzyskiwania dla urządzenia macOS z witryny sieci Web Intune — Portal firmy
description: Wyświetl klucz odzyskiwania dla zarejestrowanego, zarządzanego urządzenia macOS.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 1e7831712b4c07d015aa0f587ff6ba6183940897
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75855240"
---
# <a name="get-a-recovery-key-for-a-macos-device"></a>Pobieranie klucza odzyskiwania dla urządzenia macOS

Użyj witryny sieci Web Portal firmy, aby uzyskać klucz odzyskiwania dla zablokowanego urządzenia macOS. Jeśli zapomnisz hasła urządzenia, możesz zalogować się do Portal firmy z innego urządzenia, aby pobrać klucz.  

## <a name="get-recovery-key-from-company-portal-website"></a>Pobierz klucz odzyskiwania z witryny sieci Web Portal firmy

Ta opcja jest dostępna dla urządzeń, które zostały zaszyfrowane przez organizację przy użyciu FileVault. Nie jest ona dostępna dla urządzeń, które zostały zaszyfrowane.

1. Otwórz witrynę internetową Portal firmy, wybierz przycisk [Menu](https://portal.manage.microsoft.com), a następnie wybierz pozycję **Urządzenia**.  
2. Wybierz zaszyfrowane urządzenie macOS.  
3. Wybierz pozycję **Pobierz klucz odzyskiwania**.  

    ![Zrzut ekranu przedstawiający Portal firmy witryny sieci Web z wyróżnioną sekcją Pobierz klucz odzyskiwania.](./media/1907-recovery2-cpweb-intune.PNG)  

4. Zostanie wyświetlony klucz odzyskiwania.

    ![Zrzut ekranu przedstawiający Portal firmy witryny sieci Web, który zawiera klucz odzyskiwania.](./media/1907-recovery-cpweb-intune.PNG)  

    Ze względów bezpieczeństwa klucz będzie znikał po pięciu minutach. Aby ponownie wyświetlić klucz, wybierz pozycję **uzyskać**klucza odzyskiwania.

Jeśli nie odnaleziono klucza, ale urządzenie jest prawidłowo zaszyfrowane, skontaktuj się z pomocą techniczną w Twojej organizacji. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="get-recovery-key-from-company-portal-app-for-ios"></a>Pobierz klucz odzyskiwania z aplikacji Portal firmy dla systemu iOS

Użytkownicy końcowi mogą pobrać osobisty klucz odzyskiwania (klucz FileVault) przy użyciu aplikacji Portal firmy dla systemu iOS. Urządzenie, które ma osobisty klucz odzyskiwania, musi zostać zarejestrowane w usłudze Intune i zaszyfrowane za pomocą usługi FileVault w usłudze Intune. Ta opcja jest niedostępna w przypadku urządzeń, które zostały zaszyfrowane. 

Za pomocą aplikacji Portal firmy można otworzyć widok sieci Web Safari i pobrać osobisty klucz odzyskiwania. 

1. Otwórz aplikację Portal firmy.
2. Kliknij **uzyskać**klucza odzyskiwania.

    ![Zrzut ekranu aplikacji Portal firmy dla systemu iOS, z wyświetlonym kluczem odzyskiwania](./media/get-recovery-key-cpweb-02.png)  

Witryna Portal firmy zostanie otwarta w widoku sieci Web Safari i zostanie wyświetlony klucz. 

## <a name="it-pro-support"></a>Pomoc techniczna dla specjalistów IT

Jeśli jesteś osobą odpowiedzialną za pomoc techniczną i chcesz skonfigurować szyfrowanie FileVault dla urządzeń macOS i zarządzać nimi, zobacz [używanie szyfrowania urządzeń z usługą Intune](/intune/protect/encrypt-devices).

## <a name="next-steps"></a>Następne kroki

Dowiedz się, co jeszcze można zrobić w witrynie sieci Web Portal firmy. Aby zapoznać się z listą akcji, zobacz [za pomocą](using-the-intune-company-portal-website.md) witryny internetowej Intune — Portal firmy.  

Nadal potrzebujesz pomocy? Skontaktuj się z osobą odpowiedzialną za pomoc techniczną. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
