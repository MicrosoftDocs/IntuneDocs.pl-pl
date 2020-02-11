---
title: Zasady konfiguracji zarządzanych aplikacji bez rejestracji urządzeń
titleSuffix: Microsoft Intune
description: Dowiedz się, jak konfigurować zasady dla zarządzanych aplikacji bez rejestracji urządzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 06c1119b474d82c4d00db3276179b962ff5b5a44
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755565"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Zasad konfiguracji aplikacji można używać z zarządzanymi aplikacjami, które obsługują zestaw SDK aplikacji usługi Intune, nawet na niezarejestrowanych urządzeniach. 

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Zasady konfiguracji aplikacji** > **Dodaj** > **Aplikacje zarządzane**.
3. Na stronie **podstawowych informacji** ustaw następujące szczegóły:
    - **Nazwa**: — nazwa profilu, która będzie wyświetlana w witrynie Azure Portal
    - **Opis**: — opis profilu, który będzie wyświetlany w witrynie Azure Portal
    - **Typ rejestracji urządzenia**: — wybrano aplikacje zarządzane.
4. Wybierz opcję **Wybierz aplikacje publiczne** lub **Wybierz aplikacje niestandardowe**, aby wybrać aplikację, którą chcesz skonfigurować. Wybierz aplikację z listy aplikacji zatwierdzonych i zsynchronizowanych z usługą Intune.
5. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Ustawienia**.
6. Dla każdego ustawienia konfiguracji obsługiwanego przez aplikację wpisz wartości w polach **Nazwa** i **Wartość**. 

   Aplikacje współdziałające z zestawem SDK aplikacji usługi Intune obsługują konfiguracje oparte na parach klucz-wartość. Dodatkowe informacje na temat obsługiwanych konfiguracji klucz-wartość można znaleźć w dokumentacji dotyczącej poszczególnych aplikacji. Należy pamiętać, że można użyć tokenów dynamicznie wypełnianych danymi wygenerowanymi przez aplikację. Aby uzyskać więcej informacji, zobacz sekcję [Wartości konfiguracji na potrzeby używania tokenów](~/apps/app-configuration-policies-managed-app.md#configuration-values-for-using-tokens). Aby uzyskać informacje o programie Outlook dotyczące ustawień zasad konfiguracji aplikacji dla systemu iOS, zobacz temat [Manage Outlook for iOS app configuration with Microsoft Intune](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx) (Zarządzanie programem Outlook w celu konfiguracji aplikacji dla systemu iOS w usłudze Microsoft Intune).

    Aby usunąć konfigurację, wybierz przycisk wielokropka ( **...** ) i wybierz pozycję **Usuń**.  

7. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.
8. Kliknij pozycję **Wybierz grupy do uwzględnienia**.
9. Wybierz grupę w okienku **Wybierz grupy do uwzględnienia** i kliknij pozycję **Wybierz**.
10. Kliknij pozycję **Wybierz grupy do wykluczenia**, aby wyświetlić powiązane okienko.
11. Wybierz grupy, które chcesz wykluczyć, a następnie kliknij pozycję **Wybierz**.

    >[!NOTE]
    >Jeśli podczas dodawania grupy jakakolwiek inna grupa została już dołączona do danego typu przypisania, zostanie ona wstępnie wybrana i nie będzie zmieniana dla innych typów dołączania przypisania. W związku z tym ta grupa, który została użyta, nie może zostać użyta jako wykluczona grupa.

12. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**.
13. Kliknij pozycję **Utwórz**, aby dodać zasady konfiguracji do usługi Intune.

## <a name="configuration-values-for-using-tokens"></a>Wartości konfiguracji na potrzeby używania tokenów

Usługa Intune może generować pewne tokeny i wysyłać je do aplikacji zarządzanej. Na przykład jeśli konfiguracja aplikacji obejmuje użycie ustawienia poczty e-mail, można dynamicznie dodać wiadomość e-mail przy użyciu tokenu. Wpisz nazwę oczekiwaną przez aplikację w polu **Nazwa**, a następnie wpisz `\{\{mail\}\}` w polu **Wartość**.

Usługa Intune obsługuje następujące typy tokenów w ustawieniach konfiguracji. Inne niestandardowe pary klucz/wartość nie są obsługiwane.

- \{\{userprincipalname\}\} — na przykład John@contoso.com
- \{\{mail\}\} — na przykład John@contoso.com
- \{\{partialupn\}\} — na przykład Jan
- \{\{accountid\}\} — na przykład fc0dc142-71d8-4b12-bbea-bae2a8514c81
- \{\{userid\}\} — na przykład 3ec2c00f-b125-4519-acf0-302ac3761822
- \{\{username\}\} — na przykład Jan Nowak
- \{\{PrimarySMTPAddress\}\} — na przykład testuser@ad.domain.com

> [!Note]  
> Znaki \{\{ i \}\} są używane tylko przez typy tokenów i nie mogą być używane do innych celów.

## <a name="next-steps"></a>Następne kroki

Kontynuuj [przypisywanie](apps-deploy.md) i [monitorowanie](apps-monitor.md) aplikacji tak jak dotychczas.
