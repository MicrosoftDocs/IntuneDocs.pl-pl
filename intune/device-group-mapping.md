---
title: "Kategoryzowanie urządzeń do grup w usłudze Intune"
titleSuffix: Microsoft Intune
description: "Dowiedz się, jak kategoryzować urządzenia do grup, aby ułatwić zarządzanie."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 416ce4fb671494efabf805595426f25d027d256e
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="categorize-devices-into-groups-for-easier-management"></a>Kategoryzowanie urządzeń do grup w celu ułatwienia zarządzania

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Użyj w usłudze Microsoft Intune kategorii urządzenia, aby automatycznie dodawać urządzenia do grup na podstawie zdefiniowanych kategorii, co ułatwi zarządzanie tymi urządzeniami.

Kategorie urządzeń korzystają z następującego przepływu pracy:
1. Tworzenie kategorii do wyboru dla użytkowników podczas rejestrowania urządzeń
2. Gdy użytkownik końcowy urządzenia z systemem iOS lub Android rejestruje urządzenie, musi wybrać kategorię z listy skonfigurowanych kategorii. Aby przypisać kategorię do urządzenia z systemem Windows, użytkownicy końcowi muszą skorzystać z witryny Portal firmy (aby uzyskać więcej informacji, zobacz sekcję **Po skonfigurowaniu grup urządzeń** w tym artykule).
3. Następnie możesz wdrażać do tych grup zasady i aplikacje.

Możesz utworzyć dowolne kategorie urządzeń, na przykład:
- Urządzenie w punkcie sprzedaży
- Urządzenie demonstracyjne
- Sprzedaż
- Księgowość
- Manager

## <a name="how-to-configure-device-categories"></a>Sposoby konfigurowania kategorii urządzeń

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Krok 1. Utworzenie kategorii urządzeń w bloku Intune witryny Azure Portal
1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W bloku **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
3. W bloku **Rejestrowanie urządzenia** wybierz pozycję **Kategorie urządzeń**.
4. Na stronie **Kategorie urządzeń** wybierz pozycję **Utwórz**, aby dodać nową kategorię.
5. W bloku **Tworzenie kategorii urządzeń** uzupełnij pola **Nazwa** i (opcjonalnie) **Opis** odnoszące się do nowej kategorii.
6. Po zakończeniu kliknij przycisk **Utwórz**. Nowa kategoria będzie widoczna na liście kategorii.

Nazwa kategorii urządzeń będzie używana podczas tworzenia grup zabezpieczeń usługi Azure Active Directory w kroku 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Krok 2. Utworzenie grup zabezpieczeń usługi Azure Active Directory
W tym kroku utworzysz grupy dynamiczne w Portalu Azure na podstawie kategorii urządzeń i ich nazw.

Aby kontynuować, zobacz artykuł [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) w dokumentacji usługi Azure Active Directory.

Skorzystaj z informacji podanych w tej sekcji, aby utworzyć grupę urządzeń za pomocą zaawansowanej reguły, używając atrybutu **deviceCategory**. Przykład: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Gdy skonfigurujesz grupy urządzeń, a użytkownicy zarejestrują urządzenia, zostanie wyświetlona lista skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy zabezpieczeń usługi Active Directory odpowiadającej wybranej kategorii.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Wyświetlanie kategorii zarządzanych urządzeń

1.  W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.

2. W bloku Intune witryny Azure Portal wybierz pozycję **Urządzenia**.

3.  W obszarze **Zarządzaj** kliknij przycisk **Wszystkie urządzenia**.

4.  Na liście urządzeń sprawdź kolumnę **Kategoria urządzenia**.

Jeśli kolumna **Kategoria urządzenia** nie jest wyświetlana, kliknij przycisk **Kolumny**, wybierz z listy pozycję **Kategoria urządzenia**, a następnie kliknij przycisk **Zastosuj**.

### <a name="to-change-the-category-of-a-device"></a>Zmiana kategorii urządzenia

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** w sekcji **Zarządzanie** wybierz pozycję **Wszystkie urządzenia**.
5. Wybierz odpowiednie urządzenie z listy, a następnie w bloku właściwości urządzenia w sekcji **Zarządzaj** wybierz pozycję **Właściwości**.
6. W następnym bloku można zmienić **kategorię urządzenia** na inną skonfigurowaną wcześniej kategorię o dowolnej nazwie.

## <a name="after-you-configure-device-groups"></a>Po skonfigurowaniu grup urządzeń

Gdy użytkownik końcowy urządzenia z systemem iOS lub Android rejestruje urządzenie, musi wybrać kategorię z listy skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy urządzeń usługi Intune lub odpowiadającej wybranej kategorii grupy zabezpieczeń usługi Active Directory.

Użytkownicy końcowi używający systemu Windows powinni wybrać kategorię przy użyciu witryny internetowej Portal firmy.

Bez względu na platformę użytkownicy końcowi mogą po zarejestrowaniu urządzenia skorzystać z witryny internetowej portal.manage.microsoft.com. Użytkownik powinien uzyskać dostęp do witryny internetowej Portal firmy i przejść do obszaru **Moje urządzenia**. Możliwe jest wybranie zarejestrowanego urządzenia wymienionego na stronie, a następnie wybranie kategorii.

Gdy wybierzesz kategorię, urządzenie zostanie automatycznie dodane do odpowiedniej utworzonej grupy. Jeśli urządzenie zostało zarejestrowane przed skonfigurowaniem kategorii, użytkownik końcowy zobaczy powiadomienie dotyczące urządzenia w witrynie internetowej Portal firmy i zostanie poproszony o wybranie kategorii przy następnej próbie uzyskania dostępu do aplikacji Portal firmy dla systemu iOS lub Android.

## <a name="further-information"></a>Dodatkowe informacje
- Możesz edytować kategorię urządzenia w witrynie Azure Portal, ale musisz ręcznie zaktualizować wszystkie grupy zabezpieczeń usługi Azure Active Directory odwołujące się do tej kategorii.

- W przypadku usunięcia kategorii urządzenia do niej przypisane będą wyświetlane z nazwą kategorii **Nieprzypisane**.
