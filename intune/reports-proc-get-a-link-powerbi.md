---
title: Nawiązywanie połączenia z magazynem danych przy użyciu usługi Power BI
titlesuffix: Microsoft Intune
description: Możesz pobrać plik do użycia z usługą Microsoft Power BI, który umożliwia ładowanie interaktywnych, dynamicznie generowanych raportów dla dzierżawy usługi Microsoft Intune.
keywords: Magazyn danych usługi Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c91d6951fd6f59d85b163fb998ff4833782f03e4
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834606"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Nawiązywanie połączenia z magazynem danych przy użyciu usługi Power BI

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Możesz pobrać plik do użycia z usługą Microsoft Power BI, który umożliwia ładowanie interaktywnych, dynamicznie generowanych raportów dla dzierżawy usługi Intune. Plik usługi Power BI magazynu danych (pbix) zawiera ustawienia połączenia z dzierżawą oraz następujące przykładowe raporty i wykresy:  

  -  Devices
  -  Rejestrowanie
  -  Zasady ochrony aplikacji
  -  Zasady zgodności
  -  Profile konfiguracji urządzeń
  -  Aktualizacje oprogramowania
  -  Dzienniki spisu urządzeń

Dostępne są także trendy wyróżnione do aktualizacji oprogramowania, rejestracji, zgodności i profilu konfiguracji urządzeń. Przykładowe wykresy i raporty dodają do kanwy przyjazne dla użytkownika filtry. Aby użyć filtrów zaawansowanych, zapoznaj się z zawartością okienka **Filtr** w usłudze Power BI.

W poniższej procedurze pokazano, jak pobrać plik usługi Power BI i jak użyć linku usługi OData w usłudze Power BI.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Instalowanie usługi Power BI

Zainstaluj najnowszą wersję aplikacji Power BI Desktop. Aplikację Power BI Desktop możesz pobrać z witryny: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Ładowanie danych i raportów przy użyciu pliku usługi Power BI (pbix)

Plik usługi Power BI (pbix) zawiera informacje dotyczące połączenia dla dzierżawy i zestaw wstępnie utworzonych raportów na podstawie modelu danych magazynu danych. Otwórz plik w aplikacji Power BI Desktop i zaloguj się do usługi Azure AD. Raport załaduje dane z dzierżawy usługi Intune.

> [!Important]  
> Każdy plik usługi Power BI (pbix) może różnić się w zależności od lokalizacji dzierżawy. Jeśli zarządzasz wieloma dzierżawami usługi Intune, upewnij się, że używasz pliku pobranego z witryny Azure Portal po zalogowaniu się do tej dzierżawy.  

1.  Zaloguj się do witryny Azure Portal i wybierz pozycję **Monitorowanie i zarządzanie** > **Intune**. Możesz również wyszukać zasoby i znaleźć usługę **Intune**.  
2.  Otwórz blok **Interfejs API magazynu danych usługi Microsoft Intune (wersja zapoznawcza)**.
3.  Wybierz pozycję **Pobierz plik usługi Power BI**. Plik z rozszerzeniem pbix zostanie pobrany do wskazanej lokalizacji.
4.  Otwórz plik w usłudze Power BI. Zostaną załadowane *raporty magazynu danych usługi Intune*, ale pobieranie danych dzierżawy może chwilę potrwać.
5.  Wybierz pozycję **Odśwież**, aby załadować dane dzierżawy i przejrzeć raporty.
6.  Jeśli usługa Power BI nie dokona uwierzytelnienia przy użyciu poświadczeń usługi Azure Active Directory, zostanie wyświetlony monit o podanie poświadczeń. Wybierając poświadczenia, jako metodę uwierzytelnienia wskaż **Konto organizacyjne**.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Ładowanie danych w usłudze Power BI przy użyciu linku usługi OData

Po uwierzytelnieniu klienta w usłudze Azure AD adres URL usługi OData nawiąże połączenie z punktem końcowym RESTful w interfejsie API magazynu danych, który uwidoczni model danych klienta raportowania. Postępuj zgodnie z tymi instrukcjami, aby przy użyciu aplikacji Power BI Desktop nawiązać połączenie i utworzyć własne raporty. Możesz skorzystać z rozwiązania innego niż aplikacja Power BI Desktop. Wraz z adresem URL usługi OData możesz użyć swojego ulubionego narzędzia analitycznego, o ile klient obsługuje uwierzytelnianie OAUTH2.0 i standard OData v4.0.

1.  Zaloguj się do witryny Azure Portal i wybierz pozycję **Monitorowanie i zarządzanie** > **Intune**. Możesz również wyszukać zasoby i znaleźć usługę **Intune**.  
2.  Otwórz blok **Interfejs API magazynu danych usługi Microsoft Intune (wersja zapoznawcza)**.
3. Pobierz adres URL niestandardowego kanału informacyjnego z bloku raportowania, na przykład `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4. Otwórz aplikację **Power BI Desktop**.
5. Wybierz pozycję **Narzędzia główne** > **Pobierz dane**. Zaznacz pozycję **Źródło danych OData**.
6. Wybierz pozycję **Podstawowe**.
7. Wpisz lub wklej **adres URL usługi OData** w polu adresu URL.
8. Wybierz przycisk **OK**.
9. Jeśli nie dokonano uwierzytelnienia w usłudze Azure AD dla dzierżawy z poziomu klienta aplikacji Power BI Desktop, wpisz swoje poświadczenia. Aby uzyskać dostęp do danych, musisz autoryzować się w usłudze Azure Active Directory (Azure AD) przy użyciu protokołu OAuth 2.0.  
    1.  Wybierz pozycję **Konto organizacyjne**.  
    2.  Wpisz nazwę użytkownika i hasło.  
    3.  Wybierz polecenie **Zaloguj się**.  
    4.  Wybierz polecenie **Połącz**.  
10. Wybierz polecenie **Załaduj**.

## <a name="next-steps"></a>Następne kroki

Możesz znaleźć odpowiedzi na pytania dotyczące środowiska, takie jak liczba rejestrowanych urządzeń na dzień w ostatnim tygodniu. Możesz uzyskać wgląd w dzierżawę usługi Intune i populację klientów przy użyciu raportów w pliku pbix (pliku usługi Power BI magazynu danych usługi Intune) pobranego z bloku na platformie Azure. Usługa Intune umożliwia jednak rozszerzenie lub ponowne użycie danych na szereg dodatkowych sposobów. Usługa Power BI i interfejs API magazynu danych usługi Intune dają znacznie większe możliwości, na przykład:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Dane dzierżawy są organizowane, aby ułatwić ściąganie analizy danych. Aby uzyskać więcej informacji na temat sposobu organizowania danych, zobacz [Model danych magazynu danych](reports-ref-data-model.md).
 -  Możesz również uzyskać dostęp do danych za pomocą interfejsu RESTful i dołączyć dane do własnej aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie danych z interfejsu API magazynu danych za pomocą klienta REST](reports-proc-data-rest.md).
