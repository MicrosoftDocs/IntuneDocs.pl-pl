---
# required metadata

title: Brak wymaganego certyfikatu urządzenia | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Brak wymaganego certyfikatu urządzenia
Jeśli urządzenie z systemem Android nie jest zarejestrowane w usłudze Intune i nie ma certyfikatu, który zazwyczaj jest zainstalowany w telefonie, nie można zalogować się do aplikacji Portal firmy w systemie Android. Przy próbie zalogowania się zostanie wyświetlony następujący komunikat:

![Instalowanie certyfikatu w systemie Android — brak certyfikatu](./media/andr-cert_install-1-cert_missing.png)

Aby rozwiązać ten problem i uzyskać wymagany certyfikat:

1.  W przeglądarce przejdź do tej [strony certyfikatów firmy Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Znajdź i pobierz certyfikat główny firmy CyberTrust Baltimore (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Przeciągnij z góry na dół, aby otworzyć powiadomienia, a następnie naciśnij pozycję **BaltimoreCyberTrustRoot.crt** na liście powiadomień.

4.  W oknie dialogowym **Name the Certificate** (Nazwij certyfikat) zaakceptuj domyślną nazwę certyfikatu.

5. Upewnij się, że ustawienie **Credential Use** (Użycie poświadczeń) ma wartość **Used for VPN and apps** (Używane dla sieci VPN i aplikacji), a następnie naciśnij przycisk **OK**.

    ![Instalowanie certyfikatu w systemie Android — dodawanie nazwy certyfikatu](./media/andr-cert_install-2-add_cert_name.png)

6. Zamknij przeglądarkę sieci Web i aplikację Portal firmy.

7. Otwórz ponownie aplikację Portal firmy. Zalogowanie się do aplikacji Portal firmy powinno być teraz możliwe. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).

<!--HONumber=Jun16_HO2-->


