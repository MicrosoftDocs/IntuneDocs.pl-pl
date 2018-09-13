---
title: Rozwiązywanie problemów z instalacją aplikacji
titlesuffix: Microsoft Intune
description: Użyj okienka rozwiązywania problemów w usłudze Microsoft Intune do rozwiązywania problemów z instalacją aplikacji.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: 80b6828f4768ff79f86532ef0d39ff2100b0ef25
ms.sourcegitcommit: 11cad61c565c474a8d653181675cc1109d562626
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43241715"
---
# <a name="troubleshoot-app-installation-issues"></a>Rozwiązywanie problemów z instalacją aplikacji

Na urządzeniach zarządzanych przez oprogramowanie MDM w usłudze Microsoft Intune czasami operacje instalacji aplikacji mogą zakończyć się niepowodzeniem. W takich sytuacjach zrozumienie przyczyny niepowodzenia lub rozwiązanie problemu może okazać się wyzwaniem. Usługa Microsoft Intune udostępnia szczegóły niepowodzeń instalacji aplikacji, które ułatwiają operatorom pomocy technicznej i administratorom usługi Intune wyświetlanie informacji o aplikacji pomocnych podczas obsługi żądań użytkowników dotyczących pomocy. Okienko rozwiązywania problemów w usłudze Intune zawiera szczegóły niepowodzenia, w tym szczegółowe informacje o aplikacjach zarządzanych na urządzeniu użytkownika. W obszarze każdego urządzenia w okienku **Aplikacje zarządzane** są dostępne kompleksowe szczegóły cyklu eksploatacji. Można zapoznać się z problemami dotyczącymi instalacji, takimi jak występujące podczas tworzenia, modyfikowania i wybierania aplikacji oraz dostarczania jej na urządzenie. 

## <a name="to-review-app-troubleshooting-details"></a>Aby przejrzeć szczegóły dotyczące rozwiązywania problemów z aplikacją

Usługa Intune dostarcza szczegółowe informacje na temat rozwiązywania problemów z aplikacją w oparciu o aplikacje zainstalowane na urządzeniu określonego użytkownika.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Rozwiązywanie problemów**.
4. Kliknij pozycję **Wybierz użytkownika**, aby wybrać użytkownika na potrzeby rozwiązywania problemów. Zostanie wyświetlone okienko **Wybieranie użytkowników**.
5. Wybierz użytkownika przez wpisanie jego nazwy lub adresu e-mail. Kliknij pozycję **Wybierz** w dolnej części okienka. Informacje dotyczące rozwiązywania problemów użytkownika zostaną wyświetlone w okienku **Rozwiązywanie problemów**. 
6. Wybierz urządzenie, którego problemy chcesz rozwiązać, z listy **Urządzenia**.
    ![Okienku Rozwiązywanie problemów w usłudze Intune.](media/troubleshoot-app-install-01.png)
7. Wybierz pozycję **Aplikacje zarządzane** w okienku wybranego urządzenia. Zostanie wyświetlona lista aplikacji zarządzanych.
    ![Szczegółowe informacje dotyczące określonego urządzenia zarządzanego przez usługę Intune.](media/troubleshoot-app-install-02.png)
