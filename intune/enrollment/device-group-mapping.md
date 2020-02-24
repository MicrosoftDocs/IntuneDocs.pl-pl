---
title: Kategoryzowanie urządzeń na grupy w usłudze Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak kategoryzować urządzenia do grup, aby ułatwić zarządzanie.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0976ff8e6ec45f1f861fd4a4e0474255d701ae4
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414261"
---
# <a name="categorize-devices-into-groups"></a>Kategoryzowanie urządzeń na grupy

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aby ułatwić zarządzanie urządzeniami, użyj kategorii urządzeń usługi Microsoft Intune w celu automatycznego dodawania urządzeń do grup opartych na zdefiniowanych przez Ciebie kategoriach.

Kategorie urządzeń korzystają z następującego przepływu pracy:
1. Tworzenie kategorii do wyboru dla użytkowników podczas rejestrowania urządzeń.
2. Gdy użytkownik urządzenia z systemem iOS/iPadOS lub Android rejestruje urządzenie, musi wybrać kategorię z listy skonfigurowanych kategorii. Aby przypisać kategorię do urządzenia z systemem Windows, użytkownicy muszą użyć witryny Portal firmy.
3. Następnie możesz wdrażać do tych grup zasady i aplikacje.

Możesz utworzyć dowolne kategorie urządzeń. Przykład:
- Urządzenie punktu sprzedaży
- Urządzenie demonstracyjne
- Sprzedaż
- Księgowość
- Manager

## <a name="how-to-configure-device-categories"></a>Sposoby konfigurowania kategorii urządzeń

### <a name="step-1-create-device-categories-on-the-intune-blade-of-the-azure-portal"></a>Krok 1. Utworzenie kategorii urządzeń w bloku Intune witryny Azure Portal
1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), wybierz pozycję **Urządzenia** > **Kategorie urządzeń**.
2. Na stronie **Kategorie urządzeń** wybierz pozycję **Utwórz**, aby dodać nową kategorię.
3. W bloku **Tworzenie kategorii urządzeń** uzupełnij pola **Nazwa** i (opcjonalnie) **Opis** odnoszące się do nowej kategorii.
4. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz**. Nowa kategoria będzie widoczna na liście kategorii.

Nazwa kategorii urządzeń będzie używana podczas tworzenia grup zabezpieczeń usługi Azure Active Directory (Azure AD) w kroku 2.

### <a name="step-2-create-azure-active-directory-security-groups"></a>Krok 2: Utworzenie grup zabezpieczeń usługi Azure Active Directory
W tym kroku utworzysz grupy dynamiczne w witrynie Azure Portal na podstawie kategorii urządzeń i ich nazw.

Aby kontynuować, zobacz [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) w dokumentacji usługi Azure AD.

Skorzystaj z informacji podanych w tej sekcji, aby utworzyć grupę urządzeń za pomocą zaawansowanej reguły, używając atrybutu **deviceCategory**. Na przykład: **device.deviceCategory -eq** "*nazwa kategorii urządzeń uzyskana z witryny Azure Portal*".

Gdy skonfigurujesz grupy urządzeń, a użytkownicy zarejestrują urządzenia, zostanie wyświetlona lista skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy zabezpieczeń usługi Active Directory odpowiadającej wybranej kategorii.

### <a name="view-the-categories-of-devices-that-you-manage"></a>Wyświetlanie kategorii zarządzanych urządzeń

1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) i wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.

2. Na liście urządzeń sprawdź kolumnę **Kategoria urządzenia**.

Jeśli kolumna **Kategoria urządzenia** nie jest wyświetlana, wybierz pozycję **Kolumny** > **Kategoria** > **Zastosuj**.

### <a name="change-the-category-of-a-device"></a>Zmiana kategorii urządzenia

1. Zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości**.
2. W następnym bloku można zmienić **kategorię urządzenia** na inną skonfigurowaną wcześniej kategorię o dowolnej nazwie.

## <a name="after-you-configure-device-groups"></a>Po skonfigurowaniu grup urządzeń

Gdy użytkownik urządzenia z systemem iOS/iPadOS lub Android rejestruje urządzenie, musi wybrać kategorię z listy skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy urządzeń usługi Intune lub odpowiadającej wybranej kategorii grupy zabezpieczeń usługi Active Directory.

Użytkownicy systemu Windows powinni wybrać kategorię przy użyciu witryny internetowej Portal firmy.

Bez względu na platformę użytkownicy mogą po zarejestrowaniu urządzenia skorzystać z witryny internetowej portal.manage.microsoft.com. Użytkownik powinien uzyskać dostęp do witryny internetowej Portal firmy i przejść do obszaru **Moje urządzenia**. Użytkownik może wybrać zarejestrowane urządzenie wymienione na stronie, a następnie wybrać kategorię.

Gdy wybierzesz kategorię, urządzenie zostanie automatycznie dodane do odpowiedniej utworzonej grupy. Jeśli urządzenie zostało już zarejestrowane przed skonfigurowaniem kategorii, użytkownik zobaczy powiadomienie o urządzeniu w witrynie Portal firmy. Dzięki temu użytkownik wie, że musi wybrać kategorię podczas kolejnego dostępu do aplikacji Portal firmy w systemie iOS/iPadOS lub Android.

## <a name="further-information"></a>Dodatkowe informacje
- Kategorię urządzenia możesz edytować w witrynie Azure Portal, ale musisz ręcznie zaktualizować wszystkie grupy zabezpieczeń usługi Azure AD odwołujące się do tej kategorii.

- W przypadku usunięcia kategorii urządzenia do niej przypisane będą wyświetlane z nazwą kategorii **Nieprzypisane**.
