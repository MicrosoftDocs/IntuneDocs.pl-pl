---
# required metadata

title: Twój komputer jest już zarejestrowany | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Twój komputer jest już zarejestrowany
Widzisz tę stronę, ponieważ została przez Ciebie uruchomiona instalacja oprogramowania klienckiego usługi Intune. Jednak to oprogramowanie jest już zainstalowane na Twoim komputerze i nie można kontynuować instalacji.

Możliwe przyczyny:

-   Oprogramowanie klienckie zostało zainstalowane wcześniej, a program instalacyjny został uruchomiony ponownie.

-   Program instalacyjny uruchomiono na komputerze po tym, jak administrator IT wycofał Twoje urządzenie z usługi Intune. Po wycofaniu urządzenia może upłynąć kilka godzin, zanim oprogramowanie klienckie zostanie usunięte z komputera.

-   Program instalacyjny wykrył niedawną nieudaną instalację lub nieudane usunięcie oprogramowania klienckiego.

## Co program instalacyjny instaluje na komputerze
Program instalacyjny instaluje klienta usługi Intune. Po zakończeniu pracy programu instalacyjnego oprogramowanie klienckie jest nadal uruchomione w tle, ponieważ konfiguruje na komputerze używanie usługi Intune. Może to potrwać jakiś czas i obejmuje:

-   Zarejestrowanie komputera w usłudze Intune

-   Przesłanie spisu informacji o sprzęcie komputera oraz zainstalowanym oprogramowaniu

-   Skonfigurowanie zasad usługi Intune, w tym zainstalowanie programu Endpoint Protection (jeśli jest to skonfigurowane)

-   Instalowanie programu Intune Center

Po zainstalowaniu programu Intune Center można za jego pomocą uzyskać dostęp do portalu firmy, gdzie można połączyć komputer z kontem służbowym.

## Microsoft Intune Center
Program Intune Center jest instalowany jako aplikacja na komputerze po pomyślnym zainstalowaniu na komputerze oprogramowania klienckiego i zarejestrowaniu komputera w usłudze Intune. Oto co można zrobić w programie Intune Center:

-   **Pobierz aplikacje z Portalu firmy** — znajdź i zainstaluj aplikacje wdrożone przez administratora IT. Gdy pierwszy raz logujesz się do portalu firmy na nowo zarejestrowanym komputerze, jest Ci udostępniana opcja połączenia Twojego konta służbowego z tym komputerem.

-   **Sprawdź, czy są aktualizacje oprogramowania** — znajdź aktualizacje oprogramowania wdrożone przez administratora usługi Intune.

-   **Rozpocznij skanowanie komputera za pomocą programu Endpoint Protection** — możesz uruchomić skanowanie w poszukiwaniu złośliwego oprogramowania na komputerze.

-   **Poproś o pomoc zdalną** — ta opcja jest dostępna tylko w przypadku, gdy pomoc zdalna jest obsługiwana przez system operacyjny używanego komputera.

## Sprawdzanie, czy oprogramowanie klienckie jest zainstalowane lub zostało usunięte
**Sprawdzanie, czy klient jest zainstalowany:**
Instalacja klienta usługi Intune została ukończona, gdy następujące aplikacje są dostępne na komputerze:

-   **Intune Center**

-   **Intune Endpoint Protection** (jeśli program Endpoint Protection został włączony przez administratora IT)

Jeśli potrafisz używać Menedżera zadań, możesz wyszukać usługę klienta usługi Intune, która powinna być uruchomiona:

-   **OmcSvc**

**Sprawdzanie, czy klient został usunięty:**
Po odinstalowaniu z komputera klienta usługi Intune aplikacje, które zostały zainstalowane podczas instalacji klienta, są usuwane, także program Intune Center.

Usługa klienta usługi Intune, **OmcSvc**, jest usuwana.

## Jak usunąć z komputera oprogramowanie klienckie
Domyślnie kilka godzin po wycofaniu komputera przez administratora IT w konsoli administracyjnej usługi Intune oprogramowanie klienckie usługi Intune zostanie odinstalowane.

Aby ręcznie odinstalować oprogramowanie klienckie usługi Intune z komputera, można wymusić dezinstalację, wykonując następujące kroki:

1.  Na komputerze otwórz wiersz polecenia w trybie administratora.

2.  Przejdź do folderu **%programfiles%\Microsoft\OnlineManagement\Common**

3.  Uruchom następujące polecenie: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

Spowoduje to zaplanowanie usunięcia oprogramowania klienckiego.



<!--HONumber=May16_HO1-->


