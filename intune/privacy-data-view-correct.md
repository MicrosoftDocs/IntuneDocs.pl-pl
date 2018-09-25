---
title: Wyświetlanie i poprawianie danych osobowych
description: Informacje na temat wyświetlania i poprawiania danych osobowych.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b9efb60d169ba6f88b4765d3fc651f3a0596b230
ms.sourcegitcommit: 378474debffbc85010c54e20151d81b59b7a7828
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028583"
---
# <a name="view-and-correct-personal-data"></a>Wyświetlanie i poprawianie danych osobowych

Administratorzy usługi Intune mogą wyświetlać niektóre dane osobowe w zależności od swoich uprawnień dostępu, ale tylko użytkownicy końcowi mogą zmieniać dane osobowe związane z ich urządzeniami.

[!INCLUDE [GDPR-related guidance](./includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Wyświetlanie danych osobowych

Administratorzy mogą wyświetlać informacje osobiste użytkowników końcowych w różnych blokach interfejsu użytkownika usługi Intune. W następujących artykułach wyjaśniono, do jakich informacji administratorzy mają dostęp, a do jakich nie mają:
- W artykule [Wyświetlanie szczegółów urządzenia](device-inventory.md) w usłudze Intune wyjaśniono, jak można przejrzeć informacje o urządzeniu użytkownika końcowego.
- W artykule [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md) wyjaśniono, jak wyświetlić informacje o aplikacjach zainstalowanych na urządzeniu użytkownika końcowego.
- Artykuł [Jakie informacje może wyświetlać moja firma, gdy zarejestruję swoje urządzenie?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) zawiera listę danych, które może i których nie może wyświetlać firma użytkownika końcowego. Najlepszym rozwiązaniem jest przejrzyste poinformowanie użytkowników, jakiego rodzaju dane gromadzisz i dlaczego to robisz. Ten artykuł może być pierwszym krokiem na drodze do takiej przejrzystości.

### <a name="who-can-view-the-data"></a>Kto może wyświetlać dane?

Firma Microsoft używa restrykcyjnych mechanizmów kontroli, aby zarządzać dostępem do danych klienta, udzielając najniższego poziomu dostępu wymaganego do wykonania kluczowych zadań i odbierając dostęp, gdy nie jest już potrzebny. 

Aby zabezpieczyć i kontrolować dostęp do danych osobowych użytkowników końcowych, można użyć kontroli dostępu na podstawie ról (RBAC, role-based access control). Aby uzyskać więcej informacji, zobacz [Kontrola RBAC w usłudze Microsoft Intune](role-based-access-control.md).

Aby dowiedzieć się więcej o praktykach firmy Microsoft dotyczących danych, przeczytaj Warunki korzystania z witryny Online Services i [Zasady zachowania poufności informacji w witrynie Microsoft Online Services](http://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409). 

## <a name="correct-end-user-personal-data"></a>Poprawianie danych osobowych użytkownika końcowego

Administratorzy nie mogą aktualizować informacji specyficznych dla urządzenia ani aplikacji. Jeśli użytkownik chce poprawić jakieś dane osobowe (np. nazwę urządzenia), musi to zrobić bezpośrednio na urządzeniu. Takie zmiany są synchronizowane przy następnym połączeniu z usługą Intune.


## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak [przeprowadzać inspekcję danych osobowych oraz eksportować i usuwać je](privacy-data-audit-export-delete.md) w usłudze Intune.