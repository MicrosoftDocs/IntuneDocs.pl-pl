---
title: "Brak wymaganego certyfikatu urządzenia | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 56564589417d074b151383a95eea04a4ba7a22ad


---


# <a name="your-device-is-missing-a-required-certificate"></a>Brak wymaganego certyfikatu urządzenia


## <a name="your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Urządzenie nie ma certyfikatu, który zazwyczaj jest zainstalowany na telefonie
Jeśli urządzenie z systemem Android nie jest zarejestrowane w usłudze Intune i nie ma certyfikatu, który zazwyczaj jest zainstalowany w telefonie, nie można zalogować się do aplikacji Portal firmy w systemie Android. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Aby rozwiązać ten problem i uzyskać wymagany certyfikat:

1.  W przeglądarce przejdź do tej [strony certyfikatów firmy Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Znajdź i pobierz certyfikat główny firmy CyberTrust Baltimore (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Przeciągnij z góry na dół, aby otworzyć powiadomienia, a następnie naciśnij pozycję **BaltimoreCyberTrustRoot.crt** na liście powiadomień.

4.  W oknie dialogowym **Name the Certificate** (Nazywanie certyfikatu) zaakceptuj domyślną nazwę certyfikatu.

5. Upewnij się, że ustawienie **Credential Use** (Użycie poświadczeń) ma wartość **Used for VPN and apps** (Używane dla sieci VPN i aplikacji), a następnie naciśnij przycisk **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Zamknij przeglądarkę sieci Web i aplikację Portal firmy.

7. Otwórz ponownie aplikację Portal firmy. Zalogowanie się do aplikacji Portal firmy powinno być teraz możliwe. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT.

## <a name="your-device-is-missing-a-certificate-required-by-your-it-admin"></a>Urządzenie nie ma certyfikatu wymaganego przez administratora IT
Jeśli urządzenie z systemem Android nie zostało zarejestrowane w usłudze Intune i nie ma certyfikatu wymaganego przez administratora IT, nie można zalogować się do aplikacji Portal firmy w systemie Android. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Jeśli komunikat „Brak certyfikatu” został już wyświetlony i wykonano kroki opisane w temacie [Urządzenie nie ma certyfikatu, który zazwyczaj jest zainstalowany na telefonie](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone), należy to zignorować. Jest to inny komunikat i inny certyfikat, więc wykonaj kroki opisane w tej sekcji, aby pobrać brakujący certyfikat.

Aby rozwiązać ten problem i uzyskać wymagany certyfikat, wykonaj dwa podstawowe kroki:

- Zidentyfikowanie brakującego certyfikatu przez sprawdzenie komputera służbowego.
- Pobranie brakującego certyfikatu z Internetu przy użyciu urządzenia.

### <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a>Identyfikowanie brakującego certyfikatu przez sprawdzenie komputera służbowego

1. Na komputerze otwórz przeglądarkę Internet Explorer. Jeśli nie masz komputera do użycia w tym celu, skontaktuj się z administratorem IT. Aby znaleźć informacje kontaktowe administratora IT, sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com).

2. Otwórz [witrynę sieci Web aplikacji Portal firmy](http://portal.manage.microsoft.com), a następnie zaloguj się przy użyciu poświadczeń konta służbowego.

3. Po prawej stronie paska adresu w przeglądarce wybierz symbol, który wygląda jak kłódka, jak pokazano na poniższym zrzucie ekranu.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    Jeśli nie widzisz symbolu kłódki, przerwij korzystanie z programu i skontaktuj się z administratorem IT. Kłódka oznacza bezpieczne zalogowanie, więc użytkownik nie powinien kontynuować, jeśli nie widzi tego symbolu.

4. Wybierz pozycję **Wyświetl certyfikaty**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. W oknie dialogowym **Certyfikat** wybierz kartę **Ścieżka certyfikacji**, a następnie zidentyfikuj certyfikat, który należy pobrać z Internetu. Nazwa potrzebnego certyfikatu będzie znajdować się w tym samym miejscu, które zostało wyróżnione na poprzednim zrzucie ekranu.

### <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a>Pobieranie i instalowanie brakującego certyfikatu na urządzenia przenośne z systemem Android

1. Korzystając z wyszukiwarki, takiej jak Bing czy Google, wyszukaj nazwę brakującego certyfikatu, który został zidentyfikowany w poprzedniej sekcji. Certyfikat może mieć różne rozszerzenia, takie jak „crt”, „pem” itp.

2. Pobierz certyfikat główny z witryny sieci Web.

3. Po pobraniu certyfikatu przeciągnij w dół od górnej krawędzi urządzenia, aby otworzyć powiadomienia, a następnie wybierz nazwę certyfikatu na liście powiadomień.

4. W przedstawionym na poniższym zrzucie ekranu oknie dialogowym **Name the Certificate** (Nazywanie certyfikatu) zaakceptuj domyślną nazwę certyfikatu.

5. Upewnij się, że ustawienie **Credential Use** (Użycie poświadczeń) ma wartość **Used for VPN and apps** (Używane dla sieci VPN i aplikacji), a następnie naciśnij przycisk **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Zamknij aplikację Portal firmy.

7. Otwórz ponownie aplikację Portal firmy. Zalogowanie się do aplikacji Portal firmy powinno być teraz możliwe. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT.

Jeśli widzisz tę samą wiadomość „Brak certyfikatu”, jak pokazano wcześniej, i została już wykonana procedura, oznacza to prawdopodobnie, że istnieje inny certyfikat, który trzeba będzie zainstalować, korzystając z pomocy administratora IT. Skontaktuj się z administratorem IT i przekaż mu ten link do [problemów związanych z certyfikatem w systemie Android](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), który zawiera kroki pomocne w rozwiązywaniu problemu.



<!--HONumber=Dec16_HO2-->


