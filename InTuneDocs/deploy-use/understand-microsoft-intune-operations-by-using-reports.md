---
title: "Informacje o operacjach — korzystanie z raportów | Microsoft Docs"
description: "Tworzenie raportów dotyczących oprogramowania, sprzętu i licencji na oprogramowanie w organizacji i zarządzanie nimi."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 3400a49feaca9ef34bcffcc176bc496310d4c357



---

# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Informacje w tym temacie mają na celu ułatwienie tworzenia raportów usługi Microsoft Intune zawierających informacje dotyczące oprogramowania, sprzętu i licencji na oprogramowanie w organizacji oraz zarządzanie tymi raportami.

## <a name="using-reports"></a>Używanie raportów
Raporty usługi Intune zawierają informacje dotyczące oprogramowania, sprzętu i licencji na oprogramowanie w organizacji. Raporty ułatwiają potwierdzanie bieżącego zapotrzebowania i prognozowanie wydatków w przyszłości. Obszar roboczy **Raporty** zawiera narzędzia służące do tworzenia raportów i zarządzania nimi. 

### <a name="report-types"></a>Typy raportów

|Typ raportu|Opis|
|---------------|---------------|
|**Raporty dotyczące aktualizacji**|Zawierają informacje o aktualizacjach oprogramowania, które zakończyły się pomyślnie na komputerach w organizacji, oraz o aktualizacjach zakończonych niepowodzeniem, oczekujących lub wymaganych. Aby uzyskać więcej informacji o aktualizacjach oprogramowania, zobacz [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Raporty dotyczące wykrytego oprogramowania**|Zawierają informacje o oprogramowaniu zainstalowanym na komputerach w organizacji. Uwzględniane są wersje oprogramowania. Wyświetlane informacje można filtrować według wydawcy oprogramowania i kategorii oprogramowania. Można rozwinąć aktualizacje na liście w celu wyświetlenia większej liczby szczegółów (takich jak komputery, na których zainstalowano aktualizację), wybierając strzałkę kierunkową obok elementu listy.<br /><br />Po wycofaniu komputerów lub zmianie ich członkostwa w grupach w usłudze Intune może upłynąć kilka minut, zanim zmiany zostaną odzwierciedlone w raporcie dotyczącym wykrytego oprogramowania. W celu uzyskania najdokładniejszych danych spisu oprogramowania poczekaj kilka minut po wycofaniu komputerów lub zmianie ich członkostwa w grupach przed uruchomieniem raportu dotyczącego wykrytego oprogramowania, w którym są uwzględnione te komputery.|
|**Raporty dotyczące spisu komputerów**|Zawierają informacje o zarządzanych komputerach w organizacji. Ten raport służy do planowania zakupów sprzętu i uzyskiwania informacji o zapotrzebowaniu na sprzęt użytkowników w organizacji. Więcej informacji dotyczących pracy z zarządzanymi komputerami można znaleźć w temacie [Zarządzanie komputerami z systemem Windows przy użyciu usługi Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Raporty dotyczące spisu urządzeń przenośnych**|Zawierają informacje o urządzeniach przenośnych w organizacji. Wyświetlane informacje można filtrować według grup, urządzeń ze zdjętymi zabezpieczeniami lub z możliwością dostępu z uprawnieniami administratora oraz według systemu operacyjnego.|
|**Raporty dotyczące zakupionych licencji**|Zawierają tytuły wszystkich licencjonowanych programów w wybranych grupach licencji na podstawie umów licencyjnych. Jeśli informacje o licencji oprogramowania nie były odświeżane w ciągu 24 godzin, zostaną odświeżone podczas generowania raportu dotyczącego licencji. Raport dotyczący licencji nie jest dokładnym wyliczeniem tytułów używanego oprogramowania lub potwierdzeniem zgodności z umowami. Raport jest narzędziem ułatwiającym podejmowanie decyzji dotyczących licencjonowania w organizacji. Usługa Intune może nie wykrywać niektórych produktów, które mogą mieć licencję zbiorczą firmy Microsoft. Dostępne są następujące filtry:<br /><br />**Wszystkie umowy** — Pokazuje wszystkie licencjonowane programy zarządzane przez usługę Intune.<br /><br />**Umowy licencjonowania zbiorowego** — Pokazuje tylko oprogramowanie z witryny Volume Licensing Service Center (VLSC).<br /><br />**Inne umowy licencyjne oprogramowania** — Pokazuje oprogramowanie zarządzane poza witryną VLSC.|
|**Raporty dotyczące instalacji licencji**|Umożliwiają porównanie oprogramowania zainstalowanego na komputerach w organizacji z zakresem bieżącej umowy licencyjnej w witrynie VLSC. Dostępne są następujące filtry:<br /><br />**Wszystkie umowy** — Pokazuje wszystkie licencjonowane programy zarządzane przez usługę Intune.<br /><br />**Umowy licencjonowania zbiorowego** — Pokazuje tylko oprogramowanie z witryny VLSC.<br /><br />**Inne umowy licencyjne oprogramowania** — Pokazuje oprogramowanie zarządzane poza witryną VLSC.|
|**Raporty dotyczące warunków i postanowień**|Wskazują, czy użytkownicy zaakceptowali wdrożone warunki i postanowienia oraz która wersja została zaakceptowana. Można wybrać maksymalnie 10 użytkowników, dla których raport będzie zawierać informacje o wszystkich wdrożonych warunkach i postanowieniach zaakceptowanych przez te osoby lub informacje o stanie akceptacji określonych warunków wdrożonych dla tych użytkowników.|
|**Raporty dotyczące niezgodności aplikacji**|Zawierają informacje dotyczące użytkowników, którzy mają zainstalowane aplikacje znajdujące się na liście zgodnych i niezgodnych aplikacji. Ten raport umożliwia znalezienie użytkowników i urządzeń niezgodnych z zasadami firmy dotyczącymi aplikacji.|
|**Raporty dotyczące zgodności certyfikatów**|Zawierają informacje o certyfikatach, które zostały wydane dla użytkowników i urządzeń za pośrednictwem protokołu SCEP lub PKCS #12 (PFX). Ten raport umożliwia znalezienie wydanych, wygasłych i odwołanych certyfikatów.|
|**Raporty dotyczące historii urządzeń**|Zawierają dziennik historyczny akcji wycofania, czyszczenia i usuwania. Użyj tego raportu, aby zobaczyć, kto w przeszłości zainicjował akcje na urządzeniach.|
|**Raporty zaświadczania o kondycji**|Pokazują kondycję urządzeń przenośnych.|
|**Raport dotyczący sprzętu z systemem Mac OS X**|Wyświetla szczegóły sprzętu dla wszystkich zarejestrowanych urządzeń z systemem Mac OS X w wybranych grupach. Aby uzyskać informacje o spisie sprzętu opartym na danych zbieranych z tych urządzeń, zobacz [Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Raport dotyczący oprogramowania dla systemu Mac OS X**|Wyświetla oprogramowanie zainstalowane na wszystkich zarejestrowanych urządzeniach z systemem Mac OS X w wybranych grupach. Raport zawiera informacje o nazwie oprogramowania (w postaci identyfikatora pakietu), skróconej (lub przyjaznej) nazwie, wersji i liczbie urządzeń, na których oprogramowanie jest zainstalowane.|

#### <a name="to-create-a-report"></a>Aby utworzyć raport

1.  W konsoli administracyjnej usługi Intune wybierz pozycję **Raporty**. Następnie wybierz typ raportu, który chcesz wygenerować, na podstawie opisu w poprzedniej tabeli.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Na przykład możesz określić, że w raporcie dotyczącym wykrytego oprogramowania będzie wyświetlane tylko oprogramowanie opublikowane przez firmę Microsoft.

3.  Wybierz pozycję **Wyświetl raport**, aby otworzyć raport w nowym oknie.

Aby posortować raport według dowolnej z wyświetlanych kolumn, wybierz nagłówek kolumny. Ponadto niektóre raporty umożliwiają rozwijanie elementów na liście w celu wyświetlenia dodatkowych szczegółów.

## <a name="more-report-actions"></a>Więcej akcji raportów
Ponadto raporty obsługują następujące akcje:

|Akcja|Więcej informacji|
|----------|--------------------|
|**Drukowanie**|W otwartym raporcie wybierz ikonę drukowania i postępuj zgodnie z instrukcjami.|
|**Eksportowanie**|W otwartym raporcie wybierz ikonę eksportowania i postępuj zgodnie z instrukcjami. Raport można wyeksportować w formacie wartości rozdzielanych przecinkami (.csv) lub w formacie HTML.|
|**Zapisywanie**|Na stronie **Tworzenie nowego raportu** każdy użytkownik może zapisać do 100 raportów. Skonfiguruj parametry raportu według własnych potrzeb, a następnie wybierz pozycję **Zapisz**lub **Zapisz jako**, jeśli chcesz użyć innej nazwy.|
|**Ładowanie**|Na stronie **Tworzenie nowego raportu** wybierz pozycję **Ładuj**, aby pobrać wszystkie zapisane wcześniej zestawy parametrów raportu.|
|**Usuwanie**|W obszarze roboczym **Raporty** wybierz żądany typ raportu i wybierz pozycję **Ładuj**. Następnie na liście raportów wybierz ikonę usuwania (x) obok raportu.|

### <a name="see-also"></a>Zobacz też
[Monitorowanie i raporty w usłudze Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


