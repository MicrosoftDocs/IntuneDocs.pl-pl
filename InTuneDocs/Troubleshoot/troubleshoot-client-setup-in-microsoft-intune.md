---
title: "Rozwiązywanie problemów z instalacją klientów | Microsoft Intune"
description: "Rozwiązywanie typowych problemów z instalacją klientów."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: 3f9c3a69d96aa6886138de2e1b4ff8b8913cb372


---

# Rozwiązywanie problemów z instalacją klientów w usłudze Microsoft Intune
Skorzystaj z następujących informacji, aby rozwiązać typowe problemy z instalacją klientów. Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md), aby znaleźć więcej sposobów uzyskania pomocy.

## Instalacja klienta kończy się niepowodzeniem

-   Jeśli w [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) nie są wyświetlane dla komputera żadne alerty dotyczące wdrażania oprogramowania klienckiego, sprawdź łączność komputera z Internetem oraz konfigurację serwera i upewnij się, że komputer może komunikować się z adresem URL usługi: [https://manage.microsoft.com](https://manage.microsoft.com/). Następnie ponów próbę instalacji oprogramowania klienckiego.

-   Możesz ustawić wysyłanie wiadomości e-mail do wybranych adresatów, gdy występuje alert o niepowodzeniu wdrażania oprogramowania klienckiego, konfigurując regułę powiadomień w obszarze roboczym **Administrator** . Aby uzyskać więcej informacji, zobacz [Otrzymywanie powiadomień dzięki alertom w usłudze Microsoft Intune](/intune/deploy-use/get-notified-by-alerts).

-   Usługa Intune wyświetla alert krytyczny **Wdrożenie oprogramowania klienckiego nie powiodło się**, gdy nie można wdrożyć oprogramowania klienckiego. Jest on wyświetlany na stronie **Przegląd systemu** oraz na stronach **Alerty** w [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/). Oto jak sprawdzić alerty:

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycje **Alerty** &gt; **Przegląd**.

2.  Na stronie **Przegląd alertów** możesz przejrzeć następujące informacje:

    -   Trzy najważniejsze alerty, które można sortować według daty, kategorii lub ważności

    -   Łączna liczba aktywnych alertów

3.  Wybierz pozycję **Wszystkie alerty** , aby wyświetlić poniższe informacje na stronie **Alerty** . Alerty krytyczne są wyświetlane jako pierwsze:

    -   **Nazwa** — nazwa typu alertu, który wygenerował alert.

    -   **Źródło** — link do źródła alertu.  Jeśli dla progu wyświetlania typu alertu ustawiono wartość **Wszystkie**, link ten będzie wyświetlać pojedyncze urządzenie, którego alert dotyczy.  Jeśli dla progu wyświetlania typu alertu ustawiono określoną wartość, link ten będzie wyświetlać listę wszystkich urządzeń, których alert dotyczy.

    -   **Ostatnia aktualizacja** — wskazuje godzinę ostatniej modyfikacji alertu. Jeśli alert został zamknięty, wyświetlany jest czas zamknięcia alertu.

    -   **Ważność** — wskazuje ważność alertu.

## Pakiet rejestracyjny komputera nie jest pobierany
**Problem:** Podczas próby zarejestrowania komputera występują następujące problemy:
-  Pobieranie pakietu rejestracyjnego kończy się niepowodzeniem
-  Okno dialogowe pobierania jest wyświetlane, ale limit czasu zostaje przekroczony

**Rozwiązanie:** Upewnij się, że w okresie pobierania w przeglądarce używanej do pobierania włączone jest pobieranie, a zaszyfrowane pliki można zapisywać na dysku lokalnym.

## Instalacja klienta zawiesza się. Kod błędu: 0x80040154
**Problem:**

-  Instalacja klienta zawiesza się podczas rejestracji

-  Nie można zarejestrować urządzenia

-  Błąd 0x80040154 w pliku WindowsUpdate.log

Może to być spowodowane brakiem krytycznych aktualizacji oprogramowania na komputerze.

**Rozwiązanie:** Upewnij się, że Twoje zasady aktualizacji oprogramowania umożliwiają instalację aktualizacji krytycznych, jak opisano w temacie [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)


## Błędy związane z zasadami usługi Microsoft Intune w pliku policyplatform.log
W przypadku urządzeń z systemem Windows niezarządzanych przez usługę MDM błędy zasad w pliku policyplatform.log mogą wynikać z innych niż domyślne ustawień w Kontroli konta użytkownika systemu Windows na urządzeniu. Niektóre inne niż domyślne ustawienia funkcji Kontroli konta użytkownika mogą wpływać na instalacje klienta usługi Microsoft Intune i wykonywanie zasad.

### Aby rozwiązać problemy z Kontrolą konta użytkownika

1.  Wycofaj komputer w sposób opisany w temacie [Wycofywanie danych i urządzeń z zarządzania usługi Microsoft Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Zaczekaj 20 minut na usunięcie oprogramowania klienckiego.

    > [!NOTE]
    > Nie należy próbować usuwać klienta z poziomu opcji Programy i funkcje.

3.  W menu start wpisz wartość **Kontrola konta użytkownika**, aby otworzyć ustawienia Kontroli konta użytkownika.

4.  Przesuń suwak powiadomień na ustawienie domyślne.

## Co zrobić, jeśli klient nie zostanie odinstalowany z poziomu konsoli administratora usługi Microsoft Intune

### Aby usunąć oprogramowanie klienckie za pomocą narzędzia wiersza polecenia usługi Microsoft Intune

1.  Otwórz wiersz polecenia w trybie administratora.

2.  Przejdź do folderu *%programfiles%\Microsoft\OnlineManagement\Common*.

3.  Uruchom następujące polecenie ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## Kody błędów instalacji klienta
W poniższej tabeli opisano kody błędów, które są wyświetlane w obszarze roboczym **Alerty** w przypadku niepowodzenia instalacji oprogramowania klienckiego. Zawiera ona sugestie dotyczące rozwiązywania problemów reprezentowanych przez poszczególne kody błędów.

|Kod błędu|Możliwy problem|Sugerowane rozwiązanie|
|--------------|--------------------|------------------------|
|**0x80CF0437**|W zegarze na komputerze klienckim nie ustawiono prawidłowego czasu.|Upewnij się, że dla zegara i strefy czasowej na komputerze klienckim ustawiono prawidłową godzinę i strefę czasową.|
|**0x80240438**, **0x80CF0438**, **0x80CF401B**|Nie można nawiązać połączenia z usługą Intune. Sprawdź ustawienia serwera proxy klienta.|Sprawdź, czy konfiguracja serwera proxy na komputerze klienckim jest obsługiwana przez usługę Intune i czy komputer kliencki ma dostęp do Internetu. Aby uzyskać więcej informacji dotyczących obsługiwanych konfiguracji serwera proxy, zobacz [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80CF402C**|Nie można nawiązać połączenia z usługą Intune. Sprawdź łączność sieciową.|Sprawdź, czy komputer ma łączność sieciową. Upewnij się, że jest podłączony kabel sieciowy lub że sieć bezprzewodowa jest włączona.|
|**0x80240438, 0x80CF0438**|Nie skonfigurowano ustawień serwera proxy w programie Internet Explorer i w systemie lokalnym.|Sprawdź ustawienia serwera proxy klienta i upewnij się, że konfiguracja serwera proxy na komputerze klienckim jest obsługiwana przez usługę Intune i że komputer kliencki ma dostęp do Internetu. Aby uzyskać więcej informacji dotyczących obsługiwanych konfiguracji serwera proxy, zobacz [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80043001**|Pakiet rejestracyjny jest nieaktualny.|Pobierz i zainstaluj bieżący pakiet oprogramowania klienckiego z poziomu obszaru roboczego **Administrator** . Aby uzyskać instrukcje, zobacz temat [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).|
|**0x80043004**|Subskrypcja nie istnieje lub jest wyłączona.|Sprawdź, czy Twoje konto i subskrypcja usługi Intune są nadal aktywne. Aby wyświetlić ustawienia swojego konta, zaloguj się do niego w [centrum administracyjnym usługi Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043002**|Konto jest w trybie konserwacji.|Nie można zarejestrować nowych komputerów klienckich, gdy konto jest w trybie konserwacji. Aby wyświetlić ustawienia swojego konta, zaloguj się do niego w [centrum administracyjnym usługi Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043003**|Konto zostało usunięte.|Sprawdź, czy Twoje konto i subskrypcja usługi Intune są nadal aktywne. Aby wyświetlić ustawienia swojego konta, zaloguj się do niego.|
|**0x80043005**|Komputer kliencki został wycofany.|Poczekaj kilka godzin, usuń wszelkie wcześniejsze wersje oprogramowania klienckiego z komputera, a następnie ponów próbę instalacji oprogramowania klienckiego. Instrukcje znajdują się w powyższym temacie **Co zrobić, jeśli klient nie zostanie odinstalowany z poziomu konsoli administratora usługi Microsoft Intune**.|
|**0x80043006**|Osiągnięto maksymalną liczbę licencji na stanowiska dozwoloną dla konta.|Twoja organizacja musi zakupić dodatkowe licencje na stanowiska, aby można było zarejestrować więcej komputerów klienckich w usłudze.|
|**0x80043007**|Nie można odnaleźć pliku certyfikatu w folderze programu instalacyjnego.|Wyodrębnij wszystkie pliki przed rozpoczęciem instalacji. Nie zmieniaj nazw wyodrębnionych plików ani ich nie przenoś: wszystkie pliki muszą znajdować się w tym samym folderze — w przeciwnym razie instalacja się nie powiedzie. Aby uzyskać więcej informacji, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).|
|**0x8024D015**, **0x00240005**, **0x80070BC2**, **0x80070BC9**, **0x80CFD015**|Nie można zainstalować oprogramowania, ponieważ komputer kliencki oczekuje na ponowne uruchomienie.|Uruchom ponownie komputer, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|**0x80070032**|Na komputerze klienckim nie odnaleziono co najmniej jednego wymagania wstępnego dotyczącego instalacji oprogramowania klienckiego.|Upewnij się, że na komputerze klienckim są zainstalowane wszystkie wymagane aktualizacje, a następnie ponów próbę instalacji oprogramowania klienckiego. Aby uzyskać więcej informacji na temat wymagań wstępnych dotyczących instalowania oprogramowania klienckiego, zobacz [Wymagania usługi Microsoft Intune dotyczące infrastruktury sieciowej](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0x80043008**|Nie można uruchomić usługi Microsoft Online Management Updates.|Skontaktuj się z pomocą techniczną zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md).|
|**0x80043009**|Komputer kliencki jest już zarejestrowany w usłudze.|Aby móc ponownie zarejestrować komputer kliencki w usłudze, musisz go najpierw wycofać. Aby uzyskać instrukcje, zobacz [Wycofywanie urządzeń z zarządzania usługi Microsoft Intune](/intune/deploy-use/retire-devices-from-microsoft-intune-management).|
|**0x8004300B**|Nie można uruchomić pakietu instalacyjnego oprogramowania klienckiego, ponieważ wersja systemu Windows uruchomiona na kliencie jest nieobsługiwana.|Usługa Intune nie obsługuje wersji systemu Windows uruchomionej na komputerze klienckim. Aby wyświetlić listę obsługiwanych systemów operacyjnych, zobacz [Wymagania usługi Microsoft Intune dotyczące infrastruktury sieciowej](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0xAB2**|Instalator Windows nie może uzyskać dostępu do środowiska wykonawczego VBScript w celu wykonania akcji niestandardowej.|Przyczyną tego błędu jest próba wykonania akcji niestandardowej opartej na dołączanych dynamicznie bibliotekach (DLL). Podczas rozwiązywania problemu z biblioteką DLL może być konieczne użycie narzędzi opisanych w artykule KB198038 z bazy wiedzy pomocy technicznej firmy Microsoft: [Useful Tools for Package and Deployment Issues](http://go.microsoft.com/fwlink/?LinkID=234255).|
|**0x8004300f**|Nie można zainstalować oprogramowania, ponieważ jest już zainstalowany klient programu System Center Configuration Manager.|Usuń klienta programu Configuration Manager, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|**0x80043010**|Nie można zainstalować oprogramowania, ponieważ jest już zainstalowany klient programu Open Mobile Alliance Device Management (OMADM).|Wyrejestruj klienta programu OMADM, a następnie ponów próbę instalacji oprogramowania klienckiego.|
Jeśli problemy z instalacją występują nadal, skontaktuj się z pomocą techniczną zgodnie z opisem w temacie [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md). Przygotuj dziennik rejestracji komputerów klienckich (znajdujący się w pliku %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log i %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollement.log) oraz dziennik usługi Windows Update (znajdujący się w pliku %*windir*%\windowsupdate.log) do przedstawienia inżynierom pomocy technicznej.

### Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).



<!--HONumber=Jul16_HO4-->


