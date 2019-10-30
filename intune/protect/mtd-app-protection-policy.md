---
title: Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense (MTD) za pomocą usługi Intune
titleSuffix: Microsoft Intune
description: Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense (MTD) za pomocą usługi Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15d986bc5017a44571c6194f9c6b53167b671349
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72794423"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense za pomocą usługi Intune

> [!NOTE] 
> Niniejszy artykuł dotyczy wszystkich partnerów usługi Mobile Threat Defense (MTD), którzy obsługują zasady ochrony aplikacji: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

Usługa Intune w połączeniu z usługą MTD pomaga wykrywać zagrożenia i oceniać ryzyko na urządzeniach przenośnych. Istnieje możliwość utworzenia zasad ochrony aplikacji usługi Intune, które oceniają ryzyko w celu określenia, czy urządzenie może uzyskać dostęp do danych firmowych. 

## <a name="before-you-begin"></a>Przed rozpoczęciem

W ramach procesu konfiguracji usługi MTD w konsoli tej usługi zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz poziom usługi Mobile Threat Defense trzeba ustawić w zasadach ochrony aplikacji usługi Intune.

Wymagania wstępne dla zasad ochrony aplikacji za pomocą usługi MTD:

- Skonfiguruj integrację usługi MTD z usługą Intune. Bez tej integracji zasady ochrony aplikacji usługi MTD nie będą działać.

## <a name="to-create-an-mtd-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji usługi MTD

1. Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2. Na stronie **Pulpit nawigacyjny platformy Azure** w menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz wartość **Intune**.

3. Wybierz pozycję **Intune**. Zostanie otwarty **Pulpit nawigacyjny Intune**.

4. Na stronie **Pulpit nawigacyjny usługi Intune** wybierz pozycję **Aplikacje klienckie**, a następnie wybierz pozycję **Zasady ochrony aplikacji**  w sekcji **Zarządzanie**.

5. Wybierz pozycję **Utwórz zasady**, podaj wartości **Nazwa** i **Opis** oraz wybierz wartość **Platforma**. 

6. W okienku **Uruchamianie warunkowe** w tabeli **Warunki urządzenia** wybierz pozycję Poziom zagrożeń mobilnych z listy rozwijanej w polu **Maksymalny dozwolony poziom zagrożenia urządzenia**.

    a.  **Zabezpieczone**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.

    b.  **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.

    c.  **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.

    d.  **Wysoki**: ten poziom jest najmniej bezpieczny. Zezwala na wszystkie poziomy zagrożenia i wykorzystuje usługę Mobile Threat Defense w programie Skycure tylko do celów raportowania. Na urządzeniach musi znajdować się aplikacja MTD, w której to ustawienie zostało aktywowane.

7. Kliknij dwukrotnie polecenie **Zapisz**, a następnie wybierz pozycję **Utwórz**.

## <a name="to-assign-an-mtd-app-protection-policy"></a>Przypisywanie zasad ochrony aplikacji usługi MTD

Aby przypisać użytkownikom zasady zgodności urządzeń, wybierz wcześniej skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w okienku **Zgodność urządzeń — zasady**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie okienka, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.

2. Wybierz pozycję **Wybierz grupy do uwzględnienia**, aby otworzyć okienko, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD. Wybranie pozycji **Wybierz** powoduje wdrożenie zasad dla użytkowników.

> [!NOTE] 
> Zasady zostały zastosowane do użytkowników. Urządzenia używane przez użytkowników, których dotyczą zasady, są oceniane pod kątem dostępu do danych firmowych za pomocą docelowych aplikacji przez funkcję ochrony aplikacji usługi Intune.

## <a name="next-steps"></a>Następne kroki  

- Dowiedz się więcej na temat [usługi Mobile Threat Defense](~/protect/mobile-threat-defense.md) w ramach usługi Microsoft Intune.
