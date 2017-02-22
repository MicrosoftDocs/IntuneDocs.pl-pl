---
title: "Korzystanie z kategorii urządzeń w usłudze Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: korzystanie z kategorii urządzeń, spośród których mogą wybierać użytkownicy rejestrujący swoje urządzenia w usłudze Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 57dce5b23b9c8cd878a9ce746e6459a69f1270ff


---

# <a name="map-device-groups"></a>Mapowanie grup urządzeń


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Użyj w usłudze Microsoft Intune kategorii urządzenia, aby automatycznie dodawać urządzenia do grup na podstawie zdefiniowanych kategorii, co ułatwi zarządzanie tymi urządzeniami.

Kategorie urządzeń korzystają z następującego przepływu pracy:
1.    Utworzenie kategorii do wyboru dla użytkowników podczas rejestrowania urządzeń
4.    Gdy użytkownik końcowy rejestruje urządzenie, musi wybrać kategorię na liście skonfigurowanych kategorii. Jeśli urządzenie jest już zarejestrowane, użytkownik końcowy zostanie poproszony o wybranie kategorii podczas następnego uzyskiwania dostępu do aplikacji Portal firmy.


Możesz utworzyć dowolne kategorie urządzeń, na przykład:
- Urządzenie w punkcie sprzedaży
- Urządzenie demonstracyjne
- Sprzedaż
- Księgowość
- Manager

## <a name="how-to-configure-device-categories"></a>Sposoby konfigurowania kategorii urządzeń

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Krok 1. Utworzenie kategorii urządzeń w bloku Intune witryny Azure Portal
1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarejestruj urządzenia**.
3. W bloku **Rejestracja** wybierz pozycję **Kategorie urządzeń**.
4. Na stronie **Kategorie urządzeń** wybierz pozycję **Utwórz**, aby dodać nową kategorię.
5. W następnym bloku uzupełnij pola **Nazwa** i (opcjonalnie) **Opis** odnoszące się do nowej kategorii.
6. Po zakończeniu kliknij przycisk **Utwórz**. Utworzona kategoria zostanie wyświetlona na liście kategorii.

Nazwa kategorii urządzeń będzie używana podczas tworzenia grup zabezpieczeń usługi Azure Active Directory w kroku 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Krok 2. Utworzenie grup zabezpieczeń usługi Azure Active Directory
W tym kroku utworzysz grupy dynamiczne w Portalu Azure na podstawie kategorii urządzeń i ich nazw.

Aby kontynuować, zobacz [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) w dokumentacji usługi Azure Active Directory. 

Skorzystaj z informacji podanych w tej sekcji, aby utworzyć grupę urządzeń za pomocą zaawansowanej reguły, używając atrybutu **deviceCategory**. Przykład: (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Gdy skonfigurujesz grupy urządzeń, a użytkownicy zarejestrują urządzenia, zostanie wyświetlona lista skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy zabezpieczeń usługi Active Directory odpowiadającej wybranej kategorii.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Wyświetlanie kategorii zarządzanych urządzeń

1.    W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune witryny Azure Portal wybierz pozycję **Urządzenia i grupy**.

3.    W obszarze **Zarządzaj** kliknij przycisk **Wszystkie urządzenia**.

4.    Na liście urządzeń sprawdź kolumnę **Kategoria**.

Jeśli kolumna **Kategoria** nie jest wyświetlana, kliknij przycisk **Kolumny**, wybierz z listy pozycję **Kategoria**, a następnie kliknij przycisk **Zastosuj**.

### <a name="to-change-the-category-of-a-device"></a>Zmiana kategorii urządzenia

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Urządzenia i grupy**.
4. W bloku **Urządzenia i grupy** wybierz kolejno pozycje **Zarządzaj** > **Wszystkie urządzenia**.
5. Wybierz odpowiednie urządzenie z listy, a następnie w bloku właściwości wybierz opcje **Zarządzaj** > **Właściwości**.
6. W następnym bloku można zmienić **kategorię urządzenia** na inną skonfigurowaną wcześniej kategorię o dowolnej nazwie.



## <a name="further-information"></a>Dodatkowe informacje
- Możesz edytować kategorię urządzenia w witrynie Azure Portal, jeśli jednak to zrobisz, musisz ręcznie zaktualizować wszystkie grupy zabezpieczeń usługi Azure Active Directory odwołujące się do tej kategorii.

- Jeśli usuniesz kategorię, dla wszelkich urządzeń, które zostały do niej przypisane, zostanie wyświetlona nazwa kategorii **Nieprzypisane**.





<!--HONumber=Feb17_HO3-->


