---
title: Dozwolone i zablokowane aplikacje dla systemu KNOX | Microsoft Intune
description: "Niestandardowy profil umożliwiający utworzenie listy dozwolonych i zablokowanych aplikacji dla systemu KNOX."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c7679d624ba22b2a062ef2534a642e38a5f57fde
ms.openlocfilehash: 273627573f58e1bde4fd19c548ce87639f25ca4b



---
# Użycie niestandardowych zasad do zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung KNOX

Użyj procedur opisanych w tym temacie, aby utworzyć niestandardowe zasady usługi Microsoft Intune, co powoduje utworzenie następujących elementów:

- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Uruchamianie aplikacji na tej liście jest blokowane, nawet jeśli były one już zainstalowane, gdy zasady zostały zastosowane.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu klepu Google Play. Można zainstalować tylko aplikacje na liście. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko w przypadku urządzeń z systemem Samsung KNOX.

## Tworzenie listy dozwolonych lub zablokowanych aplikacji

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Zasady** &gt; **Zasady konfiguracji** &gt; **Dodaj**.
2. W oknie dialogowym **Tworzenie nowych zasad** rozwiń pozycję **Android**, wybierz pozycję **Konfiguracja niestandardowa**, a następnie wybierz polecenie **Utwórz zasady**.
3. Podaj nazwę i opcjonalny opis zasad, a następnie w sekcji **Ustawienia OMA-URI** wybierz polecenie **Dodaj**.
4. W oknie dialogowym **Dodawanie lub edytowanie ustawienia OMA-URI** podaj następujące dane: listę aplikacji, których uruchamianie na urządzeniu jest zablokowane:
    
    - **Nazwa ustawienia.** Podaj ciąg **PreventStartPackages**.
    - **Opis ustawienia.** Podaj opcjonalny opis, taki jak „Lista aplikacji, których uruchamianie jest zablokowane”.
    -   **Typ danych.** Wybierz z listy rozwijanej opcję **Ciąg**.
    -   **OMA-URI.** Wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -   **Wartość.** Podaj listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku **; : ,** lub **|**. (Przykład: pakiet1;pakiet2;)

    Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play, przy czym wszystkie inne aplikacje są wykluczone:

    - **Nazwa ustawienia.** Podaj ciąg **AllowInstallPackages**.
    - **Opis ustawienia.** Wpisz opcjonalny opis, taki jak „Lista aplikacji, które użytkownicy mogą instalować ze sklepu Google Play”.
    - **Typ danych.** Wybierz z listy rozwijanej opcję **Ciąg**.
    - **OMA-URI.** Wpisz ciąg **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
    - **Wartość.** Podaj listę nazw pakietów aplikacji, na których uruchamianie chcesz zezwolić. Jako ogranicznika możesz użyć znaku **; : ,** lub **|**. (Przykład: pakiet1;pakiet2;)

4. Kliknij pozycję **OK**, a następnie kliknij polecenie **Zapisz zasady**. 

>[!TIP]
> Identyfikator pakietu aplikacji możesz znaleźć, przechodząc do aplikacji w sklepie Google Play. Identyfikator pakietu znajduje się w adresie URL strony aplikacji. Na przykład identyfikator pakietu aplikacji Microsoft Word to **com.microsoft.office.word**.

Gdy docelowe urządzenie nawiąże połączenie następny raz, zostaną zastosowane ustawienia aplikacji.


## Wdrożenie zasad

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie kliknij pozycje **Dodaj** &gt; **OK**.

 
Po wybraniu wdrożonych zasad można wyświetlić więcej informacji dotyczących wdrożenia w dolnej części listy zasad.

### Zobacz także
[Ustawienia zasad konfiguracji systemu Android i Samsung KNOX w usłudze Microsoft Intune](android-policy-settings-in-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


