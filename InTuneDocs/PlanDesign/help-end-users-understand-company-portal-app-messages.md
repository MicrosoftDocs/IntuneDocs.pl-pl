---
# required metadata

title: Pomaganie użytkownikom końcowym w zrozumieniu komunikatów aplikacji Portal firmy | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Pomaganie użytkownikom końcowym w zrozumieniu komunikatów aplikacji Portal firmy

Poniższe informacje dotyczą tylko urządzeń z systemem Android w wersji 6.0 lub nowszym. Podczas rejestracji urządzenia użytkownicy końcowi otrzymują dwa komunikaty w trakcie procesu rejestracji:

- Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?
- Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?

Zobacz szczegółowe informacje poniżej, aby dowiedzieć się więcej o tych komunikatach i uzyskać informacje, którymi możesz podzielić się ze swoimi użytkownikami końcowymi.

## Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?

### Tekst komunikatu i miejsce, w którym występuje
Tekst komunikatu to **Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?**. Komunikat jest wyświetlany, gdy użytkownicy logują się do aplikacji Portal firmy po raz pierwszy, aby rozpocząć proces rejestracji urządzenia.

### Znaczenie komunikatu
Komunikat jest monitem kierowanym do użytkowników, który umożliwia wysłanie numeru telefonu i kodu IMEI urządzenia użytkownika do usługi Intune, gdzie będą one wyświetlane w konsoli administracyjnej na stronie Sprzęt.

> [!NOTE]
> **Aplikacja Portal firmy nigdy nie wykonuje połączeń telefonicznych ani nie zarządza nimi.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.

Aby wyświetlić stronę **Sprzęt**, wybierz pozycję **Grupy** > **Wszystkie urządzenia przenośne** > **Urządzenia**. Wybierz urządzenie użytkownika, a następnie wybierz pozycję **Wyświetl właściwości** > **Sprzęt**.

### Co się stanie, gdy użytkownik zezwoli lub nie zezwoli na dostęp
Jeśli użytkownik zezwoli na dostęp, numer telefonu i kod IMEI urządzenia będą wyświetlane na stronie Sprzęt w konsoli administracyjnej.

Jeśli użytkownik nie zezwoli na dostęp, może nadal używać aplikacji Portal firmy i zarejestrować urządzenie, lecz pola numeru telefonu i kodu IMEI urządzenia użytkownika na stronie Sprzęt konsoli administracyjnej będą puste. Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie.

Jeśli użytkownik zezwoli na dostęp, lecz potem anuluje zezwolenie, komunikat zostanie wyświetlony podczas następnego logowania użytkownika do aplikacji Portal firmy po rejestracji.</br></br>Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Telefon** i włączyć uprawnienie.

### Gdzie użytkownicy mogą znaleźć więcej informacji
[Logowanie się w aplikacji Portal firmy](/Intune/EndUser/sign-in-to-the-company-portal-app-android)

## Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?

### Tekst komunikatu i miejsce, w którym występuje
Tekst komunikatu to **Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?**. Komunikat jest wyświetlany, gdy użytkownik naciśnie opcję **Wyślij dane**, aby wysłać dzienniki danych do administratora IT.

### Znaczenie komunikatu
Komunikat jest monitem kierowanym do użytkowników, który umożliwia ich urządzeniom zapisywanie dzienników danych na kartach SD oraz umożliwia przenoszenie tych dzienników za pośrednictwem kabla USB.   

> [!NOTE]
> **Aplikacja Portal firmy nigdy nie uzyskuje dostępu do zdjęć, multimediów ani plików użytkownika.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.

### Co się stanie, gdy użytkownik zezwoli lub nie zezwoli na dostęp
Jeśli użytkownik zezwoli na dostęp, dzienniki będą kopiowane na kartę SD.

Jeśli użytkownik nie zezwoli na dostęp, nadal może wysyłać dzienniki danych, ale dzienniki nie będą kopiowane na kartę SD urządzenia.

Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie. Jeśli użytkownik zezwoli na dostęp, lecz potem anuluje zezwolenie, komunikat zostanie wyświetlony podczas następnej próby wysłania dzienników przez użytkownika. Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Pamięć** i włączyć uprawnienie.

### Gdzie użytkownicy mogą znaleźć więcej informacji
[Wysyłanie dzienników danych diagnostycznych do administratora IT pocztą e-mail](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Zobacz także
[Co mówić użytkownikom końcowym na temat korzystania z usługi Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune.md)


<!--HONumber=May16_HO1-->


