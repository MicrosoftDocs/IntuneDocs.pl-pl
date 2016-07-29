---
title: "Brak wymaganego certyfikatu urządzenia | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: noindex,nofollow
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 618e2abda642c3b9b2e813824dfd4235c9309faa
ms.openlocfilehash: 220d877763352e62c4057494b69633356ef081c6


---


# Brak wymaganego certyfikatu urządzenia


## Urządzenie nie ma certyfikatu, który zazwyczaj jest zainstalowany na telefonie
Jeśli urządzenie z systemem Android nie jest zarejestrowane w usłudze Intune i nie ma certyfikatu, który zazwyczaj jest zainstalowany w telefonie, nie można zalogować się do aplikacji Portal firmy w systemie Android. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Aby rozwiązać ten problem i uzyskać wymagany certyfikat:

1.  W przeglądarce przejdź do tej [strony certyfikatów firmy Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Znajdź i pobierz certyfikat główny firmy CyberTrust Baltimore (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Przeciągnij z góry na dół, aby otworzyć powiadomienia, a następnie naciśnij pozycję **BaltimoreCyberTrustRoot.crt** na liście powiadomień.

4.  W oknie dialogowym **Name the Certificate** (Nazwij certyfikat) zaakceptuj domyślną nazwę certyfikatu.

5. Upewnij się, że ustawienie **Credential Use** (Użycie poświadczeń) ma wartość **Used for VPN and apps** (Używane dla sieci VPN i aplikacji), a następnie naciśnij przycisk **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Zamknij przeglądarkę sieci Web i aplikację Portal firmy.

7. Otwórz ponownie aplikację Portal firmy. Zalogowanie się do aplikacji Portal firmy powinno być teraz możliwe. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT.

## Urządzenie nie ma certyfikatu wymaganego przez administratora IT
Jeśli urządzenie z systemem Android nie zostało zarejestrowane w usłudze Intune i nie ma certyfikatu wymaganego przez administratora IT, nie można zalogować się do aplikacji Portal firmy w systemie Android. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Jeśli komunikat „Brak certyfikatu” został już wyświetlony i wykonano kroki opisane w temacie [Urządzenie nie ma certyfikatu, który zazwyczaj jest zainstalowany na telefonie](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone), należy to zignorować. Jest to inny komunikat i inny certyfikat, więc wykonaj kroki opisane w tej sekcji, aby pobrać brakujący certyfikat.

Aby rozwiązać ten problem i uzyskać wymagany certyfikat, wykonaj dwa podstawowe kroki:

- Zidentyfikowanie brakującego certyfikatu przez sprawdzenie komputera służbowego.
- Pobranie brakującego certyfikatu z Internetu przy użyciu urządzenia.

### Identyfikowanie brakującego certyfikatu przez sprawdzenie komputera służbowego

1. Na komputerze otwórz przeglądarkę Internet Explorer. Jeśli nie masz komputera do użycia w tym celu, skontaktuj się z administratorem IT. Informacje kontaktowe administratora IT są dostępne w [witrynie sieci Web aplikacji Portal firmy](http://portal.manage.microsoft.com).

2. Otwórz [witrynę sieci Web aplikacji Portal firmy](http://portal.manage.microsoft.com), a następnie zaloguj się przy użyciu poświadczeń konta służbowego.

3. Po prawej stronie paska adresu w przeglądarce kliknij symbol, który wygląda jak kłódka, jak pokazano poniżej. Jeśli nie widzisz symbolu kłódki, przerwij korzystanie z programu i skontaktuj się z administratorem IT. Kłódka oznacza bezpieczne zalogowanie, więc użytkownik nie powinien kontynuować, jeśli nie widzi tego symbolu.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

4. Kliknij pozycję **Wyświetl certyfikaty**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. W oknie dialogowym **Certyfikat** kliknij kartę **Ścieżka certyfikacji**, a następnie zidentyfikuj certyfikat, który należy pobrać z Internetu. Nazwa potrzebnego certyfikatu będzie znajdować się w tym samym miejscu, które zostało wyróżnione na zrzucie ekranu powyżej.

### Pobieranie i instalowanie brakującego certyfikatu na urządzenia przenośne z systemem Android

1. Korzystając z wyszukiwarki, takiej jak Bing czy Google, wyszukaj nazwę brakującego certyfikatu, który został zidentyfikowany w poprzedniej sekcji. Certyfikat może mieć różne rozszerzenia, takie jak „crt”, „pem” itp.

2. Pobierz certyfikat główny z witryny sieci Web.

3. Po pobraniu certyfikatu przeciągnij w dół od górnej krawędzi urządzenia, aby otworzyć powiadomienia, a następnie wybierz nazwę certyfikatu na liście powiadomień.

4. W przedstawionym poniżej oknie dialogowym **Name the Certificate** (Nazwij certyfikat) zaakceptuj domyślną nazwę certyfikatu.

5. Upewnij się, że ustawienie **Credential Use** (Użycie poświadczeń) ma wartość **Used for VPN and apps** (Używane dla sieci VPN i aplikacji), a następnie naciśnij przycisk **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Zamknij aplikację Portal firmy.

7. Otwórz ponownie aplikację Portal firmy. Zalogowanie się do aplikacji Portal firmy powinno być teraz możliwe. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT.

Jeśli widzisz tę samą wiadomość „Brak certyfikatu”, jak pokazano powyżej, i zostały już wykonane powyższe kroki, oznacza to prawdopodobnie, że istnieje inny certyfikat, który trzeba będzie zainstalować, korzystając z pomocy administratora IT. Skontaktuj się z administratorem IT i podaj mu ten [link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), który zawiera kroki ułatwiające rozwiązanie problemu.

### Zobacz także
[Korzystanie z urządzenia z systemem Windows i usługi Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO4-->


