## <a name="enable-windows-10-automatic-enrollment"></a>Włączanie automatycznej rejestracji urządzeń z systemem Windows 10

Automatyczna rejestracja pozwala użytkownikom rejestrować należące do firmy lub osobiste urządzenia i komputery z systemami Windows 10 i Windows 10 Mobile w usłudze Intune przez dodanie konta służbowego i wyrażenie zgody na to, aby były zarządzane. Proste. W tle urządzenie użytkownika zostaje zarejestrowane i przyłączone do usługi Azure Active Directory. Po zarejestrowaniu urządzenie jest zarządzane za pomocą usługi Intune.

**Wymagania wstępne**
- Subskrypcja usługi Azure Active Directory — wersja Premium ([subskrypcja wersji próbnej](http://go.microsoft.com/fwlink/?LinkID=816845))
- Subskrypcja usługi Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurowanie automatycznej rejestracji w usłudze MDM

1. Zaloguj się do [Portalu zarządzania Azure](https://portal.azure.com) (https://manage.windowsazure.com) i wybierz usługę **Azure Active Directory**.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-azure-main.png)

2. Wybierz pozycję **Mobilność (MDM i MAM)**.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-mdm.png)

3. Wybierz pozycję **Microsoft Intune**.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-intune.png)

4. Skonfiguruj użytkowników, którzy będą rejestrowani automatycznie.

  ![Zrzut ekranu witryny Azure Portal](../media/auto-enroll-scope.png)

  Użyj wartości domyślnych dla następujących adresów URL:
  - **Rejestracja w usłudze zarządzania urządzeniami przenośnymi**
  - **Warunki użytkowania usługi zarządzania urządzeniami przenośnymi**
  - **Zgodność z usługą zarządzania urządzeniami przenośnymi**

5. Określ użytkowników, których urządzenia powinny być zarządzane przez usługę Microsoft Intune. Urządzenia z systemem Windows 10 tych użytkowników zostaną automatycznie zarejestrowane w usłudze Microsoft Intune.

  - **Wszystkie**
  - **GRUPY**
  - **Brak**

6. Wybierz pozycję **Zapisz**.
