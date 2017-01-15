---
title: "Monitorowanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune | Microsoft Docs"
description: "Zobacz, jak wielu użytkowników korzysta z zasad, i poznaj więcej szczegółów."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9e208608d50c9b5f7fe66743de0d3c7e741dbfbd
ms.openlocfilehash: 2a18ad7226c6fc6de0277f1f20443ea64dc8b918


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Monitorowanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Po skonfigurowaniu zasad zarządzania aplikacjami mobilnymi i zastosowaniu ich względem użytkowników można monitorować stan zgodności w [witrynie Azure Portal](https://portal.azure.com). Witryna Azure Portal zawiera informacje o użytkownikach, których dotyczą zasady, o stanie zgodności, a także o wszelkich problemach, które mogą napotykać użytkownicy.
## <a name="summary-view"></a>Widok podsumowania
W bloku **Zarządzanie aplikacjami mobilnymi w usłudze Intune** widoczne jest podsumowanie stanu zgodności:


![Kafelek podsumowania w bloku zarządzania aplikacjami mobilnymi usługi Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Użytkownicy:** całkowita liczba użytkowników w firmie, którzy korzystają z aplikacji skojarzonych z zasadami.

-   **ZARZĄDZANE PRZEZ ZASADY:** liczba użytkowników, którzy użyli co najmniej jednej z tych aplikacji w kontekście służbowym.

-   **BRAK ZASAD:** liczba użytkowników, którzy używają aplikacji powiązanych z zasadami, ale którzy nie są objęci zasadami. Można rozważyć dodanie tych użytkowników do zasad.

- **Oflagowani użytkownicy:** liczba użytkowników, którzy napotykają problemy. Obecnie tylko użytkownicy z urządzeniami ze zdjętymi zabezpieczeniami systemu są zgłaszani w sekcji **Oflagowani użytkownicy**.


## <a name="detailed-view"></a>Widok szczegółowy
Aby uzyskać szczegółowy widok podsumowania, wybierz kafelek **Stan użytkownika** i kafelek **Oflagowani użytkownicy**.

### <a name="user-status"></a>Stan użytkownika
Możesz wyszukać pojedynczego użytkownika i sprawdzić jego stan zgodności. Blok **Raportowanie aplikacji** pokazuje następujące informacje dotyczące wybranego użytkownika:
- Urządzenia, które są skojarzone z kontem użytkownika

- Aplikacje z zasadami zarządzania aplikacjami mobilnymi na urządzeniu

- Stan:

  - **Zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, a aplikacja została co najmniej raz użyta w kontekście służbowym.

  - **Nie zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, ale od tego momentu aplikacja nie była używana w kontekście służbowym.

>[!NOTE]
> Jeśli poszukiwany użytkownik nie ma wdrożonych zasad zarządzania aplikacjami mobilnymi, pojawi się komunikat z informacją, że użytkownik nie jest objęty przez żadne zasady dotyczące aplikacji.

Aby wyświetlić raportowanie dla użytkownika, wykonaj następujące kroki:

1.  Aby wybrać użytkownika, wybierz kafelek **Podsumowanie** lub opcję **RAPORTOWANIE APLIKACJI WG UŻYTKOWNIKA** w bloku **Ustawienia**:

    ![Opcja Raportowanie aplikacji w bloku Ustawienia](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. W bloku **Raportowanie aplikacji**, który się otworzy, wybierz opcję **Wybierz użytkownika**, aby wyszukać użytkownika w usłudze Azure Active Directory.

    ![Opcja Wybierz użytkownika w bloku Raportowanie aplikacji](../media/mam-azure-portal-app-reporting-select-user.png)

3. Wybierz użytkownika z listy. Zostaną wyświetlone szczegółowe informacje o stanie zgodności tego użytkownika.

    ![Szczegóły raportowania aplikacji](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Oflagowani użytkownicy
W widoku szczegółowym wyświetlane są: komunikat o błędzie, aplikacja używana w momencie wystąpienia błędu, platforma urządzenia i sygnatura czasowa.  

### <a name="see-also"></a>Zobacz też
[Zarządzanie przesyłaniem danych między aplikacjami systemu iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Oczekiwany przebieg zarządzania aplikacją systemu Android przez zasady zarządzania aplikacjami mobilnymi](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Oczekiwany przebieg zarządzania aplikacją systemu iOS przez zasady zarządzania aplikacjami mobilnymi](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


