---
title: "Tworzenie zasad zgodności urządzeń | Microsoft Docs"
description: "Utwórz zasady zgodności, aby zabezpieczyć urządzenia przenośne i komputery używane do uzyskiwania dostępu do danych firmowych."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5336dac0-a2cc-4cd4-8511-67e4f95bd700
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 21875001129da8f5ca01869fa69960f18ae28c56


---

# <a name="create-a-device-compliance-policy-in-microsoft-intune"></a>Tworzenie zasad zgodności urządzeń w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym temacie opisano czynności służące do tworzenia zasad zgodności, które urządzenie musi spełnić, aby było uznane za zgodne.

##  <a name="step-1-add-a-new-policy"></a>Krok 1. Dodanie nowej zasady
  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Zasady zgodności** &gt; **Dodaj**.

  ![Zrzut ekranu strony zasad zgodności w konsoli administracyjnej usługi Intune przedstawiający opcję Dodaj w menu u góry strony](./media/intune-sa-3a-add-compliance-policy.png)

##  <a name="step-2--configure-settings"></a>Krok 2. Konfigurowanie ustawień
Na stronie **Tworzenie zasad** włącz wymagane ustawienia:
  -   Ustawienia zabezpieczeń systemu, np. hasło i szyfrowanie.
  -   Ustawienia kondycji urządzenia, np. określanie, czy urządzenie ma zdjęte zabezpieczenia lub jest zgłoszone jako urządzenie w dobrej kondycji przez usługę zaświadczania o kondycji urządzenia systemu Windows.
  -   Ustawienia właściwości urządzenia, np. minimalna wymagana wersja systemu operacyjnego lub dozwolona maksymalna wersja systemu operacyjnego.
![Karta Ogólne na stronie Tworzenie zasad](./media/intune-sa-3b-create-policy.png)


##  <a name="step-3-save-the-policy"></a>Krok 3. Zapisanie zasad
Gdy skończysz, wybierz pozycję **Zapisz zasady**.

Zasady będzie można wdrożyć od razu po ich zapisaniu lub później. Nowe zasady zostaną wyświetlone w węźle **Zasady zgodności** w obszarze roboczym **Zasady**.

##  <a name="step-4-set-the-compliance-status-validity-period"></a>Krok 4. Ustawienie okresu ważności stanu zgodności
Aby określić czas, w którym urządzenie musi zostać zaewidencjonowane, zanim zostanie uznane za niezgodne, przejdź do ustawień zasad zgodności i zaktualizuj czas. Domyślnie opcja jest ustawiona na 30 dni.

![Opcja ustawień zasad zgodności na pasku menu zasad](../media/mdm-compliance-policy-settings.png)

![Okno dialogowe zasad zgodności](../media/mdm-ca-compliance-status-validity-period.png)

## <a name="supported-policy-settings"></a>Obsługiwane ustawienia zasad
W poniższej tabeli wymieniono ustawienia zasad zgodności i platformy, na których są obsługiwane.

-------------
|Ustawienie|iOS|Android|Windows|
|-----|----|-----|-----|
|Wymagaj hasła do odblokowania urządzeń przenośnych|iOS 6 i nowsze|Android 4.0 i nowsze <br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy|
|Zezwalaj na proste hasła|iOS 6 i nowsze|Nieobsługiwane|System Windows Phone 8.1 lub nowszy|
|Minimalna długość hasła|iOS 6 i nowsze| Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze| System Windows Phone 8.1 lub nowszy<br>Windows 8.1|
|Wymagany typ hasła|iOS 6 i nowsze|Niedostępne|System Windows Phone 8.1 lub nowszy <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Minimalna liczba zestawów znaków|iOS 6 i nowsze|Niedostępne|System Windows Phone 8.1 lub nowszy <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Jakość hasła|Niedostępne|Android 4.0 i nowsze <br>KNOX Samsung  Standard 4.0 i nowsze|Niedostępne|
|Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy<br>Windows RT i Windows RT 8.1<br>Windows 8.1|
|Wygaśnięcie hasła w dniach|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy<br>Windows RT i Windows RT 8.1<br>Windows 8.1|
|Pamiętaj historię haseł|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy<br>Windows RT i Windows RT 8.1<br>Windows 8.1|
|Zapobiegaj ponownemu używaniu poprzednich haseł|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy<br>Windows RT i Windows RT 8.1<br>Windows 8.1|
|Wymagaj hasła po przywróceniu urządzenia ze stanu bezczynności| Niedostępne| Niedostępne|Windows 10 Mobile|
|Wymagaj szyfrowania na urządzeniu przenośnym|Nie dotyczy|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy<br> Windows 8.1|
|Wymagaj zgłoszenia dobrej kondycji urządzeń| Niedostępne| Niedostępne|Windows <br>Windows 10 Mobile|
|Nie zezwalaj na zdjęcie zabezpieczeń systemu ani na uzyskanie dostępu do konta root|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|Niedostępne|
|Konto e-mail musi być zarządzane przez usługę Intune|iOS 6 i nowsze|Niedostępne| Niedostępne|
|Wybierz profil poczty e-mail, który ma być zarządzany przez usługę Intune|iOS 6 i nowsze|Niedostępne| Niedostępne|
|Wymagana minimalna wersja systemu operacyjnego|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze| System Windows Phone 8.1 lub nowszy<br>Windows 8.1|
|Dozwolona maksymalna wersja systemu operacyjnego|iOS 6 i nowsze|Android 4.0 i nowsze<br>KNOX Samsung  Standard 4.0 i nowsze|System Windows Phone 8.1 lub nowszy<br>Windows 8.1|

Wybierz jeden z następujących elementów, aby dowiedzieć się więcej o ustawieniach zgodności obsługiwanych na każdej platformie:
> [!div class="op_single_selector"]
- [Ustawienia zasad zgodności dla urządzeń z systemem iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemem Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Ustawienia zasad zgodności dla urządzeń z systemami Windows i Windows Phone](windows-compliance-policy-settings-in-microsoft-intune.md)


## <a name="next-steps"></a>Następne kroki
[Wdrażanie i monitorowanie zasad zgodności](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Zobacz także
[Wprowadzenie do zasad zgodności urządzeń](introduction-to-device-compliance-policies-in-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->

