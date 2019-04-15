---
ms.openlocfilehash: 04afc9c44bc1c4898950e6f3aff5dac7cb93370f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "56323420"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Włączanie automatycznej rejestracji urządzeń z systemem Windows 10

Automatyczna rejestracja umożliwia użytkownikom rejestrowanie urządzeń z systemem Windows 10 w usłudze Intune. Aby zarejestrować urządzenie, użytkownik dodaje konto służbowe do swojego urządzenia osobistego lub łączy urządzenie należące do firmy z usługą Azure Active Directory. W tle urządzenie zostaje zarejestrowane i przyłączone do usługi Azure Active Directory. Po zarejestrowaniu urządzenie jest zarządzane za pomocą usługi Intune.

**Wymagania wstępne**
- Subskrypcja usługi Azure Active Directory — wersja Premium ([subskrypcja wersji próbnej](http://go.microsoft.com/fwlink/?LinkID=816845))
- Subskrypcja usługi Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurowanie automatycznej rejestracji w usłudze MDM

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i wybierz pozycję **Azure Active Directory**.

   ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-azure-main.png)

2. Wybierz pozycję **Mobilność (MDM i MAM)**.

   ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-mdm.png)

3. Wybierz pozycję **Microsoft Intune**.

   ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-intune.png)

4. Skonfiguruj **zakres użytkownika oprogramowania MDM**. Określ użytkowników, których urządzenia powinny być zarządzane przez usługę Microsoft Intune. Te urządzenia z systemem Windows 10 mogą zostać automatycznie zarejestrowane w celu zarządzania w usłudze Microsoft Intune.

   - **Brak** — automatyczne rejestrowanie w usłudze zarządzania urządzeniami mobilnymi (MDM) jest wyłączone
   - **Niektóre** — wybierz **grupy**, które mogą automatycznie rejestrować swoje urządzenia z systemem Windows 10
   - **Wszystkie** — wszyscy użytkownicy mogą automatycznie rejestrować swoje urządzenia z systemem Windows 10

      > [!IMPORTANT]
      > W przypadku urządzeń BYOD zakres użytkownika funkcji MAM ma pierwszeństwo, jeśli dla wszystkich użytkowników (lub tych samych grup użytkowników) jest włączony zarówno zakres użytkownika funkcji MAM, jak i zakres użytkownika oprogramowania MDM (automatyczne rejestrowanie MDM). Urządzenie będzie używało zasad funkcji Windows Information Protection (WIP) (jeśli je skonfigurowano) i nie zostanie zarejestrowane przez funkcję zarządzania urządzeniami mobilnymi.
      >
      > W przypadku urządzeń firmowych zakres użytkownika oprogramowania MDM ma pierwszeństwo, jeśli włączone są oba zakresy. Urządzenia są rejestrowane przez funkcję zarządzania urządzeniami mobilnymi.

   > [!NOTE]
   > Zakres użytkowników funkcji MAM należy ustawić na kolekcję lub grupę użytkowników.

   ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-scope.png)

5. Użyj wartości domyślnych dla następujących adresów URL:
    - **Adres URL Warunków użytkowania zarządzania urządzeniami mobilnymi**
    - **Adres URL odnajdywania zarządzania urządzeniami przenośnymi**
    - **Adres URL zgodności oprogramowania MDM**

6. Wybierz pozycję **Zapisz**.

Uwierzytelnianie dwuskładnikowe nie jest domyślnie włączone dla usługi. Zaleca się jednak korzystanie z uwierzytelniania dwuskładnikowego podczas rejestrowania urządzenia. Aby włączyć uwierzytelnianie dwuskładnikowe, należy skonfigurować dostawcę usługi uwierzytelniania dwuskładnikowego w usłudze Azure AD i skonfigurować konta użytkowników do uwierzytelniania wieloskładnikowego. Zobacz temat [Wprowadzenie do usługi Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
