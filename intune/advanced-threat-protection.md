---
title: Korzystanie z usługi Microsoft Defender ATP w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Korzystaj z usługi Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) w usłudze Intune, m.in. przeprowadź instalację i konfigurację, dołączaj urządzenia Intune do usługi ATP, a następnie korzystaj z oceny ryzyka ATP urządzeń w oparciu o swoje zasady zgodności i dostępu warunkowego urządzeń w usłudze Intune w celu ochrony zasobów sieciowych.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8508915f0b4711b2aa65465dd7ac79f575a8d008
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670959"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Wymuszanie zgodności usługi Microsoft Defender ATP z dostępem warunkowym w usłudze Intune  

Usługę Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) można zintegrować z usługą Microsoft Intune w ramach rozwiązania Mobile Threat Defense, aby ułatwić zapobieganie naruszeniom bezpieczeństwa oraz ograniczyć wpływ naruszeń w organizacji. Usługa Microsoft Defender ATP współpracuje z urządzeniami z systemem Windows 10 lub nowszym.

Aby pomyślnie korzystać z usługi, należy równocześnie zastosować następujące konfiguracje:
- **Ustanowienie połączenia typu usługa do usługi między usługą Intune i usługą Microsoft Defender ATP**. To połączenie umożliwia usłudze Microsoft Defender ATP zbieranie danych dotyczących ryzyka maszyny ze strony urządzeń z systemem Windows 10 zarządzanych za pomocą usługi Intune.  
- **Użycie profilu konfiguracji urządzenia w celu dołączania urządzeń do usługi Microsoft Defender ATP**. Urządzenia należy dołączyć, aby je skonfigurować do komunikowania się z usługą Microsoft Defender ATP i dostarczyć dane, które pomogą ocenić ich poziom ryzyka.  
 - **Użycie zasad zgodności urządzeń w celu ustawienia dozwolonego poziomu ryzyka**. Poziomy ryzyka są zgłaszane przez usługę Microsoft Defender ATP.  Urządzenia, które przekraczają dozwolony poziom ryzyka, są identyfikowane jako niezgodne.  
- **Użycie zasad dostępu warunkowego**, aby uniemożliwić użytkownikom dostęp do zasobów firmy z niezgodnych urządzeń.  

