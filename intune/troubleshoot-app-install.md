---
title: Rozwiązywanie problemów z instalacją aplikacji
titlesuffix: Microsoft Intune
description: Użyj okienka rozwiązywania problemów w usłudze Microsoft Intune do rozwiązywania problemów z instalacją aplikacji.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: c1c2a37103f8fedc09a70b4387aae3f472dfb636
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138683"
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
    > Obecnie usługa Intune nie filtruje aplikacji w oparciu o platformę systemu operacyjnego.

Szczegóły błędu instalacji aplikacji będą wskazywać problem. Tych szczegółów można użyć, aby określić najlepszą akcję do podjęcia w celu rozwiązania problemu. Aby uzyskać dodatkowe informacje na temat rozwiązywania problemów z instalacją aplikacji, zobacz [Error Codes For Troubleshooting App Installation Issues](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues) (Kody błędów na potrzeby rozwiązywania problemów z instalacją aplikacji).

> [!Note]  
> Dostęp do okienka **Rozwiązywanie problemów** można też uzyskać przez przejście w przeglądarce do strony [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów z usługą Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](help-desk-operators.md). 
- Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Znane problemy w usłudze Microsoft Intune](known-issues.md).
- Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
