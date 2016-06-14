---
# required metadata

title: Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń w usłudze Microsoft Intune
Użyj funkcji **mapowania grup urządzeń** w usłudze Microsoft Intune do grupowania urządzeń w zdefiniowane kategorie, co ułatwi zarządzanie tymi urządzeniami. 

Podczas mapowania grup urządzeń jest używany następujący przepływ pracy:
1. Tworzenie grup urządzeń usługi Intune dla każdej kategorii, której chcesz użyć.
2. Konfigurowanie reguł mapowania grup urządzeń, które mapują wybraną kategorię na utworzoną grupę urządzeń.
3. Gdy użytkownik końcowy rejestruje urządzenie, musi wybrać kategorię spośród skonfigurowanych kategorii. Po dokonaniu wyboru urządzenie jest automatycznie dodawane do odpowiedniej utworzonej grupy urządzeń.
4. Następnie można używać tych grup urządzeń podczas wdrażania zasad i aplikacji.

Przykłady kategorii:
* Osobiste
* Urządzenie w punkcie sprzedaży
* Urządzenie demonstracyjne
* Sprzedaż
* Księgowość
* Menedżer

Możesz jednak skonfigurować dowolne żądane kategorie.

## Jak skonfigurować mapowanie grup urządzeń
1. Dla każdej żądanej kategorii urządzeń utwórz grupę urządzeń usługi Intune. Aby uzyskać więcej informacji na temat tworzenia grup, zobacz [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)..
2. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Administracja**.
3. W obszarze roboczym **Administracja** rozwiń węzeł **Zarządzanie urządzeniami przenośnymi**, a następnie kliknij pozycję **Mapowanie grup urządzeń**..
4. Na stronie **Mapowanie grup urządzeń** włącz mapowanie grup urządzeń.
5. Kliknij pozycję **Dodaj**, aby utworzyć nową regułę mapowania.
6. W oknie dialogowym **Dodawanie reguły mapowania grup urządzeń** wprowadź nazwę kategorii, którą chcesz utworzyć, a następnie wybierz z listy rozwijanej kolekcję urządzeń, na którą chcesz zamapować tę kategorię. Po zakończeniu kliknij pozycję **Dodaj**.
7. Po zakończeniu dodawania kategorii i grup kliknij pozycję **Zapisz**..

Podczas rejestrowania swoich urządzeń użytkownicy zobaczą listę skonfigurowanych kategorii. Po wybraniu kategorii i zakończeniu rejestracji urządzenie zostanie dodane do grupy urządzeń odpowiadającej wybranej kategorii.

### Zobacz także
[Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=May16_HO1-->