8. Z listy wybierz aplikację, dla której **Stan instalacji** wskazuje niepowodzenie.
    ![Wybrana aplikacja z wyświetlonymi szczegółami niepowodzenia instalacji.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Tę samą aplikację można przypisać do wielu grup, ale z inną zamierzoną akcją (intencją) dla aplikacji. Na przykład rozpoznaną intencją aplikacji będzie wartość **wykluczona**, jeśli aplikacja została wykluczona w przypadku użytkownika podczas przypisywania aplikacji. Aby uzyskać więcej informacji, zobacz [Jak są rozwiązywane konflikty intencji aplikacji](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > W przypadku wystąpienia błędu instalacji wymaganej aplikacji użytkownik lub dział pomocy technicznej będzie w stanie zsynchronizować urządzenie i ponowić próbę instalacji aplikacji.

Szczegóły błędu instalacji aplikacji będą wskazywać problem. Tych szczegółów można użyć, aby określić najlepszą akcję do podjęcia w celu rozwiązania problemu. Aby uzyskać dodatkowe informacje na temat rozwiązywania problemów z instalacją aplikacji, zobacz [Error Codes For Troubleshooting App Installation Issues](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues) (Kody błędów na potrzeby rozwiązywania problemów z instalacją aplikacji).

> [!Note]  
> Dostęp do okienka **Rozwiązywanie problemów** można też uzyskać przez przejście w przeglądarce do strony [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="app-installation-errors"></a>Błędy instalacji aplikacji

Następujące komunikaty o błędach oraz opisy zapewniają szczegółowe informacje o błędach instalacji w systemie Android i iOS. 

### <a name="android-errors"></a>Błędy systemu Android

|    Komunikat o błędzie/kod    |    Opis    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Instalowanie aplikacji nie powiodło się. (0xC7D14FB5)    |    Ten komunikat o błędzie jest wyświetlany, gdy usługa Intune nie może ustalić głównej przyczyny błędu instalacji aplikacji dla systemu Android. Podczas awarii system Android nie dostarczył żadnych informacji.       Ten błąd jest zwracany, gdy pobieranie pakietu APK zakończyło się pomyślnie, ale instalacja aplikacji nie powiodła się. Jego najczęstszą przyczyną może być nieprawidłowy plik APK, którego nie można zainstalować na urządzeniu. Możliwą przyczyną może być też zablokowanie instalacji aplikacji przez funkcję Google Play Protect ze względów bezpieczeństwa. Inna możliwa przyczyna tego błędu może polegać na tym, że urządzenie nie obsługuje danej aplikacji. Na przykład jeśli aplikacja wymaga interfejsu API w wersji 21 lub nowszej, a urządzenia aktualnie ma interfejs API w wersji 19.         Usługa Intune zwraca ten błąd dla urządzeń DA i KNOX i chociaż może zostać wyświetlone powiadomienie, które można kliknąć, aby ponowić próbę, to jeśli występuje problem z pakietem APK, kontynuacja nigdy nie nastąpi ze względu na niepowodzenie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.        |
|    Anulowano instalowanie aplikacji, ponieważ plik instalacyjny (APK) został usunięty po pobraniu, ale przed instalacją. (0xC7D14FBA)    |    Pobieranie pakietu APK zakończyło się pomyślnie, ale przed zainstalowaniem aplikacji plik został usunięty z urządzenia. Może się to zdarzyć, jeśli między pobraniem a instalacją upłynęło sporo czasu. Na przykład użytkownik anulował pierwotną instalację, odczekał jakiś czas, a następnie kliknął powiadomienie, aby spróbować ponownie.         Ten komunikat o błędzie jest zwracany jedynie dla scenariuszy DA. Scenariusze KNOX mogą być realizowane w trybie cichym. Powiadomienie o ponownej próbie jest wyświetlane, aby użytkownik mógł zaakceptować, zamiast anulować. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Anulowano instalowanie aplikacji, ponieważ proces został uruchomiony ponownie podczas instalacji. (0xC7D14FBB)    |    Urządzenie zostało uruchomione ponownie podczas procesu instalacji pliku APK, co spowodowało anulowanie instalacji.        Ten komunikat o błędzie jest zwracany dla urządzeń DA i KNOX. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby przeprowadzić ponowną próbę. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Aplikacja nie została wykryta po pomyślnym ukończeniu instalacji. (0x87D1041C)    |    Użytkownik jawnie odinstalował aplikację. Ten błąd nie jest zwracany przez klienta. Jest od generowany wtedy, gdy aplikacja została w pewnym momencie zainstalowana, ale następnie użytkownik ją odinstalował. Ten błąd powinien być wyświetlany tylko w przypadku wymaganych aplikacji. Użytkownicy mogą odinstalowywać aplikacje, które nie są wymagane. Ten błąd może wystąpić tylko na urządzeniach DA. System KNOX blokuje dezinstalację aplikacji zarządzanych.       Przy następnej synchronizacji na urządzeniu zostanie ponownie opublikowane powiadomienie, aby użytkownik przeprowadził instalację.   Użytkownik może zignorować to powiadomienie. Błąd będzie stale zgłaszany, aż do momentu, gdy użytkownik zainstaluje aplikację.    |
|    Pobieranie nie powiodło się z powodu nieoczekiwanego błędu. (0xC7D14FB2)    |    Ten błąd występuje, gdy pobieranie nie powiedzie się. Ten błąd często występuje z powodu problemów z siecią Wi-Fi lub powolnego połączenia.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby spróbować ponownie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Pobieranie nie powiodło się z powodu nieoczekiwanego błędu. Zasada zostanie ponowiona przy kolejnej synchronizacji urządzenia. (0xC7D15078)    |    Ten błąd występuje, gdy pobieranie nie powiedzie się. Ten błąd często występuje z powodu problemów z siecią Wi-Fi lub powolnego połączenia.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym.    |
|    Użytkownik końcowy anulował instalację aplikacji. (0xC7D14FB1)    |    Użytkownik jawnie odinstalował aplikację. Ten błąd jest zwracany, gdy użytkownik anuluje akcję instalacji systemu operacyjnego Android. Użytkownik kliknął przycisk anulowania po wyświetleniu monitu o instalacji systemu operacyjnego, lub kliknął poza monitem.        Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby spróbować ponownie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Proces pobierania pliku został nieoczekiwanie zatrzymany. (0xC7D15015)    |    System operacyjny zatrzymał proces pobierania przed ukończeniem. Ten błąd może wystąpić, gdy poziom naładowania baterii urządzenia jest niski lub gdy pobieranie trwa zbyt długo.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym. Usługa Intune wyświetla powiadomienie, które użytkownik może kliknąć, aby spróbować ponownie. Jeśli aplikacja jest aplikacją dostępną, powiadomienie można odrzucić. Jeśli jednak dana aplikacja jest wymagana, nie można go odrzucić.    |
|    Usługa pobierania pliku została nieoczekiwanie zatrzymana. Zasada zostanie ponowiona przy kolejnej synchronizacji urządzenia. (0xC7D1507C)    |    System operacyjny zatrzymał proces pobierania przed ukończeniem. Ten błąd może wystąpić, gdy poziom naładowania baterii urządzenia jest niski lub gdy pobieranie trwa zbyt długo.       Ten błąd jest zwracany jedynie dla scenariuszy DA. W przypadku scenariuszy KNOX użytkownik nie otrzymuje monitu o instalację, ponieważ można ją przeprowadzić w trybie cichym.    |

### <a name="ios-errors"></a>Błędy systemu iOS

|    Komunikat o błędzie/kod    |    Opis    |
|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    (0x87D12906)    |    Agent MDM firmy Apple zwrócił informację, że polecenie instalacji nie powiodło się.        |
|    (0x87D1313C)    |    Utracono połączenie sieciowe, gdy zaktualizowany adres URL usługi pobierania został wysłany na urządzenie. W szczególności nie można odnaleźć serwera z określoną nazwą hosta.    |
|    Urządzenie z systemem iOS jest aktualnie zajęte. (0x87D11388)    |    Urządzenia z systemem iOS było zajęte, co spowodowało błąd.    |
|    Instalacja aplikacji nie powiodła się. (0x87D13B64)    |    Wystąpił błąd instalacji aplikacji. Do rozwiązania tego problemu są wymagane dzienniki programu XCODE.    |
|    Aplikacja jest zarządzana, ale wygasła lub została usunięta przez użytkownika. (0x87D13B66)    |    Użytkownik jawnie odinstalował aplikację. Może być też tak, że aplikacja wygasła, ale nie można jej pobrać, lub wykrywanie aplikacji jest niezgodne z odpowiedzią z urządzenia.   Ponadto ten błąd może wystąpić na podstawie usterki platformy iOS 9.2.2.    |
|    Zaplanowano zainstalowanie tej aplikacji, ale sfinalizowanie transakcji wymaga kodu realizacji.   (0x87D13B60)    |    Ten błąd zazwyczaj występuje w przypadku aplikacji ze sklepu dla systemu iOS, które są płatne.     |
|    Aplikacja nie została wykryta po pomyślnym ukończeniu instalacji. (0x87D1041C)    |    Proces wykrywania aplikacji jest niezgodny z odpowiedzią z urządzenia.    |
|    Użytkownik odrzucił ofertę zainstalowania aplikacji. (0x87D13B62)    |    Podczas początkowej instalacji aplikacji użytkownik kliknął przycisk Anuluj.    |
|    Użytkownik odrzucił ofertę zaktualizowania aplikacji. (0x87D13B63)    |    Użytkownik końcowy kliknął przycisk Anuluj podczas procesu aktualizacji.     |
|    Nieznany błąd (0x87D103E8)    |    Wystąpił nieznany błąd instalacji aplikacji. Jest to błąd wynikowy, gdy nie wystąpią inne błędy.    |


## <a name="next-steps"></a>Następne kroki

- Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów z usługą Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](help-desk-operators.md). 
- Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Znane problemy w usłudze Microsoft Intune](known-issues.md).
- Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).