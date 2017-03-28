---
title: "Rejestrowanie urządzeń z systemem Windows"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: włączanie zarządzania urządzeniami przenośnymi (MDM) dla urządzeń z systemem Windows w usłudze Intune."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 03/21/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 609656c2831c09c67e911c8150d31f38faad020b
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-windows-devices"></a>Rejestrowanie urządzeń z systemem Windows

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Skorzystaj z jednej z następujących metod konfigurowania usługi rejestracji urządzeń z systemem Windows:

- [**Automatyczna rejestracja w systemie Windows 10 i Windows 10 Mobile przy użyciu usługi Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Metoda ta ma zastosowanie tylko w przypadku urządzeń z systemem Windows 10 lub Windows 10 Mobile.
 -  Użycie tej metody wymaga usługi Azure Active Directory Premium. Jeśli nie masz tej usługi, skorzystaj z metody rejestracji dla systemów Windows 8.1 i Windows Phone 8.1.
 -  Jeśli nie wybrano włączenia automatycznego rejestrowania, należy użyć metody rejestracji dla systemów Windows 8.1 i Windows Phone 8.1.

- [**Rejestracja bez automatycznego rejestrowania w usłudze Azure AD Premium**](#enable-windows-enrollment-without-azure-ad-premium)
 - Ta metoda służy do rejestrowania urządzeń z systemem Windows 8.1 lub Windows Phone 8.1.
 - Jeśli nie chcesz używać usługi Azure Active Directory (AD) Premium, możesz użyć tej metody dla urządzeń z systemem Windows 8.1 i nowszym.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Włączanie rejestrowania dla systemu Windows bez usługi Azure AD Premium

Można umożliwić użytkownikom instalowanie i rejestrowanie urządzeń bez automatycznego rejestrowania w usłudze Azure AD Premium. Utworzenie rekordów zasobów CNAME systemu DNS umożliwia użytkownikom łączenie się i rejestrowanie w usłudze Intune bez podawania nazwy serwera.

1. **Tworzenie rekordów CNAME** (opcjonalnie)<br>
 Utworzyć rekordy zasobów **CNAME** systemu DNS dla domeny Twojej firmy. Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny enterpriseenrollment-s.manage.microsoft.com.

    Chociaż tworzenie wpisów DNS rekordów CNAME jest opcjonalne, rekordy CNAME ułatwiają użytkownikom rejestrację. Jeśli rekord CNAME nie zostanie znaleziony, użytkownicy są proszeni o ręczne wprowadzenie nazwy serwera MDM: enrollment.manage.microsoft.com.

    Jeśli zweryfikowano więcej niż jedną domenę, należy utworzyć rekord CNAME dla każdej z nich. Rekordy zasobów CNAME muszą zawierać następujące informacje:

    Rekordy zasobów CNAME muszą zawierać następujące informacje:

  |TYPE|Nazwa hosta|Przekierowanie na|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.domena_firmowa.com|EnterpriseEnrollment-s.manage.microsoft.com |1 godzina|
  |CNAME|EnterpriseRegistration.domena_firmowa.com|EnterpriseRegistration.windows.net|1 godzina|

  `EnterpriseEnrollment-s.manage.microsoft.com` — obsługuje przekierowanie do usługi Intune z rozpoznawaniem domeny na podstawie nazwy domeny adresu e-mail

  Jeśli firma używa wielu domen dla poświadczeń użytkowników, należy utworzyć rekordy CNAME dla każdej domeny.

  Jeśli na przykład witryna internetowa firmy to contoso.com, w systemie DNS należy utworzyć rekord CNAME, który przekierowuje domenę EnterpriseEnrollment.contoso.com do domeny EnterpriseEnrollment-s.manage.microsoft.com. Propagowanie zmian rekordów DNS może potrwać do 72 godzin. Nie można zweryfikować zmiany w systemie DNS w usłudze Intune, dopóki trwa propagowanie rekordu DNS.

2.  **Weryfikowanie rekordu CNAME**<br>W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz kolejno opcje **Zarejestruj urządzenia** > **Rejestracja Windows**. W polu **Podaj nazwę zweryfikowanej domeny** wpisz adres URL zweryfikowanej domeny witryny sieci Web firmy, a następnie wybierz pozycję **Przetestuj automatyczne wykrywanie**.

3.  **Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia i czego mogą oczekiwać po włączeniu ich do zarządzania.**

    Instrukcje dotyczące rejestrowania przez użytkownika końcowego można znaleźć w temacie [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Możesz również odesłać użytkowników do artykułu [What can my IT admin see on my device](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) (Co widzi administrator IT na moim urządzeniu).

    Aby uzyskać więcej informacji o zadaniach użytkowników końcowych, zobacz [Zasoby dotyczące środowiska użytkownika końcowego w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

Nie są wymagane żadne dodatkowe czynności, chyba że nastąpi wdrożenie aplikacji Portal firmy na urządzeniach.  Kroki 2 i 3 w konsoli administracyjnej można bezpiecznie zignorować.

