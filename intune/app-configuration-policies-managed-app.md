---
title: "Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń | Microsoft Docs"
titlesuffix: Azure portal
description: "Dowiedz się, jak używać zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasad konfiguracji aplikacji można używać z zarządzanymi aplikacjami, które obsługują zestaw SDK aplikacji usługi Intune, nawet na niezarejestrowanych urządzeniach. 

1. Zaloguj się do witryny Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** + **Intune**.
3. Wybierz obciążenie **Aplikacje mobilne**.
4. Kliknij pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie kliknij przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa**  
      — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**  
      — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**  
      Wybierz pozycję **Zarządzaj aplikacjami**.
6. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, którą chcesz skonfigurować. Wybierz aplikację z listy aplikacji zatwierdzonych i zsynchronizowanych z usługą Intune.
7. Dla każdego ustawienia konfiguracji obsługiwanego przez aplikację wpisz wartości w polach **Nazwa** i **Wartość**, a następnie kliknij przycisk wielokropka (**...**).  
    Aby usunąć konfigurację, kliknij przycisk wielokropka (**...**) i wybierz pozycję **Usuń**.  
    Aplikacje współdziałające z zestawem SDK aplikacji usługi Intune obsługują konfiguracje oparte na parach klucz-wartość. Dodatkowe informacje na temat obsługiwanych konfiguracji klucz-wartość można znaleźć w dokumentacji dotyczącej poszczególnych aplikacji.  
    Ponadto można użyć tokenów dynamicznie wypełnianych danymi wygenerowanymi przez aplikację.

## <a name="configuration-values-using-tokens"></a>Konfigurowanie wartości przy użyciu tokenów

Usługa Intune może generować niektóre tokeny i je wysyłać do zarządzanej aplikacji. Na przykład jeśli konfiguracja aplikacji obejmuje użycie ustawienia poczty e-mail, można dynamicznie dodać wiadomość e-mail przy użyciu tokenu. Wpisz nazwę oczekiwaną przez aplikację w polu **Nazwa**, a następnie wpisz `\{\{mail\}\}` w polu **Wartość**.

Usługa Intune obsługuje następujące typy tokenów w ustawieniach konfiguracji:

- \{\{userprincipalname\}\} — (przykład: **John@contoso.com**)
- \{\{mail\}\} — (przykład: **John@contoso.com**)
- \{\{partialupn\}\} — (przykład: **Michał**)
- \{\{accountid\}\} -—(przykład: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} — (przykład: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} — (przykład: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} — (przykład: **Michał Kowalski**)
- \{\{PrimarySMTPAddress\}\} — (przykład: testuser@ad.domain.com) 


> [!Note]  
> Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji tak jak dotychczas.