---
title: Rozwiązywanie problemów z zasadami w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz, jak korzystać z wbudowanej funkcji rozwiązywania problemów, i zapoznaj się z typowymi problemami lub problemami i ich rozwiązaniami podczas korzystania z zasad zgodności i profilów konfiguracji w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9acb934cdf67aae9c18091a0340f27de635b5399
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511021"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Rozwiązywanie problemów związanych z zasadami i profilami w usłudze Intune

Usługa Microsoft Intune zawiera kilka wbudowanych funkcji rozwiązywania problemów. Korzystanie z tych funkcji ułatwia rozwiązywanie problemów z zasadami zgodności i profilami konfiguracji w środowisku.

W tym artykule wymieniono niektóre typowe techniki rozwiązywania problemów i opisano niektóre problemy, które mogą wystąpić.

## <a name="check-tenant-status"></a>Sprawdzenie stanu dzierżawy

Sprawdź [stan dzierżawy](../fundamentals/tenant-status.md) i upewnij się, że subskrypcja jest aktywna. Możesz również wyświetlić szczegóły dotyczące aktywnych zdarzeń i porad, które mogą mieć wpływ na wdrożenie zasad lub profilu.

## <a name="use-built-in-troubleshooting"></a>Korzystanie z wbudowanej funkcji rozwiązywania problemów

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rozwiązywanie problemów i pomoc techniczna**:

    ![W usłudze Intune przejdź do obszaru Pomoc i obsługa techniczna, a następnie wybierz pozycję Rozwiązywanie problemów.](./media/troubleshoot-policies-in-microsoft-intune/help-and-support-troubleshoot.png)

2. Wybierz pozycję **Wybierz użytkownika** > zaznacz użytkownika, który napotkał problem > wybierz pozycję **Wybierz**.
3. Upewnij się, że przy pozycjach **Licencja usługi Intune** oraz **Stan konta** wyświetlane są zielone znaczniki wyboru:

    ![W usłudze Intune wybierz użytkownika i upewnij się, że przy pozycjach Stan konta i Licencja usługi Intune wyświetlane są zielone znaczniki wyboru.](./media/troubleshoot-policies-in-microsoft-intune/account-status-intune-license-show-green.png)

    **Przydatne linki**:

    - [Przypisywanie licencji, aby użytkownicy mogli rejestrować urządzenia](../fundamentals/licenses-assign.md)
    - [Dodawanie użytkowników do usługi Intune](../fundamentals/users-add.md)

