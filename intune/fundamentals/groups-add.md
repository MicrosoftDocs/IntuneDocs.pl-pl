---
title: Dodawanie grup w celu zorganizowania użytkowników i urządzeń
titleSuffix: Microsoft Intune
description: Możesz dodawać grupy, aby organizować użytkowników i urządzenia na podstawie lokalizacji geograficznej, działu lub kryteriów dotyczących sprzętu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e3219e32ef9bea838f0c19258d0b22a99083a12
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2019
ms.locfileid: "74261575"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Dodawanie grup w celu zorganizowania użytkowników i urządzeń

Do zarządzania urządzeniami i użytkownikami w usłudze Intune służą grupy usługi Azure Active Directory (AD). Jako administrator usługi Intune możesz skonfigurować grupy zgodnie z potrzebami organizacji. Utwórz grupy w celu zorganizowania użytkowników i urządzeń według lokalizacji geograficznej, działu lub parametrów sprzętowych. Użyj grup, aby zarządzać zadaniami na dużą skalę. Możesz na przykład ustawić zasady dla wielu użytkowników lub wdrożyć aplikacje na zestawie urządzeń.

Dodawać można następujące typy grup:

- **Grupy przypisane** — ręczne dodawanie użytkowników lub urządzeń do grup statycznych. 
- **Grupy dynamiczne** (wymagana usługa Azure AD Premium) — automatyczne dodawanie użytkowników lub urządzeń do grup użytkowników lub urządzeń na podstawie utworzonego wyrażenia.

  Na przykład użytkownik z tytułem menedżera jest automatycznie dodawany do grupy użytkowników **Wszyscy menedżerowie**. Z kolei urządzenie z typem systemu operacyjnego ustawionym na iOS jest automatycznie dodawane do grupy **Wszystkie urządzenia z systemem iOS**.

## <a name="add-a-new-group"></a>Dodawanie nowej grupy

Aby utworzyć nową grupę, wykonaj następujące czynności.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno opcje **Grupy** > **Nowa grupa**:

   ![Zrzut ekranu przedstawiający witrynę Azure Portal z wybraną opcją Nowa grupa](./media/groups-add/groups-add-new.png)

3. Jako **Typ grupy** wybierz jedną z następujących opcji:

    - **Zabezpieczenia**: Grupy zabezpieczeń określają, kto może uzyskać dostęp do zasobów. Są zalecane do użytku z grupami w usłudze Intune. Na przykład można utworzyć grupy użytkowników, takie jak **Wszyscy pracownicy z Charlotte** lub **Wszystkie kobiety w firmie Contoso**. Można też utworzyć grupy urządzeń, takie jak **Wszystkie urządzenia z systemem iOS** lub **Wszystkie urządzenia uczniów z systemem Windows 10**.

        > [!TIP]
        > Utworzonych użytkowników i grupy można też zobaczyć w [centrum administracyjnym platformy Microsoft 365](https://admin.microsoft.com), centrum administracyjnym usługi Azure Active Directory i [usłudze Microsoft Intune w witrynie Azure Portal](https://go.microsoft.com/fwlink/?linkid=2090973). W dzierżawie swojej organizacji możesz tworzyć grupy we wszystkich tych obszarach i nimi zarządzać.
        >
        > Jeśli Twoją główną rolą jest zarządzanie urządzeniami, zalecamy korzystanie z [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

    - **Office 365**: te grupy służą do kontrolowania dostępu i udostępniania zasobów usługi Office 365. Na przykład można utworzyć grupę usługi Office 365 w celu udostępniania skrzynki pocztowej lub kalendarza programu Outlook. Aby dowiedzieć się więcej, zobacz [Informacje o grupach usługi Office 365](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

4. Wypełnij pola **Nazwa grupy** i **Opis grupy** dotyczące nowej grupy. Zamieść w nich szczegółowe informacje, aby również inni znali przeznaczenie grupy.

    Na przykład nazwij grupę **Wszystkie urządzenia uczniów z systemem Windows 10** i wpisz opis **Wszystkie urządzenia z systemem Windows 10 używane przez uczniów klas 9–12 szkoły średniej Contoso**.

5. Wybierz **typ członkostwa**. Dostępne opcje:

    - **Przypisane**: administratorzy ręcznie przypisują użytkowników lub urządzenia do grupy i ręcznie je z niej usuwają.
    - **Dynamiczny użytkownik**: administratorzy tworzą reguły członkostwa w celu automatycznego dodawania i usuwania członków.
    - **Dynamiczne urządzenie**: administratorzy tworzą dynamiczne reguły grupy w celu automatycznego dodawania i usuwania urządzeń.

        ![Zrzut ekranu przedstawiający właściwości grupy w usłudze Intune](./media/groups-add/groups-add-properties.png)

    Więcej informacji o tych typach członkostwa i tworzeniu wyrażeń dynamicznych:

    - [Tworzenie grupy podstawowej i dodawanie członków przy użyciu usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    - [Reguły członkostwa dynamicznego dla grup w Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

    > [!NOTE]
    > W tym centrum administracyjnym po utworzeniu użytkowników lub grup może nie zostać wyświetlone znakowanie **Azure Active Directory**. Używana jest jednak właśnie ta usługa.

6. Wybierz pozycję **Utwórz**, aby dodać nową grupę. Grupa zostanie wyświetlona na liście.

> [!TIP]
> Zastanów się, jakie inne dynamiczne grupy użytkowników i urządzeń można utworzyć, na przykład:
>
> - Wszyscy uczniowie szkoły średniej Contoso
> - Wszystkie urządzenia z systemem Android Enterprise
> - Wszystkie urządzenia z systemem iOS 11 lub starszym
> - Marketing
> - Kadry
> - Wszyscy pracownicy z Charlotte
> - Wszyscy pracownicy ze stanu Waszyngton

## <a name="groups-and-policies"></a>Grupy i zasady

Dostęp do zasobów organizacji jest kontrolowany za pomocą użytkowników i grup, które utworzysz.

Podczas tworzenia grup zastanów się nad sposobem stosowania [zasad zgodności](../protect/device-compliance-get-started.md) i [profilów konfiguracji](../configuration/device-profiles.md). Możesz na przykład mieć:

- zasady dotyczące określonego systemu operacyjnego,
- zasady dotyczące różnych ról w organizacji,
- zasady dotyczące jednostek organizacyjnych zdefiniowanych w usłudze Active Directory.

W celu ustalenia podstawowych wymagań zgodności w firmie można utworzyć domyślne zasady dotyczące wszystkich grup i urządzeń. Następnie można utworzyć bardziej szczegółowe zasady dla najszerszych kategorii użytkowników i urządzeń. Można na przykład utworzyć zasady poczty e-mail dla każdego systemu operacyjnego urządzenia.

Zalecenia i wskazówki dotyczące profilów konfiguracji znajdziesz w sekcjach poświęconych [przypisywaniu zasad do grup użytkowników i urządzeń](../configuration/device-profile-assign.md#user-groups-vs-device-groups) oraz [zaleceniom dotyczącym profilów](../configuration/device-profile-create.md#recommendations).

## <a name="see-also"></a>Zobacz także

- [Kontrola dostępu oparta na rolach (RBAC) w usłudze Microsoft Intune](role-based-access-control.md)
- [Zarządzanie dostępem do aplikacji i zasobów przy użyciu grup usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
