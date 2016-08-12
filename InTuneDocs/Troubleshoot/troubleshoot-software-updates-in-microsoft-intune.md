---
title: "Rozwiązywanie problemów z aktualizacjami oprogramowania | Microsoft Intune"
description: "Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 906371576609152aaf61e033da5ce60744ddd255
ms.openlocfilehash: 07e5737b75870319445f5af4d7038916b155d083


---

# Rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune
W tej sekcji przedstawiono informacje, które ułatwią rozwiązywanie problemów z aktualizacjami oprogramowania w usłudze Microsoft Intune.

Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md), aby znaleźć więcej sposobów uzyskania pomocy.

## Kody błędów programu Update Agent

Poniższa tabela zawiera listę kodów błędów programu **Update Agent** usługi Intune. Jeśli nie możesz znaleźć określonego kodu błędu w tej tabeli, zobacz dodatek zawierający [kody wyników programu Windows Update Agent](http://go.microsoft.com/fwlink/?LinkID=221542).

|Kod błędu|Nazwa symboliczna|Więcej informacji|
|--------------|-----------------|--------------------|
|**0x00cf0001**|OM_S_SERVICE_STOP|Agent został pomyślnie zatrzymany.|
|**0x00cf0003**|OM_S_UPDATE_ERROR|Operacja została ukończona pomyślnie, ale wystąpiły błędy podczas stosowania aktualizacji.|
|**0x00cf0004**|OM_S_MARKED_FOR_DISCONNECT|Wywołanie zwrotne zostało oznaczone do późniejszego rozłączenia, ponieważ żądanie rozłączenia operacji wystąpiło, gdy wywołanie zwrotne było uruchomione.|
|**0x00cf0005**|OM_S_REBOOT_REQUIRED|Aby ukończyć instalację aktualizacji, należy ponownie uruchomić system.|
|**0x00cf0006**|OM_S_ALREADY_INSTALLED|Aktualizacja, która ma zostać zainstalowana, jest już zainstalowana w systemie.|
|**0x00cf0007**|OM_S_ALREADY_UNINSTALLED|Aktualizacja, która ma zostać usunięta, nie jest zainstalowana w systemie.|
|**0x00cf2015**|OM_S_UH_INSTALLSTILLPENDING|Trwa instalacja aktualizacji.|
|**0x80cf0001**|OM_E_NO_SERVICE|Agent nie może świadczyć usługi.|
|**0x80cf0002**|OM_E_MAX_CAPACITY_REACHED|Przekroczono maksymalną pojemność usługi.|
|**0x80cf0003**|OM_E_UNKNOWN_ID|Nie można odnaleźć identyfikatora.|
|**0x80cf0004**|OM_E_NOT_INITIALIZED|Nie można zainicjować obiektu.|
|**0x80cf0007**|OM_E_INVALIDINDEX|Indeks kolekcji jest nieprawidłowy.|
|**0x80cf0008**|OM_E_ITEMNOTFOUND|Nie można odnaleźć klucza dla elementu, którego dotyczy zapytanie.|
|**0x80cf0009**|OM_E_OPERATIONINPROGRESS|Operacja powodująca konflikt jest w toku. Niektóre operacje, na przykład kilka instalacji naraz, nie mogą być wykonywane równocześnie.|
|**0x80cf000B**|OM_E_CALL_CANCELLED|Operacja została anulowana.|
|**0x80cf000C**|OM_E_NOOP|Nie jest wymagana żadna operacja.|
|**0x80cf000D**|OM_E_XML_MISSINGDATA|Agent nie może odnaleźć wymaganych informacji w danych XML aktualizacji.|
|**0x80cf000E**|OM_E_XML_INVALID|Agent odnalazł nieprawidłowe informacje w danych XML aktualizacji.|
|**0x80cf000F**|OM_E_CYCLE_DETECTED|W metadanych wykryto cykliczne relacje aktualizacji.|
|**0x80cf0010**|OM_E_TOO_DEEP_RELATION|Relacje aktualizacji są zbyt głęboko zagnieżdżone, aby można było je ocenić.|
|**0x80cf0011**|OM_E_INVALID_RELATIONSHIP|Znaleziono nieprawidłową relację aktualizacji.|
|**0x80cf0012**|OM_E_REG_VALUE_INVALID|Odczytano nieprawidłową wartość rejestru.|
|**0x80cf0013**|OM_E_DUPLICATE_ITEM|W ramach operacji podjęto próbę dodania zduplikowanego elementu do listy.|
|**0x80cf0014**|OM_E_INVALID_INSTALL_REQUESTED|Element wywołujący nie może zainstalować aktualizacji zażądanych do zainstalowania.|
|**0x80cf0016**|OM_E_INSTALL_NOT_ALLOWED|W ramach operacji podjęto próbę instalacji, gdy trwała inna instalacja lub gdy system oczekiwał na obowiązkowe ponowne uruchomienie.|
|**0x80cf0017**|OM_E_NOT_APPLICABLE|Operacja nie została wykonana, ponieważ nie ma żadnych aktualizacji do zastosowania.|
|**0x80cf0018**|OM_E_NO_USERTOKEN|Operacja nie powiodła się, ponieważ brakuje wymaganego tokenu użytkownika.|
|**0x80cf0019**|OM_E_EXCLUSIVE_INSTALL_CONFLICT|Nie można zainstalować aktualizacji w trybie wyłączności równocześnie z innymi aktualizacjami.|
|**0x80cf001A**|OM_E_POLICY_NOT_SET|Wartość zasad nie została ustawiona.|
|**0x80cf001D**|OM_E_INVALID_UPDATE|Aktualizacja zawiera nieprawidłowe metadane.|
|**0x80cf001E**|OM_E_SERVICE_STOP|Nie można ukończyć operacji, ponieważ trwa zamykanie usługi lub systemu.|
|**0x80cf001F**|OM_E_NO_CONNECTION|Nie można ukończyć operacji, ponieważ połączenie sieciowe jest niedostępne.|
|**0x80cf0020**|OM_E_NO_INTERACTIVE_USER|Nie można ukończyć operacji, ponieważ nie ma żadnego zalogowanego użytkownika interaktywnego.|
|**0x80cf0021**|OM_E_TIME_OUT|Nie można ukończyć operacji, ponieważ upłynął jej limit czasu.|
|**0x80cf0022**|OM_E_ALL_UPDATES_FAILED|Operacja nie powiodła w przypadku wszystkich aktualizacji.|
|**0x80cf0024**|OM_E_NO_UPDATE|Brak aktualizacji.|
|**0x80cf0025**|OM_E_USER_ACCESS_DISABLED|Ustawienia zasad grupy uniemożliwiają dostęp do usługi Windows Update.|
|**0x80cf0026**|OM_E_INVALID_UPDATE_TYPE|Typ aktualizacji jest nieprawidłowy.|
|**0x80cf0028**|OM_E_UNINSTALL_NOT_ALLOWED|Nie można odinstalować aktualizacji, ponieważ żądanie nie pochodzi z serwera programu WSUS.|
|**0x80cf0029**|OM_E_INVALID_PRODUCT_LICENSE|W wyszukiwaniu mogły zostać pominięte niektóre aktualizacje lub w systemie może się znajdować nielicencjonowana aplikacja.|
|**0x80cf002C**|OM_E_BIN_SOURCE_ABSENT|Nie można zainstalować aktualizacji skompresowanej różnicowo, ponieważ wymaga ona źródła.|
|**0x80cf002D**|OM_E_SOURCE_ABSENT|Nie można zainstalować aktualizacji w postaci pełnego pliku, ponieważ wymaga ona źródła.|
|**0x80cf002E**|OM_E_WU_DISABLED|Dostęp do niezarządzanego serwera jest niedozwolony.|
|**0x80cf002F**|OM_E_CALL_CANCELLED_BY_POLICY|Nie można ukończyć operacji, ponieważ ustawiono zasadę **DisableWindowsUpdateAccess**.|
|**0x80cf0030**|OM_E_INVALID_PROXY_SERVER|Format listy serwerów proxy jest nieprawidłowy.|
|**0x80cf0031**|OM_E_INVALID_FILE|Plik jest w niewłaściwym formacie.|
|**0x80cf0032**|OM_E_INVALID_CRITERIA|Ciąg kryteriów wyszukiwania jest nieprawidłowy.|
|**0x80cf0034**|OM_E_DOWNLOAD_FAILED|Nie można pobrać aktualizacji.|
|**0x80cf0035**|OM_E_UPDATE_NOT_PROCESSED|Aktualizacja nie została przetworzona.|
|**0x80cf0036**|OM_E_INVALID_OPERATION|Bieżący stan obiektu nie zezwala na tę operację.|
|**0x80cf0037**|OM_E_NOT_SUPPORTED|Operacja jest nieobsługiwana.|
|**0x80cf0038**|OM_E_WINHTTP_INVALID_FILE|Pobrany plik zawiera nieoczekiwany typ zawartości.|
|**0x80cf0039**|OM_E_TOO_MANY_RESYNC|Serwer zgłosił agentowi zbyt wiele żądań ponownej synchronizacji.|
|**0x80cf0043**|OM_E_NO_UI_SUPPORT|Interfejs użytkownika programu Windows Update Agent jest nieobsługiwany.|
|**0x80cf0044**|OM_E_PER_MACHINE_UPDATE_ACCESS_DENIED|Ta operacja może być wykonywana na aktualizacjach dla poszczególnych komputerów tylko przez administratorów.|
|**0x80cf0045**|OM_E_UNSUPPORTED_SEARCHSCOPE|Podjęto próbę wyszukiwania w nieobsługiwanym zakresie.|
|**0x80cf0046**|OM_E_BAD_FILE_URL|Adres URL nie wskazuje pliku.|
|**0x80cf0047**|OM_E_NOTSUPPORTED|Żądana operacja jest nieobsługiwana.|
|**0x80cf0049**|OM_E_OUTOFRANGE|Dane są poza zakresem.|
|**0x80cf004A**|OM_E_INVALIDWUAVERSION|Dane zawierają nieprawidłową wersję.|
|**0x80cf004B**|OM_E_SEARCH_COMPLETED_WITH_SOME_FAILURES|Wywołanie wyszukiwania zostało ukończone, ale nie mogło wykryć niektórych aktualizacji.|
|**0x80cf004C**|OM_E_DOWNLOAD_COMPLETED_WITH_SOME_FAILURES|Wywołanie pobierania zostało ukończone, ale nie mogło pobrać niektórych aktualizacji.|
|**0x80cf004D**|OM_E_INSTALL_COMPLETED_WITH_SOME_FAILURES|Wywołanie instalacji zostało ukończone, ale nie mogło zainstalować niektórych aktualizacji.|
|**0x80cf004E**|OM_E_WINUPDATE_CACHE_UNINITIALIZED|Pamięć podręczna usługi Windows Update jest pusta, ponieważ nie została zainicjowana.|
|**0x80cf0436**|OM_E_PT_CATALOG_SYNC_REQUIRED|Serwer nie obsługuje wyszukiwania w poszczególnych kategoriach. Zamiast tego należy wydać polecenie wyszukiwania w pełnym wykazie.|
|**0x80cf0437**|OM_E_PT_SECURITY_VERIFICATION_FAILURE|Wystąpił problem z autoryzacją w usłudze.|
|**0x80cf0438**|OM_E_PT_ENDPOINT_UNREACHABLE|Nie ma żadnej trasy do punktu końcowego ani łączności sieciowej z punktem końcowym.|
|**0x80cf0439**|OM_E_PT_INVALID_FORMAT|Odebrane dane nie spełniają oczekiwań kontraktu danych.|
|**0x80cf043A**|OM_E_PT_INVALID_URL|Adres URL jest nieprawidłowy.|
|**0x80cf043B**|OM_E_PT_NWS_NOT_LOADED|Nie można załadować środowiska wykonawczego NWS.|
|**0x80cf043C**|OM_E_PT_PROXY_AUTH_SCHEME_NOT_SUPPORTED|Schemat uwierzytelniania serwera proxy jest nieobsługiwany.|
|**0x80cf043D**|OM_E_SERVICEPROP_NOTAVAIL|Żądana właściwość usługi jest niedostępna.|
|**0x80cf043E**|OM_E_PT_ENDPOINT_REFRESH_REQUIRED|Wtyczka dostawcy punktu końcowego wymaga odświeżenia w trybie online.|
|**0x80cf043F**|OM_E_PT_ENDPOINTURL_NOTAVAIL|Adres URL żądanego punktu końcowego usługi jest niedostępny.|
|**0x80cf0440**|OM_E_PT_ENDPOINT_DISCONNECTED|Połączenie z punktem końcowym usługi zostało zakończone.|
|**0x80cf0441**|OM_E_PT_INVALID_OPERATION|Operacja jest nieprawidłowa, ponieważ rozmówca protokołu jest w nieodpowiednim stanie.|
|**0x80cf0FFF**|OM_E_UNEXPECTED|Operacja nie powiodła się z przyczyn, które nie zostały wyjaśnione przy użyciu innego kodu błędu.|
|**0x80cf1001**|OM_E_MSI_WRONG_VERSION|W wyszukiwaniu mogły zostać pominięte niektóre aktualizacje, ponieważ Instalator Windows jest w wersji wcześniejszej niż wersja 3.1.|
|**0x80cf1002**|OM_E_MSI_NOT_CONFIGURED|W wyszukiwaniu mogły zostać pominięte niektóre aktualizacje, ponieważ Instalator Windows jest nieskonfigurowany.|
|**0x80cf1003**|OM_E_MSP_DISABLED|W wyszukiwaniu mogły zostać pominięte niektóre aktualizacje, ponieważ zasady wyłączyły stosowanie poprawek do Instalatora Windows.|
|**0x80cf1004**|OM_E_MSI_WRONG_APP_CONTEXT|Nie można zastosować aktualizacji, ponieważ aplikacja została zainstalowana dla poszczególnych użytkowników.|
|**0x80cf2000**|OM_E_UH_REMOTEUNAVAILABLE|Nie można ukończyć żądania dotyczącego procedury obsługi aktualizacji zdalnej, ponieważ nie jest dostępny żaden proces zdalny.|
|**0x80cf2001**|OM_E_UH_LOCALONLY|Nie można ukończyć żądania dotyczącego procedury obsługi aktualizacji zdalnej, ponieważ procedura obsługi jest dostępna tylko lokalnie.|
|**0x80cf2003**|OM_E_UH_REMOTEALREADYACTIVE|Nie można utworzyć procedury obsługi aktualizacji zdalnej, ponieważ już ona istnieje.|
|**0x80cf2004**|OM_E_UH_DOESNOTSUPPORTACTION|Nie można ukończyć żądania dotyczącego procedury obsługi instalowania (odinstalowywania) aktualizacji, ponieważ aktualizacja nie obsługuje instalowania (odinstalowywania).|
|**0x80cf2005**|OM_E_UH_WRONGHANDLER|Nie można ukończyć operacji, ponieważ określono niewłaściwą procedurę obsługi.|
|**0x80cf2006**|OM_E_UH_INVALIDMETADATA|Nie można ukończyć operacji procedury obsługi, ponieważ aktualizacja zawiera nieprawidłowe metadane.|
|**0x80cf2007**|OM_E_UH_INSTALLERHUNG|Nie można ukończyć operacji, ponieważ instalator przekroczył limit czasu. Sprawdź, czy aktualizacja wymagająca interakcji z użytkownikiem została zatwierdzona do wdrożenia. W tym przypadku musisz skorygować parametry instalacji aktualizacji, aby można ją było zainstalować w trybie dyskretnym.|
|**0x80cf2008**|OM_E_UH_OPERATIONCANCELLED|Operacja wykonywana przez procedurę obsługi aktualizacji została anulowana.|
|**0x80cf2009**|OM_E_UH_BADHANDLERXML|Nie można ukończyć operacji, ponieważ metadane właściwe dla procedury obsługi są nieprawidłowe.|
|**0x80cf200B**|OM_E_UH_INSTALLERFAILURE|Instalator nie może zainstalować (odinstalować) co najmniej jednej aktualizacji.|
|**0x80cf200D**|OM_E_UH_NEEDANOTHERDOWNLOAD|Procedura obsługi aktualizacji nie zainstalowała aktualizacji, ponieważ aktualizacja musi zostać ponownie pobrana.|
|**0x80cf200E**|OM_E_UH_NOTIFYFAILURE|Procedura obsługi aktualizacji nie może wysłać powiadomienia o stanie operacji instalowania (odinstalowywania).|
|**0x80cf2014**|OM_E_UH_POSTREBOOTSTILLPENDING|Nadal trwa operacja po ponownym rozruchu dotycząca aktualizacji.|
|**0x80cf2015**|OM_E_UH_POSTREBOOTRESULTUNKNOWN|Nie można ustalić wyniku operacji po ponownym rozruchu dotyczącej aktualizacji.|
|**0x80cf2016**|OM_E_UH_POSTREBOOTUNEXPECTEDSTATE|Nieoczekiwany stan aktualizacji po ukończeniu dotyczącej jej operacji po ponownym rozruchu.|
|**0x80cf2017**|OM_E_UH_NEW_SERVICING_STACK_REQUIRED|Przed pobraniem lub zainstalowaniem tej aktualizacji należy zaktualizować stos obsługi systemu operacyjnego.|
|**0x80cf2018**|OM_E_UH_CALLED_BACK_FAILURE|Instalator wywołania zwrotnego wykonał wywołanie zwrotne z błędem.|
|**0x80cf2019**|OM_E_UH_CUSTOMINSTALLER_INVALID_SIGNATURE|Podpis instalatora niestandardowego jest niezgodny z podpisem wymaganym przez aktualizację.|
|**0x80cf201A**|OM_E_UH_UNSUPPORTED_INSTALLCONTEXT|Konfiguracja instalacji jest nieobsługiwana przez instalatora.|
|**0x80cf201B**|OM_E_UH_INVALID_TARGETSESSION|Sesja docelowa instalacji jest nieprawidłowa.|
|**0x80cf2FFF**|OM_E_UH_UNEXPECTED|Błąd procedury obsługi aktualizacji nie pasuje do żadnego innego kodu OM_E_UH_&#42;.|
|**0x80cf3FFD**|OM_E_NON_UI_MODE|Nie można wyświetlić interfejsu użytkownika w trybie innym niż tryb interfejsu użytkownika. Moduły interfejsu użytkownika klienta usługi Windows Update mogą nie być zainstalowane.|
|**0x80cf3FFE**|OM_E_WUCLTUI_UNSUPPORTED_VERSION|Ta wersja funkcji wyeksportowanych z interfejsu użytkownika klienta usługi Windows Update jest nieobsługiwana.|
|**0x80cf3FFF**|OM_E_AUCLIENT_UNEXPECTED|Wystąpił błąd interfejsu użytkownika, który nie pasuje do żadnego innego kodu błędu OM_E_AUCLIENT_&#42;.|
|**0x80cf4007**|OM_E_PT_SOAPCLIENT_SOAPFAULT|Taki sam jak **SOAPCLIENT_SOAPFAULT**. Wystąpił błąd klienta protokołu SOAP z powodu błędu protokołu SOAP, którego typ kodu błędu to **OM_E_PT_SOAP_&#42;**.|
|**0x80cf4008**|OM_E_PT_SOAPCLIENT_PARSEFAULT|Taki sam jak **SOAPCLIENT_PARSEFAULT_ERROR**.  Klient protokołu SOAP nie może przeanalizować błędu protokołu SOAP.|
|**0x80cf400A**|OM_E_PT_SOAPCLIENT_PARSE|Taki sam jak **SOAPCLIENT_PARSE_ERROR**.  Klient protokołu SOAP nie może przeanalizować odpowiedzi z serwera.|
|**0x80cf400B**|OM_E_PT_SOAP_VERSION|Taki sam jak **SOAP_E_VERSION_MISMATCH**. Klient protokołu SOAP odnalazł nierozpoznawalną przestrzeń nazw dla koperty protokołu SOAP.|
|**0x80cf400C**|OM_E_PT_SOAP_MUST_UNDERSTAND|Taki sam jak **SOAP_E_MUST_UNDERSTAND**. Klient protokołu SOAP nie może zinterpretować nagłówka.|
|**0x80cf400D**|OM_E_PT_SOAP_CLIENT|Taki sam jak **SOAP_E_CLIENT**. Klient protokołu SOAP ustalił, że komunikat ma nieprawidłową postać. Popraw przed ponownym wysłaniem.|
|**0x80cf400E**|OM_E_PT_SOAP_SERVER|Taki sam jak **SOAP_E_SERVER**. Nie można przetworzyć komunikatu protokołu SOAP z powodu błędu serwera. Wyślij ponownie później.|
|**0x80cf4010**|OM_E_PT_EXCEEDED_MAX_SERVER_TRIPS|Liczba wystąpień komunikacji dwustronnej z serwerem przekroczyła maksymalny limit.|
|**0x80cf4012**|OM_E_PT_DOUBLE_INITIALIZATION|Nie można zainicjować obiektu, ponieważ został on już zainicjowany.|
|**0x80cf4013**|OM_E_PT_INVALID_COMPUTER_NAME|Nie można ustalić nazwy komputera.|
|**0x80cf4015**|OM_E_PT_REFRESH_CACHE_REQUIRED|Odpowiedź z serwera wskazuje, że serwer został zmieniony lub plik cookie jest nieprawidłowy. Odśwież wewnętrzną pamięć podręczną i spróbuj ponownie.|
|**0x80cf4016**|OM_E_PT_HTTP_STATUS_BAD_REQUEST|Taki sam jak **stan HTTP 400**. Serwer nie może przetworzyć żądania, ponieważ składnia jest nieprawidłowa.|
|**0x80cf4017**|OM_E_PT_HTTP_STATUS_DENIED|Taki sam jak **stan HTTP 401**. Żądany zasób wymaga uwierzytelnienia użytkownika.|
|**0x80cf4018**|OM_E_PT_HTTP_STATUS_FORBIDDEN|Taki sam jak **stan HTTP 403**. Serwer zrozumiał żądanie, ale odmówił jego spełnienia.|
|**0x80cf4019**|OM_E_PT_HTTP_STATUS_NOT_FOUND|Taki sam jak **stan HTTP 404**. Serwer nie może odnaleźć żądanego identyfikatora URI (Uniform Resource Identifier).|
|**0x80cf401A**|OM_E_PT_HTTP_STATUS_BAD_METHOD|Taki sam jak **stan HTTP 405**. Metoda HTTP jest niedozwolona.|
|**0x80cf401B**|OM_E_PT_HTTP_STATUS_PROXY_AUTH_REQ|Taki sam jak **stan HTTP 407**. Wymagane jest uwierzytelnienie serwera proxy.|
|**0x80cf401C**|OM_E_PT_HTTP_STATUS_REQUEST_TIMEOUT|Taki sam jak **stan HTTP 408**. Upłynął limit czasu serwera podczas oczekiwania na żądanie.|
|**0x80cf401D**|OM_E_PT_HTTP_STATUS_CONFLICT|Taki sam jak **stan HTTP 409**. Żądanie nie zostało ukończone z powodu konfliktu z bieżącym stanem zasobu.|
|**0x80cf401E**|OM_E_PT_HTTP_STATUS_GONE|Taki sam jak **stan HTTP 410**. Żądany zasób nie jest już dostępny na serwerze.|
|**0x80cf401F**|OM_E_PT_HTTP_STATUS_SERVER_ERROR|Taki sam jak **stan HTTP 500**. Wewnętrzny błąd serwera uniemożliwił spełnienie żądania.|
|**0x80cf4020**|OM_E_PT_HTTP_STATUS_NOT_SUPPORTED|Taki sam jak **stan HTTP 500**. Serwer nie obsługuje funkcji wymaganych do spełnienia żądania.|
|**0x80cf4021**|OM_E_PT_HTTP_STATUS_BAD_GATEWAY|Taki sam jak **stan HTTP 502**. Serwer działający jako brama lub serwer proxy otrzymał nieprawidłową odpowiedź od nadrzędnego serwera, do którego uzyskiwał dostęp podczas próby spełnienia żądania.|
|**0x80cf4022**|OM_E_PT_HTTP_STATUS_SERVICE_UNAVAIL|Taki sam jak **stan HTTP 503**. Usługa jest tymczasowo przeciążona.|
|**0x80cf4023**|OM_E_PT_HTTP_STATUS_GATEWAY_TIMEOUT|Taki sam jak **stan HTTP 503**. Upłynął limit czasu żądania w oczekiwaniu na bramę.|
|**0x80cf4024**|OM_E_PT_HTTP_STATUS_VERSION_NOT_SUP|Taki sam jak **stan HTTP 505**. Serwer nie obsługuje wersji protokołu HTTP, która jest używana dla żądania.|
|**0x80cf4025**|OM_E_PT_FILE_LOCATIONS_CHANGED|Operacja nie powiodła się z powodu zmienionej lokalizacji pliku. Odśwież stan wewnętrzny i wyślij ponownie.|
|**0x80cf4027**|OM_E_PT_NO_AUTH_PLUGINS_REQUESTED|Serwer zwrócił pustą listę informacji o uwierzytelnianiu.|
|**0x80cf4028**|OM_E_PT_NO_AUTH_COOKIES_CREATED|Agent nie mógł utworzyć żadnych prawidłowych plików cookie uwierzytelniania.|
|**0x80cf4029**|OM_E_PT_INVALID_CONFIG_PROP|Wartość właściwości konfiguracji jest nieprawidłowa.|
|**0x80cf402A**|OM_E_PT_CONFIG_PROP_MISSING|Brak wartości właściwości konfiguracji.|
|**0x80cf402B**|OM_E_PT_HTTP_STATUS_NOT_MAPPED|Nie można ukończyć żądania HTTP, a przyczyna nie odpowiada żadnemu kodowi błędu **OM_E_PT_HTTP_&#42;**.|
|**0x80cf402C**|OM_E_PT_WINHTTP_NAME_NOT_RESOLVED|Taki sam jak **ERROR_WINHTTP_NAME_NOT_RESOLVED**. Nie można ustalić nazwy serwera proxy lub serwera docelowego.|
|**0x80cf402F**|OM_E_PT_ECP_SUCCEEDED_WITH_ERRORS|Przetwarzanie zewnętrznych plików CAB zostało ukończone z pewnymi błędami.|
|**0x80cf4030**|OM_E_PT_ECP_INIT_FAILED|Nie ukończono inicjalizacji procesora zewnętrznych plików CAB.|
|**0x80cf4031**|OM_E_PT_ECP_INVALID_FILE_FORMAT|Format pliku metadanych jest nieprawidłowy.|
|**0x80cf4032**|OM_E_PT_ECP_INVALID_METADATA|Procesor zewnętrznych plików CAB odnalazł nieprawidłowe metadane.|
|**0x80cf4033**|OM_E_PT_ECP_FAILURE_TO_EXTRACT_DIGEST|Nie można wyodrębnić skrótu pliku z zewnętrznego pliku CAB.|
|**0x80cf4034**|OM_E_PT_ECP_FAILURE_TO_DECOMPRESS_CAB_FILE|Nie można zdekompresować zewnętrznego pliku CAB.|
|**0x80cf4035**|OM_E_PT_ECP_FILE_LOCATION_ERROR|Procesor zewnętrznych plików CAB nie może pobrać lokalizacji plików.|
|**0x80cf4FFF**|OM_E_PT_UNEXPECTED|Wystąpił błąd komunikacji, który nie pasuje do żadnego innego kodu błędu **OM_E_PT_&#42;**.|
|**0x80cf6001**|OM_E_DM_URLNOTAVAILABLE|Nie można ukończyć operacji menedżera pobierania, ponieważ żądany plik nie ma adresu URL.|
|**0x80cf6002**|OM_E_DM_INCORRECTFILEHASH|Nie można ukończyć operacji menedżera pobierania, ponieważ nie został rozpoznany skrót pliku.|
|**0x80cf6003**|OM_E_DM_UNKNOWNALGORITHM|Nie można ukończyć operacji menedżera pobierania, ponieważ metadane pliku zażądały nierozpoznanego algorytmu wyznaczania wartości skrótu.|
|**0x80cf6005**|OM_E_DM_NONETWORK|Nie można ukończyć operacji menedżera pobierania, ponieważ połączenie sieciowe jest niedostępne.|
|**0x80cf6007**|OM_E_DM_NOTDOWNLOADED|Aktualizacja nie została pobrana.|
|**0x80cf6008**|OM_E_DM_FAILTOCONNECTTOBITS|Operacja menedżera pobierania nie powiodła się, ponieważ menedżer pobierania nie może nawiązać połączenia z usługą inteligentnego transferu w tle (Background Intelligent Transfer Service, BITS).|
|**0x80cf6009**|OM_E_DM_BITSTRANSFERERROR|Operacja menedżera pobierania nie powiodła się z powodu nieokreślonego błędu transferu usługi inteligentnego transferu w tle (BITS).|
|**0x80cf600a**|OM_E_DM_DOWNLOADLOCATIONCHANGED|Pobieranie musi zostać ponownie uruchomione, ponieważ lokalizacja źródła pobierania została zmieniona.|
|**0x80cf600B**|OM_E_DM_CONTENTCHANGED|Pobieranie musi zostać ponownie uruchomione, ponieważ zawartość aktualizacji została zmieniona w nowej wersji.|
|**0x80cf6FFF**|OM_E_DM_UNEXPECTED|Wystąpił błąd menedżera pobierania, który nie pasuje do żadnego innego kodu błędu **OM_E_DM_&#42;**.|
|**0x80cf7003**|OM_E_INVALID_EVENT_PAYLOAD|Określono nieprawidłowy ładunek zdarzenia.|
|**0x80cf7004**|OM_E_INVALID_EVENT_PAYLOADSIZE|Rozmiar przekazanego ładunku zdarzenia jest nieprawidłowy.|
|**0x80cf7005**|OM_E_SERVICE_NOT_REGISTERED|Usługa jest niezarejestrowana.|
|**0x80cf8000**|OM_E_DS_SHUTDOWN|Operacja nie powiodła się, ponieważ trwa zamykanie agenta.|
|**0x80cf8001**|OM_E_DS_INUSE|Operacja nie powiodła się, ponieważ magazyn danych jest w użyciu.|
|**0x80cf8002**|OM_E_DS_INVALID|Stan bieżący i stan oczekiwany magazynu danych są niezgodne.|
|**0x80cf8003**|OM_E_DS_TABLEMISSING|W magazynie danych brakuje tabeli.|
|**0x80cf8004**|OM_E_DS_TABLEINCORRECT|Magazyn danych zawiera tabelę, w której znajdują się nieoczekiwane kolumny.|
|**0x80cf8005**|OM_E_DS_INVALIDTABLENAME|Nie można otworzyć tabeli, ponieważ nie znajduje się ona w magazynie danych.|
|**0x80cf8006**|OM_E_DS_BADVERSION|Wersja bieżąca i wersja oczekiwana magazynu danych są niezgodne.|
|**0x80cf8007**|OM_E_DS_NODATA|Żądane informacje nie znajdują się w magazynie danych.|
|**0x80cf8008**|OM_E_DS_MISSINGDATA|W magazynie danych brakuje wymaganych informacji lub zawiera on wartość null w kolumnie tabeli, która wymaga wartości innej niż null.|
|**0x80cf8009**|OM_E_DS_MISSINGREF|W magazynie danych brakuje wymaganych informacji lub zawiera on odwołanie do brakujących postanowień licencyjnych, pliku, zlokalizowanej właściwości lub połączonego wiersza.|
|**0x80cf800A**|OM_E_DS_UNKNOWNHANDLER|Aktualizacja nie została przetworzona, ponieważ jej procedura obsługi nie została rozpoznana.|
|**0x80cf800B**|OM_E_DS_CANTDELETE|Aktualizacja nie została usunięta, ponieważ nadal odwołuje się do niej co najmniej jedna usługa.|
|**0x80cf800C**|OM_E_DS_LOCKTIMEOUTEXPIRED|Nie można zablokować sekcji magazynu danych w wyznaczonym czasie.|
|**0x80cf800E**|OM_E_DS_ROWEXISTS|Nie dodano wiersza, ponieważ istniejący wiersz ma ten sam klucz podstawowy.|
|**0x80cf800F**|OM_E_DS_STOREFILELOCKED|Nie można zainicjować magazynu danych, ponieważ został on zablokowany przez inny proces.|
|**0x80cf8010**|OM_E_DS_CANNOTREGISTER|Zarejestrowanie magazynu danych w modelu COM w bieżącym procesie jest niedozwolone.|
|**0x80cf8011**|OM_E_DS_UNABLETOSTART|Operacja nie może utworzyć obiektu magazynu danych w innym procesie.|
|**0x80cf8013**|OM_E_DS_DUPLICATEUPDATEID|Serwer wysłał tę samą aktualizację do klienta przy użyciu identyfikatorów o dwóch różnych wersjach.|
|**0x80cf8014**|OM_E_DS_UNKNOWNSERVICE|Nie można ukończyć operacji, ponieważ usługa nie znajduje się w magazynie danych.|
|**0x80cf8015**|OM_E_DS_SERVICEEXPIRED|Nie można ukończyć operacji z powodu wygaśnięcia rejestracji usługi.|
|**0x80cf8016**|OM_E_DS_DECLINENOTALLOWED|Żądanie ukrycia aktualizacji zostało odrzucone, ponieważ aktualizacja ta jest obowiązkowa lub została ona wdrożona na podstawie terminu.|
|**0x80cf8017**|OM_E_DS_TABLESESSIONMISMATCH|Tabela nie została zamknięta, ponieważ nie jest skojarzona z sesją.|
|**0x80cf8018**|OM_E_DS_SESSIONLOCKMISMATCH|Tabela nie została zamknięta, ponieważ nie jest skojarzona z sesją.|
|**0x80cf8019**|OM_E_DS_NEEDWINDOWSSERVICE|Żądanie usunięcia lub wyrejestrowania usługi zostało odrzucone, ponieważ usługa ta jest wbudowana lub dlatego, że aktualizacje automatyczne nie mogą wracać do innej usługi.|
|**0x80cf801A**|OM_E_DS_INVALIDOPERATION|Żądanie zostało odrzucone, ponieważ operacja jest niedozwolona.|
|**0x80cf801B**|OM_E_DS_SCHEMAMISMATCH|Schemat bieżącego magazynu danych i schemat tabeli w kopii zapasowej dokumentu XML są niezgodne.|
|**0x80cf801C**|OM_E_DS_RESETREQUIRED|Magazyn danych wymaga zresetowania sesji. Zwolnij sesję, a następnie ponów próbę w nowej sesji.|
|**0x80cf801D**|OM_E_DS_IMPERSONATED|Nie można ukończyć operacji magazynu danych, ponieważ zażądano jej przy użyciu tożsamości spersonifikowanej.|
|**0x80cf8FFF**|OM_E_DS_UNEXPECTED|Wystąpił błąd magazynu danych, który nie pasuje do żadnego innego kodu **OM_E_DS_&#42;**.|
|**0x80cfA000**|OM_E_AU_NOSERVICE|Usługa Aktualizacje automatyczne nie może obsłużyć żądań przychodzących.|
|**0x80cfA004**|OM_E_AU_PAUSED|Usługa Aktualizacje automatyczne nie może przetworzyć żądań przychodzących, ponieważ została wstrzymana.|
|**0x80cfA005**|OM_E_AU_NO_REGISTERED_SERVICE|W usłudze Aktualizacje automatyczne nie została zarejestrowana żadna usługa niezarządzana.|
|**0x80cfA006**|OM_E_AU_DETECT_SVCID_MISMATCH|Podczas wyszukiwania została zmieniona usługa domyślna zarejestrowana w usłudze Aktualizacje automatyczne.|
|**0x80cfA007**|OM_E_AU_ALREADY_PROMPTING_FOR_REBOOT|W usłudze Aktualizacje automatyczne jest już wyświetlany użytkownikowi monit o ponowne uruchomienie.|
|**0x80cfAFFF**|OM_E_AU_UNEXPECTED|Wystąpił błąd usługi Aktualizacje automatyczne, który nie pasuje do żadnego innego kodu **OM_E_AU &#42;**.|
|**0x80cfE001**|OM_E_EE_UNKNOWN_EXPRESSION|Nie można ukończyć operacji ewaluatora wyrażeń, ponieważ wyrażenie nie zostało rozpoznane.|
|**0x80cfE002**|OM_E_EE_INVALID_EXPRESSION|Nie można ukończyć operacji ewaluatora wyrażeń, ponieważ wyrażenie jest nieprawidłowe.|
|**0x80cfE003**|OM_E_EE_MISSING_METADATA|Nie można ukończyć operacji ewaluatora wyrażeń, ponieważ wyrażenie zawiera niewłaściwą liczbę węzłów metadanych.|
|**0x80cfE004**|OM_E_EE_INVALID_VERSION|Nie można ukończyć operacji ewaluatora wyrażeń, ponieważ wersja serializowanych danych wyrażenia jest nieprawidłowa.|
|**0x80cfE005**|OM_E_EE_NOT_INITIALIZED|Nie można zainicjować ewaluatora wyrażeń.|
|**0x80cfE006**|OM_E_EE_INVALID_ATTRIBUTEDATA|Nie można ukończyć operacji ewaluatora wyrażeń, ponieważ atrybut jest nieprawidłowy.|
|**0x80cfE007**|OM_E_EE_CLUSTER_ERROR|Nie można ukończyć operacji ewaluatora wyrażeń, ponieważ nie można ustalić stanu klastra komputera.|
|**0x80cfEFFF**|OM_E_EE_UNEXPECTED|Wystąpił błąd ewaluatora wyrażeń, który nie pasuje do żadnego innego kodu błędu **OM_E_EE_&#42;**.|
|**0x80cfF001**|OM_E_REPORTER_EVENTCACHECORRUPT|Plik pamięci podręcznej zdarzeń jest uszkodzony.|
|**0x80cfF002**|OM_E_REPORTER_EVENTNAMESPACEPARSEFAILED|Nie można przeanalizować kodu XML w deskryptorze przestrzeni nazw zdarzeń.|
|**0x80cfF003**|OM_E_INVALID_EVENT|Kod XML w deskryptorze przestrzeni nazw zdarzeń jest nieprawidłowy.|
|**0x80cfF004**|OM_E_SERVER_BUSY|Serwer odrzucił zdarzenie, ponieważ był zbyt zajęty.|
|**0x80cfFFFF**|OM_E_REPORTER_UNEXPECTED|Wystąpił błąd osoby zgłaszającej błąd, który nie pasuje do żadnego innego kodu błędu.|
|**0x80af0005**|OMC_E_INSTALL_NOT_ALLOWED_REBOOT_REQUIRED|Instalacja nie powiodła się z powodu oczekującego obowiązkowego ponownego rozruchu.|
|**0x80af0006**|OMC_E_DOWNLOAD_CANCELLED|Pobieranie zostało anulowane.|

## Komputery z systemem Windows 7 z dużą liczbą zastąpionych aktualizacji przestają raportować do konsoli usługi Microsoft Intune
**Problem**: Może mieć miejsce sytuacja, w której na klientach usługi Microsoft Intune występuje jeden lub więcej z następujących objawów:
- Raportowanie do konsoli administracyjnej firmy Microsoft zostaje nagle zatrzymane.  
- Wykorzystanie procesora CPU jest wysokie.
- Aplikacje instalowane za pośrednictwem portalu Intune są instalowane powoli.
- Program Microsoft Intune Center wyzwala następujący błąd: *Wystąpił błąd podczas aktualizowania komputera. Znaleziono błąd: Kod 0x800705b4*.
- W polu stanu w obszarze konsoli administracyjnej usługi Intune > Grupy > Wszystkie urządzenia jest wyświetlany komunikat: *Co najmniej jeden agent zainstalowany na tym komputerze ma błędy. Informacje na temat tego komputera mogą być niedokładne lub nieaktualne*.

Ten problem może wystąpić, jeśli zastąpione aktualizacje (aktualizacje, które zostały zastąpione przez inne aktualizacje) nie były odrzucane od dłuższego czasu. Podczas niektórych procesów, takich jak instalowanie aplikacji, system Windows sprawdza kolejno wszystkie zastąpione aktualizacje w celu zapewnienia prawidłowego mapowania aktualizacji oraz ich następców. Jeśli lista zastąpionych aktualizacji zbytnio się rozrośnie, zadanie sprawdzania może powodować wysokie wykorzystanie procesora CPU ze względu na obciążenie związane z przetwarzaniem i wymagany czas. Ten problem dotyczy głównie klientów z systemem Windows 7 ze względu na dużą liczbę zastąpionych aktualizacji dostępnych w systemie Windows 7. W systemie Windows 8 i nowszych systemach operacyjnych liczba zastąpionych aktualizacji nie jest tak duża, dlatego nie są one tak podatne na ten problem.

**Rozwiązanie**: Aby rozwiązać ten problem, wykonaj następujące kroki:
1. Zaloguj się do [konsoli administracyjnej usługi Intune](https://manage.microsoft.com).
2. Wybierz pozycje **Aktualizacje** > **Wszystkie aktualizacje**.
3. Użyj opcji filtrowania na pasku narzędzi u góry, aby filtrować zastąpione aktualizacje.
4. Odrzuć wszystkie zastąpione aktualizacje, które mogą być zastosowane do systemu Windows 7 lub aplikacji (na przykład pakietu Microsoft Office) zainstalowanych na komputerach, których dotyczy problem.
5. Uruchom ponownie klientów, których dotyczy problem.

Ponadto jeśli korzystasz z systemu Windows 7, upewnij się, że następująca aktualizacja jest zainstalowana: [3050265 Klient usługi Windows Update dla systemu Windows 7: czerwiec 2015 r.](https://support.microsoft.com/kb/3050265)

### Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).



<!--HONumber=Aug16_HO2-->