4. W obszarze **Urządzenia** znajdź urządzenie, które napotkało problem. Przejrzyj różne kolumny:

    - **Zarządzane**: aby urządzenie mogło odbierać zasady zgodności lub konfiguracji, ta właściwość musi mieć wartość **MDM** lub **EAS/MDM**.

        - Jeśli właściwość **Zarządzane** nie ma wartości **MDM** lub **EAS/MDM**, oznacza to, że urządzenie nie jest zarejestrowane. Nie odbierze ono zasad zgodności ani konfiguracji, dopóki nie zostanie zarejestrowane.

        - Zasady ochrony aplikacji (zarządzanie aplikacjami mobilnymi) nie wymagają, aby urządzenia były zarejestrowane. Aby uzyskać więcej informacji, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](../apps/app-protection-policies.md).

    - **Typ dołączenia do usługi Azure AD**: powinna mieć wartość **Obszar roboczy** lub **AzureAD**.
 
        - Jeśli ta kolumna ma wartość **Niezarejestrowane**, może to oznaczać problem z rejestracją. Zazwyczaj wyrejestrowywanie i ponowne zarejestrowanie urządzenia rozwiązuje ten problem.

    - **Zgodne z usługą Intune**: powinna mieć wartość **Tak**. Jeśli jest wyświetlana wartość **Nie**, może to oznaczać problem z zasadami zgodności lub urządzenie nie łączy się z usługą Intune. Na przykład urządzenie może być wyłączone lub nie mieć połączenia sieciowego. Po pewnym czasie urządzenie stanie się niezgodne, prawdopodobnie po upływie 30 dni.

        Aby uzyskać więcej informacji, zobacz [Wprowadzenie do zasad zgodności urządzeń](../protect/device-compliance-get-started.md).

    - **Zgodne z usługą Azure AD**: powinna mieć wartość **Tak**. Jeśli jest wyświetlana wartość **Nie**, może to oznaczać problem z zasadami zgodności lub urządzenie nie łączy się z usługą Intune. Na przykład urządzenie może być wyłączone lub nie mieć połączenia sieciowego. Po pewnym czasie urządzenie stanie się niezgodne, prawdopodobnie po upływie 30 dni.

        Aby uzyskać więcej informacji, zobacz [Wprowadzenie do zasad zgodności urządzeń](../protect/device-compliance-get-started.md).

    - **Ostatnie zaewidencjonowanie**: powinna być niedawną godziną i datą. Domyślnie urządzenia w usłudze Intune są ewidencjonowane co 8 godzin.

        - Jeśli **Ostatnie zaewidencjonowanie** ma wartość większą niż 24 godziny, może to oznaczać problem z urządzeniem. Urządzenie, którego nie można zaewidencjonować, nie może odbierać zasad z usługi Intune.

        - Aby wymusić zaewidencjonowanie, wykonaj następujące czynności:
            - Na urządzeniu z systemem Android, Otwórz aplikację Portal firmy > **Urządzenia** > wybierz urządzenie z listy > **Sprawdź ustawienia urządzenia**.
            - Na urządzeniu z systemem iOS/iPadOS otwórz aplikację Portal firmy > **Urządzenia** > wybierz urządzenie z listy > **Sprawdź ustawienia**.

        - Na urządzeniu z systemem Windows otwórz pozycję **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki** > wybierz konto lub rejestrację w usłudze zarządzania urządzeniami mobilnymi > **Informacje** > **Synchronizuj**.

    - Wybierz urządzenie, aby wyświetlić informacje dotyczące zasad.

        **Zgodność urządzenia** przedstawia stany zasad zgodności przypisanych do urządzenia.

        **Konfiguracja urządzenia** przedstawia stany zasad konfiguracji przypisanych do urządzenia.

        Jeśli oczekiwane zasady nie są wyświetlane w obszarze **Zgodność urządzenia** lub **Konfiguracja urządzenia**, oznacza to, że zasady nie mają prawidłowego elementu docelowego. Otwórz zasady, a następnie przypisz je do tego użytkownika lub urządzenia.

        **Stany zasad**:

        - **Nie dotyczy**: te zasady nie są obsługiwane na tej platformie. Na przykład zasady systemu iOS/iPadOS nie działają w systemie Android. Zasady systemu Samsung KNOX nie działają na urządzeniach z systemem Windows.
        - **Konflikt**: na urządzeniu istnieje ustawienie, którego usługa Intune nie może zastąpić. Lub wdrożono dwie zasady z tym samym ustawieniem przy użyciu różnych wartości.
        - **Oczekujące**: urządzenie nie zostało zaewidencjonowane w usłudze Intune w celu otrzymania zasad. Lub urządzenie odebrało zasady, ale nie zgłosiło stanu usłudze Intune.
        - **Błędy**: wyszukaj błędy i możliwe rozwiązania w artykule [Rozwiązywanie problemów z dostępem do zasobów firmy](../fundamentals/troubleshoot-company-resource-access-problems.md).

        **Przydatne linki**: 

        - [Sposoby wdrażania zasad zgodności urządzeń](../protect/device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
        - [Monitorowanie zasad zgodności urządzeń](../protect/compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Nie masz pewności, czy poprawnie zastosowano profil

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Konfiguracja urządzenia**. 

    Każde urządzenie ma listę swoich profilów. Każdy profil ma **Stan**. Stan ma zastosowanie, gdy wszystkie przypisane profile, w tym sprzęt oraz wymagania i ograniczenia systemu operacyjnego, są uwzględniane razem. Dostępne są następujące stany:

    - **Zgodne**: urządzenie odebrało profil i zgłasza usłudze Intune, że działa zgodnie z ustawieniem.

    - **Nie dotyczy**: ustawienie profilu nie ma zastosowania. Na przykład ustawienia poczty e-mail dla urządzeń z systemem iOS/iPadOS nie mają zastosowania do urządzenia z systemem Android.

    - **Oczekujące**: profil został wysłany do urządzenia, ale nie zgłosiło ono stanu usłudze Intune. Na przykład szyfrowanie w systemie Android wymaga od użytkownika końcowego włączenia szyfrowania, dlatego może być wyświetlany stan Oczekujące.

**Przydatny link**: [Monitorowanie profilów urządzeń konfiguracji](../configuration/device-profile-monitor.md)

> [!NOTE]
> Jeśli dwie zasady z różnymi poziomami ograniczeń dotyczą tego samego urządzenia lub użytkownika, zostaną zastosowane zasady bardziej restrykcyjne.

## <a name="policy-troubleshooting-resources"></a>Zasoby służące do rozwiązywania problemów z zasadami

- [Rozwiązywanie problemów z zasadami systemu iOS/iPadOS lub Android, których nie udaje się zastosować do urządzeń](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-tip-Troubleshooting-iOS-or-Android-policies-not-applying/ba-p/280154) (przejście do innej witryny firmy Microsoft)
- [Rozwiązywanie problemów z błędami dotyczącymi zasad usługi Intune systemu Windows 10](https://blogs.technet.microsoft.com/configmgrdogs/2018/08/09/troubleshooting-windows-10-intune-policy-failures/) (przejście do bloga)
- [Rozwiązywanie problemów z ustawieniami niestandardowymi programu CSP dla systemu Windows 10](https://support.microsoft.com/en-us/help/4055338/troubleshoot-csp-setting-windows-10-computer-intune) (przejście do innej witryny firmy Microsoft)
- [Zasady grupy w systemie Windows 10 a zasady zarządzania urządzeniami mobilnymi w usłudze Intune](https://blogs.technet.microsoft.com/cbernier/2018/04/02/windows-10-group-policy-vs-intune-mdm-policy-who-wins/) (przejście do innej witryny firmy Microsoft)

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alert: Zapisywanie reguł dostępu w programie Exchange nie powiodło się

**Problem**: w konsoli administracyjnej odebrano alert **Zapisywanie reguł dostępu w programie Exchange nie powiodło się**.

Jeśli utworzysz w obszarze roboczym Zasady lokalnej instalacji programu Exchange (konsola administracyjna), ale używasz usługi Office 365, skonfigurowane ustawienia zasad nie będą wymuszane przez usługę Intune. Zanotuj źródło zasad w alercie. W obszarze roboczym Zasady lokalnej instalacji programu Exchange usuń starsze reguły. Starsze reguły to globalne reguły programu Exchange w usłudze Intune dla lokalnego programu Exchange i nie są odpowiednie w przypadku usługi Office 365. Następnie utwórz nowe zasady dla usługi Office 365.

Przydatne informacje można znaleźć w artykule [Rozwiązywanie problemów z lokalnym łącznikiem Exchange Connector usługi Intune](../protect/troubleshoot-exchange-connector.md).

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Nie można zmienić zasad zabezpieczeń dla zarejestrowanych urządzeń

Urządzenia z systemem Windows Phone nie zezwalają na obniżenie bezpieczeństwa zasad zabezpieczeń ustawionych wcześniej przy użyciu usługi MDM lub EAS. Na przykład po ustawieniu dla zasady **Minimalna liczba znaków hasła** wartości 8 nastąpiła próba jej zmniejszenia do 4. Do urządzenia są stosowane bardziej restrykcyjne zasady.

Urządzenia z systemem Windows 10 mogą nie usunąć zasad zabezpieczeń podczas cofania przypisania zasad (zatrzymania wdrażania). Może być konieczne pozostawienie przypisanych zasad, a następnie zmiana ustawień zabezpieczeń z powrotem na wartości domyślne.

W zależności od platformy urządzenia jeśli chcesz zmienić zasady na wartość mniej bezpieczną, może być konieczne zresetowanie zasad zabezpieczeń.

Na przykład w systemie Windows 8.1 na pulpicie przesuń palcem z prawej strony, aby otworzyć pasek **Panele funkcji**. Wybierz pozycję **Ustawienia** > **Panel sterowania** > **Konta użytkowników**. Po lewej stronie wybierz link **Resetuj zasady zabezpieczeń** i wybierz pozycję **Resetuj zasady**.

W przypadku innych platform, takich jak Android, iOS/iPadOS czy Windows Phone 8.1, zastosowanie mniej restrykcyjnych zasad może wymagać wycofania i ponownego zarejestrowania urządzenia.

Przydatne informacje można znaleźć w artykule [Rozwiązywanie problemów z rejestrowaniem urządzeń](../enrollment/troubleshoot-device-enrollment-in-intune.md).

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Komputery z oprogramowaniem klienckim usługi Intune — portal klasyczny

> [!NOTE]
> Ta sekcja dotyczy portalu klasycznego. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Błędy związane z zasadami usługi Microsoft Intune w pliku policyplatform.log

W przypadku komputerów z systemem Windows zarządzanych przy użyciu oprogramowania klienckiego usługi Intune błędy zasad w pliku `policyplatform.log` mogą wynikać z innych niż domyślne ustawień w Kontroli konta użytkownika (UAC) systemu Windows na urządzeniu. Niektóre inne niż domyślne ustawienia funkcji Kontroli konta użytkownika mogą wpływać na instalacje klienta usługi Microsoft Intune i wykonywanie zasad.

#### <a name="resolve-uac-issues"></a>Rozwiązywanie problemów z Kontrolą konta użytkownika

1. Wycofaj komputer. Zobacz [Usuwanie urządzeń](../remote-actions/devices-wipe.md).

2. Zaczekaj 20 minut na usunięcie oprogramowania klienckiego.

    > [!NOTE]
    > Nie należy próbować usuwać klienta z poziomu opcji Programy i funkcje.

3. W menu start wpisz wartość **Kontrola konta użytkownika**, aby otworzyć ustawienia Kontroli konta użytkownika.

4. Przesuń suwak powiadomień na ustawienie domyślne.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>BŁĄD: Nie można uzyskać wartości z komputera, 0x80041013

Występuje, jeśli godzina w systemie lokalnym różni się o pięć lub więcej minut. Jeśli godzina na komputerze lokalnym nie jest zsynchronizowana, zabezpieczone transakcje zakończą się niepowodzeniem ze względu na nieprawidłowe sygnatury czasowe.

Aby rozwiązać ten problem, ustaw czas sytemu lokalnego na wartość jak najbliższą czasowi internetowemu. Lub ustaw czas zgodny z czasem w kontrolerach domeny w sieci.

## <a name="next-steps"></a>Następne kroki

[Typowe problemy dotyczące profilów poczty e-mail i sposoby ich rozwiązania](../configuration/troubleshoot-email-profiles-in-microsoft-intune.md)

Uzyskaj [pomoc techniczną od firmy Microsoft](../fundamentals/get-support.md) lub skorzystaj z [forum społeczności](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
