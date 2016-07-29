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
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: d6d929b83b967cc4efdc84ecc3262c5c1f509351


---

# Używanie zasad niestandardowych do tworzenia profilu sieci VPN dla aplikacji na urządzeniach z systemem Android

Dla urządzeń z systemem Android zarządzanych przez usługę Intune można utworzyć profil sieci VPN dla aplikacji. Najpierw zostanie utworzony profil sieci VPN korzystający z typu połączenia Pulse Secure, a następnie niestandardowe zasady konfiguracji kojarzące ten profil z określonymi aplikacjami. Po wdrożeniu tych zasad na urządzeniu z systemem Android lub w grupach użytkowników otwarcie jednej z określonych aplikacji na tych urządzeniach będzie powodować otwarcie połączenia sieci VPN dla danej aplikacji.

### Krok 1. Tworzenie profilu sieci VPN

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Zasady** > **Dodaj zasady**.
2. Wybierz szablon dla nowych zasad, rozwijając węzeł **Android** i wybierając pozycję **Profil sieci VPN (Android 4 i nowsze)**.

3. W szablonie wybierz dla pozycji **Typ połączenia** opcję **Pulse Secure**.
4. Ukończ tworzenie profilu sieci VPN i zapisz go. Aby uzyskać więcej informacji na temat profilów sieci VPN, zobacz [Połączenia VPN](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
Zanotuj nazwę profilu sieci VPN w celu użycia jej w następnym kroku. Przykład: **mój_profil_VPN_aplikacji**.

### Krok 2. Tworzenie niestandardowych zasad konfiguracji

   1. W konsoli administracyjnej usługi Intune wybierz pozycję **Zasady** -> **Dodaj zasady** -> **Android** -> **Konfiguracja niestandardowa** -> **Utwórz zasady**.
   2. Podaj nazwę zasad.
   3. W obszarze **Ustawienia OMA-URI** kliknij pozycję **Dodaj**.
   4. Podaj nazwę ustawienia.
   5. Dla pozycji **Typ danych** określ wartość **Ciąg**.
   6. Dla pozycji **OMA-URI** określ następujący ciąg: **./Vendor/MSFT/VPN/Profile/*Nazwa*/PackageList**, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/mój_profil_VPN_aplikacji/PackageList**.
   7.   W polu **Wartość** podaj rozdzieloną średnikami listę pakietów, które powinny być skojarzone z profilem.  Jeśli na przykład chcesz, aby program Excel i przeglądarka Google Chrome używały połączenia sieci VPN, wprowadź ciąg: **com.microsoft.office.excel;com.android.chrome**.


   ![Przykład niestandardowych zasad sieci VPN dla aplikacji systemu Android](..\media\android_per_app_vpn_oma_uri.png)
#### Ustawianie listy aplikacji jako listy zabronionych lub listy dozwolonych (opcjonalne)
Korzystając z wartości **BLACKLIST**, można określić, że aplikacje uwzględnione na liście *nie* będą mogły korzystać z połączenia sieci VPN.  Wszystkie pozostałe aplikacje będą łączyć się za pośrednictwem sieci VPN.

Można także użyć wartości **WHITELIST** w celu określenia, że *tylko* określone aplikacje będą mogły korzystać z połączenia sieci VPN.


1.  W obszarze ustawień OMA-URI kliknij pozycję **Dodaj**.
2.  Podaj nazwę ustawienia.
3.  Dla pozycji **Typ danych** określ wartość **Ciąg**.
4.  Dla pozycji **OMA-URI** określ następujący ciąg: **./Vendor/MSFT/VPN/Profile/*Nazwa*/Mode**, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/mój_profil_VPN_aplikacji/Mode**.
5.  W polu **Wartość** wprowadź wartość **BLACKLIST** lub **WHITELIST**.



### Krok 3. Wdrażanie obu zasad

Należy wdrożyć *obie* zasady w *tych samych* grupach usługi Intune.

   1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie kliknij pozycję **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — kliknij przycisk **Anuluj**.

W podsumowaniu stanu i alertach na stronie **Przegląd** obszaru roboczego **Zasady** są pokazane problemy z zasadami, które wymagają Twojej uwagi. Ponadto w obszarze roboczym Pulpit nawigacyjny jest wyświetlane podsumowanie stanu.



<!--HONumber=Jul16_HO4-->


