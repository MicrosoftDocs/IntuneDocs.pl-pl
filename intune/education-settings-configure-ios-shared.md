---
title: "Ustawienia udostępnionych urządzeń usługi Intune dla aplikacji Classroom w systemie iOS"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień aplikacji Classroom na urządzeniach z systemem iOS."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6dc373f831b574abf7d63e97935a379e731422
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-configure-intune-education-settings-for-shared-ipad-devices"></a>Jak skonfigurować ustawienia rozwiązań dla edukacji usługi Intune dla udostępnianych urządzeń iPad

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune obsługuje aplikację Classroom dla systemu iOS, która pomaga nauczycielom w prowadzeniu nauczania oraz kontrolowaniu urządzeń uczniów w klasie. Oprócz aplikacji Classroom firma Apple obsługuje możliwość skonfigurowania urządzeń iPad uczniów w taki sposób, że wielu uczniów może współdzielić jedno urządzenie. W tym dokumencie opisano sposób osiągnięcia tego celu przy użyciu usługi Intune.

Informacje o konfigurowaniu dedykowanych (1:1) urządzeń iPad do używania aplikacji Classroom zawiera temat [Jak konfigurować ustawienia usługi Intune dla aplikacji Classroom w systemie iOS](education-settings-configure-ios.md).

## <a name="before-you-start"></a>Przed rozpoczęciem

Wymagania wstępne w celu używania funkcji udostępnionych urządzeń iPad:

