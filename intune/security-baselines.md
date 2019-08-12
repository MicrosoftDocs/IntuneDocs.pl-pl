---
title: Używanie punktów odniesienia zabezpieczeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Użyj zalecanych ustawień zabezpieczeń systemu Windows w celu ochrony użytkowników i danych na urządzeniach za pomocą usługi Microsoft Intune w ramach zarządzania urządzeniami przenośnymi. Włącz funkcję szyfrowania, skonfiguruj usługę Microsoft Defender Advanced Threat Protection, kontroluj program Internet Explorer, ustawiaj lokalne zasady zabezpieczeń, wymagaj hasła, blokuj pobieranie materiałów z Internetu i nie tylko.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c378fd3b208396f9d2f83b7bd56f50dbf7a7e3f7
ms.sourcegitcommit: 864fdf995c2b41f104a98a7e2665088c2864774f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68679967"
---
# <a name="use-security-baselines-to-configure-windows-10-devices-in-intune"></a>Konfigurowanie urządzeń z systemem Windows 10 w usłudze Intune przy użyciu punktów odniesienia zabezpieczeń

Punkty odniesienia zabezpieczeń usługi Intune pomogą Ci zabezpieczyć i chronić użytkowników i urządzenia. Punkty odniesienia zabezpieczeń to wstępnie skonfigurowane grupy ustawień systemu Windows, które ułatwiają stosowanie znanych grup ustawień i wartości domyślnych zalecanych przez odpowiednie zespoły ds. zabezpieczeń. Tworząc profil punktu odniesienia zabezpieczeń w usłudze Intune, tworzysz profil *konfiguracji urządzenia*.

Ta funkcja ma zastosowanie do:

- System Windows 10 w wersji 1809 lub nowszej

Punkty odniesienia zabezpieczeń wdraża się dla grup użytkowników lub urządzeń w usłudze Intune, a ustawienia są stosowane do urządzeń z systemem Windows 10 lub nowszym. Na przykład *punkt odniesienia zabezpieczeń rozwiązania MDM* automatycznie włącza funkcję BitLocker dla dysków wymiennych, automatycznie wymaga podania hasła przed odblokowaniem urządzenia, automatycznie wyłącza uwierzytelnianie podstawowe i wykonuje inne czynności. Jeśli wartość domyślna nie sprawdza się w Twoim środowisku, dostosuj punkt odniesienia, aby zastosować ustawienia, których potrzebujesz.  

Poszczególne typy punktów odniesienia mogą zawierać te same ustawienia, ale używać różnych wartości domyślnych dla tych ustawień. Ważne jest, aby poznać wartości domyślne w punktach odniesienia, których zdecydujesz się użyć, a następnie zmodyfikować każdy punkt odniesienia tak, aby spełniał potrzeby Twojej organizacji.  

> [!NOTE]
> Firma Microsoft nie zaleca używania wersji zapoznawczych punktów odniesienia zabezpieczeń w środowisku produkcyjnym. Ustawienia punktu odniesienia w wersji zapoznawczej mogą ulec zmianie w trakcie trwania tej wersji zapoznawczej. 

Celem użycia punktów odniesienia zabezpieczeń jest zapewnienie kompleksowego, bezpiecznego przepływu pracy podczas korzystania z rozwiązania Microsoft 365. Oto niektóre korzyści:

- Punkt odniesienia zabezpieczeń oferuje najlepsze rozwiązania i rekomendacje dotyczące ustawień, które mają wpływ na zabezpieczenia. Usługa Intune współpracuje z tym samym zespołem ds. zabezpieczeń systemu Windows, który tworzy punkty odniesienia zabezpieczeń dla zasad grupy. Te rekomendacje opierają się na wskazówkach i rozbudowanym środowisku.
- Jeśli zaczynasz używać usługi Intune i nie wiesz, od czego zacząć, warto skorzystać z punktów odniesienia. Można szybko tworzyć i wdrażać bezpieczny profil, wiedząc, że pomagasz chronić zasoby i dane organizacji.
- Jeśli obecnie używasz zasad grupy, migrowanie do usługi Intune na potrzeby zarządzania jest znacznie łatwiejsze z użyciem tych punktów odniesienia. Punkty odniesienia są natywnie wbudowane w usłudze Intune i oferują nowoczesne środowisko zarządzania.



