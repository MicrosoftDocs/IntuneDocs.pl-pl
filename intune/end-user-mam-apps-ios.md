---
title: Aplikacje dla systemu iOS z zasadami ochrony aplikacji
description: "W tym temacie opisano, czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e66042e5198b76ec484fe0218127acb653394cce
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2017
---
# Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji
<a id="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

 W tym temacie opisano środowisko użytkownika aplikacji objętych zasadami ochrony aplikacji. Zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane do celów służbowych, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

##  Dostęp do aplikacji
<a id="access-apps" class="xliff"></a>

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik zostanie poproszony o ponowne uruchomienie aplikacji przy jej pierwszym użyciu. Aby do aplikacji można było zastosować zasady ochrony aplikacji, należy ponownie uruchomić urządzenie.

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Na urządzeniach, które są **zarejestrowane do celów zarządzania w usłudze Intune**, użytkownik zobaczy komunikat, że jego aplikacja jest teraz zarządzana.

##  Korzystanie z aplikacji z obsługą wielu tożsamości
<a id="use-apps-with-multi-identity-support" class="xliff"></a>

Aplikacje, które obsługują wiele tożsamości, umożliwiają uzyskiwanie dostępu do tych samych aplikacji przy użyciu różnych kont (służbowych i osobistych), podczas gdy zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane w kontekście służbowym.  

Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie numeru PIN. W przypadku **aplikacji Outlook** użytkownik musi podać numer PIN podczas uruchamiania aplikacji. Korzystając z **aplikacji OneDrive**, użytkownik jest monitowany o numer PIN przy podawaniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint** i **Excel** numer PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

- Dowiedz się więcej o aplikacjach, które obsługują [zarządzanie aplikacjami mobilnymi (MAM) i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

Zasady ochrony aplikacji są stosowane tylko w kontekście służbowym. W związku z tym aplikacja może zachowywać się inaczej w zależności od tego, czy jest używana w kontekście służbowym czy osobistym.

##  Zarządzanie kontami użytkowników na urządzeniu
<a id="manage-user-accounts-on-the-device" class="xliff"></a>

Usługa Intune obsługuje wdrażanie zasad ochrony aplikacji tylko na jednym koncie użytkownika na każdym urządzeniu.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady ochrony aplikacji.
  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady ochrony aplikacji nie są stosowane do tego konta.  

  * W przypadku aplikacji **OneDrive** i **Outlook** można używać tylko jednego konta służbowego. Nie możesz dodawać wielu kont służbowych dla tych aplikacji. Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.

* Jeśli na urządzeniu istnieje wiele kont użytkowników przed wdrożeniem zasad ochrony aplikacji, pierwsze konto, na którym wdrożono zasady ochrony aplikacji, jest zarządzane przez zasady ochrony aplikacji usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady obsługi wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Zasady ochrony aplikacji zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane zgodnie z zasadami ochrony aplikacji, musisz usunąć konto użytkownika skojarzone z Firmą X.

### Dodawanie drugiego konta
<a id="add-a-second-account" class="xliff"></a>

Jeśli korzystasz z urządzenia z systemem iOS, podczas próby dodania drugiego konta służbowego na tym urządzeniu może zostać wyświetlony komunikat o blokadzie. Konta zostaną wyświetlone, umożliwiając wybranie konta do usunięcia.

## Następne kroki
<a id="next-steps" class="xliff"></a>
[Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](end-user-mam-apps-android.md)
