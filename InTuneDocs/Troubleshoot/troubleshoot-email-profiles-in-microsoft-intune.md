---
title: "Rozwiązywanie problemów z profilami poczty e-mail | Microsoft Intune"
description: "Problemy dotyczące profilów poczty e-mail oraz opisano sposoby ich rozwiązywania."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: 9b699229489be2f09ea4c7a80e1e80f6ec7b106e


---

# Rozwiązywanie problemów z profilami poczty e-mail w usłudze Microsoft Intune
W tym artykule wymieniono niektóre problemy dotyczące profilów poczty e-mail oraz opisano sposoby ich rozwiązywania.

Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](how-to-get-support-for-microsoft-intune.md), aby znaleźć więcej sposobów uzyskania pomocy.


## Nie można wysyłać obrazów z konta e-mail
Użytkownicy, którzy mają automatycznie skonfigurowane konta e-mail, nie mogą wysyłać obrazów ze swoich urządzeń.
Dzieje się tak, gdy opcja **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm** jest wyłączona.

### Rozwiązanie przy użyciu usługi Intune

1.  Otwórz konsolę administracyjną usługi Microsoft Intune i wybierz obciążenie **Zasady** &gt; **Zasady konfiguracji**.

2.  Wybierz profil poczty e-mail i wybierz polecenie **Edytuj**.

3.  Wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

### Rozwiązanie przy użyciu programu Configuration Manager zintegrowanego z usługą Intune

1.  Otwórz program Configuration Manager &gt; **Zasoby i zgodność**.

2.  Rozwiń węzeł **Przegląd** -&gt; **Ustawienia zgodności** -&gt; **Dostęp do zasobów firmy** i wybierz pozycję **Profile poczty e-mail**.

3.  Kliknij prawym przyciskiem myszy profil poczty e-mail i otwórz pozycję **Właściwości**.

4.  Na karcie **Ustawienia synchronizacji** wybierz pozycję **Zezwalaj na wysyłanie wiadomości e-mail z aplikacji innych firm**.

## Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).



<!--HONumber=Jul16_HO4-->