Artykuł [Windows security baselines](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) (Punkty odniesienia zabezpieczeń systemu Windows) to doskonały zasób, z którego dowiesz się więcej na temat tej funkcji. Artykuł [Mobile device management](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) (Zarządzanie urządzeniami mobilnymi) to doskonały zasób zawierający informacje na temat funkcji MDM i czynności, które można wykonywać na urządzeniach z systemem Windows.

## <a name="security-baseline-versions-and-instances"></a>Wystąpienia i wersje punktu odniesienia zabezpieczeń
Od czasu do czasu udostępniane są nowe aktualizacje dla punktu odniesienia. Każde nowe wystąpienie wersji punktu odniesienia może dodawać lub usuwać ustawienia oraz wprowadzać inne zmiany. Jeśli na przykład w nowych wersjach systemu Windows 10 udostępniane są nowe ustawienia systemu Windows 10, punkt odniesienia zabezpieczeń rozwiązania MDM może otrzymać nowe wystąpienie wersji, które obejmuje te najnowsze ustawienia.  

W konsoli usługi Intune można sprawdzić, które punkty odniesienia zabezpieczeń są dostępne, i wyświetlić informacje na ich temat. Dostępne informacje obejmują liczbę Twoich profili, które korzystają z punktu odniesienia danego typu, liczbę dostępnych oddzielnych wystąpień punktu odniesienia danego typu oraz termin udostępnienia lub opublikowania najnowszego wystąpienia.  Poniższy przykład pokazuje kafelek powszechnie używanego punktu odniesienia zabezpieczeń rozwiązania MDM:  

![Kafelek punktu odniesienia](./media/security-baselines/baseline-tile.png)

Aby wyświetlić informacje o używanych wersjach punktów odniesienia, wybierz punkt odniesienia, a następnie wybierz pozycję **Wersje**. Usługa Intune wyświetli szczegółowe informacje o wersjach używanych przez Twoje profile. W okienku wersji możesz wybrać jedną wersję, aby wyświetlić bardziej szczegółowe informacje o profilach, które używają tej wersji. Możesz również wybrać dwie różne wersje, a następnie wybrać pozycję **Porównaj punkty odniesienia**, aby pobrać plik CSV ze szczegółami różnic.  

![Porównywanie punktów odniesienia](./media/security-baselines/compare-baselines.png)

Kiedy tworzysz *profil* punktu odniesienia zabezpieczeń, ten profil automatycznie używa ostatnio wydanego wystąpienia punktu odniesienia zabezpieczeń.  Nadal możesz używać i edytować profile, które zostały utworzone wcześniej i które korzystają z wcześniejszego wystąpienia wersji punktu odniesienia, w tym z punktów odniesienia utworzonych przy użyciu wersji zapoznawczej. 

