---
title: Nawiązywanie połączenia z magazynem danych przy użyciu usługi Power BI
titleSuffix: Microsoft Intune
description: Możesz pobrać plik do użycia z usługą Microsoft Power BI, który umożliwia ładowanie interaktywnych, dynamicznie generowanych raportów dla dzierżawy usługi Microsoft Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d99410416da4c98bb01611051176b793c845237
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654111"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Nawiązywanie połączenia z magazynem danych przy użyciu usługi Power BI

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aplikacja Power BI Compliance umożliwia ładowanie interaktywnych, dynamicznie generowanych raportów dotyczących dzierżawy usługi Intune. Ponadto można ładować dane dotyczące dzierżawy w usłudze Power BI za pomocą połączenia OData. Usługa Intune udostępnia ustawienia połączenia z dzierżawą, dzięki czemu można wyświetlać przykładowe raporty i wykresy dotyczące następujących tematów:  

- Devices
- Rejestrowanie
- Zasady ochrony aplikacji
- Zasady zgodności
- Profile konfiguracji urządzeń
- Aktualizacje oprogramowania
- Dzienniki spisu urządzeń

Dostępne są także trendy wyróżnione do aktualizacji oprogramowania, rejestracji, zgodności i profilu konfiguracji urządzeń. Przykładowe wykresy i raporty dodają do kanwy przyjazne dla użytkownika filtry. Aby użyć filtrów zaawansowanych, zapoznaj się z zawartością okienka **Filtr** w usłudze Power BI.

W poniższej procedurze pokazano, jak pobrać plik usługi Power BI i jak użyć linku usługi OData w usłudze Power BI.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Instalowanie usługi Power BI

Zainstaluj najnowszą wersję aplikacji [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). Aby uzyskać więcej informacji, zobacz [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Ładowanie danych i raportów za pomocą aplikacji Intune Compliance (Data Warehouse) dla usługi Power BI

Aplikacja Power BI [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) zawiera informacje dla dzierżawcy oraz zestaw wstępnie skompilowanych raportów opartych o model danych Data Warehouse.

1. Przejdź do strony **AppSource** aplikacji [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp), aby rozpocząć proces instalacji.
2. Kliknij przycisk **Pobierz teraz** , a następnie kliknij przycisk **Kontynuuj**.
3. Po wyświetleniu monitu o zainstalowanie aplikacji Power BI kliknij przycisk **Zainstaluj**.
4. Po zakończeniu instalacji kliknij kafelek App zgodność z usługą **Intune (Data Warehouse)** .
5. Kliknij przycisk **Połącz** . Zostanie wyświetlone okno dialogowe **Łączenie z aplikacją Intune Compliance (Data Warehouse)** .
6. Kliknij przycisk **Zaloguj**.
7. Zaloguj się przy użyciu konta użytkownika mającego dostęp do magazynu danych usługi Intune dla dzierżawy, której raporty chcesz wyświetlić.
8. Aby wyświetlić dołączony pulpit nawigacyjny, kliknij kartę **pulpity nawigacyjne** , a następnie kliknij pulpit nawigacyjny **przegląd zgodności** .
9. Aby wyświetlić wszystkie dostępne raporty, kliknij kartę **raporty** , a następnie kliknij raport zgodność ze standardem **v 1.0** . Przeglądaj strony raportu, klikając karty w dolnej części.
10. Aby móc łatwo wrócić później do tych raportów, kliknij gwiazdkę obok raportu **Compliance V1.0**. Spowoduje to dodanie tego raportu do ulubionych w usłudze Power BI.

Ewentualnie można zainstalować tę aplikację z portalu usługi Intune:

1. Zaloguj się do witryny Azure Portal i wybierz pozycję **Monitorowanie i zarządzanie** > **Intune**. Możesz również wyszukać usługę Intune w zasobach.
2. Otwórz blok **Skonfiguruj magazyn danych usługi Intune**.
3. Wybierz pozycję **Pobierz aplikację Power BI**, aby uzyskać dostęp do wstępnie utworzonych raportów usługi Power BI dotyczących Twojej dzierżawy w przeglądarce i je udostępniać.
4. Wykonaj kroki 2–10 powyżej.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Ładowanie danych w usłudze Power BI przy użyciu linku usługi OData

Po uwierzytelnieniu klienta w usłudze Azure AD adres URL usługi OData nawiąże połączenie z punktem końcowym RESTful w interfejsie API magazynu danych, który uwidoczni model danych klienta raportowania. Postępuj zgodnie z tymi instrukcjami, aby przy użyciu aplikacji Power BI Desktop nawiązać połączenie i utworzyć własne raporty. Możesz skorzystać z rozwiązania innego niż aplikacja Power BI Desktop. Wraz z adresem URL usługi OData możesz użyć swojego ulubionego narzędzia analitycznego, o ile klient obsługuje uwierzytelnianie OAUTH2.0 i standard OData v4.0.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Kliknij pozycję **Skonfiguruj magazyn danych usługi Intune** w sekcji **inne zadania** po prawej stronie bloku przegląd. Zostanie wyświetlony blok **Magazyn danych usługi Intune** .
3. Pobierz adres URL niestandardowego kanału informacyjnego z bloku raportowania, na przykład:<br>
    `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
4. Otwórz aplikację **Power BI Desktop**.
5. Wybierz pozycję **plik** > **Pobierz dane**. Zaznacz pozycję **Źródło danych OData**.
6. Wybierz pozycję **Podstawowe**.
7. Wpisz lub wklej **adres URL usługi OData** w polu adresu URL.
8. Wybierz przycisk **OK**.
9. Jeśli nie dokonano uwierzytelnienia w usłudze Azure AD dla dzierżawy z poziomu klienta aplikacji Power BI Desktop, wpisz swoje poświadczenia. Aby uzyskać dostęp do danych, musisz autoryzować się w usłudze Azure Active Directory (Azure AD) przy użyciu protokołu OAuth 2.0.  
    1. Wybierz pozycję **Konto organizacyjne**.  
    2. Wpisz nazwę użytkownika i hasło.  
    3. Wybierz polecenie **Zaloguj się**.  
    4. Wybierz polecenie **Połącz**.  
10. Wybierz polecenie **Załaduj**.

## <a name="next-steps"></a>Następne kroki

Możesz znaleźć odpowiedzi na pytania dotyczące środowiska, takie jak liczba rejestrowanych urządzeń na dzień w ostatnim tygodniu. Możesz uzyskać wgląd w dzierżawę usługi Intune i populację klientów przy użyciu raportów magazynu danych usługi Intune dla usługi Power BI, pobranych z odpowiedniego bloku na platformie Azure. Usługa Intune umożliwia jednak rozszerzenie lub ponowne użycie danych na szereg dodatkowych sposobów. Usługa Power BI i interfejs API magazynu danych usługi Intune zapewniają między innymi następujące dodatkowe funkcje:

<!-- - You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
- Dane dzierżawy są organizowane, aby ułatwić ściąganie analizy danych. Aby uzyskać więcej informacji na temat sposobu organizowania danych, zobacz [Model danych magazynu danych](reports-ref-data-model.md).
- Możesz również uzyskać dostęp do danych za pomocą interfejsu RESTful i dołączyć dane do własnej aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie danych z interfejsu API magazynu danych za pomocą klienta REST](../reports-proc-data-rest.md).
