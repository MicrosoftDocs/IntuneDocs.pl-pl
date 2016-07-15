---
# required metadata

title: Nazwy domen w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Nazwy domen w usłudze Microsoft Intune

Przed skonfigurowaniem usługi Microsoft Intune przejrzyj ten temat i inne wymagania wymienione w artykule [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Gdy organizacja rejestruje się w usłudze firmy Microsoft w chmurze, takiej jak Intune, otrzymuje początkową nazwę domeny, która wygląda podobnie do następującej: **contoso.onmicrosoft.com**. W tym przykładzie **contoso** jest nazwą domeny wybraną podczas rejestracji, a **onmicrosoft.com** jest sufiksem przypisanym do kont dodanych do subskrypcji. Po zakończeniu procesu rejestracji nie można zmienić nazwy domeny. Jednak administrator globalny może dodać własne nazwy domen organizacji, które będą używane w usłudze, lub usunąć wcześniej dodane domeny.

W przypadku korzystania z domeny onmicrosoft do głównej nazwy każdego zaimportowanego użytkownika (nazwy UPN) jest domyślnie dodawany sufiks **onmicrosoft.com**.

Aby zamiast domeny otrzymanej podczas rejestracji używać własnej nazwy domeny, możesz dodać ją do usługi Azure Active Directory. Po dodaniu domeny i zweryfikowaniu, że jesteś jej właścicielem, możesz utworzyć konta i grupy zawierające tę nazwę domeny, zmieniając rekordy zasobów DNS u dostawcy hostingu DNS. Aby uprościć zarządzanie kontami użytkowników w przypadku używania własnej domeny, przed rozpoczęciem synchronizowania użytkowników z lokalnej usługi Active Directory skonfiguruj niestandardową nazwę domeny dla swojej subskrypcji.

Konfigurowanie nazw domen i rekordów zasobów DNS dla usługi Intune odbywa się tak samo jak w przypadku pozostałych dzierżaw usługi Azure Active Directory. Aby uzyskać instrukcje, zobacz [Dodawanie niestandardowej nazwy domeny w celu uproszczenia logowania za pomocą usługi Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

### Zobacz także
[Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


