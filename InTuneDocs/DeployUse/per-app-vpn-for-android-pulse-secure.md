---
title: "Sieć VPN dla aplikacji systemu Android korzystających z typu połączenia Pulse Secure | Microsoft Intune"
description: "Dla urządzeń z systemem Android zarządzanych przez usługę Intune można utworzyć profil sieci VPN dla aplikacji."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a2464a9d2276319f75a3da7db70c2613152bed9b
ms.openlocfilehash: 177ed5f693b8f1ce16d96e1b3e729630d661475f


---

# Używanie zasad niestandardowych do tworzenia profilu sieci VPN dla aplikacji na urządzeniach z systemem Android

W przypadku urządzeń z systemem Android zarządzanych przez usługę Intune można utworzyć profil sieci VPN dla aplikacji. Najpierw utwórz profil sieci VPN, który używa typu połączenia Pulse Secure. Następnie utwórz niestandardowe zasady konfiguracji, które kojarzą profil sieci VPN z określonymi aplikacjami. Po wdrożeniu zasad na urządzeniu z systemem Android lub w grupach użytkowników otwarcie przez użytkownika jednej z określonych aplikacji na jednym z tych urządzeń będzie powodować otwarcie połączenia sieci VPN dla danej aplikacji.

> [!NOTE]
>
> Dla tego profilu obsługiwany jest tylko typ połączenia Pulse Secure.


### Krok 1. Tworzenie profilu sieci VPN

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** > **Dodaj zasady**.
2. Aby wybrać szablon dla nowych zasad, rozwiń węzeł **Android** i wybierz pozycję **Profil sieci VPN (Android 4 i nowsze)**.
3. W szablonie wybierz dla pozycji **Typ połączenia** opcję **Pulse Secure**.
4. Zakończ tworzenie profilu sieci VPN i zapisz go. Aby uzyskać więcej informacji na temat profilów sieci VPN, zobacz [Połączenia VPN](../deploy-use/vpn-connections-in-microsoft-intune.md).

> [!NOTE]
>
> Zanotuj nazwę profilu sieci VPN w celu użycia jej w następnym kroku. Przykład: mój_profil_VPN_aplikacji.

### Krok 2. Tworzenie niestandardowych zasad konfiguracji

   1. W konsoli administracyjnej usługi Intune wybierz pozycję **Zasady** > **Dodaj zasady** > **Android** > **Konfiguracja niestandardowa** > **Utwórz zasady**.
   2. Podaj nazwę zasad.
   3. W obszarze **Ustawienia OMA-URI** wybierz pozycję **Dodaj**.
   4. Podaj nazwę ustawienia.
   5. Dla pozycji **Typ danych** określ wartość **Ciąg**.
   6. Dla pozycji **OMA-URI** określ następujący ciąg: **./Vendor/MSFT/VPN/Profile/*Nazwa*/PackageList**, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/mój_profil_VPN_aplikacji/PackageList**.
   7.   W polu **Wartość** utwórz listę pakietów rozdzielonych średnikami do skojarzenia z profilem. Jeśli na przykład chcesz, aby program Excel i przeglądarka Google Chrome używały połączenia sieci VPN, podaj ciąg: **com.microsoft.office.excel;com.android.chrome**.


    ![Przykład niestandardowych zasad sieci VPN dla aplikacji systemu Android](..\media\android_per_app_vpn_oma_uri.png)

#### Ustawianie listy aplikacji jako listy zabronionych lub listy dozwolonych (opcjonalne)
  Korzystając z wartości **BLACKLIST**, możesz określić listę aplikacji, które *nie* będą mogły korzystać z połączenia sieci VPN. Wszystkie pozostałe aplikacje będą nawiązywać połączenia za pośrednictwem sieci VPN.
Alternatywnie możesz użyć wartości **WHITELIST**, aby określić listę aplikacji, które *mogą* korzystać z połączenia sieci VPN. Aplikacje, które nie znajdują się na liście, nie będą nawiązywały połączeń za pośrednictwem sieci VPN.
  1.    W obszarze **Ustawienia OMA-URI** wybierz pozycję **Dodaj**.
  2.    Podaj nazwę ustawienia.
  3.    Dla pozycji **Typ danych** określ wartość **Ciąg**.
  4.    Dla pozycji **OMA-URI** użyj ciągu **./Vendor/MSFT/VPN/Profile/*Nazwa*/Mode**, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/mój_profil_VPN_aplikacji/Mode**.
  5.    W polu **Wartość** podaj wartość **BLACKLIST** lub **WHITELIST**.



### Krok 3. Wdrażanie obu zasad

Należy wdrożyć *obie* zasady w *tych samych* grupach usługi Intune.

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.
2.  W oknie dialogowym **Zarządzanie wdrażaniem** :
    -   **Aby wdrożyć zasady**, wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycję **Dodaj** > **OK**.
    -   **Aby zamknąć okno dialogowe bez wdrażania zasad**, wybierz pozycję **Anuluj**.

W podsumowaniu stanu i alertach na stronie **Przegląd** obszaru roboczego **Zasady** są pokazane problemy z zasadami, które wymagają Twojej uwagi. Podsumowanie stanu jest wyświetlane także w obszarze roboczym **Pulpit nawigacyjny**.



<!--HONumber=Aug16_HO3-->


