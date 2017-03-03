## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Konfiguracja automatycznej rejestracji w systemach Windows 10 i Windows 10 Mobile przy użyciu usługi Azure Active Directory Premium

Automatyczna rejestracja pozwala użytkownikom rejestrować należące do firmy lub osobiste urządzenia i komputery z systemami Windows 10 i Windows 10 Mobile w usłudze Intune przez dodanie konta służbowego i wyrażenie zgody na to, aby były zarządzane. Proste. W tle urządzenie użytkownika zostaje zarejestrowane i przyłączone do usługi Azure Active Directory. Po zarejestrowaniu urządzenie jest zarządzane za pomocą usługi Intune.

**Wymagania wstępne**
- Subskrypcja usługi Azure Active Directory — wersja Premium ([subskrypcja wersji próbnej](http://go.microsoft.com/fwlink/?LinkID=816845))
- Subskrypcja usługi Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurowanie automatycznej rejestracji w usłudze MDM

1. W [portalu zarządzania Azure](https://portal.azure.com) (https://manage.windowsazure.com) przejdź do węzła **Active Directory** i wybierz swój katalog.

2. Wybierz kartę **Aplikacje**. Na liście aplikacji zostanie wyświetlona pozycja **Microsoft Intune**.

    ![Aplikacje usługi Azure AD z usługą Microsoft Intune](../media/aad-intune-app.png)

3. Wybierz strzałkę dla pozycji **Microsoft Intune**. Zostanie otwarta strona, która umożliwia skonfigurowanie usługi Microsoft Intune.

4. Wybierz pozycję **Konfiguruj**, aby rozpocząć konfigurowanie automatycznej rejestracji w usłudze MDM za pomocą usługi Microsoft Intune.

5. Użyj wartości domyślnych dla następujących adresów URL:

  - **Rejestracja w usłudze zarządzania urządzeniami przenośnymi**
  - **Warunki użytkowania usługi zarządzania urządzeniami przenośnymi** 
  - **Zgodność z usługą zarządzania urządzeniami przenośnymi**

6.  Określ użytkowników, których urządzenia powinny być zarządzane przez usługę Microsoft Intune. Urządzenia z systemem Windows 10 tych użytkowników zostaną automatycznie zarejestrowane w usłudze Microsoft Intune.

  - **Wszystkie**
  - **GRUPY**
  - **Brak**

7. Wybierz polecenie **Zapisz**.