---
title: Wyświetlanie i poprawianie danych osobowych
titleSuffix: Microsoft Intune
description: Informacje na temat wyświetlania i poprawiania danych osobowych.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9b6ca291f55511be9e88b0ff898d9383691542bf
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310891"
---
# <a name="view-and-correct-personal-data"></a>Wyświetlanie i poprawianie danych osobowych

Administratorzy usługi Intune mogą wyświetlać niektóre dane osobowe w zależności od swoich uprawnień dostępu, ale tylko użytkownicy końcowi mogą zmieniać dane osobowe związane z ich urządzeniami.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Wyświetlanie danych osobowych

Administratorzy mogą wyświetlać informacje osobiste użytkowników końcowych w różnych blokach interfejsu użytkownika usługi Intune. W następujących artykułach wyjaśniono, do jakich informacji administratorzy mają dostęp, a do jakich nie mają:
- W artykule [Wyświetlanie szczegółów urządzenia](../remote-actions/device-inventory.md) w usłudze Intune wyjaśniono, jak można przejrzeć informacje o urządzeniu użytkownika końcowego.
- W artykule [Monitorowanie informacji o aplikacji i przypisań](../apps/apps-monitor.md) wyjaśniono, jak wyświetlić informacje o aplikacjach zainstalowanych na urządzeniu użytkownika końcowego.
- Artykuł [Jakie informacje może wyświetlać moja firma, gdy zarejestruję swoje urządzenie?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) zawiera listę danych, które może i których nie może wyświetlać firma użytkownika końcowego. Najlepszym rozwiązaniem jest przejrzyste poinformowanie użytkowników, jakiego rodzaju dane gromadzisz i dlaczego to robisz. Ten artykuł może być pierwszym krokiem na drodze do takiej przejrzystości.

### <a name="who-can-view-the-data"></a>Kto może wyświetlać dane?

Firma Microsoft używa restrykcyjnych mechanizmów kontroli, aby zarządzać dostępem do danych klienta, udzielając najniższego poziomu dostępu wymaganego do wykonania kluczowych zadań i odbierając dostęp, gdy nie jest już potrzebny. 

Aby zabezpieczyć i kontrolować dostęp do danych osobowych użytkowników końcowych, można użyć kontroli dostępu na podstawie ról (RBAC, role-based access control). Aby uzyskać więcej informacji, zobacz [Kontrola RBAC w usłudze Microsoft Intune](../fundamentals/role-based-access-control.md).

Aby dowiedzieć się więcej o praktykach firmy Microsoft dotyczących danych, przeczytaj Warunki korzystania z witryny Online Services i [Zasady zachowania poufności informacji w witrynie Microsoft Online Services](https://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409). 

## <a name="correct-end-user-personal-data"></a>Poprawianie danych osobowych użytkownika końcowego

Administratorzy nie mogą aktualizować informacji specyficznych dla urządzenia ani aplikacji. Jeśli użytkownik chce poprawić jakieś dane osobowe (np. nazwę urządzenia), musi to zrobić bezpośrednio na urządzeniu. Takie zmiany są synchronizowane przy następnym połączeniu z usługą Intune.


## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak [przeprowadzać inspekcję danych osobowych oraz eksportować i usuwać je](privacy-data-audit-export-delete.md) w usłudze Intune.
