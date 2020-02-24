---
title: Tworzenie i wdrażanie zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: W tym temacie opisano, jak tworzyć i przypisywać zasady ochrony aplikacji (APP) usługi Microsoft Intune do użytkowników.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7a6914e8174023704cfc593ec08a525ec5889f3
ms.sourcegitcommit: ecaff388038fb800f2e646f8efcf8f3b1e2fd1b1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "77437906"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Tworzenie i przypisywanie zasad ochrony aplikacji

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dowiedz się, jak tworzyć i przypisywać zasady ochrony aplikacji usługi Microsoft Intune do użytkowników w organizacji. W tym temacie opisano również sposób wprowadzania zmian istniejących zasad.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Zasady ochrony aplikacji można stosować do aplikacji działających na urządzeniach, które mogą być zarządzane przez usługę Intune lub nie. Aby uzyskać bardziej szczegółowy opis działania zasad ochrony aplikacji oraz informacje dotyczące scenariuszy obsługiwanych przy użyciu zasad ochrony aplikacji usługi Intune, zobacz [What are Microsoft Intune app protection policies? (Co to są zasady ochrony aplikacji usługi Microsoft Intune)](app-protection-policy.md).

Jeśli szukasz listy aplikacji z obsługą zasad MAM, zobacz [listę aplikacji z zarządzaniem aplikacjami mobilnymi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Aby uzyskać informacje o dodawaniu aplikacji biznesowych (LOB) Twojej organizacji do usługi Microsoft Intune w celu przygotowania do zastosowania zasad ochrony aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md).

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Zasady ochrony aplikacji w systemach iOS/iPadOS i Android

