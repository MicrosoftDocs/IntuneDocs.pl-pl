---
title: "Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń | Microsoft Docs"
titlesuffix: Azure portal
description: "Dowiedz się, jak używać zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c2266e460d816dfdd908d6a68944c8c2cc5c0afc
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zasad konfiguracji aplikacji można używać z zarządzanymi aplikacjami, które obsługują zestaw SDK aplikacji usługi Intune, nawet na niezarejestrowanych urządzeniach. 

1. Zaloguj się do witryny Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** + **Intune**.
3. Wybierz obciążenie **Aplikacje mobilne**.
4. Wybierz pozycję **Zasady konfiguracji aplikacji** w grupie **Zarządzaj**, a następnie wybierz przycisk **Dodaj**.
5. Ustaw następujące szczegóły:
    - **Nazwa**  
      — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**  
      — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**  
      Wybierz pozycję **Zarządzaj aplikacjami**.
6. Wybierz pozycję **Skojarzona aplikacja**, aby wybrać aplikację, którą chcesz skonfigurować. Wybierz aplikację z listy aplikacji zatwierdzonych i zsynchronizowanych z usługą Intune.
7. Dla każdego ustawienia konfiguracji obsługiwanego przez aplikację wpisz wartości w polach **Nazwa** i **Wartość**, a następnie wybierz przycisk wielokropka (**...**).  
    Aby usunąć konfigurację, wybierz przycisk wielokropka (**...**) i wybierz pozycję **Usuń**.  
    Aplikacje współdziałające z zestawem SDK aplikacji usługi Intune obsługują konfiguracje oparte na parach klucz-wartość. Dodatkowe informacje na temat obsługiwanych konfiguracji klucz-wartość można znaleźć w dokumentacji dotyczącej poszczególnych aplikacji.  
    Ponadto można użyć tokenów dynamicznie wypełnianych danymi wygenerowanymi przez aplikację.

## <a name="configuration-values-for-using-tokens"></a>Wartości konfiguracji na potrzeby używania tokenów

Usługa Intune może generować pewne tokeny i wysyłać je do aplikacji zarządzanej. Na przykład jeśli konfiguracja aplikacji obejmuje użycie ustawienia poczty e-mail, można dynamicznie dodać wiadomość e-mail przy użyciu tokenu. Wpisz nazwę oczekiwaną przez aplikację w polu **Nazwa**, a następnie wpisz `\{\{mail\}\}` w polu **Wartość**.

Usługa Intune obsługuje następujące typy tokenów w ustawieniach konfiguracji:

- \{\{userprincipalname\}\}—na przykład **John@contoso.com**
- \{\{mail\}\}—na przykład **John@contoso.com**
- \{\{partialupn\}\}—na przykład **Jan**
- \{\{accountid\}\}—na przykład **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{userid\}\}—na przykład **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—na przykład **Jan Nowak**
- \{\{PrimarySMTPAddress\}\}—na przykład **testuser@ad.domain.com** 


> [!Note]  
> Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji tak jak dotychczas.