## Rejestracja w usłudze Azure Active Directory

Automatyczna rejestracja pozwala użytkownikom rejestrować należące do firmy lub osobiste urządzenia i komputery z systemami Windows 10 i Windows 10 Mobile w usłudze Intune przez dodanie konta służbowego i wyrażenie zgody na to, aby były zarządzane. Proste. W tle urządzenie użytkownika zostaje zarejestrowane i przyłączone do usługi Azure Active Directory. Po zarejestrowaniu urządzenie jest zarządzane za pomocą usługi Intune.

**Wymagania wstępne**
- Subskrypcja usługi Azure Active Directory — wersja Premium ([subskrypcja wersji próbnej](http://go.microsoft.com/fwlink/?LinkID=816845))
- Subskrypcja usługi Microsoft Intune


### Konfigurowanie automatycznej rejestracji w usłudze MDM

1. W [portalu zarządzania Azure](https://manage.windowsazure.com) (https://manage.windowsazure.com) przejdź do węzła **Active Directory** i wybierz swój katalog.

2. Kliknij kartę **Aplikacje**. Na liście aplikacji powinna być widoczna pozycja **Microsoft Intune**.

    ![Aplikacje usługi Azure AD z usługą Microsoft Intune](../media/aad-intune-app.png)

3. Kliknij strzałkę obok pozycji **Microsoft Intune** — powinna zostać wyświetlona strona, która umożliwia skonfigurowanie usługi Microsoft Intune.

4. Kliknij pozycję **Konfiguruj**, aby rozpocząć konfigurowanie automatycznej rejestracji w usłudze MDM za pomocą usługi Microsoft Intune.

5. Określ adresy URL dla usługi Intune:

  - **Adres URL rejestracji w usłudze MDM** — użyj wartości domyślnej.
  - **Adres URL warunków użytkowania usługi MDM** — Użyj wartości domyślnej. Ten adres URL wyświetla warunki użytkowania dla użytkowników podczas rejestrowania urządzeń.
  - **Adres URL zgodności usługi MDM** — Użyj wartości domyślnej. Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat **Odmowa dostępu** z tym adresem URL. Adres URL wskazuje stronę, która pomaga użytkownikom zrozumieć, dlaczego ich urządzenie nie jest zgodne z zasadami i w jaki sposób można przywrócić jego zgodność.

6.  Określ użytkowników, których urządzenia powinny być zarządzane przez usługę Microsoft Intune. Urządzenia z systemem Windows 10 tych użytkowników zostaną automatycznie zarejestrowane w usłudze Microsoft Intune.

  - **Wszystkie**
  - **Grupy**
  - **Brak**

7. Wybierz polecenie **Zapisz**.


<!--HONumber=Oct16_HO2-->


