---
title: "Ustawienia usługi Intune dla aplikacji Classroom w systemie iOS | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień aplikacji Classroom na urządzeniach z systemem iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: 3c7ab3e33f7a1a97cd8048be059cf2f74deb00c1
ms.contentlocale: pl-pl
ms.lasthandoff: 05/03/2017


---


# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>Jak konfigurować ustawienia usługi Intune dla aplikacji Classroom w systemie iOS

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="introduction"></a>Wprowadzenie
[Classroom](https://itunes.apple.com/app/id1085319084) jest aplikacją, która pomaga nauczycielom w prowadzeniu nauczania oraz sterowaniu urządzeniami uczniów w klasie. Przy użyciu aplikacji nauczyciel może na przykład:

- Otwierać aplikacje na urządzeniach uczniów
- Blokować i odblokowywać ekran tabletu iPad
- Wyświetlać ekran tabletu iPad ucznia
- Nawigować w tabletach iPad uczniów do zakładki lub rozdziału w książce
- Wyświetlać ekran z tabletu iPad ucznia w urządzeniu Apple TV

Użyj profilu urządzenia **Edukacja** dla systemu iOS w usłudze Intune oraz informacji przedstawionych w tym temacie, aby skonfigurować aplikację Classroom oraz urządzenia, na których będzie ona używana.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem konfiguracji tych ustawień należy uwzględnić następujące kwestie:

- Tablety iPad zarówno dla nauczycieli, jak i dla uczniów muszą być zarejestrowane w usłudze Intune
- Upewnij się, że na urządzeniu nauczyciela została zainstalowana aplikacja [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8). Możesz to zrobić ręcznie lub użyć [zarządzania aplikacjami usługi Intune](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management).
- Należy skonfigurować certyfikaty, aby uwierzytelnić połączenia między urządzeniami dla nauczycieli i uczniów (zobacz Krok 2).
- Tablety iPad dla nauczycieli i uczniów muszą znajdować się w tej samej sieci Wi-Fi, jak również mieć włączoną funkcję Bluetooth.
- Aplikacja Classroom jest uruchamiania na nadzorowanych tabletach iPad z systemem iOS 9.3 lub nowszym.
- W tej wersji usługa Intune obsługuje zarządzanie scenariuszem 1:1, zgodnie z którym każdy uczeń ma swój własny dedykowany tablet iPad.


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Krok 1. Importowanie danych szkoły do usługi Azure Active Directory

Użyj narzędzia School Data Sync (SDS) firmy Microsoft do zaimportowania rekordów szkoły z istniejącego systemu informacji o uczniach (SIS) do usługi Azure Active Directory (Azure AD).
Narzędzie SDS synchronizuje informacje z systemu SIS i przechowuje je w usłudze Azure AD. Azure AD jest systemem zarządzania firmy Microsoft, który pomaga organizować użytkowników i urządzenia. Możesz następnie użyć tych danych, aby ułatwić sobie zarządzanie uczniami i klasami. [Dowiedz się więcej na temat wdrażania narzędzia SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Jak importować dane przy użyciu narzędzia SDS?

Informacje do narzędzia SDS możesz zaimportować przy użyciu jednego z następujących elementów:

- [Pliki CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) — ręcznie wyeksportuj i skompiluj pliki zawierające wartości rozdzielane przecinkami (.csv)
- [Interfejs API PowerSchool](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) — dostawca systemu SIS, który upraszcza synchronizację z usługą Azure AD
- [Interfejs API Clever](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) — rozwiązanie zarządzania tożsamościami, które umożliwia bezpośrednią synchronizację z usługą Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) — format CSV, który można wyeksportować i przekonwertować w celu synchronizacji z usługą Azure AD

### <a name="find-out-more"></a>Dowiedz się więcej

- [Więcej informacji o tym, jak w pełni korzystać z synchronizacji lokalnych danych szkoły z usługą Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Więcej informacji o narzędziu School Data Sync firmy Microsoft](https://sds.microsoft.com/)
- [Więcej informacji na temat licencjonowania w usłudze Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Krok 2. Tworzenie i przypisywanie profilu Edukacja dla systemu iOS w usłudze Intune

### <a name="configure-general-settings"></a>Konfigurowanie ustawień ogólnych

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3.    W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
4.    W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
5.    W bloku profilów wybierz pozycję **Utwórz profil**.
6.    W bloku **Utwórz profil** wypełnij pola **Nazwa** i **Opis** odnoszące się do profilu Edukacja w systemie iOS.
7.    Z listy rozwijanej **Platforma** wybierz pozycję **iOS**.
8.    Z listy rozwijanej **Typ profilu** wybierz pozycję **Edukacja**.
9.    Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**.


Następnie potrzebne są certyfikaty, aby ustanowić relację zaufania między tabletami iPad dla nauczycieli i uczniów. Certyfikaty służą do uwierzytelniania połączeń między urządzeniami w sposób płynny i dyskretny bez konieczności wprowadzania nazwy użytkownika i hasła.

>[!IMPORTANT]
>Używane certyfikaty dla nauczycieli i uczniów muszą być wystawiane przez różne urzędy certyfikacji. Należy utworzyć dwa nowe podrzędne urzędy certyfikacji połączone z istniejącą infrastrukturą certyfikatów — jeden dla nauczycieli i jeden dla uczniów.

Profile edukacyjne dla systemu iOS obsługują tylko certyfikaty PFX, natomiast certyfikaty protokołu SCEP nie są obsługiwane.

Tworzone certyfikaty poza uwierzytelnianiem użytkowników muszą obsługiwać uwierzytelnianie serwera.

### <a name="configure-teacher-certificates"></a>Konfigurowanie certyfikatów dla nauczycieli

W bloku **Edukacja** wybierz pozycję **Certyfikaty nauczycieli**.

#### <a name="configure-teacher-root-certificate"></a>Konfigurowanie certyfikatu głównego dla nauczycieli

W obszarze **Certyfikat główny nauczyciela** wybierz przycisk przeglądania, aby wybrać certyfikat główny dla nauczycieli z rozszerzeniem .cer (zakodowany w formacie DER lub Base64) lub .P7B (z pełnym łańcuchem lub bez).

#### <a name="configure-teacher-pkcs12-certificate"></a>Konfigurowanie certyfikatu PKCS#12 dla nauczycieli

W obszarze **Certyfikat PKCS#12 nauczyciela** skonfiguruj następujące wartości:

- **Format nazwy obiektu** — usługa Intune automatycznie wstawia prefiks do nazwy pospolitej certyfikatu — **leader** w przypadku certyfikatu dla nauczycieli i **member** w przypadku certyfikatu dla uczniów.
- **Urząd certyfikacji** — wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. 
- **Nazwa urzędu certyfikacji** — wprowadź nazwę urzędu certyfikacji.
- **Nazwa szablonu certyfikatu** — wprowadź nazwę szablonu certyfikatu, który dodano do urzędu wystawiającego certyfikaty. 
- **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
- **Okres ważności certyfikatu** — określ ilość czasu pozostałego do wygaśnięcia certyfikatu.
Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty.

Po zakończeniu konfigurowania certyfikatów wybierz przycisk **OK**.

### <a name="configure-student-certificates"></a>Konfigurowanie certyfikatów dla uczniów

1.    W bloku **Edukacja** wybierz pozycję **Certyfikaty uczniów**.
2.    W bloku **Certyfikaty uczniów** z listy **Typ certyfikatów urządzenia ucznia** wybierz pozycję **1:1**.

#### <a name="configure-student-root-certificate"></a>Konfigurowanie certyfikatu głównego dla uczniów

W obszarze **Certyfikat główny ucznia** wybierz przycisk przeglądania, aby wybrać certyfikat główny dla uczniów z rozszerzeniem .cer (zakodowany w formacie DER lub Base64) lub .P7B (z pełnym łańcuchem lub bez).

#### <a name="configure-student-pkcs12-certificate"></a>Konfigurowanie certyfikatów PKCS#12 dla uczniów

W obszarze **Certyfikat PKCS#12 ucznia** skonfiguruj następujące wartości:

- **Format nazwy obiektu** — usługa Intune automatycznie wstawia prefiks do nazwy pospolitej certyfikatu — **leader** w przypadku certyfikatu dla nauczycieli i **member** w przypadku certyfikatu dla uczniów.
- **Urząd certyfikacji** — wymagany jest urząd certyfikacji przedsiębiorstwa z systemem Windows Server 2008 R2 lub nowszym w wersji Enterprise. Autonomiczny urząd certyfikacji nie jest obsługiwany. 
- **Nazwa urzędu certyfikacji** — wprowadź nazwę urzędu certyfikacji.
- **Nazwa szablonu certyfikatu** — wprowadź nazwę szablonu certyfikatu, który dodano do urzędu wystawiającego certyfikaty. 
- **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
- **Okres ważności certyfikatu** — określ ilość czasu pozostałego do wygaśnięcia certyfikatu.
Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty.

Po zakończeniu konfigurowania certyfikatów wybierz przycisk **OK**.

## <a name="finish-up"></a>Zakończenie

1.    W bloku **Edukacja** wybierz przycisk OK.
2.    W bloku **Utwórz profil** wybierz pozycję **Utwórz**.
    
Profil zostanie utworzony i wyświetlony w bloku listy profilów.

Przypisz profil do urządzeń dla uczniów w grupach klas, które zostały utworzone podczas synchronizowania danych szkoły z usługą Azure AD (zobacz temat [Jak przypisywać profile urządzeń](/intune-azure/configure-devices/how-to-assign-device-profiles)).

## <a name="next-steps"></a>Następne kroki

Teraz gdy nauczyciel używa aplikacji Classroom, będzie miał pełną kontrolę nad urządzeniami uczniów.

Aby uzyskać więcej informacji o aplikacji Classroom, zobacz [pomoc dotyczącą aplikacji Classroom](https://help.apple.com/classroom/ipad/2.0/) w witrynie sieci Web firmy Apple.

