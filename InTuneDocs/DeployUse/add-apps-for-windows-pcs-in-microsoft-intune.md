---
# required metadata

title: Dodawanie aplikacji dla komputerów z systemem Windows | Usługa Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Dodawanie aplikacji dla komputerów z systemem Windows w usłudze Microsoft Intune

W tym temacie przedstawiono informacje na temat sposobu dodawania aplikacji do usługi Intune przed ich wdrożeniem.

> [!IMPORTANT]
> Informacje zawarte w tym temacie ułatwiają dodawanie aplikacji dla komputerów z systemem Windows zarządzanych za pomocą komputerowego oprogramowania klienckiego usługi Intune. Jeśli chcesz dodać aplikacje dla zarejestrowanych komputerów z systemem Windows i innych urządzeń przenośnych, zobacz [Dodawanie aplikacji dla urządzeń przenośnych w usłudze Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)..


## Dodawanie aplikacji
Wydawca oprogramowania usługi Intune służy do skonfigurowania właściwości aplikacji i przekazania jej do magazynu w chmurze za pomocą następującej procedury:

1.  W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Aplikacje** &gt; **Dodaj aplikacje**, aby uruchomić Wydawcę oprogramowania usługi Intune.

    > [!TIP]
    > Przed uruchomieniem narzędzia może być konieczne wprowadzenie nazwy użytkownika i hasła usługi Intune.



2.  Na stronie **Instalator oprogramowania** narzędzia Wydawca oprogramowania skonfiguruj następujące ustawienia:

    **Wybierz, w jaki sposób to oprogramowanie ma zostać udostępnione urządzeniom** — wybierz pozycję **Instalator oprogramowania**, a następnie określ następujące informacje:

    - **Wybierz typ pliku instalatora oprogramowania** — określa typ oprogramowania, które chcesz wdrożyć. W przypadku komputera z systemem Windows wybierz pozycję **Instalator Windows**..|
    - **Określ lokalizację plików instalacyjnych oprogramowania** — wprowadź lokalizację plików instalacyjnych lub kliknij przycisk **Przeglądaj**, aby wybrać lokalizację z listy.
    - **Dołącz dodatkowe pliki i podfoldery z tego samego folderu** — niektóre programy korzystające z Instalatora Windows wymagają plików pomocniczych, które zwykle znajdują się w folderze plików instalacyjnych. Wybierz tę opcję, jeśli chcesz również wdrożyć te pliki pomocnicze.
   W przypadku tego typu instalacji jest używana część miejsca do magazynowania w chmurze.

3.  Na stronie **Opis oprogramowania** skonfiguruj następujące ustawienia:

    W zależności od używanego pliku instalatora niektóre z tych wartości mogły zostać wprowadzone automatycznie lub mogą nie być wyświetlane.

    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Nazwa** — wprowadź nazwę aplikacji wyświetlaną w portalu firmy.<br /><br />Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownikom portalu firmy zostanie wyświetlona tylko jedna z aplikacji o tej nazwie.
    - **Opis** — wprowadź opis aplikacji. Ta informacja będzie widoczna dla użytkowników w portalu firmy.
    - **Adres URL informacji o oprogramowaniu** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o ochronie prywatności dotyczące tej aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Kategoria** — opcjonalnie wybierz jedną z wbudowanych kategorii aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Ikona** — opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.

    Jeśli na przykład chcesz opublikować aplikację o nazwie Application.msi w usłudze Intune, strona będzie wyglądała następująco:
    ![Wydawca oprogramowania komputerowego](./media/publisher-for-pc.png)

4.  Na stronie **Wymagania** wybierz wymagania, które muszą zostać spełnione, aby można było zainstalować aplikację na urządzeniu. Wybierz wartość z listy **Architektura** — wybierz, czy tę aplikację można instalować w 32-bitowych systemach operacyjnych, 64-bitowych systemach operacyjnych czy w obu tych typach systemów. Wybierz wartość z listy **System operacyjny** — wybierz minimalną wersję systemu operacyjnego, w którym można zainstalować tę aplikację.

5.  Dotyczy tylko typu pliku **Instalator Windows** (tylko z rozszerzeniem exe): na stronie **Reguły wykrywania** można skonfigurować reguły wykrywania, czy konfigurowana aplikacja jest już zainstalowana na komputerze, albo użyć domyślnych reguł wykrywania w celu automatycznego zastępowania zainstalowanych wcześniej wersji aplikacji.
    Dostępne są następujące reguły możliwe do skonfigurowania:
    - **Plik istnieje** — określ ścieżkę do pliku, który chcesz wykryć. Możesz wyszukiwać w folderze **%ProgramFiles%** (co spowoduje wyszukiwanie w folderach **Program Files**\*&lt;ścieżka&gt;* i **Program Files (x86)**\*&lt;ścieżka&gt;*) na komputerze lub w folderze **%SystemDrive%** (co spowoduje wyszukiwanie na dysku głównym komputera; zwykle jest to dysk C:).
    - **Kod produktu MSI istnieje** — kliknij przycisk **Przeglądaj**, aby wybrać plik Instalatora Windows (msi), który chcesz wykryć. 
    - **Klucz rejestru istnieje** — określ klucz rejestru rozpoczynający się od ciągu **HKEY_LOCAL_MACHINE\**. Przeszukiwane są ścieżki rejestru w wersji 32-bitowej i 64-bitowej. Jeśli określony klucz istnieje w jednej z tych lokalizacji, reguła wykrywania zostanie spełniona.

    Jeśli aplikacja spełnia dowolną ze skonfigurowanych reguł, nie zostanie zainstalowana.

6.  Dotyczy tylko typu pliku **Instalator Windows** (z rozszerzeniami msi i exe): na stronie **Argumenty wiersza polecenia** określ, czy chcesz udostępnić opcjonalne argumenty wiersza polecenia instalatora. Na przykład niektóre instalatory mogą obsługiwać argument **/q**, który umożliwia przeprowadzenie instalacji w trybie dyskretnym bez udziału użytkownika.

7.  Dotyczy tylko typu pliku **Instalator Windows** (tylko z rozszerzeniem exe): na stronie **Kody powrotne** można dodać nowe kody błędów, które będą interpretowane przez usługę Intune w przypadku instalowania aplikacji na zarządzanym komputerze z systemem Windows.
    W usłudze Intune domyślnie są używane standardowe kody powrotu umożliwiające komunikowanie powodzenia lub niepowodzenia instalacji pakietu aktualizacji: **0** — powodzenie lub **3010** — powodzenie z ponownym uruchomieniem komputera. Do tej listy można także dodawać własne kody powrotne. Jeśli określisz listę kodów powrotnych i instalacja aplikacji zwróci kod, którego nie ma na liście, zostanie on zinterpretowany jako błąd.

8.  Na stronie **Podsumowanie** przejrzyj podane informacje. Po zakończeniu kliknij pozycję **Przekaż**..

9. Kliknij pozycję **Zamknij**, aby zakończyć.

Aplikacja zostanie wyświetlona w węźle **Aplikacje** w obszarze roboczym **Aplikacje**.

## Następne kroki

Po utworzeniu aplikacji następnym krokiem jest jej wdrożenie. Aby uzyskać więcej informacji, zobacz [Wdrażanie aplikacji w usłudze Microsoft Intune](deploy-apps.md)

<!--HONumber=May16_HO1-->


