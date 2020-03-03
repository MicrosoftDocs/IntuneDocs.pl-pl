---
title: Dodawanie usługi Microsoft Defender ATP na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat dodawania usługi Microsoft Defender ATP na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ae6e8a621b10ec969fa3fcfb2dfeabb8d5a7bdd
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569563"
---
# <a name="add-microsoft-defender-atp-to-macos-devices-using-microsoft-intune"></a>Dodawanie usługi Microsoft Defender ATP na urządzeniach z systemem macOS przy użyciu usługi Microsoft Intune

Aby móc wdrażać, konfigurować, monitorować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. Jednym z dostępnych [typów aplikacji](~/apps/apps-add.md#app-types-in-microsoft-intune) jest usługa Microsoft Defender Advanced Threat Protection (ATP). Po wybraniu tego typu aplikacji w usłudze Intune możesz przypisać i zainstalować usługę Microsoft Defender ATP na zarządzanych urządzeniach z systemem macOS. Ten typ aplikacji ułatwia przypisanie usługi Microsoft Defender ATP do urządzeń z systemem macOS bez konieczności używania narzędzia opakowującego aplikacje systemu macOS. Aby pomóc w zachowaniu bezpieczeństwa i aktualności aplikacji, dołączamy do nich program Microsoft AutoUpdate (MAU).

## <a name="prerequisites"></a>Wymagania wstępne
- Na urządzeniu z systemem macOS musi być zainstalowany system macOS w wersji 10.13 lub nowszy.
- Urządzenie z systemem macOS musi mieć co najmniej 650 MB miejsca na dysku.
- Wdróż rozszerzenie jądra w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Dodawanie rozszerzeń jądra systemu macOS w usłudze Intune](~/configuration/kernel-extensions-overview-macos.md).

> [!IMPORTANT]
> Rozszerzenie jądra można zatwierdzać automatycznie tylko wtedy, gdy jest ono obecne na urządzeniu przed zainstalowaniem aplikacji Microsoft Defender ATP. W przeciwnym razie użytkownicy zobaczą na komputerach Mac komunikat informujący o zablokowaniu rozszerzeniu systemu i będą musieli zatwierdzić rozszerzenie, przechodząc do pozycji **Preferencje zabezpieczeń** lub **Preferencje systemowe** > **Zabezpieczenia i prywatność**, a następnie wybierając pozycję **Zezwól**. Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z rozszerzeniami jądra w usłudze Microsoft Defender ATP dla komputerów Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-support-kext).

## <a name="add-microsoft-defender-atp-to-intune"></a>Dodawanie usługi Microsoft Defender ATP do usługi Intune
Do usługi Intune można dodać usługę Microsoft Defender ATP, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. Na liście **Typ aplikacji** w obszarze **Microsoft Defender ATP** wybierz pozycję **macOS**.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji
W tym kroku podajesz informacje o tym wdrożeniu aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.

1. Kliknij **Informacje o aplikacji**, aby wyświetlić okienko **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** należy podać informacje o tym wdrożeniu aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.
    - **Nazwa**: Wprowadź nazwę aplikacji wyświetlaną w Portalu firmy. Upewnij się, że wszystkie nazwy są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis**: Wprowadź opis aplikacji. Przykładowo w opisie możesz wymienić docelowych użytkowników.
    - **Wydawca**: w roli wydawcy występuje firma Microsoft.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. To ustawienie ułatwi użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić aplikację w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: w roli dewelopera występuje firma Microsoft.
    - **Właściciel**: w roli właściciela występuje firma Microsoft.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
3. Wybierz przycisk **OK**.

## <a name="select-scope-tags-optional"></a>Wybieranie tagów zakresu (opcjonalnie)
Za pomocą tagów zakresu można określić, kto będzie mógł wyświetlać informacje o aplikacji klienckiej w usłudze Intune. Więcej informacji o tagach zakresu zawiera artykuł Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej.
1.  Wybierz pozycję **Zakres (tagi)** > **Dodaj**.
2.  Użyj pola **Wybierz**, aby wyszukać tagi zakresu.
3.  Zaznacz pole wyboru obok tagów zakresu, które chcesz przypisać do aplikacji.
4.  Kliknij kolejno pozycje **Wybierz** > **OK**.

## <a name="add-the-app"></a>Dodawanie aplikacji
Po zakończeniu konfigurowania wybierz opcję **Dodaj** w okienku **Aplikacja**. 

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

> [!NOTE]
> Obecnie firma Apple nie udostępnia możliwości odinstalowania usługi Microsoft Defender ATP z urządzenia z systemem macOS za pomocą usługi Intune.

## <a name="next-steps"></a>Następne kroki
- Aby dowiedzieć się, jak skonfigurować usługę Microsoft Defender ATP na urządzeniach z systemem macOS, zobacz [Konfigurowanie usługi Microsoft Defender ATP na urządzeniach z systemem macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-preferences).
- Aby dowiedzieć się więcej o dołączaniu i wykluczaniu przypisań aplikacji względem grup użytkowników, zobacz [Dołączanie i wykluczanie przypisań aplikacji](~/apps/apps-inc-exl-assignments.md).
- [Przypisywanie aplikacji do grup](~/apps/apps-deploy.md)