Aby utworzyć zasady ochrony aplikacji w systemach iOS/iPadOS i Android, należy postępować zgodnie ze nowoczesnym przepływem procesu usługi Intune, który powoduje utworzenie nowych zasad ochrony aplikacji.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji w systemie iOS/iPadOS lub Android
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. W portalu usługi Intune wybierz pozycję **Aplikacje** > **Zasady ochrony aplikacji**. Ten wybór spowoduje otwarcie szczegółów obszaru **Zasady ochrony aplikacji**, w którym można tworzyć nowe zasady i edytować istniejące.
3. Wybierz pozycję **Utwórz zasady**, a następnie wybierz system **iOS/iPadOS** lub **Android**. Zostanie wyświetlone okienko **Tworzenie zasad**.
4. Na stronie **Podstawowe** dodaj następujące wartości:

    | Wartość | Opis |
    |--------------|------------------------------------------------|
    | Nazwa | Nazwa zasad ochrony aplikacji. |
    | Opis | [Opcjonalnie] Opis zasad ochrony aplikacji. |


    Wartość **Platforma** jest ustawiana na podstawie wybranych wyżej opcji.

    ![Zrzut ekranu przedstawiający stronę Podstawowe w okienku Tworzenie zasad](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Aplikacje**.<br>
    Strona **Aplikacje** umożliwia wybranie sposobu zastosowania zasad do aplikacji na różnych urządzeniach. Należy dodać co najmniej jedną aplikację.<p>
    
    | Wartość/opcja | Opis |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Jako docelowe ustaw aplikacje na wszystkich typach urządzeń | Ta opcja umożliwia zastosowanie zasad do aplikacji na urządzeniach w dowolnym stanie zarządzania. Wybierz pozycję **Nie**, aby zastosować zasady do aplikacji na konkretnych typach urządzeń. Aby uzyskać więcej informacji, zobacz sekcję [Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem](#target-app-protection-policies-based-on-device-management-state) |
    |     Typy urządzeń | Dzięki tej opcji można określić, czy zasady mają zastosowanie do urządzeń zarządzanych przez MDM, czy urządzeń niezarządzanych. W przypadku zasad aplikacji systemu iOS/iPadOS można wybierać spośród urządzeń **niezarządzanych** i **zarządzanych**. W przypadku zasad aplikacji systemu Android do wyboru są opcje **Niezarządzane**, **Administrator urządzeń z systemem Android** i **System Android dla firm**.  |
    | Aplikacje publiczne | Kliknij pozycję **Wybierz aplikacje publiczne**, aby wybrać aplikacje docelowe. |
    | Aplikacje niestandardowe | Kliknij pozycję **Wybierz aplikacje niestandardowe**, aby wybrać docelowe aplikacje niestandardowe na podstawie identyfikatora pakietu. |
    
    Wybrane aplikacje będą widoczne na liście aplikacji publicznych i niestandardowych. 
6. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Ochrona danych**.<br>
    Ta strona udostępnia ustawienia funkcji ochrony przed utratą danych ograniczające działania, takie jak wycinanie, kopiowanie, wklejanie i zapisywanie pod nową nazwą. Te ustawienia określają, jak użytkownicy używają danych w aplikacjach, do których mają zastosowanie zasady ochrony.

    **Ustawienia ochrony danych**:<br>
    - **Ochrona danych w systemie iOS/iPadOS** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — ochrona danych](~/apps/app-protection-policy-settings-ios.md#data-protection).
    - **Ochrona danych w systemie Android** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — ochrona danych](~/apps/app-protection-policy-settings-android.md#data-protection).

7. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Wymagania dotyczące dostępu**.<br>
    Ta strona zawiera ustawienia pozwalające skonfigurować wymagania dotyczące numeru PIN i poświadczeń, które użytkownicy muszą spełnić, aby uzyskać dostęp do aplikacji w kontekście służbowym. 
 
    **Ustawienia wymagań dotyczących dostępu**:<br>
    - **Wymagania dotyczące dostępu w systemie iOS/iPadOS** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — wymagania dotyczące dostępu](~/apps/app-protection-policy-settings-ios.md#access-requirements).
    - **Wymagania dotyczące dostępu w systemie Android** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — wymagania dotyczące dostępu](~/apps/app-protection-policy-settings-android.md#access-requirements).

8. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Uruchamianie warunkowe**.<br>
    Ta strona zawiera ustawienia umożliwiające skonfigurowanie wymagań dotyczących zabezpieczeń logowania na potrzeby zasad ochrony aplikacji. Wybierz pozycję w kolumnie **Ustawienie** i w kolumnie **Wartość** wprowadź wartość, która będzie wymagana od użytkowników, aby mogli zalogować się do aplikacji firmowej. Następnie w kolumnie **Akcja** wybierz akcję, którą chcesz wykonać, jeśli użytkownicy nie spełnili Twoich wymagań. W niektórych przypadkach dla pojedynczego ustawienia można skonfigurować wiele akcji.

    **Ustawienia uruchamiania warunkowego**:<br>
    - **Uruchamianie warunkowe w systemie iOS/iPadOS** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — uruchamianie warunkowe](~/apps/app-protection-policy-settings-ios.md#conditional-launch).
    - **Uruchamianie warunkowe w systemie Android** — aby uzyskać więcej informacji, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — uruchamianie warunkowe](~/apps/app-protection-policy-settings-android.md#conditional-launch).

9. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.<br>
   Na stronie **Przypisania** możesz przypisywać zasady ochrony aplikacji do grup użytkowników.

10. Kliknij przycisk **Dalej: Przeglądanie + tworzenie**, aby przejrzeć wartości i ustawienia wprowadzone dla tych zasad ochrony aplikacji.

11. Gdy skończysz, kliknij pozycję **Utwórz**, aby utworzyć zasady ochrony aplikacji w usłudze Intune. 

    > [!TIP]
    > Te ustawienia zasad obowiązują tylko w przypadku stosowania aplikacji w kontekście pracy. Gdy użytkownicy końcowi używają aplikacji do wykonywania zadania osobistego, te zasady nie obowiązują. Należy pamiętać, że nowo utworzony plik jest uznawany za plik osobisty. 

Użytkownicy końcowi mogą pobrać aplikacje ze sklepu App Store lub Google Play. Aby uzyskać więcej informacji, zobacz:
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS/iPadOS jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Zmiana istniejących zasad
Możesz edytować istniejące zasady i zastosować je do użytkowników docelowych. Jednak w przypadku zmiany istniejących zasad użytkownicy zalogowani do aplikacji zobaczą zmiany dopiero po 8 godzinach.

Aby zobaczyć efekt zmian natychmiast, użytkownik końcowy musi wylogować się z aplikacji i ponownie do niej zalogować.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Aby zmienić listę aplikacji powiązanych z zasadami

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Właściwości**.

3. Obok sekcji *Aplikacje* wybierz pozycję **Edytuj**.

4. Strona **Aplikacje** umożliwia wybranie sposobu zastosowania zasad do aplikacji na różnych urządzeniach. Należy dodać co najmniej jedną aplikację.<p>
    
    | Wartość/opcja | Opis |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Jako docelowe ustaw aplikacje na wszystkich typach urządzeń | Ta opcja umożliwia zastosowanie zasad do aplikacji na urządzeniach w dowolnym stanie zarządzania. Wybierz pozycję **Nie**, aby zastosować zasady do aplikacji na konkretnych typach urządzeń. Aby uzyskać więcej informacji, zobacz sekcję [Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem](#target-app-protection-policies-based-on-device-management-state) |
    |     Typy urządzeń | Dzięki tej opcji można określić, czy zasady mają zastosowanie do urządzeń zarządzanych przez MDM, czy urządzeń niezarządzanych. W przypadku zasad aplikacji systemu iOS/iPadOS można wybierać spośród urządzeń **niezarządzanych** i **zarządzanych**. W przypadku zasad aplikacji systemu Android do wyboru są opcje **Niezarządzane**, **Administrator urządzeń z systemem Android** i **System Android dla firm**.  |
    | Aplikacje publiczne | Kliknij pozycję **Wybierz aplikacje publiczne**, aby wybrać aplikacje docelowe. |
    | Aplikacje niestandardowe | Kliknij pozycję **Wybierz aplikacje niestandardowe**, aby wybrać docelowe aplikacje niestandardowe na podstawie identyfikatora pakietu. |

    Wybrane aplikacje będą widoczne na liście aplikacji publicznych i niestandardowych. 

5. Kliknij pozycję **Przegląd + Tworzenie**, aby przejrzeć aplikacje wybrane dla tych zasad.

6. Gdy skończysz, kliknij pozycję **Zapisz**, aby zaktualizować zasady ochrony aplikacji.
 
#### <a name="to-change-the-list-of-user-groups"></a>Aby zmienić listę grup użytkowników

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Właściwości**.

3. Obok sekcji *Przypisania* wybierz pozycję **Edytuj**.

4. Aby dodać nową grupę użytkowników do zasad, na karcie *Uwzględnianie* wybierz pozycję **Wybierz grupy do uwzględnienia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby dodać grupę. 

5. Aby wykluczyć grupę użytkowników, na karcie *Wykluczanie* wybierz pozycję **Wybierz grupy do wykluczenia** i wybierz grupę użytkowników. Wybierz pozycję **Wybierz**, aby usunąć grupę użytkowników.  

6. Aby usunąć grupy dodane wcześniej, na karcie *Dołączanie* lub *Wykluczanie* wybierz wielokropek (...) i wybierz pozycję **Usuń**.

7. Kliknij pozycję **Przegląd + Tworzenie**, aby przejrzeć grupy użytkowników wybrane dla tych zasad.

8. Gdy zmiany przypisań będą gotowe, wybierz pozycję **Zapisz**, aby zapisać konfigurację i wdrożyć zasady do zestawu nowych użytkowników. Jeśli przed zapisaniem konfiguracji wybierzesz pozycję **Anuluj**, wszystkie zmiany wprowadzone na kartach *Dołączanie* i *Wykluczanie* zostaną odrzucone.

### <a name="to-change-policy-settings"></a>Aby zmienić ustawienia zasad

1. W okienku **Zasady ochrony aplikacji** wybierz zasady, które chcesz zmienić.

2. W okienku *Intune App Protection* wybierz pozycję **Właściwości**.

3. Obok sekcji odpowiadającej ustawieniom, które chcesz zmienić, wybierz pozycję **Edytuj**. Następnie zmień te ustawienia na nowe wartości.

7. Kliknij pozycję **Przegląd + Tworzenie**, aby przejrzeć zaktualizowane ustawienia zasad.

4. Wybierz ikonę **Zapisz**, aby zapisać zmiany. Powtórz te czynności, aby wybrać obszar ustawień, zmodyfikować go i zapisać zmiany, dopóki nie zostaną zakończone wszystkie zmiany. Następnie możesz zamknąć okienko *Intune App Protection — właściwości*. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Zasady ochrony aplikacji docelowych oparte na stanie zarządzania urządzeniem
W wielu organizacjach powszechne jest zezwalanie na korzystanie przez użytkowników końcowych zarówno z urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami mobilnymi usługi Intune, takich jak urządzenia należące do firmy, jak i z urządzeń niezarządzanych, które są chronione tylko za pomocą zasad ochrony aplikacji usługi Intune. Urządzenia niezarządzane są często określane jako urządzenia BYOD.

Ponieważ zasady ochrony aplikacji usługi Intune dotyczą tożsamości użytkownika, ustawienia ochrony dla użytkownika można stosować zarówno do urządzeń zarejestrowanych (zarządzanych przez rozwiązanie MDM), jak i niezarejestrowanych (niezarządzanych przez rozwiązanie MDM). W związku z tym można określić zasady ochrony aplikacji usługi Intune dla zarejestrowanych lub niezarejestrowanych w usłudze Intune urządzeń z systemem iOS/iPadOS lub Android. Jedne zasady ochrony mogą być przeznaczone dla urządzeń niezarządzanych, w przypadku których są wdrożone ścisłe środki ochrony przed utratą danych, a inne zasady mogą być przeznaczone dla urządzeń zarządzanych przez rozwiązanie MDM, w przypadku których środki ochrony przed utratą danych mogą być mniej restrykcyjne. Aby uzyskać więcej informacji o działaniu zasad w przypadku urządzeń osobistych z systemem Android Enterprise, zobacz temat [Zasady ochrony aplikacji i profile służbowe](android-deployment-scenarios-app-protection-work-profiles.md).

Aby utworzyć te zasady, przejdź do opcji **Aplikacje** > **Zasady ochrony aplikacji** w konsoli usługi Intune, a następnie wybierz pozycję **Utwórz zasady**. Istniejące zasady ochrony aplikacji są także dostępne do edycji. Aby zastosować zasady ochrony aplikacji zarówno do urządzeń zarządzanych, jak i niezarządzanych, przejdź na stronę **Aplikacje** i upewnij się, że opcja **Jako docelowe ustaw aplikacje na wszystkich typach urządzeń** ma domyślną wartość **Tak**. Jeśli chcesz przypisać z większą dokładnością na podstawie stanu zarządzania, ustaw opcję **Jako docelowe ustaw aplikacje na wszystkich typach urządzeń** na wartość **Nie**. 

### <a name="device-types"></a>Typy urządzeń

- **Niezarządzane**: Urządzenia niezarządzane to urządzenia, na których nie wykryto zarządzania urządzeniami mobilnymi usługi Intune. Obejmuje urządzenia zarządzane przez dostawców rozwiązań do zarządzania urządzeniami mobilnymi innych firm.
- **Urządzenia zarządzane przez usługę Intune**: Urządzenia zarządzane są zarządzane przez zarządzanie urządzeniami mobilnymi usługi Intune.
- **Administrator urządzenia z systemem Android**: Urządzenia zarządzane przez usługę Intune przy użyciu interfejsu API administrowania urządzeniami z systemem Android.
- **Android Enterprise**: Urządzenia zarządzane przez usługę Intune przy użyciu profilów służbowych systemu Android Enterprise lub pełnego zarządzania urządzeniami w systemie Android Enterprise.

> [!NOTE]
> W przypadku urządzeń z systemem Android zostanie wyświetlony monit o zainstalowanie aplikacji Intune — Portal firmy niezależnie od wybranego typu aplikacji. Jeśli na przykład wybierzesz pozycję „Android Enterprise”, nadal będą wyświetlane monity dla użytkowników z niezarządzanymi urządzeniami z systemem Android.

W przypadku systemu iOS wymagane są dodatkowe ustawienia konfiguracji aplikacji przeznaczone dla ustawień zasad ochrony aplikacji na urządzeniach zarejestrowanych w usłudze Intune:

- Ustawienie **IntuneMAMUPN** musi być skonfigurowane dla wszystkich aplikacji zarządzanych przez oprogramowanie MDM. Aby uzyskać więcej informacji, zobacz [Jak zarządzać przesyłaniem danych między aplikacjami systemu iOS/iPadOS w usłudze Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- Ustawienie **IntuneMAMDeviceID** musi być skonfigurowane dla wszystkich aplikacji innych firm i aplikacji biznesowych zarządzanych przez rozwiązanie MDM. Ustawienie **IntuneMAMDeviceID** powinno zostać skonfigurowane do tokenu identyfikacyjnego urządzenia. Na przykład `key=IntuneMAMDeviceID, value={{deviceID}}`. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS/iPadOS](app-configuration-policies-use-ios.md).
- Jeśli skonfigurowane zostanie tylko ustawienie **IntuneMAMDeviceID**, zasady ochrony aplikacji usługi Intune uznają urządzenie za niezarządzane.

> [!NOTE]
> Informacje dotyczące obsługi zasad ochrony aplikacji stosowanych na podstawie stanu zarządzania urządzeniem przez konkretną wersję systemu iOS/iPadOS zawiera sekcja [Zasady ochrony funkcji zarządzania aplikacjami mobilnymi określane na podstawie stanu zarządzania](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state).

## <a name="policy-settings"></a>Ustawienia zasad
Aby wyświetlić pełną listę ustawień zasad dla systemów iOS/iPadOS i Android, wybierz jeden z następujących linków:

- [Zasady systemu iOS](app-protection-policy-settings-ios.md)
- [Zasady systemu Android](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Następne kroki
[Monitorowanie zgodności i stanu użytkownika](app-protection-policies-monitor.md)

## <a name="see-also"></a>Zobacz także
* [Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS/iPadOS jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-ios.md)
