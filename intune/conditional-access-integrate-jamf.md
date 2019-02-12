---
title: Integrowanie narzędzia Jamf Pro z usługą Microsoft Intune w celu zachowania zgodności | Microsoft Intune
description: Stosuj zasady zgodności usługi Microsoft Intune z dostępem warunkowym usługi Azure Active Directory, aby pomóc zabezpieczać urządzenia zarządzane przez narzędzie Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2fe73c0dab855f43daf71e9564f17490fa6366
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846999"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrowanie narzędzia Jamf Pro z usługą Intune w celu zachowania zgodności

Dotyczy: Usługa Intune w witrynie Azure Portal

Jeśli do zarządzania użytkownikami końcowymi komputerów Mac Twoja organizacja używa narzędzia [Jamf Pro](https://www.jamf.com), zastosowanie zasad zgodności usługi Microsoft Intune i dostępu warunkowego usługi Azure Active Directory zapewnia, że urządzenia w organizacji będą zgodne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować dostęp warunkowy przy użyciu narzędzia Jamf Pro, wymagane są następujące elementy:

- Program Jamf Pro 10.1.0 lub nowsza wersja
- [Aplikacja Portal firmy dla systemu macOS](https://aka.ms/macoscompanyportal)
- Urządzenia z systemem macOS (OS X 10.11 Yosemite lub nowszy)

## <a name="connecting-intune-to-jamf-pro"></a>Połączenie usługi Intune z narzędziem Jamf Pro

Aby połączyć usługę Intune z narzędziem Jamf Pro:

1. Utworzenie nowej aplikacji na platformie Azure
2. Włączanie możliwości integracji usługi Intune z narzędziem Jamf Pro
3. Skonfigurowanie dostępu warunkowego w narzędziu Jamf Pro

## <a name="create-an-application-in-azure-active-directory"></a>Utworzenie aplikacji w usłudze Azure Active Directory

1. W witrynie [Azure Portal](https://portal.azure.com) przejdź kolejno do pozycji **Azure Active Directory** > **Rejestracje aplikacji**.
2. Wybierz przycisk **+Rejestrowanie nowej aplikacji**.
3. Wprowadź **nazwę wyświetlaną**, np. **Dostęp warunkowy Jamf**.
4. Wybierz opcję **Interfejs API/aplikacja internetowa**.
5. Określ **Adres URL logowania** przy użyciu adresu URL wystąpienia narzędzia Jamf Pro.
6. Wybierz przycisk **Utwórz**. Aplikacja zostanie utworzona, a w portalu zostaną wyświetlone szczegóły aplikacji.
7. Zapisz kopię **identyfikatora aplikacji** dla nowej aplikacji. W dalszej części procedury należy podać ten identyfikator. Następnie wybierz pozycję **Ustawienia** i przejdź do pozycji **Dostęp do interfejsu API** > **Klucze**.
8. W okienku *Klucze* wprowadź **Opis**, czas oczekiwania przed **wygaśnięciem**, a następnie wybierz pozycję **Zapisz**, aby wygenerować klucz aplikacji (wartość).

   > [!IMPORTANT]
   > W trakcie tego procesu klucz aplikacji jest wyświetlany tylko raz. Pamiętaj, aby zapisać go w innym miejscu, z którego łatwo można go będzie pobrać.

8. W okienku *Ustawienia* aplikacji przejdź do pozycji **Dostęp do interfejsu API** > **Wymagane uprawnienia**. Zaznacz wszelkie istniejące uprawnienia, a następnie kliknij przycisk **Usuń**, aby usunąć wszystkie uprawnienia. Usunięcie istniejących uprawnień jest konieczne, ponieważ dodajesz nowe uprawnienie, a aplikacja działa wyłącznie wówczas, gdy ma tylko jedno wymagane uprawnienie.  
9. Aby przypisać nowe uprawnienie, wybierz polecenie **+ Dodaj** > **Wybierz interfejs API** > **Interfejs API usługi Microsoft Intune**, a następnie kliknij przycisk **Wybierz**.
10. W okienku *Włącz dostęp* wybierz polecenie **Wyślij atrybuty urządzenia do usługi Microsoft Intune**, a następnie kliknij kolejno opcje **Wybierz** i **Gotowe**.
11. W okienku *Wymagane uprawnienia* wybierz opcję **Udziel uprawnień**, a następnie wybierz opcję **Tak**, aby zastosować wymagane uprawnienia do aplikacji.

    > [!NOTE]
    > Jeśli klucz aplikacji wygaśnie, należy utworzyć nowy klucz aplikacji na platformie Microsoft Azure, a następnie zaktualizować dane dostępu warunkowego w narzędziu Jamf Pro. Aby uniknąć zakłóceń w świadczeniu usług, platforma Azure umożliwia stosowanie zarówno starego, jak i nowego klucza.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Włączanie możliwości integracji usługi Intune z narzędziem Jamf Pro

1. W witrynie [Azure Portal](https://portal.azure.com) przejdź do pozycji **Microsoft Intune** > **Zgodność urządzeń** > **Zarządzanie urządzeniami partnerskimi**.
2. Włącz Łącznik zgodności dla narzędzia Jamf poprzez wklejenie identyfikatora aplikacji zapisanego we wcześniejszej części procedury w polu **Identyfikator aplikacji usługi Azure Active Directory w oprogramowaniu Jamf**.
3. Wybierz pozycję **Zapisz**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurowanie integracji z usługą Microsoft Intune w narzędziu Jamf Pro

1. W narzędziu Jamf Pro przejdź do opcji **Globalne zarządzanie** > **Dostęp warunkowy**. Kliknij przycisk **Edytuj** znajdujący się na karcie **Integracja z usługą Microsoft Intune**.
2. Zaznacz pole wyboru dla opcji **Włącz integrację z usługą Microsoft Intune**.
3. Podaj wymagane informacje o dzierżawie platformy Azure, w tym zapisane w poprzednich krokach wartości pól **Lokalizacja**, **Nazwa domeny**, **Identyfikator aplikacji** i **Klucz aplikacji**.
4. Wybierz pozycję **Zapisz**. Narzędzie Jamf Pro sprawdza ustawienia i weryfikuje poprawność konfiguracji.

## <a name="set-up-compliance-policies-and-register-devices"></a>Konfigurowanie zasad zgodności i rejestrowanie urządzeń

Po skonfigurowaniu integracji między usługą Intune i narzędziem Jamf musisz [zastosować zasady zgodności do urządzeń zarządzanych za pomocą narzędzia Jamf](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Następne kroki

- [Stosowanie zasad zgodności do urządzeń zarządzanych za pomocą narzędzia Jamf](conditional-access-assign-jamf.md)
- [Dane wysyłane do usługi Intune przez narzędzie Jamf](data-jamf-sends-to-intune.md)
