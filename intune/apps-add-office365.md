---
title: "Instalowanie aplikacji usługi Office 365 na urządzeniach przy użyciu usługi Microsoft Intune"
titlesuffix: 
description: "Dowiedz się, jak przy użyciu usługi Microsoft Intune można ułatwić instalowanie aplikacji usługi Office 365 na urządzeniach z systemem Windows 10."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 076d228f3b18416e4ecb8fd1b3543a58d037e386
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Jak przypisać aplikacje usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune

Ten typ aplikacji ułatwia przypisywanie aplikacji usługi Office 365 do zarządzanych przez Ciebie urządzeń z systemem Windows 10. Możesz także zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Pro dla usługi Office 365, jeśli masz ich licencje. Wybrane aplikacje są wyświetlane jako jeden wpis na liście aplikacji w konsoli usługi Intune.


## <a name="before-you-start"></a>Przed rozpoczęciem

>[!IMPORTANT]
>Ta metoda instalacji pakietu Office jest obsługiwana tylko w przypadku, gdy żadne inne wersje pakietu Microsoft Office nie zostały zainstalowane na urządzeniu.

- Na urządzeniach, na których wdrażasz te aplikacje, musi być zainstalowana aktualizacja Windows 10 Creators Update lub jej nowsza wersja.
- Usługa Intune obsługuje tylko dodawanie aplikacji pakietu Office z pakietu usługi Office 365.
- Jeśli jakiekolwiek aplikacje pakietu Office są otwarte, gdy usługa Intune instaluje pakiet aplikacji, instalacja może zakończyć się niepowodzeniem, a użytkownicy końcowi mogą utracić dane z niezapisanych plików.
- Ta metoda instalacji nie jest obsługiwana na urządzeniach z systemem Windows 10S, Windows Home, Windows Team, Windows Holographic i Windows Holographic for Business.
- Usługa Intune nie obsługuje instalowania aplikacji komputerowych usługi Office 365 ze sklepu Microsoft Store (znanych jako aplikacje pakietu Office Centennial) na urządzeniach, na których już wdrożono aplikacje usługi Office 365 przy użyciu usługi Intune. Jeśli zainstalujesz tę konfigurację, może dojść do utraty lub uszkodzenia danych.
- Wielokrotne wymagane lub dostępne przypisania aplikacji nie są dodawane. Nowsze przypisanie aplikacji spowoduje zastąpienie zainstalowanych wcześniej przypisań aplikacji. Jeśli na przykład pierwszy zestaw aplikacji pakietu Office zawiera program Word, a późniejszy go nie zawiera, program Word zostanie odinstalowany. Takie zachowanie nie dotyczy aplikacji Visio ani Project.


## <a name="get-started"></a>Wprowadzenie

1.  Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2.  Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3.  W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4.  W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w sekcji **Zarządzaj**.
5.  Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6.  Na liście **Typ aplikacji** w bloku **Dodaj aplikacje** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**.
    Możesz teraz skonfigurować pakiet aplikacji.

## <a name="configure-the-app-suite"></a>Konfigurowanie pakietu aplikacji

W tym kroku wybierz aplikacje pakietu Office, które chcesz przypisać do urządzeń.

1.  W bloku **Dodawanie aplikacji** wybierz pozycję **Konfiguruj pakiet aplikacji**.
2.  W bloku **Konfigurowanie pakietu aplikacji** wybierz standardowe aplikacje pakietu Office, które chcesz przypisać do urządzeń. Ponadto możesz zainstalować aplikacje dla klienta klasycznego usługi Microsoft Project Online i programu Microsoft Visio Pro dla usługi Office 365, jeśli masz ich licencje.
3.  Gdy wszystko będzie gotowe, kliknij przycisk **OK**.

>[!IMPORTANT]
> Po utworzeniu pakietu aplikacji nie można edytować jej właściwości. Aby skonfigurować inne właściwości, usuń pakiet aplikacji i utwórz nowy.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji

W tym kroku musisz podać informacje o pakiecie aplikacji. Te informacje pomagają zidentyfikować pakiet aplikacji w usłudze Intune, a także ułatwiają użytkownikom wyszukiwanie go w aplikacji Portal firmy.

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
    - **Logo** — przekaż ikonę, która jest wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3.  Gdy wszystko będzie gotowe, kliknij przycisk **OK**.

## <a name="configure-app-settings"></a>Konfigurowanie ustawień aplikacji

W tym kroku skonfigurujesz opcje instalacji pakietu aplikacji. Ustawienia są stosowane do wszystkich aplikacji dodawanych do pakietu.

1.  W bloku **Dodawanie aplikacji** wybierz pozycję **Ustawienia pakietu aplikacji**.
2.  W bloku **Ustawienia pakietu aplikacji** skonfiguruj poniższe informacje:
    - **Wersja pakietu Office** — wybierz, czy chcesz przypisać 32-bitową, czy 64-bitową wersję pakietu Office. Wersję 32-bitową można zainstalować na urządzeniach 32-bitowych i 64-bitowych, ale wersję 64-bitową można zainstalować tylko na urządzeniach 64-bitowych.
    - **Kanał aktualizacji** — wybierz sposób aktualizacji pakietu Office na urządzeniach. Aby uzyskać informacje dotyczące innych kanałów aktualizacji, zobacz [Omówienie kanałów aktualizacji usługi Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Wybierz spośród opcji:
        - **Raz na miesiąc**
        - **Raz na miesiąc (docelowy)**
        - **Półroczny**
        - **Półroczny (docelowy)**
    - **Automatycznie akceptuj umowę licencyjną użytkownika końcowego aplikacji** — wybierz tę opcję, jeśli nie wymagasz, aby użytkownicy końcowi akceptowali umowę licencyjną. Usługa Intune zaakceptuje umowę automatycznie.
    - **Użyj aktywacji na komputerze udostępnionym** — aktywacja na komputerze udostępnionym jest używana w przypadku, gdy wielu użytkowników współużytkuje komputer. Aby uzyskać więcej informacji, zobacz omówienie aktywacji na komputerze udostępnionym dla usługi Office 365.
    - **Języki** — pakiet Office jest automatycznie instalowany w obsługiwanych językach, które zostały zainstalowane w systemie Windows na urządzeniu użytkownika końcowego. Wybierz tę opcję, jeśli chcesz zainstalować dodatkowe języki z pakietem aplikacji.

>[!IMPORTANT]
> Po utworzeniu pakietu aplikacji nie można edytować jej właściwości. Aby skonfigurować inne właściwości, usuń pakiet aplikacji i utwórz nowy.

## <a name="finish-up"></a>Zakończenie

Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Dodaj**. Utworzona aplikacja jest wyświetlana na liście aplikacji.

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

- Teraz można przypisać aplikacjom wybrane grupy — zobacz [Jak przypisać aplikacje do grup](/intune-azure/manage-apps/deploy-apps).
