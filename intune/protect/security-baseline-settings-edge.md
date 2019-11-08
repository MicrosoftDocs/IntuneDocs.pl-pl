---
title: Ustawienia linii bazowych zabezpieczeń usługi Intune dla przeglądarki Microsoft Edge
titleSuffix: Microsoft Intune
description: Ustawienia linii bazowej zabezpieczeń obsługiwane przez usługę Intune do zarządzania przeglądarką Microsoft Edge
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/30/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f4e56340d871ea5e0bcec7e541a418c32d021d0
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415649"
---
# <a name="microsoft-edge-baseline-settings-for-intune"></a>Ustawienia linii bazowej programu Microsoft Edge dla usługi Intune

Wyświetl ustawienia linii bazowej przeglądarki sieci Web Microsoft Edge, które są obsługiwane przez Microsoft Intune. Ustawienia domyślne linii bazowej Microsoft Edge reprezentują zalecaną konfigurację przeglądarek Microsoft Edge i mogą nie odpowiadać ustawieniom bazowym dla innych linii bazowych zabezpieczeń.

> [!NOTE]
> Linia bazowa Microsoft Edge jest w publicznej wersji zapoznawczej. 

## <a name="microsoft-edge"></a>Microsoft Edge

- **Zapobiegaj pomijaniu pominięcia programu Microsoft Defender SmartScreen dla lokacji**  
  **Domyślne**: włączone  
  Microsoft Edge CSP: [Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

  To ustawienie zasad umożliwia określenie, czy użytkownicy mogą przesłaniać ostrzeżenia filtru SmartScreen programu Microsoft Defender dotyczące potencjalnie złośliwych witryn sieci Web. 
  - Jeśli włączysz to ustawienie, użytkownicy nie będą mogli zignorować ostrzeżeń filtru SmartScreen usługi Microsoft Defender i nie będą mogli kontynuować pracy z tą lokacją. 
  - Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą mogli ignorować ostrzeżenia filtru SmartScreen programu Microsoft Defender i kontynuować pracę z tą lokacją.

- **Minimalna włączona wersja protokołu SSL**  
  **Domyślne**: włączone  

  Ustaw minimalną obsługiwaną wersję protokołu SSL. Jeśli ustawisz tę zasadę jako *Nieskonfigurowane*, przeglądarka Microsoft Edge będzie używać domyślnej minimalnej wersji *protokołu TLS 1,0*. Jeśli ustawiono opcję *włączone*, można wybrać minimalną wersję z następujących wartości:

  - TLS 1.0
  - TLS 1.1
  - TLS 1.2

  - **Minimalna włączona wersja protokołu SSL**  
    **Wartość domyślna**: TLS 1,2

- **Zapobiegaj pominięciu ostrzeżeń programu Microsoft Defender SmartScreen dotyczących pobierania**  
  **Domyślne**: włączone  
  Microsoft Edge CSP: [Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)  

  Te zasady umożliwiają określenie, czy użytkownicy mogą przesłaniać ostrzeżenia filtru SmartScreen programu Microsoft Defender dotyczące niezweryfikowanych plików do pobrania.
  - Jeśli włączysz tę zasadę, użytkownicy w Twojej organizacji nie będą mogli zignorować ostrzeżeń filtru SmartScreen usługi Microsoft Defender i nie będą mogli zakończyć wykonywania niezweryfikowanych plików do pobrania.
  - Jeśli ta zasada zostanie wyłączona lub nie zostanie skonfigurowana, użytkownicy mogą ignorować ostrzeżenia filtru SmartScreen programu Microsoft Defender i kończyć niezweryfikowane pliki do pobrania.

- **Zezwól użytkownikom na przechodzenie ze strony ostrzeżenia protokołu SSL**  
  **Domyślne**: wyłączone  
  Microsoft Edge CSP: [Browser/PreventCertErrorOverrides](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventcerterroroverrides)  

  Przeglądarka Microsoft Edge pokazuje stronę ostrzeżenia, gdy użytkownicy odwiedzają witryny z błędami protokołu SSL. Jeśli ta zasada zostanie ustawiona na wartość *włączone* lub *Nieskonfigurowane*, użytkownicy będą mogli klikać te strony ostrzegawcze. Gdy ta zasada jest *wyłączona*, użytkownicy nie mogą klikać stron ostrzegawczych. 

- **Domyślne ustawienie programu Adobe Flash**  
  **Domyślne**: włączone  
  Microsoft Edge CSP: [Browser/AllowFlash](https://docs.microsoft.coms/windows/client-management/mdm/policy-csp-browser#browser-allowflash)i [Browser/AllowFlashClickToRun](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowflashclicktorun)  

  Określa, czy witryny sieci Web, które nie są objęte usługą "PluginsAllowedForUrls" lub "PluginsBlockedForUrls", mogą automatycznie uruchamiać wtyczkę Adobe Flash. 

  - Wybierz opcję "BlockPlugins", aby zablokować program Adobe Flash we wszystkich lokacjach
  - Wybierz opcję "ClickToPlay", aby umożliwić programowi Adobe Flash uruchomienie, ale wymaganie od użytkownika kliknięcia symbolu zastępczego, aby go uruchomić.
  
   W każdym przypadku zasady "PluginsAllowedForUrls" i "PluginsBlockedForUrls" mają pierwszeństwo przed "DefaultPluginsSetting". Automatyczne odtwarzanie jest dozwolone tylko w przypadku domen jawnie wymienionych w zasadach "PluginsAllowedForUrls". 
   Jeśli chcesz włączyć automatyczne odtwarzanie dla wszystkich lokacji, rozważ dodanie http://* i https://* do tej listy. 
   
   - Jeśli ustawisz tę zasadę jako *Nieskonfigurowane*, użytkownik może zmienić to ustawienie ręcznie. * 2 = Blokuj wtyczkę Adobe Flash * 3 = Kliknij, aby odtworzyć poprzednią opcję "1" ustawioną na wszystkie, ale ta funkcja jest teraz obsługiwana tylko przez zasady "PluginsAllowedForUrls". Istniejące zasady korzystające z opcji "1" będą działać w trybie kliknij i Odtwórz.  
 
  - **Domyślne ustawienie programu Adobe Flash**  
    **Domyślne**: Blokuj wtyczkę Adobe Flash

- **Włącz izolację lokacji dla każdej lokacji**  
  **Domyślne**: włączone  

  Zasad "SitePerProcess" można użyć, aby uniemożliwić użytkownikom rezygnację z domyślnego zachowania izolowania wszystkich lokacji. Zasad IsolateOrigins można także użyć do izolowania dodatkowych, bardziej precyzyjnych źródeł.

  - Jeśli te zasady są *włączone*, użytkownicy nie mogą zrezygnować z domyślnego zachowania w przypadku, gdy każda lokacja jest uruchamiana we własnym procesie. 
  - Jeśli używasz opcji *wyłączone* lub *Nieskonfigurowane*, użytkownik może zrezygnować z izolacji lokacji. (Na przykład przy użyciu wpisu "Wyłącz izolację lokacji" w edge://flags). Wyłączenie zasad lub niekonfigurowanie zasad nie powoduje wyłączenia izolacji lokacji.

- **Obsługiwane schematy uwierzytelniania**  
  **Domyślne**: włączone  

  Określa, które schematy uwierzytelniania HTTP są obsługiwane. Zasady można skonfigurować przy użyciu następujących wartości: "Basic", "Digest", "NTLM" i "Negotiate". Rozdziel wiele wartości przecinkami. Jeśli nie skonfigurujesz tych zasad, zostaną użyte wszystkie cztery schematy.
 
  - **Obsługiwane schematy uwierzytelniania**  
    Wybierz jedną z następujących opcji: 
    - Podstawowe
    - Szyfrowane
    - NTLM *(wybrane domyślnie)*
    - Negocjuj *(wybrane domyślnie)*

- **Włącz zapisywanie haseł w Menedżerze haseł**  
  **Domyślne**: wyłączone  
  Microsoft Edge CSP: [Browser/AllowPasswordManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowpasswordmanager)  

  Włącz program Microsoft Edge, aby zapisać hasła użytkownika. 
  - Po włączeniu tych zasad użytkownicy będą mogli zapisywać swoje hasła w przeglądarce Microsoft Edge. Podczas następnego odwiedzania witryny program Microsoft Edge wprowadzi hasło automatycznie. 
  - Jeśli wyłączysz tę zasadę, użytkownicy nie będą mogli zapisywać nowych haseł, ale mogą nadal używać wcześniej zapisanych haseł. 
  
  Po ustawieniu zasad na *włączone* lub *wyłączone*użytkownicy nie mogą zmieniać ani zastępować tych zasad w przeglądarce Microsoft Edge. 
  
  Jeśli ustawisz tę opcję na wartość *Nieskonfigurowane*, użytkownicy będą mogli zapisywać hasła, a także wyłączać tę funkcję.

- **Kontrolowanie, które rozszerzenia nie mogą być zainstalowane**  
  **Domyślne**: włączone  

  Wyświetl listę konkretnych rozszerzeń, których użytkownicy nie mogą instalować w przeglądarce Microsoft Edge. Po wdrożeniu tych zasad wszystkie rozszerzenia na tej liście, które zostały wcześniej zainstalowane, są wyłączone, a użytkownik nie będzie mógł ich włączyć. Jeśli usuniesz element z listy zablokowanych rozszerzeń, to rozszerzenie zostanie automatycznie ponownie włączone wszędzie tam, gdzie zostało wcześniej zainstalowane.
  
  Użyj **\*** , aby zablokować wszystkie rozszerzenia, które nie są jawnie wymienione na liście dozwolonych. Jeśli ta zasada ma wartość *Nieskonfigurowane*, użytkownicy będą mogli zainstalować dowolne rozszerzenia w przeglądarce Microsoft Edge. 
  
  Przykładowa wartość: extension_id1 extension_id2.  
  <br>
  - **Identyfikatory rozszerzeń, dla których użytkownik nie powinien być instalowany (lub * dla wszystkich)**  
    Wybierz pozycję **Dodaj** i określ dodatkowe rozszerzenia. Znak **\*** jest wybierany domyślnie.

- **Konfigurowanie filtru SmartScreen programu Microsoft Defender**  
  **Domyślne**: włączone  
  Microsoft Edge CSP: [Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)  
  
  To ustawienie zasad umożliwia skonfigurowanie, czy program Microsoft Defender SmartScreen ma zostać włączony. Program Microsoft Defender SmartScreen oferuje komunikaty ostrzegawcze pomagające w ochronie użytkowników przed potencjalnymi phishingami i złośliwym oprogramowaniem. 
  
  - Domyślnie program Microsoft Defender SmartScreen jest włączony. Jeśli włączysz to ustawienie, program Microsoft Defender SmartScreen zostanie włączony i użytkownicy nie będą mogli go wyłączyć.
  - Jeśli wyłączysz to ustawienie, program Microsoft Defender SmartScreen zostanie wyłączony i użytkownicy nie będą mogli go włączać. 
  - Jeśli ustawiono wartość *nie skonfigurowano*, użytkownicy mogą wybrać, czy program Microsoft Defender SmartScreen ma być używany. 
  
  Te zasady są dostępne tylko w wystąpieniach systemu Windows, które są przyłączone do domeny programu Microsoft Active Directory lub w wystąpieniach systemu Windows 10 Pro lub Enterprise zarejestrowanych na potrzeby zarządzania urządzeniami.

- **Zezwalaj na natywne hosty obsługi komunikatów na poziomie użytkownika (zainstalowane bez uprawnień administratora)**  
  **Domyślne**: wyłączone  

  Umożliwia instalację natywnych hostów obsługi komunikatów na poziomie użytkownika. 
  - Jeśli wyłączysz tę zasadę, przeglądarka Microsoft Edge będzie używać tylko natywnych hostów obsługi komunikatów zainstalowanych na poziomie systemu. Domyślnie jeśli te zasady nie zostaną skonfigurowane, przeglądarka Microsoft Edge zezwoli na użycie natywnych hostów obsługi komunikatów na poziomie użytkownika.

## <a name="next-steps"></a>Następne kroki

[Korzystanie z linii bazowych zabezpieczeń w usłudze Intune](security-baselines.md)
