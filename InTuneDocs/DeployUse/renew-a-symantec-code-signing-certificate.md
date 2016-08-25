---
# required metadata

title: Odnawianie certyfikatu podpisywania kodu przedsiębiorstwa firmy Symantec w celu użycia z usługą Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Odnawianie certyfikatu podpisywania kodu przedsiębiorstwa firmy Symantec dla urządzeń z systemem Windows

Okresowo należy odnawiać certyfikat firmy Symantec służący do zarządzania określonymi urządzeniami przenośnymi z systemem Windows i Windows Phone. W przypadku urządzeń z systemem Windows Phone 8.0 do rejestracji urządzenia wymagana jest podpisana aplikacja Portal firmy i certyfikat podpisywania kodu. Urządzenia z nowszymi wersjami systemu Windows Phone mogą korzystać z aplikacji Portal firmy pobranej ze Sklepu. Certyfikat podpisywania kodu jest również wymagany podczas wdrażania aplikacji biznesowych.

## Jak odnowić certyfikat podpisywania kodu przedsiębiorstwa firmy Symantec

1.  Poszukaj wiadomości e-mail dotyczącej odnowienia certyfikatu, która została wysłana przez firmę Symantec około 14 dni przed jego wygaśnięciem. Zawiera ona instrukcje od firmy Symantec w zakresie odnowienia certyfikatu przedsiębiorstwa.

    Aby uzyskać dodatkowe informacje o certyfikatach firmy Symantec, odwiedź witrynę [www.symantec.com](http://www.symantec.com) lub zadzwoń pod numer 1-877-438-8776 lub 1-650-426-3400.

2.  Przejdź do witryny internetowej (na przykład: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) i zaloguj się za pomocą identyfikatora wydawcy firmy Symantec oraz adresu e-mail skojarzonego z certyfikatem. Pamiętaj o tym, aby rozpocząć procedurę odnowienia na tym samym komputerze, na którym będzie pobierany certyfikat.

3.  Po zatwierdzeniu odnowienia i uregulowaniu płatności pobierz certyfikat.

## Jak zainstalować zaktualizowany certyfikat dla systemu Windows Phone 8.0

1.  Z następującej lokalizacji pobierz najnowszą wersję aplikacji Portal firmy dla systemu Windows Phone, a następnie podpisz ją: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060)..

2.  Otwórz konsolę administracyjną usługi Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)), przejdź do pozycji **Administracja**, **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**, a następnie kliknij pozycję **Przekaż podpisaną aplikację**.

3.  Przekaż nowo podpisaną aplikację Portal firmy. Konieczny jest nowo podpisany plik SSP.xap oraz nowy plik .PFX otrzymany od firmy Symantec lub token rejestracji aplikacji utworzony za pomocą tego nowego pliku .PFX.

4.  Po zakończeniu przekazywania usuń starą wersję Portalu firmy w obszarze roboczym **Oprogramowanie** w programie Intune Management Console.

5.  Podpisz ponownie wszystkie aplikacje biznesowe przedsiębiorstwa za pomocą tego samego certyfikatu, a następnie przekaż i zastąp istniejące aplikacje.

Dostarczanie podpisanego pliku SSP.xap jest obecnie jedynym sposobem zapewnienia certyfikatu podpisywania zaktualizowanego kodu. Aby obsługiwać podpisane aplikacje biznesowe, musisz podpisać i przekazać aplikację Portal firmy, nawet jeśli użytkownicy zainstalują aplikację Portal firmy ze Sklepu.

## Jak zainstalować zaktualizowany certyfikat dla urządzeń z systemem Windows Phone 8.1 i nowszych

1.  Pobierz najnowszą wersję aplikacji Portal firmy dla systemu Windows Phone z Centrum pobierania w następującej lokalizacji: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060), a następnie podpisz ją..

2.  Otwórz [konsolę administracyjną usługi Intune](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com), przejdź do pozycji **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Windows Phone**, a następnie kliknij pozycję **Przekaż podpisaną aplikację**.

3.  Przekaż nowo podpisaną aplikację Portal firmy. Konieczny jest nowo podpisany plik SSP.xap oraz nowy plik .PFX otrzymany od firmy Symantec lub token rejestracji aplikacji utworzony za pomocą tego nowego pliku .PFX.

4.  Po zakończeniu przekazywania usuń starą wersję aplikacji Portal firmy w obszarze roboczym **Oprogramowanie**  .

5.  Podpisz wszystkie nowe i zaktualizowane aplikacje biznesowe przedsiębiorstwa przy użyciu nowego certyfikatu. Istniejące aplikacje nie muszą być ponownie podpisane i wdrożone.


### Zobacz także
[Konfigurowanie zarządzania systemem Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Konfigurowanie zarządzania systemem Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


