---
title: "Informacje o operacjach — korzystanie z raportów | Microsoft Intune"
description: "Tworzenie raportów dotyczących oprogramowania, sprzętu i licencji na oprogramowanie w organizacji i zarządzanie nimi."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 8d5dd37c6e41c6c9bb40b9bff6696583d4215730


---

# Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów
Informacje w tym temacie mają na celu ułatwienie tworzenia raportów usługi Microsoft Intune zawierających informacje dotyczące oprogramowania, sprzętu i licencji na oprogramowanie w organizacji oraz zarządzanie tymi raportami.

## Korzystanie z raportów
Raporty usługi Intune zawierają informacje dotyczące oprogramowania, sprzętu i licencji na oprogramowanie w organizacji. Raporty ułatwiają potwierdzanie bieżącego zapotrzebowania i prognozowanie wydatków w przyszłości. Obszar roboczy **Raporty** zawiera narzędzia służące do tworzenia raportów i zarządzania nimi. Aby uzyskać więcej informacji o raportach, zobacz [Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](understand-microsoft-intune-operations-by-using-reports.md).

### Typy raportów

|Typ raportu|Opis|
|---------------|---------------|
|**Raporty aktualizacji**|Zawierają informacje o aktualizacjach oprogramowania, które zakończyły się pomyślnie na komputerach w organizacji, oraz o aktualizacjach zakończonych niepowodzeniem, oczekujących lub wymaganych. Aby uzyskać więcej informacji o aktualizacjach oprogramowania, zobacz [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Raporty dotyczące wykrytego oprogramowania**|Zawierają informacje o oprogramowaniu zainstalowanym na komputerach i wersjach oprogramowania. Wyświetlane informacje można filtrować według wydawcy oprogramowania i kategorii oprogramowania. Można rozwinąć aktualizacje na liście w celu wyświetlenia większej liczby szczegółów (takich jak komputery, na których zainstalowano aktualizacje), klikając strzałkę kierunkową obok elementu listy.<br /><br />Po wycofaniu komputerów lub zmianie ich członkostwa w grupach w usłudze Intune może upłynąć kilka minut, zanim zmiany zostaną odzwierciedlone w raporcie dotyczącym wykrytego oprogramowania. W celu uzyskania najdokładniejszych danych spisu oprogramowania poczekaj kilka minut po wycofaniu komputerów lub zmianie ich członkostwa w grupach przed uruchomieniem raportu dotyczącego wykrytego oprogramowania, w którym są uwzględnione te komputery.|
|**Raporty dotyczące spisu komputerów**|Zawierają informacje o zarządzanych komputerach w organizacji. Ten raport służy do planowania zakupów sprzętu i uzyskiwania informacji o zapotrzebowaniu na sprzęt użytkowników w organizacji. Więcej informacji dotyczących pracy z zarządzanymi komputerami można znaleźć w temacie [Zarządzanie komputerami z systemem Windows przy użyciu usługi Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Raporty dotyczące spisu urządzeń przenośnych**|Zawierają informacje o urządzeniach przenośnych w organizacji. Wyświetlane informacje można filtrować według grup, urządzeń ze zdjętymi zabezpieczeniami lub z możliwością dostępu z uprawnieniami administratora oraz według systemu operacyjnego.|
|**Raporty o zakupach licencji**|Zawierają tytuły wszystkich licencjonowanych programów w wybranych grupach licencji na podstawie umów licencyjnych. Jeśli informacje o licencji oprogramowania nie były odświeżane w ciągu 24 godzin, zostaną odświeżone podczas generowania raportu dotyczącego licencji. Raport dotyczący licencji nie jest dokładnym wyliczeniem tytułów używanego oprogramowania lub potwierdzeniem zgodności z umowami. Raport jest narzędziem ułatwiającym podejmowanie decyzji dotyczących licencjonowania w organizacji. Usługa Intune może nie wykrywać niektórych produktów, które mogą mieć licencję zbiorczą firmy Microsoft. Dostępne są następujące filtry:<br /><br />**Wszystkie umowy** — Pokazuje wszystkie licencjonowane programy zarządzane przez usługę Intune.<br /><br />**Umowy licencjonowania zbiorowego** — Pokazuje tylko oprogramowanie z witryny VLSC.<br /><br />**Inne umowy licencyjne oprogramowania** — Pokazuje oprogramowanie zarządzane poza witryną VLSC.|
|**Raporty dotyczące instalacji licencji**|Umożliwiają porównanie oprogramowania zainstalowanego na komputerach w organizacji z zakresem bieżącej umowy licencyjnej w witrynie Volume Licensing Service Center (VLSC). Dostępne są następujące filtry:<br /><br />**Wszystkie umowy** — Pokazuje wszystkie licencjonowane programy zarządzane przez usługę Intune.<br /><br />**Umowy licencjonowania zbiorowego** — Pokazuje tylko oprogramowanie z witryny VLSC.<br /><br />**Inne umowy licencyjne oprogramowania** — Pokazuje oprogramowanie zarządzane poza witryną VLSC.|
|**Raporty dotyczące warunków i postanowień**|Wskazują, czy użytkownicy zaakceptowali wdrożone warunki i postanowienia oraz która wersja została zaakceptowana. Można wybrać maksymalnie 10 użytkowników, dla których raport będzie zawierać informacje o wszystkich wdrożonych warunkach i postanowieniach zaakceptowanych przez te osoby lub informacje o stanie akceptacji określonych warunków wdrożone do tych użytkowników.|
|**Raporty dotyczące niezgodności aplikacji**|Zawierają informacje dotyczące użytkowników, którzy mają zainstalowane aplikacje znajdujące się na liście zgodnych i niezgodnych aplikacji. Ten raport umożliwia znalezienie użytkowników i urządzeń niezgodnych z zasadami firmy dotyczącymi aplikacji.|
|**Raporty o zgodności certyfikatów**|Zawierają informacje o certyfikatach, które zostały wydane dla użytkowników i urządzeń za pośrednictwem protokołu SCEP lub PKCS #12 (PFX). Ten raport umożliwia znalezienie wydanych, wygasłych i odwołanych certyfikatów.|
|**Raporty historii urządzeń**|Zawierają dziennik historyczny akcji wycofania, czyszczenia i usuwania. Użyj tego raportu, aby zobaczyć, kto w przeszłości zainicjował akcje na urządzeniach.|
|**Raporty zaświadczania o kondycji**|Pokazują kondycję urządzeń przenośnych.|
|**Raport sprzętu z systemem Mac OS X**|Wyświetla szczegóły sprzętu dla wszystkich zarejestrowanych urządzeń z systemem Mac OS X w wybranych grupach. Aby uzyskać informacje o spisie sprzętu opartym na danych zbieranych z tych urządzeń, zobacz [Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Raport oprogramowania dla systemu Mac OS X**|Wyświetla oprogramowanie zainstalowane na wszystkich zarejestrowanych urządzeniach z systemem Mac OS X w wybranych grupach. Raport zawiera informacje o nazwie oprogramowania (w postaci identyfikatora pakietu), skróconej (lub przyjaznej) nazwie, wersji i liczbie urządzeń, na których oprogramowanie jest zainstalowane.|

#### Aby utworzyć raport

1.  W konsoli administracyjnej usługi Intune kliknij pozycję **Raporty**, a następnie kliknij typ raportu, który chcesz wygenerować na podstawie opisu w powyższej tabeli.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Na przykład możesz określić, że w raporcie dotyczącym wykrytego oprogramowania będzie wyświetlane tylko oprogramowanie opublikowane przez firmę Microsoft.

3.  Kliknij pozycję **Wyświetl raport** , aby otworzyć raport w nowym oknie.

Aby posortować raport według dowolnej z wyświetlanych kolumn, kliknij nagłówek kolumny. Ponadto niektóre raporty umożliwiają rozwijanie elementów na liście w celu wyświetlenia dodatkowych szczegółów.

## Więcej akcji raportów
Ponadto raporty obsługują następujące akcje:

|Akcja|Więcej informacji|
|----------|--------------------|
|**Drukowanie**|W otwartym raporcie kliknij ikonę drukowania i postępuj zgodnie z instrukcjami.|
|**Eksportowanie**|W otwartym raporcie kliknij ikonę eksportowania i postępuj zgodnie z instrukcjami. Raport można wyeksportować w formacie wartości rozdzielanych przecinkami (.csv) lub w formacie HTML.|
|**Zapisywanie**|Na stronie **Tworzenie nowego raportu** każdy użytkownik może zapisać do 100 raportów. Skonfiguruj parametry raportu według własnych potrzeb, a następnie kliknij pozycję **Zapisz**lub **Zapisz jako** , jeśli chcesz użyć innej nazwy.|
|**Ładowanie**|Na stronie **Tworzenie nowego raportu** kliknij pozycję **Ładuj** , aby pobrać wszystkie zapisane wcześniej zestawy parametrów raportu.|
|**Usuwanie**|W obszarze roboczym **Raporty** wybierz żądany typ raportu, kliknij pozycję **Ładuj**, a następnie na liście raportów kliknij ikonę usuwania (x) obok raportu.|

### Zobacz także
[Monitorowanie i raporty w usłudze Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


