---
title: Konfigurowanie ustawień ochrony tożsamości w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie profilu urządzenia do zestawu ustawień usługi Windows Hello dla firm na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7012479023ece83ef475431c5cefe150ab2ef342
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43317916"
---
# <a name="configure-identity-protection-settings-in-microsoft-intune"></a>Konfigurowanie ustawień ochrony tożsamości w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profile ochrony tożsamości kontrolują, jak usługa Windows Hello dla firm jest aprowizowana i konfigurowana na zarządzanych urządzeniach z systemem Windows 10. Utwórz ten profil, aby skonfigurować:  
* Dostępność usługi Windows Hello dla firm dla urządzeń i użytkowników.
* Wymagania dotyczące numeru PIN urządzenia.
* Użytkownicy gestów mogą i nie mogą ich używać do logowania się na swoich urządzeniach.  

 Możesz przypisać ten profil, aby wybrać grupy użytkowników i urządzeń, lub do wszystkich użytkowników, jak i do wszystkich urządzeń. Grupy otrzymują profil ochrony tożsamości podczas ewidencjonowania w usłudze Intune.    

Skorzystaj z informacji w tym artykule, aby tworzyć profile ochrony tożsamości. Następnie [przypisz swój profil](device-profile-assign.md) do grup użytkowników i urządzeń.

Ta funkcja ma zastosowanie do urządzenia z systemem:  
- System Windows 10 lub nowszy
- Windows Holographic for Business  

## <a name="create-a-device-profile-with-identity-protection-settings"></a>Tworzenie profilu urządzenia przy użyciu ustawień ochrony tożsamości

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Wprowadź **Nazwę** i **Opis** dla profilu ochrony tożsamości.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**. Usługa Windows Hello dla firm jest obsługiwana tylko na urządzeniach z systemem Windows 10 lub nowszym.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Identity Protection**.
7. W okienku usługi Windows Hello dla firm wybierz z poniższych opcji dotyczących konfigurowania usługi Windows Hello dla firm:
    * Wyłączona. Wybierz to ustawienie, jeśli nie chcesz używać usługi Windows Hello dla firm. Wszystkie inne ustawienia na ekranie będą wtedy niedostępne.
    * Włączone. Wybierz to ustawienie, jeśli chcesz skonfigurować ustawienia usługi Windows Hello dla firm.  

8. W przypadku wybrania w poprzednim kroku pozycji **Włączony** należy skonfigurować wymagane ustawienia, które są stosowane do docelowych zarejestrowanych urządzeń z systemami Windows 10 i Windows 10 Mobile oraz użytkowników.

