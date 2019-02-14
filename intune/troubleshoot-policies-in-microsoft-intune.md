---
title: Rozwiązywanie problemów z zasadami w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz, jak korzystać z wbudowanej funkcji rozwiązywania problemów, i zapoznaj się z typowymi problemami lub problemami i ich rozwiązaniami podczas korzystania z zasad zgodności i profilów konfiguracji w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77e86912870b22168a7e2dd3e146b9410c482744
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841083"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Rozwiązywanie problemów związanych z zasadami i profilami w usłudze Intune

Usługa Microsoft Intune zawiera kilka wbudowanych funkcji rozwiązywania problemów. Korzystanie z tych funkcji ułatwia rozwiązywanie problemów z zasadami zgodności i profilami konfiguracji w środowisku.

W tym artykule wymieniono niektóre typowe techniki rozwiązywania problemów i opisano niektóre problemy, które mogą wystąpić.

## <a name="use-built-in-troubleshooting"></a>Korzystanie z wbudowanej funkcji rozwiązywania problemów

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Rozwiązywanie problemów**:

    ![W usłudze Intune przejdź do obszaru Pomoc i obsługa techniczna, a następnie wybierz pozycję Rozwiązywanie problemów.](./media/help-and-support-troubleshoot.png)

3. Wybierz pozycję **Wybierz użytkownika** > zaznacz użytkownika, który napotkał problem > wybierz pozycję **Wybierz**.
4. Upewnij się, że przy pozycjach **Licencja usługi Intune** oraz **Stan konta** wyświetlane są zielone znaczniki wyboru:

    ![W usłudze Intune wybierz użytkownika i upewnij się, że przy pozycjach Stan konta i Licencja usługi Intune wyświetlane są zielone znaczniki wyboru.](./media/account-status-intune-license-show-green.png)

    **Przydatne linki**:

    - [Przypisywanie licencji, aby użytkownicy mogli rejestrować urządzenia](licenses-assign.md)
    - [Dodawanie użytkowników do usługi Intune](users-add.md)

