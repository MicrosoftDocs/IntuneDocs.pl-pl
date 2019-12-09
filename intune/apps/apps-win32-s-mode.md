---
title: Włączanie obsługi aplikacji Win32 na urządzeniach w trybie S
titleSuffix: Microsoft Intune
description: Dowiedz się, jak włączyć obsługę aplikacji Win32 na urządzeniach w trybie S przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e17972a3a87bd9c42db54753d4da3bb81703377
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563624"
---
# <a name="enable-win32-apps-on-s-mode-devices"></a>Włączanie obsługi aplikacji Win32 na urządzeniach w trybie S

[Tryb S systemu Windows 10](https://docs.microsoft.com/windows/deployment/s-mode) to zablokowany system operacyjny, który uruchamia tylko aplikacje ze Sklepu. Domyślnie urządzenia w trybie S systemu Windows nie zezwalają na instalowanie i wykonywanie aplikacji Win32. Te urządzenia zawierają jedną *zasadę podstawową systemu Win 10S*, która blokuje na urządzeniu w trybie S uruchamianie jakichkolwiek aplikacji Win32. Jednak dzięki utworzeniu i zastosowaniu **zasad uzupełniających trybu S** w usłudze Intune można instalować i uruchamiać aplikacje Win32 na urządzeniach zarządzanych w trybie S systemu Windows 10. Używając narzędzi programu PowerShell dla [Kontroli aplikacji usługi Microsoft Defender (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control), można utworzyć jedną lub kilka zasad uzupełniających dla trybu S systemu Windows. Należy podpisać zasady uzupełniające za pomocą [usługi Device Guard — podpisywanie (DGSS)](https://go.microsoft.com/fwlink/?linkid=2095629) lub narzędzia [SignTool.exe](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/signing-policies-with-signtool), a następnie przekazać i rozpowszechnić zasady za pośrednictwem usługi Intune. Alternatywnie zasady uzupełniające można podpisać przy użyciu certyfikatu podpisywania kodu swojej organizacji, jednak preferowaną metodą jest użycie usługi DGSS. W przypadku korzystania z certyfikatu podpisywania kodu swojej organizacji certyfikat główny, do którego jest dowiązany certyfikat podpisywania kodu, musi znajdować się na urządzeniu.

Przypisując zasady uzupełniające trybu S w usłudze Intune, umożliwiasz urządzeniu zastosowanie wyjątku dla istniejących zasad trybu S urządzenia, co pozwala na przekazanie odpowiedniego podpisanego wykazu aplikacji. Zasady te określają listę dozwolonych aplikacji (wykaz aplikacji), które mogą być używane na urządzeniu w trybie S.

> [!NOTE]
> Aplikacje Win32 na urządzeniach w trybie S są obsługiwane tylko w aktualizacji systemu Windows 10 z listopada 2019 r. (kompilacja 18363) i w nowszych wersjach.

<!-- Add WDAC tooling diagram  -->

Kroki umożliwiające uruchamianie aplikacji Win32 na urządzeniu z systemem Windows 10 w trybie S są następujące:

1. Włącz urządzenia w trybie S za pośrednictwem usługi Intune w ramach procesu rejestracji systemu Windows 10 S.
2. Utwórz zasady uzupełniające, aby zezwolić na aplikacje Win32:
   - Aby utworzyć zasady uzupełniające, możesz użyć narzędzi [Kontroli aplikacji usługi Microsoft Defender (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control). Identyfikator zasad podstawowych w obrębie tych zasad musi być zgodny z identyfikatorem zasad podstawowych trybu S (który jest na stałe zakodowany na kliencie). Upewnij się również, że wersja zasad jest wyższa niż poprzednia wersja.
   - Użyj usługi DGSS, aby podpisać zasady uzupełniające. Aby uzyskać więcej informacji, zobacz [Podpisywanie zasad integralności kodu przy użyciu usługi Device Guard — podpisywanie](https://docs.microsoft.com/microsoft-store/sign-code-integrity-policy-with-device-guard-signing).
   - Aby przekazać podpisane zasady uzupełniające do usługi Intune, należy utworzyć zasady uzupełniające trybu S systemu Windows 10 (zobacz poniżej).
3. Aby zezwolić na wykazy aplikacji Win32, należy użyć usługi Intune:
   - Tworzysz pliki wykazu (1 dla każdej aplikacji) i podpisujesz je za pomocą usługi DGSS lub innej infrastruktury certyfikatów.
   - Pakujesz podpisany wykaz do pliku *.intunewin* przy użyciu narzędzia [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730). Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami Win32 — Przygotowanie zawartości aplikacji Win32 do przekazania](~/apps/apps-win32-app-management.md#prepare-the-win32-app-content-for-upload).
   - Usługa Intune stosuje podpisany wykaz aplikacji w celu zainstalowania aplikacji Win32 na urządzeniu w trybie S przy użyciu [rozszerzenia do zarządzania usługi Intune](~/apps/intune-management-extension.md).

> [!NOTE]
> Aplikacje biznesowe `.appx` i pakiety `.appx` w trybie S systemu Windows 10 będą obsługiwane za pośrednictwem funkcji podpisywania sklepu Microsoft Store dla Firm (MSFB).
>
> **Zasady uzupełniające trybu S** dla aplikacji muszą zostać dostarczone za pośrednictwem rozszerzenia do zarządzania usługi Intune.
>
> Zasady trybu S są wymuszane na poziomie urządzenia. Na urządzeniu zostanie scalonych wiele zasad docelowych. Scalone zasady zostaną wymuszone na urządzeniu.

Aby utworzyć zasady uzupełniające trybu S systemu Windows 10, wykonaj następujące czynności:

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Aplikacje** > **Zasady uzupełniające trybu S** > **Utwórz zasady**.
3. Przed dodaniem **pliku zasad** należy go utworzyć i podpisać. Aby uzyskać więcej informacji, zobacz:
    - [Tworzenie zasad WDAC przy użyciu narzędzi programu PowerShell i konwertowanie ich na format binarny](https://go.microsoft.com/fwlink/?linkid=2095387)
    - [Podpisywanie przy użyciu usługi Device Guard — podpisywanie (DGSS)](https://go.microsoft.com/fwlink/?linkid=2095629) **(zalecane)**

4. Na stronie **Podstawowe** dodaj następujące wartości:

    | Wartość | Opis |
    |--------------|------------------------------------------------|
    | Plik zasad | Plik, który zawiera zasady WDAC. |
    | Nazwa | Nazwa tych zasad. |
    | Opis | [Opcjonalnie] Opis tych zasad. |

5. Kliknij przycisk **Dalej: Tagi zakresu**.<br>
   Na stronie **Tagi zakresu** można opcjonalnie skonfigurować tagi zakresu, aby określić, kto może zobaczyć zasady aplikacji w usłudze Intune. Więcej informacji na temat tagów zakresu można znaleźć w artykule [Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej](~/fundamentals/scope-tags.md).

6. Kliknij przycisk **Dalej: Przypisania**.<br>
   Strona **Przypisania** umożliwia przypisanie zasad do użytkowników i urządzeń. Ważne jest, aby pamiętać, że zasady można przypisać do urządzenia bez względu na to, czy jest ono zarządzane przez usługę Intune.
7. Kliknij przycisk **Dalej: Przeglądanie + tworzenie**, aby przejrzeć wartości wprowadzone dla profilu.
8. Gdy skończysz, kliknij pozycję **Utwórz**, aby utworzyć zasady uzupełniające trybu S w usłudze Intune. 

Po utworzeniu zasad zobaczysz, że zostaną one dodane do listy zasad uzupełniających trybu S w usłudze Intune. Po przypisaniu zasad zostaną one wdrożone na urządzeniach. Należy pamiętać, że aplikacja musi zostać wdrożona w tej samej grupie zabezpieczeń, co zasady uzupełniające. Możesz zacząć kierować i przypisywać aplikacje do tych urządzeń. Dzięki temu użytkownicy końcowi będą mogli instalować i uruchamiać aplikacje na urządzeniach w trybie S.

## <a name="removal-of-s-mode-policy"></a>Usuwanie zasad trybu S

Obecnie, aby usunąć zasady uzupełniające trybu S z urządzenia, należy przypisać i wdrożyć puste zasady w celu zastąpienia istniejących zasad uzupełniających trybu S.

## <a name="policy-reporting"></a>Raportowanie zasad

Zasady uzupełniające trybu S, które są wymuszane na poziomie urządzenia, mają tylko raportowanie na poziomie urządzenia. Raportowanie na poziomie urządzenia jest dostępne dla warunków powodzenia i błędów. 

Raportowane wartości, które są wyświetlane w konsoli usługi Intune dla zasad raportowania trybu S:
- **Powodzenie**: Zasady uzupełniające trybu S obowiązują.
- **Nieznane**: Stan zasad uzupełniających trybu S jest nieznany.
- **TokenError**: Zasady uzupełniające trybu S są strukturalnie dobre, ale wystąpił błąd podczas autoryzowania tokenu.
- **NotAuthorizedByToken**: Token nie autoryzuje tych zasad uzupełniających trybu S.
- **PolicyNotFound**: Zasady uzupełniające trybu S nie zostały odnalezione.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji, zobacz [Aplikacje Win32 w trybie S](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/lob-win32-apps-on-s).
- Aby uzyskać więcej informacji na temat dodawania aplikacji do usługi Intune, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](apps-add.md).
- Aby uzyskać więcej informacji o aplikacjach Win32, zobacz [Zarządzanie aplikacjami Win32 w usłudze Intune](~/apps/apps-win32-app-management.md).