- Skonfigurowanie usług [Apple School Manager](apple-school-manager-set-up-ios.md) i [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617).
- W ramach konfiguracji usługi Apple School Manager skonfigurowanie [zarządzanych identyfikatorów Apple ID](http://help.apple.com/schoolmanager/#/tes78b477c81) dla uczniów. [Dowiedz się więcej o zarządzanych identyfikatorach Apple ID](https://support.apple.com/HT205918).
- Utworzenie profilu rejestracji dla numerów seryjnych urządzeń, które są synchronizowane za pomocą usługi Apple School Manager.

## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Krok 1. Importowanie danych szkoły do usługi Azure Active Directory

Użyj narzędzia School Data Sync (SDS) firmy Microsoft do zaimportowania rekordów szkoły z istniejącego systemu informacji o uczniach (SIS) do usługi Azure Active Directory (Azure AD).
Narzędzie SDS synchronizuje informacje z systemu SIS i przechowuje je w usłudze Azure AD. Azure AD jest systemem zarządzania firmy Microsoft, który pomaga organizować użytkowników i urządzenia. Możesz następnie użyć tych danych, aby ułatwić sobie zarządzanie uczniami i klasami. [Dowiedz się więcej na temat wdrażania narzędzia SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Jak importować dane przy użyciu usługi SDS

Informacje do usługi SDS możesz zaimportować przy użyciu jednej z następujących metod:

- [Pliki CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) — ręcznie wyeksportuj i skompiluj pliki zawierające wartości rozdzielane przecinkami (.csv)
- [Interfejs API PowerSchool](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) — dostawca systemu SIS, który upraszcza synchronizację z usługą Azure AD
- [Interfejs API Clever](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) — rozwiązanie zarządzania tożsamościami, które umożliwia bezpośrednią synchronizację z usługą Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) — format CSV, który można wyeksportować i przekonwertować w celu synchronizacji z usługą Azure AD

### <a name="find-out-more"></a>Dowiedz się więcej

- [Więcej informacji o tym, jak w pełni korzystać z synchronizacji lokalnych danych szkoły z usługą Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Więcej informacji o narzędziu School Data Sync firmy Microsoft](https://sds.microsoft.com/)
- [Więcej informacji na temat licencjonowania w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)


## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Krok 2. Tworzenie i przypisywanie profilu Edukacja dla systemu iOS w usłudze Intune

### <a name="configure-general-settings"></a>Konfigurowanie ustawień ogólnych

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
5. W okienku profilów wybierz pozycję **Utwórz profil**.
6. W okienku **Utwórz profil** wypełnij pola **Nazwa** i **Opis** odnoszące się do profilu Edukacja w systemie iOS.
7. Z listy rozwijanej **Platforma** wybierz pozycję **iOS**.
8. Z listy rozwijanej **Typ profilu** wybierz pozycję **Edukacja**.
9. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**.

Następnie potrzebne są certyfikaty, aby ustanowić relację zaufania między tabletami iPad dla nauczycieli i uczniów. Certyfikaty służą do uwierzytelniania połączeń między urządzeniami w sposób płynny i dyskretny bez konieczności wprowadzania nazwy użytkownika i hasła.

>[!Important]
>Używane certyfikaty dla nauczycieli i uczniów muszą być wystawiane przez różne urzędy certyfikacji. Należy utworzyć dwa nowe podrzędne urzędy certyfikacji połączone z istniejącą infrastrukturą certyfikatów — jeden dla nauczycieli i jeden dla uczniów.

Profile edukacyjne systemu iOS obsługują tylko certyfikaty PFX. Certyfikaty SCEP nie są obsługiwane.

Tworzone certyfikaty poza uwierzytelnianiem użytkowników muszą obsługiwać uwierzytelnianie serwera.

### <a name="configure-teacher-certificates"></a>Konfigurowanie certyfikatów dla nauczycieli

W okienku **Edukacja** wybierz pozycję **Certyfikaty nauczycieli**.

#### <a name="configure-teacher-root-certificate"></a>Konfigurowanie certyfikatu głównego dla nauczycieli

W obszarze **Certyfikat główny nauczyciela** wybierz przycisk przeglądania, aby wybrać certyfikat główny dla nauczycieli z rozszerzeniem .cer (zakodowany w formacie DER lub Base64) lub .P7B (z pełnym łańcuchem lub bez).

#### <a name="configure-teacher-pkcs12-certificate"></a>Konfigurowanie certyfikatu PKCS#12 dla nauczycieli

W obszarze **Certyfikat PKCS#12 nauczyciela** skonfiguruj następujące wartości:

- **Format nazwy obiektu** — usługa Intune automatycznie wstawia prefiks do nazwy pospolitej certyfikatu — **leader** w przypadku certyfikatu dla nauczycieli i **member** w przypadku certyfikatu dla uczniów.
- **Urząd certyfikacji** — wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany.
- **Nazwa urzędu certyfikacji** — wprowadź nazwę urzędu certyfikacji.
- **Nazwa szablonu certyfikatu** — wprowadź nazwę szablonu certyfikatu, który dodano do urzędu wystawiającego certyfikaty.
- **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
- **Okres ważności certyfikatu** — określ ilość czasu pozostałego do wygaśnięcia certyfikatu. Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty.

Po zakończeniu konfigurowania certyfikatów nauczycieli wybierz przycisk **OK**.

### <a name="configure-student-certificates"></a>Konfigurowanie certyfikatów dla uczniów

1. W okienku **Edukacja** wybierz pozycję **Certyfikaty uczniów**.
2. W okienku **Certyfikaty uczniów** z listy **Typ certyfikatów urządzenia ucznia** wybierz pozycję **Udostępnione urządzenie iPad**.

#### <a name="configure-student-root-certificate"></a>Konfigurowanie certyfikatu głównego dla uczniów

W obszarze **Certyfikat główny urządzenia** wybierz przycisk przeglądania, aby wybrać certyfikat główny dla uczniów z rozszerzeniem cer (zakodowany w formacie DER lub Base64) albo P7B (z pełnym łańcuchem lub bez niego).

#### <a name="configure-device-pkcs12-certificate"></a>Konfigurowanie certyfikatu PKCS#12 dla urządzenia

W obszarze **Certyfikat PKCS#12 ucznia** skonfiguruj następujące wartości:

- **Format nazwy podmiotu** — usługa Intune automatycznie wstawia prefiks do nazwy pospolitej certyfikatu — leader w przypadku certyfikatu dla nauczycieli i member w przypadku certyfikatu dla urządzenia.
- **Urząd certyfikacji** — wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany.
- **Nazwa urzędu certyfikacji** — wprowadź nazwę urzędu certyfikacji.
- **Nazwa szablonu certyfikatu** — wprowadź nazwę szablonu certyfikatu, który dodano do urzędu wystawiającego certyfikaty.
- **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
- **Okres ważności certyfikatu** — określ ilość czasu pozostałego do wygaśnięcia certyfikatu. Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty.

Po zakończeniu konfigurowania certyfikatów wybierz przycisk **OK**.

### <a name="complete-certificate-setup"></a>Kończenie konfiguracji certyfikatu

1. W okienku **Edukacja** wybierz przycisk **OK**.
2. W okienku **Utwórz profil** wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.

## <a name="step-3---create-a-device-category"></a>Krok 3. Tworzenie kategorii urządzeń

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Rejestrowanie urządzenia**.
4. W okienku **Rejestrowanie urządzeń — Przegląd** wybierz pozycję **Kategorie urządzeń**.
5. W okienku **Rejestrowanie urządzeń — Kategorie urządzeń** wybierz pozycję **Utwórz**.
6. W okienku **Tworzenie kategorii urządzeń** uzupełnij pola **Nazwa** i **Opis** dotyczące kategorii.
7. W okienku **Tworzenie kategorii urządzeń** wybierz pozycję **Utwórz**.

Kategoria urządzeń zostanie utworzona w okienku **Rejestracja — Kategorie urządzeń**.

## <a name="step-4--create-a-dynamic-group"></a>Krok 4. Tworzenie grupy dynamicznej

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Grupy**.
4. W okienku **Użytkownicy i grupy — Wszystkie grupy** wybierz pozycję **Nowa grupa**.
5. W okienku **Grupa** wybierz pozycję **Typ grupy**, a następnie wypełnij pola **Nazwa** i **Opis** dla grupy.
6. Na liście rozwijanej **Typ członkostwa** wybierz pozycję **Urządzenie dynamiczne**.
7. Wybierz pozycję **Dynamiczne urządzenia członkowskie**, aby utworzyć reguły członkostwa.
8. W okienku **Reguły członkostwa dynamicznego**:
1. Wybierz pozycję **deviceCategory** z listy rozwijanej **Dodaj urządzenia, na których**.
2. Wybierz pozycję **Równa się**.
3. Wprowadź utworzoną kategorię urządzeń w pustym polu tekstowym.
9. W okienku **Reguły członkostwa dynamicznego** wybierz pozycję **Dodaj zapytanie**.
10. W okienku **Grupa** wybierz pozycję **Utwórz**.

Grupa dynamiczna zostanie utworzona w okienku **Użytkownicy i grupy — Wszystkie grupy**.

## <a name="step-5--assign-a-device-to-a-category-carts"></a>Krok 5. Przypisywanie urządzeń do kategorii (koszyków)

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Urządzenia**.
4. W okienku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. W okienku **Urządzenia — Wszystkie urządzenia** wybierz urządzenie.
6. W okienku urządzenia wybierz pozycję **Właściwości**.
7. W okienku właściwości urządzenia wprowadź kategorię urządzenia w polu tekstowym **Kategoria urządzenia**.
8. W okienku urządzenia wybierz pozycję **Zapisz**.

Urządzenie jest teraz skojarzone z kategorią urządzeń. Powtórz ten proces dla wszystkich urządzeń, które chcesz skojarzyć z utworzoną kategorią urządzeń.

## <a name="step-6--create-classroom-profiles"></a>Krok 6. Tworzenie profilów klas

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
4. W okienku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile koszyków**.
5. W okienku profilów wybierz pozycję **Utwórz profil**.
6. W okienku **Utwórz skojarzenie** wypełnij pola **Nazwa** i **Opis**.
7. Wybierz kolejno pozycje **Wybierz klasy** > **Konfiguruj**, aby skojarzyć grupy z profilem koszyka.
8. Wybierz klasy do dołączenia do profilu koszyka, a następnie wybierz pozycję **Wybierz**. 
9. Wybierz kolejno pozycje **Wybierz koszyki** > **Konfiguruj**, aby skojarzyć grupy z profilem koszyka.
10. Wybierz grupy do włączenia do profilu koszyka, a następnie wybierz pozycję **Wybierz**.
11. W okienku **Utwórz skojarzenie** wybierz pozycję **Zapisz** w celu zapisania profilu koszyka.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.

## <a name="step-7---assign-the-cart-profile-to-classes"></a>Krok 7. Przypisywanie profilu koszyka do klas

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
4. W okienku **Konfiguracja urządzeń** wybierz kolejno pozycje **Monitoruj** > **Stan przypisania**.
5. W okienku **Stan przypisania** wybierz utworzony **Profil koszyka**.
6. W okienku **Profil koszyka** wybierz pozycję **Przypisania**, a następnie w obszarze **Dołączanie** wybierz pozycję **Wybierz grupy do uwzględnienia**.
7. Wybierz klasy, które mają być celem profilu koszyka (nie należy wybierać grupy), a następnie wybierz pozycję **Wybierz**. 
8. Gdy skończysz, wybierz pozycję **Zapisz**.

Przypisanie zostanie zakończone i usługa Intune wdroży profil aplikacji Classroom na urządzeniach docelowych na podstawie przypisania klasy.

## <a name="next-steps"></a>Następne kroki

Teraz uczniowie mogą współdzielić urządzenia, a ponadto mogą wybrać dowolne urządzenie iPad w klasie i zalogować się za pomocą numeru PIN, a urządzenie zostanie spersonalizowane przy użyciu ich zawartości. Aby uzyskać więcej informacji o udostępnionych urządzeniach iPad, zobacz [witrynę internetową firmy Apple](https://www.apple.com/education/it/).
