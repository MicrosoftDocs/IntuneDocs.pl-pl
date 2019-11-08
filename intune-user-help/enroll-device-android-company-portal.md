---
title: Rejestrowanie urządzenia z systemem Android w aplikacji Portal firmy usługi Intune | Microsoft Docs
description: Opis sposobu rejestrowania urządzenia z systemem Android w aplikacji Portal firmy usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5baf0e9079cc148101a68e5cd2d3a4ed500f567f
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414855"
---
# <a name="enroll-your-device-with-company-portal"></a>Rejestrowanie urządzenia w aplikacji Portal firmy  
Zarejestruj swoje prywatne lub służbowe urządzenie z systemem Android, aby mieć bezpieczny dostęp do firmowej poczty e-mail, aplikacji i danych. Portal firmy obsługuje urządzenia z systemem Android, w tym Samsung Knox z systemem Android 4.4 lub nowszym.  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> Samsung Knox to rodzaj zabezpieczenia dostępnego w niektórych urządzeniach firmy Samsung. Funkcja ta zapewnia dodatkową ochronę poza zabezpieczeniami dostępnymi w natywnym systemie Android. Aby sprawdzić, czy masz urządzenie z rozwiązaniem Samsung Knox, przejdź do pozycji **Ustawienia** > **Informacje o urządzeniu**. Jeśli na tej liście nie widzisz pozycji **Knox version (Wersja systemu Knox)** , oznacza to, że masz urządzenie z natywnym systemem Android.

## <a name="enroll-device"></a>Rejestrowanie urządzenia  
[Zainstaluj bezpłatną aplikację Portal firmy usługi Intune ze sklepu Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). 

Podczas rejestrowania może pojawić się monit o wybranie kategorii, która najlepiej opisuje Twój sposób korzystania z urządzenia. Dział pomocy technicznej Twojej firmy korzysta z udzielonych tu odpowiedzi, aby sprawdzić aplikacje, do których masz dostęp.  

1. Otwórz aplikację Portal firmy i zaloguj się za pomocą konta służbowego.  

2. Jeśli zostanie wyświetlony monit o zaakceptowanie warunków i postanowień obowiązujących w organizacji, naciśnij pozycję **AKCEPTUJ WSZYSTKO**.  

   ![Przykład obrazu Portal firmy, warunków ekranu, wyróżnianie przycisku "zaakceptuj wszystko".](./media/accept-terms-1911.png)  


3. Zapoznaj się z informacjami o tym, co Twoja organizacja może zobaczyć. Następnie naciśnij pozycję **KONTYNUUJ**.


    ![Przykładowy obraz Portal firmy, opieka nad ochroną ekranu, wyróżnianie przycisku Kontynuuj.](./media/android-privacy-screen-1911.png)  
4. Zapoznaj się z oczekiwaniami w nadchodzących krokach. Następnie naciśnij przycisk **dalej**.  

    ![Przykładowy obraz Portal firmy, co jest następnym ekranem, co umożliwia wyróżnienie przycisku Dalej.](./media/android-whats-next-1911.png)  


5. W zależności od używanej wersji systemu Android może zostać wyświetlony monit o zezwolenie na dostęp do niektórych części urządzenia. Te monity są wymagane przez firmę Google i nie są kontrolowane przez Microsoft.  

    Naciśnij pozycję **Zezwalaj** na następujące uprawnienia:  
    * **Zezwalaj Portal firmy na wykonywanie połączeń telefonicznych i zarządzanie nimi**: to uprawnienie umożliwia urządzeniu udostępnianie międzynarodowego numeru telefonu stacji komórkowych (IMEI) w usłudze Intune, dostawcy zarządzania urządzeniami w organizacji. Można bezpiecznie zezwolić na to uprawnienie. Firma Microsoft nigdy nie będzie tworzyć rozmów telefonicznych ani nimi zarządzać.  
    * **Zezwól Portal firmy na dostęp do Twoich kontaktów**: to uprawnienie umożliwia aplikacji Portal firmy tworzenie i używanie konta służbowego oraz zarządzanie nim.  Można bezpiecznie zezwolić na to uprawnienie. Firma Microsoft nigdy nie uzyskuje dostępu do Twoich kontaktów. 

    Jeśli odmówisz uprawnień, zostanie wyświetlony monit z prośbą o ponowne zalogowanie się do Portal firmy. Aby wyłączyć te komunikaty, wybierz pozycję **Nigdy nie pytaj ponownie**. Aby zarządzać uprawnieniami aplikacji, przejdź do pozycji Ustawienia Aplikacja > **aplikacje** > **Portal firmy** > **uprawnień** > **telefonu**.  

