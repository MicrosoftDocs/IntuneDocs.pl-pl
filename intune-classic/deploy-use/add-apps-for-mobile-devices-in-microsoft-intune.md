---
title: Dodawanie aplikacji dla zarejestrowanych urządzeń
description: Przed wdrożeniem aplikacji należy ją dodać do usługi Intune. Będzie ona wówczas dostępna w konsoli usługi Intune, w której można wdrożyć aplikację i zarządzać nią.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 01/11/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4e53acad9fb2cf1e6c18b71900c6b671dd031e98
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="add-apps-for-enrolled-devices-to-intune"></a>Dodawanie aplikacji dla zarejestrowanych urządzeń do usługi Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Aby można było wdrożyć aplikację i zarządzać nią, należy ją najpierw dodać do usługi Microsoft Intune. W tym temacie przedstawiono sposób dodawania aplikacji dla zarejestrowanych urządzeń.


> [!IMPORTANT]
> Informacje zawarte w tym temacie ułatwiają dodawanie aplikacji, które mają zostać wdrożone na zarejestrowanych urządzeniach i zarejestrowanych komputerach z systemem Windows. Aby dodać aplikacje dla komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune, zobacz [Dodawanie aplikacji dla komputerów z systemem Windows w usłudze Microsoft Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## <a name="add-the-app"></a>Dodawanie aplikacji
Narzędzie Wydawca oprogramowania usługi Intune służy do konfigurowania właściwości aplikacji i (jeśli to możliwe) przekazywania aplikacji do magazynu w chmurze. Użyj następującej procedury:

1. W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Aplikacje** &gt; **Dodaj aplikacje**, aby uruchomić narzędzie Wydawca oprogramowania usługi Intune.

   > [!TIP]
   > Przed uruchomieniem narzędzia może być konieczne wprowadzenie nazwy użytkownika i hasła usługi Intune.

2. Na stronie **Instalator oprogramowania** Wydawcy wybierz jedną z następujących opcji dla pozycji **Wybierz, w jaki sposób to oprogramowanie ma zostać udostępnione urządzeniom**:
   - **Instalator oprogramowania** — dla aplikacji z rozszerzeniem **msi**:
       - **Wybierz typ pliku instalatora oprogramowania**. To ustawienie określa typ oprogramowania, które chcesz wdrożyć. Jeśli na przykład chcesz zainstalować aplikację systemu iOS, wybierz pozycję **Pakiet aplikacji dla systemu iOS (plik &#42;.ipa)**.
       - **Określ lokalizację plików instalacyjnych oprogramowania**. Wprowadź lokalizację plików instalacyjnych lub wybierz pozycję **Przeglądaj**, aby wybrać lokalizację z listy.
       - **Dołącz dodatkowe pliki i podfoldery z tego samego folderu**. Ta opcja dotyczy tylko typu pliku **Instalator Windows**.<br>Niektóre programy korzystające z Instalatora Windows wymagają plików pomocniczych, które zwykle znajdują się w folderze plików instalacyjnych. Wybierz tę opcję, jeśli chcesz również wdrożyć te pliki.<br>W przypadku tego typu instalacji jest używana część miejsca do magazynowania w chmurze.

   -   **Link zewnętrzny** — dla aplikacji, które mają zostać utworzone za pośrednictwem linku do sklepu z aplikacjami:

       - **Podaj adres URL**. Podaj adres URL prowadzący do jednego z następujących elementów:
           - Adres URL sklepu z aplikacjami dla aplikacji, którą chcesz wdrożyć. Jeśli na przykład chcesz wdrożyć aplikację Pulpit zdalny firmy Microsoft dla systemu Android, podaj adres **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android**.<br>Aby znaleźć adres URL aplikacji, przy użyciu aparatu wyszukiwania znajdź stronę sklepu zawierającą aplikację. Aby na przykład znaleźć aplikację Pulpit zdalny, możesz wyszukać frazę **Pulpit zdalny firmy Microsoft dla systemu Android**.
           - Witryna sieci Web. Usługa Intune wdroży na urządzeniu ikonę skrótu prowadzącą do witryny (zwaną klipem sieci Web).
           - Aplikacja sieci Web. Usługa Intune wdroży na urządzeniu ikonę skrótu prowadzącą do aplikacji.
       - **Wymagaj otwierania tego linku przez program Managed Browser (tylko systemy Android i iOS)**. Jeśli wdrażasz link do witryny lub aplikacji sieci Web dla użytkowników, będą oni mogli otworzyć je tylko w programie Intune Managed Browser. Ten program musi być zainstalowany na urządzeniu.<br>Aby uzyskać więcej informacji o aplikacji Managed Browser, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).<br>W przypadku tego typu instalacji nie jest używane miejsce do magazynowania w chmurze.

   -   **Zarządzana aplikacja systemu iOS ze sklepu App Store** — w przypadku bezpłatnych aplikacji ze sklepu iTunes, którymi chcesz zarządzać za pomocą zasad zarządzania urządzeniami mobilnymi (MAM):

       - **Podaj adres URL**. Wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz wdrożyć. Jeśli na przykład chcesz wdrożyć aplikację Foldery robocze firmy Microsoft dla systemu iOS, podaj adres **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8**.<br>W przypadku tego typu instalacji nie jest używane miejsce do magazynowania w chmurze.

       Jeśli na przykład chcesz wdrożyć aplikację Microsoft Word ze sklepu iTunes na urządzeniach, strona będzie wyglądała następująco:

       ![Wydawcy oprogramowania usługi Intune](./media/publisher-for-mobile.png)

> [!NOTE]
> Kiedy dodajesz i wdrażasz aplikację ze sklepu, użytkownicy końcowi muszą mieć konto w danym sklepie, aby móc zainstalować daną aplikację.

3.  Na stronie **Opis oprogramowania** skonfiguruj następujące ustawienia:

    > [!TIP]
    > W zależności od używanego typu instalatora niektóre z tych wartości mogły zostać wprowadzone automatycznie.

    - **Wydawca**. Wprowadź nazwę wydawcy aplikacji.
    - **Nazwa**. Wprowadź nazwę aplikacji wyświetlaną w Portalu firmy.<br>Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis**. Wprowadź opis aplikacji. Ta informacja będzie widoczna dla użytkowników w Portalu firmy.
    - **Adres URL informacji o oprogramowaniu**. To ustawienie jest dostępne tylko w przypadku wybrania pozycji **Instalator oprogramowania**. Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Adres URL zasad ochrony prywatności**. To ustawienie jest dostępne tylko w przypadku wybrania pozycji **Instalator oprogramowania**. Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Kategoria** (opcjonalnie). Wybierz jedną z wbudowanych kategorii aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetlaj jako polecaną aplikację i wyróżnij w Portalu firmy**. Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Ikona** (opcjonalnie). Przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.

        W tym przykładzie skonfigurowano opis aplikacji Microsoft Word dla systemu iOS:

        ![Przykład opisu oprogramowania](./media/ios-software-description.png)

4.  Na stronie **Wymagania** wybierz wymagania, które muszą zostać spełnione, aby aplikację można było zainstalować na urządzeniu. Na przykład w przypadku pakietu aplikacji dla systemu iOS możesz wybrać minimalną wymaganą wersję systemu iOS. Ponadto możesz wybrać wymagany typ urządzenia, na przykład iPhone lub iPad.

    > [!TIP]
    > Strona **Wymagania** jest wyświetlana tylko dla niektórych typów aplikacji.

5.  Kolejne strony kreatora są wyświetlane po wybraniu typu pliku **Instalator Windows**. Ten typ pliku jest używany podczas wdrażania oprogramowania dla komputerów z systemem Windows 10 lub nowszym zarejestrowanych w usłudze Intune.

6.  Na stronie **Podsumowanie** przejrzyj podane informacje. Po zakończeniu wybierz pozycję **Przekaż**.

7.  Wybierz pozycję **Zamknij**, aby zakończyć.

Aplikacja zostanie wyświetlona w węźle **Aplikacje** w obszarze roboczym **Aplikacje**.

## <a name="example---deploying-msi-applications-to-windows-10-devices"></a>Przykład — wdrażanie aplikacji MSI na urządzeniach z systemem Windows 10
W tym czterominutowym filmie wideo objaśniono sposób wdrażania aplikacji instalatora systemu Windows (aplikacji MSI) na zarejestrowanych urządzeniach z systemem Windows 10.<br><br>

<iframe src="https://channel9.msdn.com/Series/How-to-Control-the-Uncontrolled/6--How-to-Deploy-MSI-Applications-to-Windows-10-Using-Intune-and-Mobile-Device-Management-MDM/player" width="640" height="360" allowFullScreen frameBorder="0"></iframe>

## <a name="next-steps"></a>Następne kroki

Po utworzeniu aplikacji następnym krokiem jest jej wdrożenie. Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps.md).
