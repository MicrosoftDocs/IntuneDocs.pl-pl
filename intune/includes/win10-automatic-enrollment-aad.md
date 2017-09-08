## <a name="enable-windows-10-automatic-enrollment"></a>Włączanie automatycznej rejestracji urządzeń z systemem Windows 10

Automatyczna rejestracja umożliwia użytkownikom rejestrowanie urządzeń z systemem Windows 10 w usłudze Intune. Aby zarejestrować urządzenie, użytkownik dodaje konto służbowe do swojego urządzenia osobistego lub łączy urządzenie należące do firmy z usługą Azure Active Directory. W tle urządzenie zostaje zarejestrowane i przyłączone do usługi Azure Active Directory. Po zarejestrowaniu urządzenie jest zarządzane za pomocą usługi Intune.

**Wymagania wstępne**
- Subskrypcja usługi Azure Active Directory — wersja Premium ([subskrypcja wersji próbnej](http://go.microsoft.com/fwlink/?LinkID=816845))
- Subskrypcja usługi Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurowanie automatycznej rejestracji w zarządzaniu urządzeniami przenośnymi

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i wybierz pozycję **Azure Active Directory**.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-azure-main.png)

2. Wybierz pozycję **Mobilność (MDM i MAM)**.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-mdm.png)

3. Wybierz pozycję **Microsoft Intune**.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-intune.png)

4. Skonfiguruj **Zakres użytkownika oprogramowania MDM**. Określ użytkowników, których urządzenia powinny być zarządzane przez usługę Microsoft Intune. Te urządzenia z systemem Windows 10 mogą zostać automatycznie zarejestrowane w celu zarządzania w usłudze Microsoft Intune.

  - **Brak**
  - **Niektóre**
  - **Wszystkie**

   ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-scope.png)

5. Użyj wartości domyślnych dla następujących adresów URL:
    - **Adres URL Warunków użytkowania zarządzania urządzeniami przenośnymi**
    - **Adres URL odnajdywania dla zarządzania urządzeniami przenośnymi**
    - **Adres URL zgodności dla zarządzania urządzeniami przenośnymi**

    > [!IMPORTANT]
    > Jeśli dla danej grupy są włączone zarówno **Zakres użytkownika funkcji zarządzania aplikacjami mobilnymi**, jak i automatyczna rejestracja w zarządzaniu urządzeniami przenośnymi (**Zakres użytkownika oprogramowania MDM**), wówczas włączone jest tylko rozwiązanie zarządzania aplikacjami mobilnymi. Gdy użytkownicy w tej grupie dołączają urządzenia osobiste w miejscu pracy, dodawane jest tylko rozwiązanie zarządzania aplikacjami mobilnymi. Urządzenia nie są automatycznie rejestrowane przez rozwiązanie zarządzania urządzeniami przenośnymi.

6. Wybierz pozycję **Zapisz**.

Uwierzytelnianie dwuskładnikowe nie jest domyślnie włączone dla usługi. Zaleca się jednak korzystanie z uwierzytelniania dwuskładnikowego podczas rejestrowania urządzenia. Aby włączyć uwierzytelnianie dwuskładnikowe, należy skonfigurować dostawcę usługi uwierzytelniania dwuskładnikowego w usłudze Azure AD i skonfigurować konta użytkowników do uwierzytelniania wieloskładnikowego. Zobacz temat [Wprowadzenie do usługi Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
