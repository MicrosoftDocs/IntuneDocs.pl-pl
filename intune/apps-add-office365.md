---
title: "Instalowanie aplikacji usługi Office 365 ProPlus na urządzeniach z systemem Windows 10 przy użyciu usługi Intune"
titleSuffix: Intune on Azure
description: "Dowiedz się, jak przy użyciu usługi Intune można ułatwić instalowanie aplikacji usługi Office 365 na urządzeniach z systemem Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f6a3cdc2b5d95f57f1ffc1f68b6748b357f2ef4
ms.sourcegitcommit: 21a9db380956a50031dbea360b4c76664cbc2768
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2017
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Jak przypisać aplikacje usługi Office 365 ProPlus 2016 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune

Ten typ aplikacji ułatwia przypisywanie aplikacji usługi Office 365 ProPlus 2016 do zarządzanych przez Ciebie urządzeń z systemem Windows 10. Ponadto można także zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Pro dla usługi Office 365, jeśli masz ich licencje. Wybrane aplikacje są wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

>[!IMPORTANT]
>Ta metoda instalacji pakietu Office jest obsługiwana tylko w przypadku, gdy żadne inne wersje pakietu Microsoft Office nie zostały zainstalowane na urządzeniu.

- Na urządzeniach, na których wdrażasz te aplikacje, musi być zainstalowana aktualizacja Windows 10 Creators Update lub jej nowsza wersja.
- Usługa Intune obsługuje tylko dodawanie aplikacji pakietu Office z pakietu usługi Office 365 ProPlus 2016.
- Jeśli jakiekolwiek aplikacje pakietu Office są otwarte, gdy usługa Intune instaluje pakiet aplikacji, użytkownicy końcowi mogą utracić dane z niezapisanych plików.
- Jeśli instalujesz pakiet Office na urządzeniu z już zainstalowanym pakietem Office, zapoznaj się z poniższymi zagadnieniami:
    - Niezależnie od używanej wersji pakietu Office nie możesz zainstalować 32-bitowych i 64-bitowych produktów pakietu Office na jednym urządzeniu.
    - Nie możesz zainstalować tej samej wersji modułu Szybka instalacja ani wersji instalatora MSI dla pakietu Office na tym samym urządzeniu, ale możesz zainstalować różne wersje główne.
    - Jeśli masz już starszą wersję pakietu Office, którą zainstalowano przy użyciu modułu Szybka instalacja, musisz usunąć wszystkie aplikacje, które chcesz zastąpić nowszą wersją. Jeśli na przykład masz starszą wersję programu Word na urządzeniu i chcesz przypisać najnowszą wersję, najpierw musisz usunąć starą wersję.
    - Jeśli urządzenie ma już zainstalowaną usługę Office 365, przypisanie pakietu Office 365 ProPlus 2016 na urządzeniu może oznaczać, że trzeba zmienić poziom subskrypcji pakietu Office.


## <a name="get-started"></a>Wprowadzenie

1.  Zaloguj się do portalu Azure Portal.
2.  Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3.  W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5.  Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6.  W bloku **Dodawanie aplikacji** wybierz pozycję **Pakiet usługi Office 365 ProPlus (Windows 10)**.

## <a name="configure-the-app-suite"></a>Konfigurowanie pakietu aplikacji

W tym kroku wybierz aplikacje pakietu Office, które chcesz przypisać do urządzeń.

1.  W bloku **Dodawanie aplikacji** wybierz pozycję **Konfiguruj pakiet aplikacji**.
2.  W bloku **Konfigurowanie pakietu aplikacji** wybierz standardowe aplikacje pakietu Office, które chcesz przypisać do urządzeń. Ponadto możesz zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Pro dla usługi Office 365, jeśli masz ich licencje.
3.  Gdy wszystko będzie gotowe, kliknij przycisk **OK**.

>[!IMPORTANT]
> Po utworzeniu pakietu aplikacji nie można edytować jej właściwości. Aby skonfigurować inne właściwości, usuń pakiet aplikacji i utwórz nowy.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji

W tym kroku podaj informacje o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet w konsoli usługi Intune, a także ułatwiają użytkownikom końcowym wyszukiwanie go w aplikacji Portal firmy.

1.  W bloku **Dodawanie aplikacji** wybierz pozycję **Informacje o pakiecie aplikacji**.
2.  W bloku **Informacje o pakiecie aplikacji** podaj następujące informacje: 
    - **Nazwa pakietu** — wprowadź nazwę pakietu aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy pakietów są unikatowe. Jeśli dana nazwa pakietu aplikacji występuje dwa razy, użytkownicy portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis pakietu** — wprowadź opis pakietu aplikacji. Możesz na przykład podać listę aplikacji wybranych do uwzględnienia.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Kategoria** — opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie pakietu aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy** — wyróżnij pakiet aplikacji na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
    - **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Przekaż ikonę** — przekaż ikonę, która jest wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3.  Gdy wszystko będzie gotowe, kliknij przycisk **OK**.

## <a name="configure-app-settings"></a>Konfigurowanie ustawień aplikacji

W tym kroku skonfigurujesz opcje instalacji pakietu aplikacji. Ustawienia są stosowane do wszystkich aplikacji dodawanych do pakietu.

