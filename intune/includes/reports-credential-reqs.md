<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Wymagania dotyczące poświadczeń usług Azure AD i Intune

Uwierzytelnianie i autoryzacja są oparte na poświadczeniach usługi Azure AD i kontroli dostępu opartej na rolach (RBAC). Wszyscy administratorzy globalni i administratorzy usługi Intune dla dzierżawy domyślnie mają dostęp do magazynu danych. Przy użyciu ról usługi Intune możesz zapewnić dostęp dla większej liczby użytkowników, dając im dostęp do zasobu **magazynu danych usługi Intune**.

Wymagania dotyczące dostępu do magazynu danych usługi Intune (w tym interfejsu API) są następujące:

  -  Użytkownik musi być:
      -  administratorem globalnym usługi Azure AD,
      -  administratorem usługi Intune,
      -  użytkownikiem mającym oparty na roli dostęp do zasobu **magazynu danych usługi Intune**
      -  Uwierzytelnianie bez użytkowników przy użyciu [uwierzytelniania tylko aplikacji](../data-warehouse-app-only-auth.md) 
