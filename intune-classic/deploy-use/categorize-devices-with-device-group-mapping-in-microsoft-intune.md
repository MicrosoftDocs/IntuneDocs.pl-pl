---
title: "Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń | Microsoft Docs"
description: "Użyj funkcji mapowania grup urządzeń w usłudze Microsoft Intune do grupowania urządzeń w zdefiniowane kategorie, co ułatwi zarządzanie tymi urządzeniami."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 618827ed6baf7a9dec6aef804f19bcbca08ed39f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Użyj funkcji **mapowania grup urządzeń** w usłudze Microsoft Intune, aby automatycznie dodać urządzenia do grup na podstawie zdefiniowanych kategorii, co ułatwi zarządzanie tymi urządzeniami. 

Podczas mapowania grup urządzeń jest używany następujący przepływ pracy:
1. Utworzenie kategorii do wyboru dla użytkowników podczas rejestrowania urządzeń
2. Tworzysz grupy lub korzystasz z istniejących grup dla każdej kategorii, której chcesz używać. W zależności od używanej wersji usługi Intune będą to grupy usługi Intune lub grupy zabezpieczeń usługi Azure Active Directory.
2. Konfigurujesz reguły mapujące wybraną kategorię na utworzoną grupę urządzeń.
3. Gdy użytkownik końcowy rejestruje urządzenie, musi wybrać kategorię na liście skonfigurowanych kategorii. Po dokonaniu wyboru urządzenie zostaje automatycznie dodane do odpowiedniej utworzonej grupy. Jeśli urządzenie jest już zarejestrowane, użytkownik końcowy zostanie poproszony o wybranie kategorii podczas następnego uzyskiwania dostępu do aplikacji Portal firmy.
4. Następnie możesz wdrażać do tych grup zasady i aplikacje.

Możesz utworzyć dowolne kategorie urządzeń, na przykład:
* Urządzenie w punkcie sprzedaży
* Urządzenie demonstracyjne
* Sprzedaż
* Księgowość
* Menedżer

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Istotne informacje dotyczące zmiany wprowadzonej w zarządzaniu grupami w usłudze Intune

Na podstawie Waszych opinii zdecydowaliśmy rozpocząć proces unifikacji środowiska grupowania i określania elementów docelowych w pakiecie Enterprise Mobility + Security. Z tej przyczyny wkrótce przeprowadzimy konwertowanie grup usługi Intune na grupy zabezpieczeń oparte na usłudze Azure Active Directory. Po tej zmianie nie będzie można tworzyć grup za pomocą usługi Intune. Zamiast tego będzie można je tworzyć w Portalu Azure. Ta zmiana zostanie przeprowadzona stopniowo. Szczegółowe informacje dotyczące tej zmiany oraz jej harmonogramu podano w [tym temacie](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>Której procedury z tego tematu należy użyć w celu skonfigurowania mapowania grup urządzeń?

W związku z etapową implementacją grup zabezpieczeń opartych na usłudze Azure Active Directory musisz otworzyć obszar roboczy **Grupy** w [konsoli administratora usługi Intune](https://manage.microsoft.com), aby ustalić, której procedury należy użyć:

-  Jeśli widzisz link do Portalu Azure, już nie korzystasz z grup usługi Intune. Postępuj zgodnie z poniższą procedurą [Jak skonfigurować mapowanie grup urządzeń dla grup usługi Azure Active Directory](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups).
-  Jeśli nie widzisz linku do Portalu Azure, nadal korzystasz z grup usługi Intune. Postępuj zgodnie z poniższą procedurą [Jak skonfigurować mapowanie grup urządzeń dla grup usługi Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups).

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Jak skonfigurować mapowanie grup urządzeń dla grup usługi Intune
1. Dla każdej kategorii urządzeń, której chcesz używać, utwórz grupę urządzeń usługi Intune lub zidentyfikuj istniejącą grupę. Aby uzyskać więcej informacji na temat tworzenia grup, zobacz [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja**.
3. W obszarze roboczym **Administracja** rozwiń węzeł **Zarządzanie urządzeniami przenośnymi**, a następnie wybierz pozycję **Mapowanie grup urządzeń**.
4. Na stronie **Mapowanie grup urządzeń** włącz mapowanie grup urządzeń.
5. Wybierz pozycję **Dodaj**, aby utworzyć nową regułę mapowania.
6. W oknie dialogowym **Dodawanie reguły mapowania grup urządzeń** wprowadź nazwę kategorii, którą chcesz utworzyć, a następnie wybierz z listy rozwijanej kolekcję urządzeń, na którą chcesz zamapować tę kategorię. Po zakończeniu wybierz pozycję **Dodaj**.
7. Po zakończeniu dodawania kategorii i grup wybierz pozycję **Zapisz**.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Jak skonfigurować mapowanie grup urządzeń dla grup usługi Azure Active Directory

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>Krok 1. Utworzenie kategorii urządzeń w konsoli administratora usługi Intune
1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Administracja**.
3. W obszarze roboczym **Administracja** rozwiń węzeł **Zarządzanie urządzeniami przenośnymi**, a następnie wybierz pozycję **Kategorie urządzeń**.
4. Na stronie **Kategorie urządzeń** zostanie wyświetlona lista, na której możesz skonfigurować kategorie urządzeń: 
- Możesz wprowadzić nazwę, a następnie kliknąć przycisk **Dodaj**, aby dodać ją jako nową kategorię urządzeń.
- Ponadto możesz wybrać kategorię, a następnie ją usunąć, klikając przycisk **Usuń**.

Nazwa kategorii urządzeń będzie używana podczas tworzenia grup zabezpieczeń usługi Azure Active Directory w kroku 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Krok 2. Utworzenie grup zabezpieczeń usługi Azure Active Directory

W tym kroku utworzysz grupy dynamiczne w Portalu Azure na podstawie kategorii urządzeń i ich nazw.

Aby kontynuować, zobacz [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) w dokumentacji usługi Azure Active Directory.
Skorzystaj z informacji podanych w tym temacie, aby utworzyć grupę urządzeń za pomocą zaawansowanej reguły używającej atrybutu **deviceCategory**.
Na przykład (**device.deviceCategory -eq** "<*nazwa kategorii urządzeń uzyskana z konsoli administratora usługi Intune*>")


## <a name="after-you-configure-device-groups"></a>Po skonfigurowaniu grup urządzeń

Podczas rejestrowania swoich urządzeń użytkownicy zobaczą listę skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy urządzeń usługi Intune lub odpowiadającej wybranej kategorii grupy zabezpieczeń usługi Active Directory.

### <a name="see-also"></a>Zobacz także
[Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