Profile punktów odniesienia zabezpieczeń obsługują [zmianę wersji](#change-the-baseline-instance-for-a-profile) używanego punktu odniesienia. Oznacza to, że po wydaniu nowej wersji nie musisz tworzyć nowego profilu punktu odniesienia, aby z niej skorzystać. Zamiast tego, gdy wszystko będzie gotowe, możesz wybrać profil punktu odniesienia, a następnie użyć wbudowanej opcji, aby zmienić wersję wystąpienia dla tego profilu.  

## <a name="available-security-baselines"></a>Dostępne punkty odniesienia zabezpieczeń 

Poniższe wystąpienia punktów odniesienia zabezpieczeń są dostępne do użycia z usługą Intune. Użyj linków, aby wyświetlić ustawienia dla najnowszego wystąpienia każdego punktu odniesienia. 

- **Punkt odniesienia zabezpieczeń rozwiązania MDM**
  - [Punkt odniesienia zabezpieczeń rozwiązania MDM z maja 2019](security-baseline-settings-mdm.md)
  - [Wersja zapoznawcza: punkt odniesienia rozwiązania MDM z października 2018 r.](security-baseline-settings-mdm-archive.md)

- **Punkt odniesienia usługi Microsoft Defender ATP**  
  *(Aby móc używać tego punktu odniesienia, środowisko musi spełniać wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](advanced-threat-protection.md#prerequisites))* .
  - [Wersja zapoznawcza: punkt odniesienia usługi Microsoft Defender ATP](security-baseline-settings-defender-atp.md)  

  > [!NOTE]
  > Punkt odniesienia zabezpieczeń usługi Microsoft Defender ATP został zoptymalizowany pod kątem urządzeń fizycznych i nie jest obecnie zalecany do użycia na maszynach wirtualnych ani punktach końcowych infrastruktury VDI. Niektóre ustawienia punktu odniesienia mogą mieć wpływ na zdalne sesje interaktywne w zwirtualizowanych środowiskach.  Aby uzyskać więcej informacji, zobacz [Increase compliance to the Microsoft Defender ATP security baseline (Zwiększanie zgodności z punktem odniesienia zabezpieczeń usługi Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) w dokumentacji systemu Windows.

Nadal możesz używać i edytować profile, które zostały utworzone wcześniej na podstawie szablonu wersji zapoznawczej, nawet jeśli ten szablon wersji zapoznawczej nie jest już dostępny do tworzenia nowych profilów. 

## <a name="prerequisites"></a>Wymagania wstępne
- Aby móc zarządzać planami bazowymi w usłudze Intune, Twoje konto musi mieć wbudowaną rolę [Menedżer zasad i profilów](role-based-access-control.md#built-in-roles).

- Korzystanie z niektórych punktów odniesienia może wymagać aktywnej subskrypcji dodatkowych usług, takich jak Microsoft Defender ATP.  

## <a name="co-managed-devices"></a>Urządzenia współzarządzane

Punkty odniesienia zabezpieczeń na urządzeniach zarządzanych przez usługę Intune są podobne do urządzeń współzarządzanych w programie Configuration Manager. Urządzenia współzarządzane używają programu System Center Configuration Manager i usługi Microsoft Intune do równoczesnego zarządzania urządzeniami z systemem Windows 10. Pozwala to na łączenie istniejących inwestycji związanych z programem Configuration Manager z korzyściami dotyczącymi usługi Intune w chmurze. Artykuł [Co-management overview](https://docs.microsoft.com/sccm/comanage/overview) (Omówienie współzarządzania) to doskonały zasób, jeśli używasz programu Configuration Manager i chcesz korzystać z zalet chmury.

W przypadku używania urządzeń współzarządzanych musisz przełączyć obciążenie **Konfiguracja urządzenia** (jego ustawienia) do usługi Intune. Dalsze informacje można znaleźć w części [Device configuration workloads](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) (Obciążenia konfiguracji urządzenia).

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), a następnie wybierz pozycję **Bezpieczeństwo urządzeń** > **Punkty odniesienia zabezpieczeń**, aby wyświetlić listę dostępnych punktów odniesienia.


    ![Wybór puntu odniesienia zabezpieczeń do skonfigurowania](./media/security-baselines/available-baselines.png)

2. Wybierz punkt odniesienia, którego chcesz użyć, a następnie wybierz opcję **Utwórz profil**.  

3. Na karcie **Podstawowe** określ następujące właściwości:

    - **Nazwa**: wprowadź nazwę profilu punktu odniesienia zabezpieczeń. Na przykład wpisz *Profil standardowy dla usługi Defender ATP*.

    - **Opis**: wprowadź tekst opisujący zadania wykonywane przez dany punkt odniesienia. W polu opisu możesz wprowadzić dowolny wybrany tekst. Jest to opcjonalne, ale zalecane.  

   Wybierz **Dalej**, aby przejść do następnej karty. Po przejściu do nowej karty możesz wybrać nazwę karty, aby wrócić do poprzedniej karty.  

4. Na karcie Ustawienia konfiguracji przejrzyj grupy **ustawień** dostępnych w wybranym punkcie odniesienia. Możesz rozwinąć grupę, aby wyświetlić ustawienia w tej grupie i wartości domyślne dla ustawień w danym punkcie odniesienia. Aby znaleźć określone ustawienia:
   - Wybierz grupę, aby rozwinąć i przejrzeć dostępne ustawienia.  
   - Użyj paska *Wyszukaj*, a następnie określ słowa kluczowe filtrujące widok, aby wyświetlić tylko te grupy, które zawierają podane kryteria wyszukiwania.  
 
   Każde ustawienie w punkcie odniesienia ma konfigurację domyślną dla tej wersji punktu odniesienia. Zmień ustawienia domyślne stosownie do swoich potrzeb biznesowych. Różne punkty odniesienia mogą zawierać to samo ustawienie i używać różnych wartości domyślnych dla tego ustawienia w zależności od przeznaczenia punktu odniesienia. 

    ![Rozwijanie grupy w celu wyświetlenia ustawień dla tej grupy](./media/security-baselines/sample-list-of-settings.png)

5. Na karcie **Tagi zakresu** wybierz pozycję **Wybierz tagi zakresu**, aby otworzyć okienko *Wybieranie tagów* w celu przypisania tagów zakresu do profilu. 

6. Na karcie **Przypisania** wybierz pozycję **Wybierz grupy do uwzględnienia**, a następnie przypisz punkt odniesienia do co najmniej jednej grupy. Użyj opcji **Wybierz grupy do wykluczenia**, aby dopracować przypisanie.  

   ![Przypisywanie profilu](./media/security-baselines/assignments.png)
  
7. Gdy wszystko będzie gotowe do wdrożenia punktu odniesienia, przejdź na kartę **Przeglądanie + tworzenie**, aby przejrzeć szczegóły punktu odniesienia. Wybierz pozycję **Utwórz**, aby zapisać i wdrożyć profil.  

   Jak tylko profil zostanie utworzony, jest on wypychany do przypisanej grupy i można go natychmiast zastosować.

   > [!TIP]  
   > Jeśli zapiszesz profil bez przypisywania go do grup, możesz później edytować profil, aby to zrobić.  

   ![Przegląd punktu odniesienia](./media/security-baselines/review.png) 

  
8. Po utworzeniu profilu można go edytować. W tym celu wybierz pozycję **Bezpieczeństwo urządzeń** > **Punkty odniesienia zabezpieczeń**, wybierz skonfigurowany typ punktu odniesienia, a następnie wybierz pozycję **Profile**.  Wybierz profil z listy dostępnych profilów, a następnie wybierz pozycję **Właściwości**. Możesz edytować ustawienia na wszystkich dostępnych kartach konfiguracji. Następnie wybierz pozycję **Przejrzyj i zapisz**, aby zatwierdzić zmiany.  

## <a name="change-the-baseline-instance-for-a-profile"></a>Zmienianie wystąpienia punktu odniesienia dla profilu
Profile punktów odniesienia obsługują zmianę wystąpienia punktu odniesienia, z którego korzysta dany profil. Możesz wybrać starsze wystąpienie lub, co się zdarza częściej, nowsze wystąpienie tego samego punktu odniesienia.  Nie można zmienić punktu odniesienia na inny, na przykład nie można zmienić w profilu punktu odniesienia dla usługi Defender ATP na punkt odniesienia zabezpieczeń rozwiązania MDM. 

Podczas konfigurowania zmiany wersji punktu odniesienia będziesz mieć możliwość pobrania pliku CSV, który zawiera listę zmian między dwoma wybranymi wersjami punktu odniesienia. Możesz również wybrać, czy chcesz zachować wszystkie dostosowania z oryginalnej wersji punktu odniesienia i zastosować je do nowej wersji, czy zaimplementować wszystkie wartości domyślne nowej wersji punktu odniesienia. 

Podczas zapisywania, po zakończeniu konwersji, punkt odniesienia jest od razu wdrażany ponownie w przypisanych grupach.  

**Podczas konwersji**:
- Nowe ustawienia, których nie było w oryginalnej, używanej przez Ciebie wersji, są dodawane i są dla nich ustawiane wartości domyślne.  

- Ustawienia, których nie ma w nowej, wybranej przez Ciebie wersji punktu odniesienia, są usuwane i nie są już wymuszane przez ten profil punktu odniesienia zabezpieczeń.  

  Kiedy ustawienie nie jest już zarządzane przez profil punktu odniesienia, to ustawienie nie jest resetowane na urządzeniu. Zamiast tego ustawienie na urządzeniu pozostaje ustawione zgodnie ze swoją ostatnią konfiguracją, dopóki inny proces nie będzie nim zarządzać i go nie zmieni. Przykłady procesów, które mogą zmienić ustawienie, gdy przestaniesz nim zarządzać, obejmują inny profil punktu odniesienia, ustawienie zasad grupy lub ręczną konfigurację urządzenia. 

### <a name="to-change-the-instance-for-a-baseline"></a>Aby zmienić wystąpienie dla punktu odniesienia  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), wybierz pozycję **Bezpieczeństwo urządzeń** > **Punkty odniesienia zabezpieczeń**, a następnie wybierz kafelek dla typu punktu odniesienia zawierającego profil, który chcesz zmienić.  

2. Następnie wybierz pozycję **Profile**, zaznacz pole wyboru dla profilu, który chcesz edytować, a następnie wybierz pozycję **Zmień wersję**.  

   ![wybierz punkt odniesienia](./media/security-baselines/select-baseline.png)  

3. W okienku **Zmień wersję** użyj listy rozwijanej **Select a security baseline to update to** (Wybierz punkt odniesienia zabezpieczeń, do którego chcesz aktualizować) i wybierz wystąpienie wersji, którego chcesz użyć.  

   ![wybierz wersję](./media/security-baselines/select-instance.png)  
   
4. Wybierz pozycję **Review update** (Przejrzyj aktualizację), aby pobrać plik CSV, który pokazuje różnice między bieżącą wersją wystąpienia profilu i nową, wybraną przez Ciebie wersją. Przejrzyj ten plik, aby dowiedzieć się, które ustawienia zostaną dodane, które usunięte, oraz jakie są wartości domyślne dla tych ustawień w zaktualizowanym profilu.  

   Gdy wszystko będzie gotowe, przejdź do następnego kroku.  

5. Wybierz jedną z dwóch opcji dla pozycji **Select a method to update the profile** (Wybierz metodę aktualizowania profilu): 
   - **Accept baseline changes but keep my existing setting customizations** (Akceptuj zmiany punktu odniesienia, ale zachowaj istniejące dostosowania ustawień) — Ta opcja zachowuje dostosowania wprowadzone do profilu punktu odniesienia i stosuje je w nowej wersji wybranej przez Ciebie do użycia.
   - **Accept baseline changes and discard existing setting customizations** (Akceptuj zmiany punktu odniesienia i odrzuć istniejące dostosowania ustawień) — Ta opcja całkowicie zastępuje Twój oryginalny profil. Zaktualizowany profil użyje wartości domyślnych dla wszystkich ustawień.  

6. Wybierz pozycję **Prześlij**. Profil zostanie zaktualizowany do wybranej wersji punktu odniesienia i po zakończeniu konwersji punkt odniesienia zostanie natychmiastowo wdrożony ponownie w przypisanych grupach.

## <a name="remove-a-security-baseline-assignment"></a>Usuwanie przypisania punktu odniesienia zabezpieczeń
Kiedy ustawienie punktu odniesienia zabezpieczeń nie będzie miało już zastosowania do urządzenia lub ustawienia w punkcie odniesienia będą miały wartość *Nieskonfigurowane*, dla tych ustawień na urządzeniu nie zostanie przywrócona konfiguracja sprzed zarządzania. Zamiast tego, zarządzane wcześniej ustawienia na urządzeniu zachowają swoją ostatnią konfigurację pobraną z punktu odniesienia, dopóki jakiś inny proces nie zaktualizuje tych ustawień na urządzeniu.  

Inne procesy, które mogą później zmienić ustawienia na urządzeniu, obejmują inny lub nowy punkt odniesienia zabezpieczeń, profil konfiguracji urządzenia, konfigurację zasad grupy lub ręczną edycję ustawienia na urządzeniu.  





## <a name="q--a"></a>Pytania i odpowiedzi

### <a name="why-these-settings"></a>Dlaczego warto używać tych ustawień?

Zespół ds. zabezpieczeń firmy Microsoft w ciągu wielu lat zdobył doświadczenie w pracy bezpośrednio z deweloperami systemu Windows i społecznością zajmującą się zabezpieczeniami, co pomaga mu w tworzeniu tych rekomendacji. Ustawienia w tym punkcie odniesienia są uważane za najbardziej istotne opcje konfiguracji związane z zabezpieczeniami. W każdej nowej kompilacji systemu Windows zespół dostosowuje rekomendacje w oparciu o nowo wydane funkcje.

### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Czy istnieje różnica między rekomendacjami dotyczącymi punktów odniesienia zabezpieczeń systemu Windows dla zasad grupy i dla usługi Intune?

Ten sam zespół firmy Microsoft wybrał i zorganizował ustawienia dla każdego punktu odniesienia. Usługa Intune uwzględnia wszystkie odpowiednie ustawienia w punkcie odniesienia zabezpieczeń usługi Intune. W punkcie odniesienia zasad grupy istnieją pewne ustawienia specyficzne dla kontrolera domeny w środowisku lokalnym. Te ustawienia są wykluczane z rekomendacji w usłudze Intune. Wszystkie pozostałe ustawienia są takie same.

### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Czy punkty odniesienia zabezpieczeń usługi Intune są zgodne ze standardami organizacji CIS lub NIST?

Ściśle rzecz biorąc, nie. Zespól ds. zabezpieczeń firmy Microsoft konsultuje się z organizacjami, takimi jak CIS, podczas kompilowania rekomendacji. Ale nie istnieje mapowanie typu „jeden do jednego” między punktami odniesienia „zgodnymi z CIS” i przygotowanymi przez firmę Microsoft.

### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Jakie certyfikaty mają punkty odniesienia zabezpieczeń firmy Microsoft? 

- Firma Microsoft nadal publikuje punkty odniesienia zabezpieczeń dla zasad grupy (GPO) i zestawu narzędzi [Security Compliance Toolkit](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), tak jak robiła to przez wiele lat. Te punkty odniesienia są używane przez wiele organizacji. Rekomendacje przedstawione w tych punktach odniesienia są tworzone w trakcie współpracy zespołu ds. zabezpieczeń firmy Microsoft z klientami korporacyjnymi i agencjami zewnętrznymi, w tym z Departamentem Obrony (DoD, Department of Defense), Narodowym Instytutem Standaryzacji i Technologii (NIST, National Institute of Standards and Technology) i innymi. Udostępniamy nasze rekomendacje i punkty odniesienia tym organizacjom. Te organizacje mają również własne rekomendacje, które dokładnie odzwierciedlają rekomendacje firmy Microsoft. Ponieważ funkcja zarządzania urządzeniami przenośnymi (MDM) jest wciąż rozbudowywana w chmurze, firma Microsoft utworzyła równoważne rekomendacje oprogramowania MDM dla tych punktów odniesienia zasad grupy. Te dodatkowe punkty odniesienia są wbudowane w usłudze Microsoft Intune i oferują raporty dotyczące zgodności dla użytkowników, grup i urządzeń, które są zgodne (lub nie) z danym punktem odniesienia.

- Wielu klientów używa rekomendacji punktów odniesienia usługi Intune jako punktu startowego, a następnie dostosowuje go tak, aby spełniał wymagania dotyczące infrastruktury IT i zabezpieczeń. Pierwszy punkt odniesienia do wydania to **punkt odniesienia dotyczący oprogramowania MDM** w systemie Windows 10 RS5 firmy Microsoft. Ten punkt odniesienia został stworzony jako ogólna infrastruktura, która umożliwia klientom ostateczne importowanie innych punktów odniesienia w oparciu o standardy CIS, NIST i inne. Obecnie to rozwiązanie jest dostępne dla systemu Windows, a w przyszłości będzie również obejmować systemy iOS i Android.

- Migracja z lokalnych zasad grupy usługi Active Directory do rozwiązania działającego wyłącznie w chmurze przy użyciu usługi Azure Active Directory (AD) w usłudze Microsoft Intune to podróż. Aby ułatwić ten proces, można skorzystać z szablonów zasad grupy zawartych w zestawie narzędzi [Security Compliance Toolkit](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), które są pomocne w zarządzaniu urządzeniami przyłączonymi do hybrydowej usługi Azure AD i do usługi Azure AD. W razie potrzeby te urządzenia mogą uzyskać ustawienia zarządzania urządzeniami przenośnymi z chmury (usługi Intune), a ustawienia zasad grupy z kontrolerów domeny w środowisku lokalnym.

## <a name="next-steps"></a>Następne kroki
- Przejrzyj ustawienia w najnowszych wersjach dostępnych punktów odniesienia:  
  - [Punkt odniesienia zabezpieczeń rozwiązania MDM](security-baseline-settings-mdm.md)  
  - [Punkt odniesienia usługi Microsoft Defender ATP](security-baseline-settings-defender-atp.md)  

- Sprawdzanie stanu oraz monitorowanie [punktu odniesienia i profilu](security-baselines-monitor.md)