5. W obszarze **Urządzenia** znajdź urządzenie, które napotkało problem. Przejrzyj różne kolumny:

    - **Zarządzane**: aby urządzenie mogło odbierać zasady zgodności lub konfiguracji, ta właściwość musi mieć wartość **MDM** lub **EAS/MDM**.

      - Jeśli właściwość **Zarządzane** nie ma wartości **MDM** lub **EAS/MDM**, oznacza to, że urządzenie nie jest zarejestrowane. Nie odbierze ono zasad zgodności ani konfiguracji, dopóki nie zostanie zarejestrowane.

      - Zasady ochrony aplikacji (zarządzanie aplikacjami mobilnymi) nie wymagają, aby urządzenia były zarejestrowane. Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md).

    - **Typ dołączenia do usługi Azure AD**: powinna mieć wartość **Obszar roboczy** lub **AzureAD**.
 
      - Jeśli ta kolumna ma wartość **Niezarejestrowane**, może to oznaczać problem z rejestracją. Zazwyczaj wyrejestrowywanie i ponowne zarejestrowanie urządzenia rozwiązuje ten problem.

    - **Zgodne z usługą Intune**: powinna mieć wartość **Tak**. Jeśli jest wyświetlana wartość **Nie**, może to oznaczać problem z zasadami zgodności lub urządzenie nie łączy się z usługą Intune. Na przykład urządzenie może być wyłączone lub nie mieć połączenia sieciowego. Po pewnym czasie urządzenie stanie się niezgodne, prawdopodobnie po upływie 30 dni.

      Aby uzyskać więcej informacji, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

    - **Zgodne z usługą Azure AD**: powinna mieć wartość **Tak**. Jeśli jest wyświetlana wartość **Nie**, może to oznaczać problem z zasadami zgodności lub urządzenie nie łączy się z usługą Intune. Na przykład urządzenie może być wyłączone lub nie mieć połączenia sieciowego. Po pewnym czasie urządzenie stanie się niezgodne, prawdopodobnie po upływie 30 dni.

      Aby uzyskać więcej informacji, zobacz [Wprowadzenie do zasad zgodności urządzeń](device-compliance-get-started.md).

    - **Ostatnie zaewidencjonowanie**: powinna być niedawną godziną i datą. Domyślnie urządzenia w usłudze Intune są ewidencjonowane co 8 godzin.

      - Jeśli **Ostatnie zaewidencjonowanie** ma wartość większą niż 24 godziny, może to oznaczać problem z urządzeniem. Urządzenie, którego nie można zaewidencjonować, nie może odbierać zasad z usługi Intune.

      - Aby wymusić zaewidencjonowanie, wykonaj następujące czynności:
        - Na urządzeniu z systemem Android, Otwórz aplikację Portal firmy > **Urządzenia** > wybierz urządzenie z listy > **Sprawdź ustawienia urządzenia**.
        - Na urządzeniu z systemem iOS otwórz aplikację Portal firmy > **Urządzenia** > wybierz urządzenie z listy > **Sprawdź ustawienia**. 
        - Na urządzeniu z systemem Windows otwórz pozycję **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** > wybierz konto lub rejestrację w usłudze zarządzania urządzeniami mobilnymi > **Informacje** > **Synchronizuj**.

    - Wybierz urządzenie, aby wyświetlić informacje dotyczące zasad.

      **Zgodność urządzenia** przedstawia stany zasad zgodności przypisanych do urządzenia.

      **Konfiguracja urządzenia** przedstawia stany zasad konfiguracji przypisanych do urządzenia.

      Jeśli oczekiwane zasady nie są wyświetlane w obszarze **Zgodność urządzenia** lub **Konfiguracja urządzenia**, oznacza to, że zasady nie mają prawidłowego elementu docelowego. Otwórz zasady, a następnie przypisz je do tego użytkownika lub urządzenia.

      **Stany zasad**:

      - **Nie dotyczy**: te zasady nie są obsługiwane na tej platformie. Na przykład zasady systemu iOS nie działają w systemie Android. Zasady systemu Samsung KNOX nie działają na urządzeniach z systemem Windows.
      - **Konflikt**: na urządzeniu istnieje ustawienie, którego usługa Intune nie może zastąpić. Lub wdrożono dwie zasady z tym samym ustawieniem przy użyciu różnych wartości.
      - **Oczekujące**: urządzenie nie zostało zaewidencjonowane w usłudze Intune w celu otrzymania zasad. Lub urządzenie odebrało zasady, ale nie zgłosiło stanu usłudze Intune.
      - **Błędy**: wyszukaj błędy i możliwe rozwiązania w artykule [Rozwiązywanie problemów z dostępem do zasobów firmy](troubleshoot-company-resource-access-problems.md).

      **Przydatne linki**: 

      - [Sposoby wdrażania zasad zgodności urządzeń](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
      - [Monitorowanie zasad zgodności urządzeń](compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Nie masz pewności, czy poprawnie zastosowano profil

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Konfiguracja urządzenia**. 

    Każde urządzenie ma listę swoich profilów. Każdy profil ma **Stan**. Stan ma zastosowanie, gdy wszystkie przypisane profile, w tym sprzęt oraz wymagania i ograniczenia systemu operacyjnego, są uwzględniane razem. Dostępne są następujące stany:

    - **Zgodne**: urządzenie odebrało profil i zgłasza usłudze Intune, że działa zgodnie z ustawieniem.

    - **Nie dotyczy**: ustawienie profilu nie ma zastosowania. Pa przykład ustawienia poczty e-mail dla urządzeń z systemem iOS nie mają zastosowania do urządzenia z systemem Android.

    - **Oczekujące**: profil został wysłany do urządzenia, ale nie zgłosiło ono stanu usłudze Intune. Na przykład szyfrowanie w systemie Android wymaga od użytkownika końcowego włączenia szyfrowania, dlatego może być wyświetlany stan Oczekujące.

**Przydatny link**: [Monitorowanie profilów urządzeń konfiguracji](device-profile-monitor.md)

> [!NOTE]
> Jeśli dwie zasady z różnymi poziomami ograniczeń dotyczą tego samego urządzenia lub użytkownika, zostaną zastosowane zasady bardziej restrykcyjne.

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alert: Zapisywanie reguł dostępu w programie Exchange nie powiodło się

**Problem**: w konsoli administracyjnej odebrano alert **Zapisywanie reguł dostępu w programie Exchange nie powiodło się**.

Jeśli utworzysz w obszarze roboczym Zasady lokalnej instalacji programu Exchange (konsola administracyjna), ale używasz usługi Office 365, skonfigurowane ustawienia zasad nie będą wymuszane przez usługę Intune. Zanotuj źródło zasad w alercie. W obszarze roboczym Zasady lokalnej instalacji programu Exchange usuń starsze reguły. Starsze reguły to globalne reguły programu Exchange w usłudze Intune dla lokalnego programu Exchange i nie są odpowiednie w przypadku usługi Office 365. Następnie utwórz nowe zasady dla usługi Office 365.

Przydatne informacje można znaleźć w artykule [Rozwiązywanie problemów z lokalnym łącznikiem Exchange Connector usługi Intune](troubleshoot-exchange-connector.md).

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Nie można zmienić zasad zabezpieczeń dla zarejestrowanych urządzeń

Urządzenia z systemem Windows Phone nie zezwalają na obniżenie bezpieczeństwa zasad zabezpieczeń ustawionych wcześniej przy użyciu usługi MDM lub EAS. Na przykład po ustawieniu dla zasady **Minimalna liczba znaków hasła** wartości 8 nastąpiła próba jej zmniejszenia do 4. Do urządzenia są stosowane bardziej restrykcyjne zasady.

W zależności od platformy urządzenia jeśli chcesz zmienić zasady na wartość mniej bezpieczną, może być konieczne zresetowanie zasad zabezpieczeń.

Na przykład w systemie Windows na pulpicie przesuń palcem z prawej strony, aby otworzyć pasek **Panele funkcji**. Wybierz pozycję **Ustawienia** > **Panel sterowania** > **Konta użytkowników**. Po lewej stronie wybierz link **Resetuj zasady zabezpieczeń** i wybierz pozycję **Resetuj zasady**.

W przypadku innych urządzeń MDM, takich jak urządzenia z systemami Android, iOS czy Windows Phone 8.1, zastosowanie mniej restrykcyjnych zasad może wymagać wycofania i ponownego zarejestrowania urządzenia.

Przydatne informacje można znaleźć w artykule [Rozwiązywanie problemów z rejestrowaniem urządzeń](troubleshoot-device-enrollment-in-intune.md).

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Komputery z oprogramowaniem klienckim usługi Intune — portal klasyczny

> [!NOTE]
> Ta sekcja dotyczy portalu klasycznego. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Błędy związane z zasadami usługi Microsoft Intune w pliku policyplatform.log

W przypadku komputerów z systemem Windows zarządzanych przy użyciu oprogramowania klienckiego usługi Intune błędy zasad w pliku `policyplatform.log` mogą wynikać z innych niż domyślne ustawień w Kontroli konta użytkownika (UAC) systemu Windows na urządzeniu. Niektóre inne niż domyślne ustawienia funkcji Kontroli konta użytkownika mogą wpływać na instalacje klienta usługi Microsoft Intune i wykonywanie zasad.

#### <a name="resolve-uac-issues"></a>Rozwiązywanie problemów z Kontrolą konta użytkownika

1. Wycofaj komputer. Zobacz [Usuwanie urządzeń](devices-wipe.md).

2. Zaczekaj 20 minut na usunięcie oprogramowania klienckiego.

    > [!NOTE]
    > Nie należy próbować usuwać klienta z poziomu opcji Programy i funkcje.

3. W menu start wpisz wartość **Kontrola konta użytkownika**, aby otworzyć ustawienia Kontroli konta użytkownika.

4. Przesuń suwak powiadomień na ustawienie domyślne.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>BŁĄD: Nie można uzyskać wartości z komputera, 0x80041013

Występuje, jeśli godzina w systemie lokalnym różni się o pięć lub więcej minut. Jeśli godzina na komputerze lokalnym nie jest zsynchronizowana, zabezpieczone transakcje zakończą się niepowodzeniem ze względu na nieprawidłowe sygnatury czasowe.

Aby rozwiązać ten problem, ustaw czas sytemu lokalnego na wartość jak najbliższą czasowi internetowemu. Lub ustaw czas zgodny z czasem w kontrolerach domeny w sieci.

## <a name="next-steps"></a>Następne kroki

Jeśli nadal potrzebujesz pomocy, możesz [uzyskać pomoc dotyczącą usługi Microsoft Intune](get-support.md).