Ponadto po zintegrowaniu usługi Intune z usługą Microsoft Defender ATP można korzystać z zalet funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach usługi ATP i [używać usługi Intune do korygowania słabości punktów końcowych wykrytych przez funkcję zarządzania zagrożeniami i lukami w zabezpieczeniach](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Przykład korzystania z usługi Microsoft Defender ATP w usłudze Intune  

Poniższy przykład pomoże wyjaśnić, jak te rozwiązania ze sobą współpracują, aby pomóc w ochronie organizacji. W tym przykładzie usługa Microsoft Defender ATP i usługa Intune są już zintegrowane.  

Rozważmy sytuację, gdy ktoś wysyła użytkownikowi w organizacji załącznik programu Word z osadzonym złośliwym kodem.  
- Użytkownik otwiera załącznik i uaktywnia zawartość.  
- Rozpoczyna się atak z udziałem podniesionego przywileju i atakujący korzystający z maszyny zdalnej ma prawa administratora do urządzenia ofiary.  
- Następnie atakujący uzyskuje zdalnie dostęp do innych urządzeń użytkownika. Takie naruszenie zabezpieczeń może mieć wpływ na całą organizację.  

Za pomocą usługi Microsoft Defender ATP można łatwiej rozpoznać zdarzenia zabezpieczeń podobne do zdarzeń z tego scenariusza.  
- W naszym przykładzie usługa Microsoft Defender ATP wykrywa, że urządzenie wykonało nietypowy kod, doszło do eskalacji uprawnienia korzystania z procesu, wprowadzenia złośliwego kodu i wywołania podejrzanej powłoki zdalnej.  
- W oparciu o te czynności wykonane z danego urządzenia usługa Microsoft Defender ATP [klasyfikuje je jako urządzenie wysokiego ryzyka](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) i dodaje szczegółowy raport o podejrzanych działaniach w portalu Microsoft Defender Security Center.  

Ponieważ istnieją zasady zgodności urządzeń w usłudze Intune, zgodnie z którymi urządzenia z poziomem ryzyka *Średni* lub *Wysoki* będą klasyfikowane jako niezgodne, zagrożone urządzenie zostaje sklasyfikowane jako niezgodne. Ta klasyfikacja umożliwia zastosowanie zasad dostępu warunkowego i blokowanie dostępu do zasobów firmy z tego urządzenia.  

## <a name="prerequisites"></a>Wymagania wstępne

Aby używać usługi Microsoft Defender ATP z usługą Intune, należy się upewnić, że następujące elementy zostały skonfigurowane i są gotowe do użycia:

- Licencjonowana dzierżawa dla pakietu Enterprise Mobility + Security E3 i systemu Windows E5 (lub pakietu Microsoft 365 Enterprise E5)
- Środowisko usługi Microsoft Intune oraz urządzenia z systemem Windows 10 [zarządzane przy użyciu usługi Intune](windows-enroll.md) przyłączone również do usługi Azure AD
- Usługa [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) oraz dostęp do usługi Microsoft Defender Security Center (portal ATP)

## <a name="enable-microsoft-defender-atp-in-intune"></a>Włączanie usługi Microsoft Defender ATP w usłudze Intune

Najpierw trzeba skonfigurować połączenie typu usługa do usługi między usługą Intune i usługą Microsoft Defender ATP. Wymaga to dostępu administracyjnego zarówno do usługi Microsoft Defender Security Center, jak i do usługi Intune.  

### <a name="to-enable-defender-atp"></a>Aby włączyć usługę Defender ATP  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzenie** > **Microsoft Defender ATP**, a następnie pod obszarem *Ustawienia łącznika* wybierz pozycję **Otwórz usługę Microsoft Defender Security Center**.

    ![Wybieranie pozycji otwierającej usługę Microsoft Defender Security Center](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. W usłudze **Microsoft Defender Security Center**:
    1. Wybierz pozycję **Ustawienia** > **Funkcje zaawansowane**.
    2. Dla pozycji **Połączenie z usługą Microsoft Intune** wybierz ustawienie **Wł.** :

        ![Włączanie połączenia z usługą Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Wybierz pozycję **Zapisz preferencje**.

4. Wróć do usługi Intune i wybierz pozycję **Zgodność urządzeń** > **Microsoft Defender ATP**. Ustaw pozycję **Połącz urządzenia systemu Windows w wersji 10.0.15063 lub nowszej z usługą Microsoft Defender ATP** na **Wł.**
5. Wybierz pozycję **Zapisz**.

Zwykle należy wykonać to zadanie raz. Po włączeniu usługi Microsoft Defender ATP dla dzierżawy usługi Intune nie trzeba tego robić ponownie.

> [!TIP]  
> Po zintegrowaniu nowej aplikacji z usługą Intune Mobile Threat Defense (MTD) i włączeniu połączenia usługa Intune tworzy klasyczne zasady dostępu warunkowego w usłudze Azure Active Directory. Każda zintegrowana aplikacja MTD, na przykład [Defender ATP](advanced-threat-protection.md) lub dowolny z naszych dodatkowych [partnerów MTD](mobile-threat-defense.md#mobile-threat-defense-partners), tworzy nowe klasyczne zasady dostępu warunkowego.  Te zasady można ignorować, ale nie należy ich edytować, usuwać ani wyłączać.
> 
> Klasyczne zasady dostępu warunkowego dla aplikacji MTD mają następujące cechy: 
> 
> - Są używane przez usługę Intune MTD do żądania zarejestrowania urządzeń w usłudze Azure AD, dzięki czemu mają one identyfikator urządzenia. Ten identyfikator jest wymagany, aby urządzenia mogły pomyślnie zgłaszać swój stan do usługi Intune.  
> - Różnią się od zasad dostępu warunkowego, które można utworzyć, aby ułatwić sobie zarządzanie usługą MTD.
> - Domyślnie nie wchodzą w interakcje z innymi zasadami dostępu warunkowego używanymi na potrzeby oceny.  
> 
> Aby wyświetlić klasyczne zasady dostępu warunkowego, w witrynie [Azure Portal](https://portal.azure.com/#home) przejdź do pozycji **Azure Active Directory** > **Dostęp warunkowy** > **Zasady klasyczne**.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Dołączanie urządzeń przy użyciu profilu konfiguracji

Po nawiązaniu połączenia typu usługa do usługi między usługami Intune i Microsoft Defender ATP, możesz dołączyć urządzenia zarządzane w usłudze Intune do usługi ATP, aby można było zbierać dane dotyczące ich poziomu ryzyka, a następnie z nich korzystać. Aby dołączyć urządzenia, należy użyć profilu konfiguracji urządzenia dla usługi Microsoft Defender ATP.  

Po nawiązaniu połączenia z usługą Microsoft Defender ATP usługa Intune otrzymuje pakiet konfiguracyjny dołączania do usługi Microsoft Defender ATP z usługi Microsoft Defender ATP. Ten pakiet jest wdrażany na urządzeniach z profilem konfiguracji urządzenia. Pakiet konfiguracyjny konfiguruje urządzenia do komunikowania się z [usługami Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) w celu skanowania plików, wykrywania zagrożeń oraz zgłaszania ryzyka do usługi Microsoft Defender ATP.  

Po dołączeniu urządzenia przy użyciu pakietu konfiguracyjnego nie trzeba tego robić ponownie. Można również dodać urządzenia przy użyciu [zasad grupy lub programu System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-device-configuration-profile"></a>Tworzenie profilu konfiguracji urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W polu **Typ profilu** wybierz pozycję **Microsoft Defender ATP (Windows 10 Desktop)** .
6. Skonfiguruj ustawienia:

   - **Typ pakietu konfiguracji klienta usługi Microsoft Defender ATP**: Wybierz pozycję **Dodaj**, aby dodać pakiet konfiguracyjny do profilu. Wybierz pozycję **Odłącz**, aby usunąć pakiet konfiguracyjny z profilu.
  
     > [!NOTE]  
     > Jeśli połączenie z usługą Microsoft Defender ATP zostało ustanowione poprawnie, usługa Intune automatycznie **dołączy** profil konfiguracji dla użytkownika, a ustawienie **Typ pakietu konfiguracji klienta usługi Microsoft Defender ATP** nie będzie dostępne.
  
    - **Udostępnianie próbek dla wszystkich plików**: pozycja **Włącz** umożliwia zbieranie przykładów oraz ich udostępnianie w usłudze Microsoft Defender ATP. Na przykład, jeśli widzisz podejrzany plik, możesz go przesłać do usługi Microsoft Defender ATP w celu wykonania szczegółowej analizy. Pozycja **Nieskonfigurowane** nie udostępnia żadnych przykładów w usłudze Microsoft Defender ATP.
    - **Usprawnij częstotliwość raportowania danych telemetrycznych**: pozycja **Włącz** to ustawienie dla urządzeń narażonych na duże ryzyko, które pozwala na częstsze przekazywanie danych telemetrycznych do usługi Microsoft Defender ATP.

    Dodatkowe informacje na temat ustawień usługi Microsoft Defender ATP można znaleźć w artykule [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) (Dołączanie maszyn z systemem Windows 10 za pomocą programu System Center Configuration Manager).

7. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany i utworzyć profil.
8. [Przypisz profil konfiguracji urządzenia](device-profile-assign.md) do urządzeń, które chcesz ocenić za pomocą usługi Microsoft Defender ATP.  

## <a name="create-and-assign-the-compliance-policy"></a>Tworzenie i przypisywanie zasad zgodności  

Zasady zgodności określają poziom ryzyka, który uznaje się za akceptowalny dla urządzenia.

### <a name="create-the-compliance-policy"></a>Tworzenie zasad zgodności  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzeń** > **Zasady** > **Utwórz zasady**.
3. Uzupełnij pola **Nazwa** i **Opis**.
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W ustawieniach usługi **Microsoft Defender ATP** ustaw pozycję **Wymagaj, aby urządzenie było na poziomie niższym lub równym ocenie ryzyka maszyny** na preferowany poziom. 
   
   Klasyfikacja poziomów zagrożenia jest [określana przez usługę Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Czyste**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne. (Usługa Microsoft Defender ATP używa wartości *Bezpieczny*).
   - **Niski**: Urządzenie jest zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Urządzenia ze średnim lub wysokim poziomem zagrożenia nie są zgodne.
   - **Średni**: Urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
   - **Wysoki**: Ten poziom jest najmniej bezpieczny i zezwala na wszystkie poziomy zagrożeń. Urządzenia z wysokim, średnim i niskim poziomem zagrożeń są więc uznawane za zgodne.

6. Wybierz opcję **OK** i **Utwórz**, aby zapisać zmiany (i utworzyć zasady).  
7. [Przypisz zasady zgodności urządzeń](create-compliance-policy.md#assign-user-groups) do odpowiednich grup.



## <a name="create-a-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego  

Zasady dostępu warunkowego blokują dostęp do zasobów dla urządzeń, które przekraczają poziom zagrożenia ustawiony w zasadach zgodności. Możesz zablokować dostęp z urządzenia do zasobów firmowych, np. do programu SharePoint lub usługi Exchange Online.  

> [!TIP]  
> Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure Active Directory (Azure AD). Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*.  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), a następnie wybierz kolejno pozycje **Dostęp warunkowy** > **Nowe zasady**.
2. W polu **Nazwa** wprowadź nazwę zasad i wybierz pozycję **Użytkownicy i grupy**. Użyj opcji Dołącz lub Wyklucz, aby dodać grupy do zasad, i wybierz opcję **Gotowe**.
3. Wybierz opcję **Aplikacje w chmurze** i wybierz aplikacje, które będą chronione. Na przykład wybierz pozycję **Wybierz aplikacje**, a następnie pozycje **Office 365 SharePoint Online** i **Office 365 Exchange Online**.

    Wybierz przycisk **Gotowe**, aby zapisać zmiany.

4. Wybierz pozycję **Warunki** > **Aplikacje klienckie**, aby zastosować zasady do aplikacji i przeglądarek. Na przykład wybierz przycisk **Tak**, a następnie włącz opcje **Przeglądarka** oraz **Aplikacje mobilne i klienci stacjonarni**.

    Wybierz przycisk **Gotowe**, aby zapisać zmiany.

5. Wybierz pozycję **Udziel**, aby zastosować dostęp warunkowy w zależności od zgodności urządzeń. Na przykład wybierz pozycje **Udziel dostępu** > **Wymagaj, aby urządzenie było oznaczone jako zgodne**.

    Wybierz przycisk **Wybierz**, aby zapisać zmiany.

6. Wybierz pozycję **Włącz zasady**, a następnie **Utwórz**, aby zapisać zmiany.



## <a name="monitor-device-compliance"></a>Monitorowanie zgodności urządzenia  

Następnie monitoruj stan urządzeń objętych zasadami zgodności usługi Microsoft Defender ATP.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Zgodność urządzeń** > **Zgodność z zasadami**.
3. Znajdź na liście zasady usługi Microsoft Defender ATP i zobacz, które urządzenia są zgodne, a które niezgodne.

## <a name="next-steps"></a>Następne kroki  

[Microsoft Defender ATP conditional access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)  (Dostęp warunkowy usługi Microsoft Defender ATP)  
[Microsoft Defender ATP risk dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard) (Pulpit nawigacyjny ryzyka usługi Microsoft Defender ATP)  
[Use security tasks with ATPs Vulnerability Management to remediate issues on devices](atp-manage-vulnerabilities.md) (Korzystanie z zadań zabezpieczeń w ramach funkcji zarządzania lukami w zabezpieczeniach ATP, aby rozwiązywać problemy na urządzeniach).  
[Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md)  
 