1.  W bloku **Dodawanie aplikacji** wybierz pozycję **Ustawienia pakietu aplikacji**.
2.  W bloku **Ustawienia pakietu aplikacji** skonfiguruj poniższe informacje: 
    - **Wersja pakietu Office** — wybierz, czy chcesz przypisać 32-bitową, czy 64-bitową wersję pakietu Office. Wersję 32-bitową można zainstalować na urządzeniach 32-bitowych i 64-bitowych, ale wersję 64-bitową można zainstalować tylko na urządzeniach 64-bitowych.
    - **Kanał aktualizacji** — wybierz sposób aktualizacji pakietu Office na urządzeniach. Aby uzyskać informacje dotyczące innych kanałów aktualizacji, zapoznaj się z omówieniem kanałów aktualizacji usługi Office 365 ProPlus. Wybierz spośród opcji: 
        - **Bieżący**
        - **Odroczony**
        - **Bieżący kanał pierwszego wydania**
        - **Odroczony kanał pierwszego wydania**
    - **Automatycznie akceptuj umowę licencyjną użytkownika końcowego aplikacji** — wybierz tę opcję, jeśli nie wymagasz, aby użytkownicy końcowi akceptowali umowę licencyjną. Usługa Intune zaakceptuje umowę automatycznie.
    - **Użyj aktywacji na komputerze udostępnionym** — aktywacja na komputerze udostępnionym jest używana w przypadku, gdy wielu użytkowników współużytkuje komputer. Aby uzyskać więcej informacji, zobacz omówienie aktywacji na komputerze udostępnionym dla usługi Office 365 ProPlus.
    - **Języki** — pakiet Office jest automatycznie instalowany w obsługiwanych językach, które zostały zainstalowane w systemie Windows na urządzeniu użytkownika końcowego. Wybierz tę opcję, jeśli chcesz zainstalować dodatkowe języki z pakietem aplikacji.

>[!IMPORTANT]
> Po utworzeniu pakietu aplikacji nie można edytować jej właściwości. Aby skonfigurować inne właściwości, usuń pakiet aplikacji i utwórz nowy.

## <a name="finish-up"></a>Zakończenie

Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Zapisz**. Utworzona aplikacja jest wyświetlana na liście aplikacji.

## <a name="error-codes-when-installing-the-app-suite"></a>Kody błędów występujących podczas instalowania pakietu aplikacji

W poniższej tabeli przedstawiono listę kodów typowych błędów, które mogą wystąpić, oraz ich znaczenie.

### <a name="status-for-office-csp"></a>Stan dostawcy CSP pakietu Office: 

||||
|-|-|-|
|Stan|Etap|Opis|
|1460 (ERROR_TIMEOUT)|Pliki do pobrania|Nie można pobrać Narzędzia wdrażania pakietu Office|    
|13 (ERROR_INVALID_DATA)|-|Nie można zweryfikować podpisu pobranego Narzędzia wdrażania pakietu Office| 
|Kod błędu z zasad CertVerifyCertificateChainPolicy|-|Nie można sprawdzić certyfikatów pobranego Narzędzia wdrażania pakietu Office|    
|997|PWT|Instalowanie| 
|0|Po instalacji|Instalacja zakończona pomyślnie|    
|1603 (ERROR_INSTALL_FAILURE)|-|Nieudane sprawdzanie wymagań wstępnych, takich jak:<br>— SxS (nastąpiła próba instalacji po zainstalowaniu instalatora MSI 2016)<br>— niezgodność wersji<br>— itd.|     
|0x8000ffff (E_UNEXPECTED)|-|Podjęto próbę odinstalowania w sytuacji, gdy na maszynie nie ma modułu Szybka instalacja pakietu Office.|    
|17002|-|Nie można ukończyć scenariusza (instalacja). Możliwe przyczyny:<br>— Instalacja została anulowana przez użytkownika<br>— Instalacja została anulowana przez inną instalację<br>— Brak miejsca na dysku podczas instalacji<br>— Nieznany identyfikator języka| 
|17004|-|Nieznane jednostki SKU|   


### <a name="office-deployment-tool-error-codes"></a>Kody błędów Narzędzia wdrażania pakietu Office

|||||
|-|-|-|-|
|Scenariusz|Kod powrotu|Interfejs użytkownika|Uwaga| 
|Podjęto działania związane z odinstalowywaniem w sytuacji, gdy nie ma aktywnego modułu Szybka instalacja|-2147418113, 0x8000ffff lub 2147549183|Kod błędu: 30088-1008<br>Kod błędu: 30125-1011 (404)|Narzędzie wdrażania pakietu Office| 
|Instalacja, gdy zainstalowano wersję instalatora MSI|1603|-|Narzędzie wdrażania pakietu Office| 
|Instalacja anulowana przez użytkownika lub inną instalację|17002|-|Szybka instalacja| 
|Próba zainstalowania wersji 64-bitowej na urządzeniu z zainstalowaną wersją 32-bitową|1603|-|Kod zwrotny Narzędzia wdrażania pakietu Office| 
|Próba zainstalowania nieznanej jednostki SKU (to nie jest rzeczywisty przypadek użycia dostawcy CSP pakietu Office, ponieważ należy przekazywać tylko prawidłowe jednostki SKU)|17004|-|Szybka instalacja| 
|Brak miejsca|17002|-|Szybka instalacja| 
|Nie można uruchomić modułu Szybka instalacja (nieoczekiwana sytuacja)|17000|-|Szybka instalacja| 
|Moduł Szybka instalacja nie mógł umieścić scenariusza w kolejce (nieoczekiwana sytuacja)|17001|-|Szybka instalacja| 

## <a name="next-steps"></a>Następne kroki

Teraz można przypisać aplikacje do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps) (Jak przypisać aplikacje do grupy).

             


