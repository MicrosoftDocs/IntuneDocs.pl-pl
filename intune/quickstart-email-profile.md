---
title: Przewodnik Szybki start — tworzenie profilu urządzenia poczty e-mail dla systemu iOS
titlesuffix: Microsoft Intune
description: Dowiedz się, jak za pomocą usługi Microsoft Intune utworzyć profil urządzenia poczty e-mail, aby umożliwić bezpieczne łączenie się urządzeń z systemem iOS z firmową pocztą e-mail.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a0c554315168147249e0842b69e3e6195ed85979
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581829"
---
# <a name="quickstart-create-an-email-device-profile-for-ios"></a>Przewodnik Szybki start: tworzenie profilu urządzenia poczty e-mail dla systemu iOS

Z tego przewodnika Szybki start dowiesz się, jak utworzyć profil urządzenia poczty e-mail dla urządzeń z systemem iOS. Ten profil określa ustawienia, które są wymagane, aby wbudowana aplikacja poczty e-mail na urządzeniu z systemem iOS mogła łączyć się z firmową pocztą e-mail. Profile urządzeń poczty e-mail ułatwiają standaryzacje ustawień na różnych urządzeniach i umożliwiają użytkownikom końcowym dostęp do firmowej poczty e-mail na ich osobistych urządzeniach bez konieczności przeprowadzania konfiguracji po ich stronie. Aby dodatkowo zabezpieczyć pocztę e-mail, można za pomocą profilu poczty e-mail ustalać, czy urządzenia są zgodne, i skonfigurować dostęp warunkowy w celu zezwalania na dostęp do poczty e-mail tylko zgodnym urządzeniom. Aby uzyskać szczegółowe informacje na temat profilów poczty e-mail, zobacz [How to configure email settings in Microsoft Intune](email-settings-configure.md) (Jak skonfigurować ustawienia poczty e-mail w usłudze Microsoft Intune).

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się w usłudze [Intune](https://aka.ms/intuneportal) jako administrator globalny lub administrator usługi Intune. Dostęp do usługi Intune można uzyskać w witrynie Azure Portal, wybierając pozycję **Wszystkie usługi** > **Intune**.

## <a name="create-an-ios-email-profile"></a>Tworzenie profilu poczty e-mail dla systemu iOS
1. W obszarze Intune wybierz pozycję **Konfiguracja urządzeń**, a następnie **Profile**.
2. Wybierz pozycję **Utwórz profil**.
   
   ![Tworzenie profilu poczty e-mail dla systemu iOS](media/quickstart-email-profile/ios-create-profile.png)

3. W obszarze **Nazwa** wprowadź nazwę opisową nowego profilu. W tym przykładzie wprowadź opis **iOS require work email** (iOS — wymagaj służbowego adresu e-mail).
4. Wprowadź następujące informacje o profilu:
   - W polu **Opis** wprowadź **Require iOS devices to use work email** (Wymagaj od urządzeń z systemem iOS używania służbowego adresu e-mail).
   - W polu **Platforma** wybierz opcję **iOS**.
   - W polu **Typ profilu** wybierz opcję **E-mail**.
    
     ![Tworzenie profilu poczty e-mail dla systemu iOS](media/quickstart-email-profile/ios-email-profile-name.png)

5. Wybierz pozycję **Ustawienia**, a następnie wprowadź następujące ustawienia (w przypadku pozostałych ustawień pozostaw wartości domyślne):
   - **Serwer poczty e-mail**: na potrzeby tego przewodnika Szybki start wprowadź **outlook.office365.com**. To ustawienie określa lokalizację programu Exchange (adres URL) serwera poczty e-mail, za pomocą którego aplikacja poczty systemu iOS będzie łączyć się z kontem e-mail.
   - **Nazwa konta**: wprowadź wartość **Company Email** (Firmowa poczta e-mail).
   - **Atrybut nazwy użytkownika z usługi AAD**: ta nazwa to atrybut pobierany przez usługę Intune z usługi Azure Active Directory (Azure AD). Usługa Intune dynamicznie generuje nazwę użytkownika dla tego profilu przy użyciu tej nazwy. W tym przewodniku Szybki start przyjmiemy, że chcemy, aby jako nazwa użytkownika profilu używana była **główna nazwa użytkownika** (na przykład user1@contoso.com).
   - **Atrybut adresu e-mail z usługi AAD**: to ustawienie jest adresem e-mail z usługi Azure AD, który będzie używany do logowania się w programie Exchange. Na potrzeby tego przewodnika Szybki start wybierz opcję **Główna nazwa użytkownika**.
   - **Metoda uwierzytelniania**: na potrzeby tego przewodnika Szybki start wybierz pozycję **Nazwa użytkownika i hasło**. (Można również wybrać pozycję **Certyfikat**, jeśli skonfigurowano już certyfikat dla usługi Intune).
    
     ![Tworzenie profilu poczty e-mail dla systemu iOS](media/quickstart-email-profile/ios-email-profile.png)

6. Wybierz przycisk **OK**.
7. Wybierz przycisk **Utwórz**. Nowy profil pojawi się na liście profilów z wyświetlonym pulpitem nawigacyjnym, aby można było monitorować sposób przypisania go do urządzeń z systemem iOS i użytkowników systemu iOS.
8. Wybierz pozycję **Przypisania**.
9. Wybierz kartę **Dołącz**, a następnie wybierz pozycję **Wszyscy użytkownicy i wszystkie urządzenia**. 
10. Wybierz pozycję **Zapisz**.

## <a name="clean-up-resources"></a>Oczyszczanie zasobów
Jeśli nie zamierzasz używać utworzonego profilu w dodatkowych samouczkach ani podczas testowania, możesz go teraz usunąć.
1. W obszarze Intune wybierz pozycję **Konfiguracja urządzeń**, a następnie **Profile**.
2. Wybierz utworzony profil testowy **iOS require work email** (iOS — wymagaj służbowego adresu e-mail).
3. Wybierz wielokropek (**...**) obok profilu, a następnie wybierz pozycję **Usuń**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start utworzono profil poczty e-mail dla urządzeń z systemem iOS. Teraz za pomocą tego profilu można ustalić, czy urządzenie z systemem iOS jest zgodne, tworząc zasady zgodności oznaczające jako niezgodne wszystkie urządzenia z systemem iOS, które nie pasują do profilu. W celu zapewnienia dodatkowej ochrony można utworzyć zasady dostępu warunkowego blokujące niezgodnym urządzeniom z systemem iOS dostęp do poczty e-mail.

> [!div class="nextstepaction"]
> [Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md)