> [!NOTE]
> Podczas przypisywania profilów ochrony tożsamości tylko do użytkowników wartością domyślną kontekstu urządzenia jest **Nieskonfigurowane**.  

   - **Minimalna długość numeru PIN**/**Maksymalna długość numeru PIN**. Konfiguruje urządzenia do używania określonych minimalnych i maksymalnych długości numeru PIN, co pomaga zapewnić bezpieczne logowanie. Domyślna długość numeru PIN to sześć znaków, ale można wymusić stosowanie numerów o długości minimalnej czterech znaków. Maksymalna długość numeru PIN to 127 znaków.  

   - **Małe litery w numerze PIN**/**Wielkie litery w numerze PIN**/**Znaki specjalne w numerze PIN**. Można wymusić stosowanie silniejszych numerów PIN poprzez wymaganie użycia wielkich liter, małych liter i znaków specjalnych w numerze PIN. Wybierz spośród opcji:

     - **Dozwolone**. Użytkownicy mogą używać typu znaków w numerze PIN, ale nie jest to konieczne.

     - **Wymagane**. Użytkownicy muszą zawrzeć co najmniej jeden z typów znaków w numerze PIN. Przykładowo często wymaga się zastosowania co najmniej jednej wielkiej litery i jednego znaku specjalnego.

     - **Niedozwolone** (ustawienie domyślne). Użytkownicy nie mogą używać tego typu znaków w numerach PIN. (To zachowanie ma również miejsce, gdy ustawienie nie zostanie skonfigurowane).<br>Znaki specjalne obejmują: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Wygaśnięcie numeru PIN (dni)**. Dobrze jest ustalić okres ważności dla numeru PIN, po którym użytkownicy końcowi muszą go zmienić. Wartość domyślna to 41 dni.

   - **Pamiętaj historię numerów PIN**. Ogranicza ponowne używanie wcześniej stosowanych numerów PIN. Domyślnie nie jest dozwolone ponowne użycie żadnego z 5 ostatnich numerów PIN.  
   - **Włącz odzyskiwanie numeru PIN**: umożliwia użytkownikowi zmianę numeru PIN przy użyciu usługi odzyskiwania numeru PIN usługi Windows Hello dla firm. 
       - **Włącz**. Usługa w chmurze szyfruje wpis tajny odzyskiwania numeru PIN w celu przechowania na urządzeniu. Użytkownik może w razie potrzeby zmienić numer PIN.  
       - **Nieskonfigurowane** (wartość domyślna). Wpis tajny odzyskiwania numeru PIN nie jest tworzony ani przechowywany. Jeśli zapomnisz numer PIN użytkownika, jedynym sposobem uzyskania nowego numeru PIN jest usunięcie istniejącego numeru PIN i utworzenie nowego. Użytkownik musi ponownie zarejestrować się w jakichkolwiek usługach, do których stary numer PIN zapewniał dostęp.  
   
   - **Używaj modułu TPM (Trusted Platform Module)**. Moduł TPM zapewnia dodatkową warstwę zabezpieczeń danych. Wybierz jedną z następujących opcji:  
     - **Włącz**. Tylko urządzenia z dostępnym modułem TPM mogą aprowizować usługę Windows Hello dla firm.
     - **Nieskonfigurowane**. Wszystkie urządzenia mogą aprowizować usługę Windows Hello dla firm nawet wtedy, gdy nie ma modułu TPM, którego można używać. Urządzenia najpierw spróbują użyć modułu TPM, ale jeśli jest on niedostępny, urządzenia mogą używać szyfrowania programowego.  

   - **Zezwalaj na uwierzytelnianie biometryczne**. Umożliwia użycie uwierzytelniania biometrycznego, takiego jak rozpoznawanie twarzy lub linii papilarnych, zamiast numeru PIN na potrzeby usługi Windows Hello dla firm. Użytkownicy nadal muszą skonfigurować służbowy numer PIN na wypadek niepowodzenia uwierzytelniania biometrycznego. Wybierz spośród opcji:

     - **Włącz**. Usługa Windows Hello dla firm pozwala na użycie uwierzytelniania biometrycznego.
     - **Nieskonfigurowane** (wartość domyślna). Usługa Windows Hello dla firm nie pozwala na użycie uwierzytelniania biometrycznego (dotyczy wszystkich typów kont).

   - **Użyj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**. Określa, czy funkcje ochrony przed fałszowaniem usługi Windows Hello są używane na obsługujących je urządzeniach (np. wykrywanie fotografii twarzy zamiast prawdziwej twarzy).
       - **Włącz**. System Windows wymaga od wszystkich użytkowników używania ochrony przed fałszowaniem na potrzeby rozpoznawania twarzy, jeśli jest obsługiwane.  
       - **Nieskonfigurowane** (wartość domyślna). System Windows uwzględnia konfiguracje ochrony przed fałszowaniem na urządzeniu.

   - **Certyfikat dla zasobów lokalnych**. 
       - **Włącz**. Umożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych.
       - **Nieskonfigurowane** (wartość domyślna). Uniemożliwia usłudze Windows Hello dla firm używanie certyfikatów do uwierzytelniania w zasobach lokalnych.  
9. Kliknij przycisk **OK**, aby zapisać swój profil.  

Profil zostanie utworzony i wyświetlony na liście **Konfiguracja urządzenia — profile**. Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles (Sposoby przypisywania profilów urządzeń)](device-profile-assign.md).  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