6. Aktywuj aplikację administratora urządzenia. 

    Portal firmy wymaga uprawnień administratora urządzenia do bezpiecznego zarządzania urządzeniem. Aktywowanie aplikacji pozwala organizacji identyfikować możliwe problemy z zabezpieczeniami, takie jak powtórzone nieudane próby odblokowania urządzenia i odpowiednie reagowanie.  

    ![Przykładowy obraz ekranu aktywowanie administratora urządzenia, wyróżnienie przycisku Aktywuj.](./media/activate-device-administrator-1911.png)  

> [!NOTE]
> Firma Microsoft nie kontroluje komunikatów na tym ekranie. Rozumiemy, że jego sformułowanie może wydawać się nieco drastyczne. Portal firmy nie może określić, które ograniczenia i dostęp mają być odpowiednie dla Twojej organizacji. Jeśli masz pytania dotyczące sposobu korzystania z aplikacji przez organizację, skontaktuj się z osobą odpowiedzialną za pomoc techniczną IT. Przejdź do [witryny internetowej Portalu firmy](https://go.microsoft.com/fwlink/?linkid=2010980), w której możesz znaleźć informacje kontaktowe organizacji.  


7. Urządzenie rozpocznie rejestrowanie. Jeśli używasz urządzenia z systemem Samsung KNOX, zobaczysz najpierw monit o sprawdzenie i potwierdzenie zasad ochrony prywatności agenta ELM.   

    ![Przykładowy obraz ekranu zasad ochrony prywatności Samsung KNOX, który pojawia się podczas rejestracji.](./media/and-enroll-7-knox-privacy-policy.png)  

8. Na ekranie **Konfiguracja dostępu do zasobów firmy** Sprawdź, czy urządzenie jest zarejestrowane. Następnie naciśnij pozycję **KONTYNUUJ**.  

    ![Przykład obrazu Portal firmy, ekranu Konfiguracja dostępu do zasobów firmy.](./media/update-settings-1911.png)  

9. Organizacja może wymagać aktualizacji ustawień urządzenia. Naciśnij pozycję **Rozwiąż** , aby dostosować ustawienie. Po zakończeniu aktualizowania ustawień naciśnij pozycję **Kontynuuj**.  

   ![Przykładowy obraz Portal firmy, zaktualizowanie ustawień urządzenia, wyróżnianie przycisków Rozwiąż i Kontynuuj.](./media/resolve-settings-1911.png)  

10. Po zakończeniu instalacji naciśnij pozycję **gotowe**.    

    ![Przykładowy obraz Portal firmy, ekranu Konfiguracja dostępu do zasobów firmy, pokazuje ukończoną konfigurację i przycisk Gotowe.](./media/android-enrollment-done-1911.png) 

## <a name="next-steps"></a>Następne kroki  

Przed podjęciem próby zainstalowania szkoły lub aplikacji służbowej przejdź do pozycji **ustawienia** > **zabezpieczenia**i Włącz opcję **Nieznane źródła**. Jeśli nie włączysz tej opcji, podczas próby zainstalowania aplikacji zostanie wyświetlony następujący komunikat: „Zablokowano instalację. Ze względów bezpieczeństwa Twoje urządzenie zostało ustawione w celu blokowania instalacji aplikacji uzyskanych z nieznanych źródeł”. Możesz nacisnąć pozycję **Ustawienia** w wiadomości, aby przejść bezpośrednio do **nieznanych źródeł**.  

> [!Note]
> Jeśli Twoja organizacja korzysta z oprogramowania do zarządzania wydatkami telekomunikacyjnymi, musisz wykonać kilka dodatkowych czynności, zanim urządzenie zostanie w pełni zarejestrowane. Dowiedz się więcej [tutaj](enroll-your-device-with-telecom-expense-management-android.md).

Jeśli podczas próby zarejestrowania urządzenia w usłudze Intune wystąpi błąd, możesz [wysłać wiadomość e-mail do działu pomocy technicznej Twojej firmy](send-logs-to-your-it-admin-by-email-android.md).  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  