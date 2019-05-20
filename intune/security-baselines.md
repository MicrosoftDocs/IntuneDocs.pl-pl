---
title: Używanie punktów odniesienia zabezpieczeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj zalecane ustawienia zabezpieczeń grup w celu ochrony użytkowników i danych na urządzeniach przy użyciu usługi Microsoft Intune w ramach zarządzania urządzeniami przenośnymi. Włącz funkcję BitLocker, konfiguruj Zaawansowaną ochronę przed zagrożeniami w usłudze Windows Defender, kontroluj program Internet Explorer, używaj filtru SmartScreen, ustawiaj lokalne zasady zabezpieczeń, wymagaj hasła, blokuj materiały do pobrania z Internetu i nie tylko.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 70638228875f1fb063a2ea22dc424c00f3940a30
ms.sourcegitcommit: ef4bc7318449129af3dc8c0154e54a264b7bf4e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "65197624"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Tworzenie punktu odniesienia zabezpieczeń systemu Windows 10 w usłudze Intune

Punkty odniesienia zabezpieczeń to funkcja w wersji zapoznawczej, która jest dostępna dla urządzeń z systemem Windows 10 i nowszymi wersjami. Ta funkcja obejmuje wiele ustawień obsługiwanych przez usługę Intune, które ułatwiają zabezpieczanie i ochronę użytkowników i urządzeń. Ustawia ona również automatycznie te ustawienia na wartości zalecane przez zespoły zajmujące się zabezpieczeniami. Na przykład punkt odniesienia automatycznie włącza funkcję BitLocker, automatycznie wymaga podania hasła przed odblokowaniem urządzenia, automatycznie wyłącza uwierzytelnianie podstawowe i wykonuje inne czynności.

Ta funkcja ma zastosowanie do:

- System Windows 10 w wersji 1809 lub nowszej

> [!NOTE]
> W okresie obowiązywania wersji zapoznawczej punktów odniesienia zabezpieczeń firma Microsoft nie zaleca używania profilów w środowisku produkcyjnym, ponieważ punkty odniesienia mogą zmieniać się w trakcie korzystania z wersji zapoznawczej. Gdy punkty odniesienia zabezpieczeń staną się ogólnie dostępne, istniejące profile nie zostaną przekonwertowane na najnowsze obsługiwane profile.

Celem użycia punktów odniesienia zabezpieczeń jest zapewnienie kompleksowego, bezpiecznego przepływu pracy podczas pracy z usługą Microsoft 365. Oto niektóre korzyści:

- Punkt odniesienia zabezpieczeń oferuje najlepsze rozwiązania i rekomendacje dotyczące ustawień, które mają wpływ na zabezpieczenia. Usługa Intune współpracuje z tym samym zespołem ds. zabezpieczeń systemu Windows, który tworzy punkty odniesienia zabezpieczeń dla zasad grupy. Te rekomendacje opierają się na wskazówkach i rozbudowanym środowisku.
- Jeśli zaczynasz używać usługi Intune i nie wiesz, od czego zacząć, warto skorzystać z punktów odniesienia. Można szybko tworzyć i wdrażać bezpieczny profil, wiedząc, że pomagasz chronić zasoby i dane organizacji.
- Jeśli obecnie używasz zasad grupy, migrowanie do usługi Intune na potrzeby zarządzania jest znacznie łatwiejsze z użyciem tych punktów odniesienia. Punkty odniesienia są natywnie wbudowane w usłudze Intune i oferują nowoczesne środowisko zarządzania.

Punkty odniesienia zabezpieczeń tworzą „profil zabezpieczeń” w usłudze Intune. Ten profil zawiera wszystkie ustawienia w punkcie odniesienia. Profil jest następnie stosowany lub przypisywany do użytkowników, grup i urządzeń.

Po przypisaniu profilu można monitorować sam profil i punkt odniesienia. Można na przykład sprawdzić, które urządzenia są zgodne — lub nie — z punktem odniesienia.

W tym artykule pokazano, jak za pomocą punktów odniesienia zabezpieczeń utworzyć profil, przypisać profil i monitorować profil.

Artykuł [Windows security baselines](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) (Punkty odniesienia zabezpieczeń systemu Windows) to doskonały zasób, z którego dowiesz się więcej na temat tej funkcji. Artykuł [Mobile device management](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) (Zarządzanie urządzeniami mobilnymi) to doskonały zasób zawierający informacje na temat funkcji MDM i czynności, które można wykonywać na urządzeniach z systemem Windows.

## <a name="prerequisites"></a>Wymagania wstępne
Aby móc zarządzać planami bazowymi w usłudze Intune, Twoje konto musi mieć wbudowaną rolę [Menedżer zasad i profilów](role-based-access-control.md#built-in-roles).


## <a name="co-managed-devices"></a>Urządzenia współzarządzane

Punkty odniesienia zabezpieczeń na urządzeniach zarządzanych przez usługę Intune są podobne do urządzeń współzarządzanych w programie Configuration Manager. Urządzenia współzarządzane używają programu System Center Configuration Manager i usługi Microsoft Intune do równoczesnego zarządzania urządzeniami z systemem Windows 10. Pozwala to na łączenie istniejących inwestycji związanych z programem Configuration Manager z korzyściami dotyczącymi usługi Intune w chmurze. Artykuł [Co-management overview](https://docs.microsoft.com/sccm/comanage/overview) (Omówienie współzarządzania) to doskonały zasób, jeśli używasz programu Configuration Manager i chcesz korzystać z zalet chmury.

W przypadku używania urządzeń współzarządzanych musisz przełączyć obciążenie **Konfiguracja urządzenia** (jego ustawienia) do usługi Intune. Dalsze informacje można znaleźć w części [Device configuration workloads](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) (Obciążenia konfiguracji urządzenia).

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com/) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Zabezpieczenia urządzenia** > **Linie bazowe zabezpieczeń (wersja zapoznawcza)**. Zostanie wyświetlona lista dostępnych punktów odniesienia. Po dodaniu kolejnych punktów odniesienia zobaczysz je tutaj:

    ![Wyświetlanie listy aktualnie dostępnych punktów odniesienia zabezpieczeń w usłudze Intune](./media/security-baselines/available-baselines.png)

3. Wybierz punkt odniesienia do użycia > **Utwórz profil**.
4. W obszarze **Podstawy** wprowadź następujące właściwości:

    - **Nazwa**: wprowadź nazwę profilu punktu odniesienia zabezpieczeń. Na przykład wprowadź `pilot Windows 10 MDM baseline - Oct 2018`.
    - **Opis**: wprowadź tekst opisujący zadania wykonywane przez dany punkt odniesienia. W polu opisu możesz wprowadzić dowolny wybrany tekst. Jest to opcjonalne, ale zdecydowanie zalecane.

5. Rozwiń pozycję **Ustawienia**. Na liście zobaczysz wszystkie ustawienia w obrębie danego punktu odniesienia zabezpieczeń oraz automatycznie wybieraną wartość ustawienia. Ustawienia i ich wartości są zalecane, a Ty możesz je zmienić.

    ![Rozwijanie ustawienia w celu wyświetlenia wszystkich ustawień w punkcie odniesienia zabezpieczeń w usłudze Intune](./media/security-baselines/sample-list-of-settings.png)

    Rozwiń niektóre ustawienia, aby sprawdzić ich wartości. Na przykład rozwiń pozycję **Windows Defender**. Przyjrzyj się niektórym ustawieniom i ich wartościom:

    ![Wyświetlanie automatycznie ustawianych wartości niektórych ustawień funkcji Windows Defender w usłudze Intune](./media/security-baselines/expand-windows-defender.png)

6. **Utwórz** profil. 
7. Wybierz pozycję **Profile**. Profil zostanie utworzony i wyświetlony na liście. Ale nie będzie jeszcze wykonywać żadnych czynności. Następnie przypisz profil.

## <a name="assign-the-profile"></a>Przypisywanie profilu

Po utworzeniu profil jest gotowy do przypisania do użytkowników, urządzeń i grup. Po przypisaniu profil i jego ustawienia są stosowane do wybranych użytkowników, urządzeń i grup.

1. W usłudze Intune wybierz pozycję **Punkty odniesienia zabezpieczeń** > wybierz punkt odniesienia > **Profil**.
2. Wybierz profil > **Przypisania**.

    ![Wybieranie profilu punktu odniesienia zabezpieczeń w usłudze Intune i klikanie pozycji Przypisania w celu wdrożenia profilu](./media/security-baselines/assignments.png)

3. Na karcie **Dołączanie** dodaj grupy, użytkowników lub urządzenia, których mają dotyczyć te zasady.

    > [!TIP]
    > Zauważ, że możesz również **wykluczać** grupy. Jeśli stosujesz zasady do **wszystkich użytkowników**, rozważ wykluczenie grup administratorów. Jeśli coś się stanie, Ty i Twoi administratorzy nie zostaniecie zablokowani.

4. **Zapisz** zmiany.

Po zapisaniu profil będzie wypychany do urządzeń w momencie ich zaewidencjonowania w usłudze Intune. Może więc zdarzyć się to natychmiast.

## <a name="available-security-baselines"></a>Dostępne punkty odniesienia zabezpieczeń  

Poniższe punkty odniesienia zabezpieczeń są dostępne do użycia z usługą Intune.
- **Wersja zapoznawcza: punkt odniesienia rozwiązania MDM**
  - Wersja: [Październik 2018](security-baseline-settings-windows.md)

## <a name="q--a"></a>Pytania i odpowiedzi

#### <a name="why-these-settings"></a>Dlaczego warto używać tych ustawień?

Zespół ds. zabezpieczeń firmy Microsoft w ciągu wielu lat zdobył doświadczenie w pracy bezpośrednio z deweloperami systemu Windows i społecznością zajmującą się zabezpieczeniami, co pomaga mu w tworzeniu tych rekomendacji. Ustawienia w tym punkcie odniesienia są uważane za najbardziej istotne opcje konfiguracji związane z zabezpieczeniami. W każdej nowej kompilacji systemu Windows zespół dostosowuje rekomendacje w oparciu o nowo wydane funkcje.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Czy istnieje różnica między rekomendacjami dotyczącymi punktów odniesienia zabezpieczeń systemu Windows dla zasad grupy i dla usługi Intune?

Ten sam zespół firmy Microsoft wybrał i zorganizował ustawienia dla każdego punktu odniesienia. Usługa Intune uwzględnia wszystkie odpowiednie ustawienia w punkcie odniesienia zabezpieczeń usługi Intune. W punkcie odniesienia zasad grupy istnieją pewne ustawienia specyficzne dla kontrolera domeny w środowisku lokalnym. Te ustawienia są wykluczane z rekomendacji w usłudze Intune. Wszystkie pozostałe ustawienia są takie same.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Czy punkty odniesienia zabezpieczeń usługi Intune są zgodne ze standardami organizacji CIS lub NIST?

Ściśle rzecz biorąc, nie. Zespól ds. zabezpieczeń firmy Microsoft konsultuje się z organizacjami, takimi jak CIS, podczas kompilowania rekomendacji. Ale nie istnieje mapowanie typu „jeden do jednego” między punktami odniesienia „zgodnymi z CIS” i przygotowanymi przez firmę Microsoft.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Jakie certyfikaty mają punkty odniesienia zabezpieczeń firmy Microsoft? 

- Firma Microsoft nadal publikuje punkty odniesienia zabezpieczeń dla zasad grupy (GPO) i zestawu narzędzi [Security Compliance Toolkit](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), tak jak robiła to przez wiele lat. Te punkty odniesienia są używane przez wiele organizacji. Rekomendacje przedstawione w tych punktach odniesienia są tworzone w trakcie współpracy zespołu ds. zabezpieczeń firmy Microsoft z klientami korporacyjnymi i agencjami zewnętrznymi, w tym z Departamentem Obrony (DoD, Department of Defense), Narodowym Instytutem Standaryzacji i Technologii (NIST, National Institute of Standards and Technology) i innymi. Udostępniamy nasze rekomendacje i punkty odniesienia tym organizacjom. Te organizacje mają również własne rekomendacje, które dokładnie odzwierciedlają rekomendacje firmy Microsoft. Ponieważ funkcja zarządzania urządzeniami przenośnymi (MDM) jest wciąż rozbudowywana w chmurze, firma Microsoft utworzyła równoważne rekomendacje oprogramowania MDM dla tych punktów odniesienia zasad grupy. Te dodatkowe punkty odniesienia są wbudowane w usłudze Microsoft Intune i oferują raporty dotyczące zgodności dla użytkowników, grup i urządzeń, które są zgodne (lub nie) z danym punktem odniesienia.

- Wielu klientów używa rekomendacji punktów odniesienia usługi Intune jako punktu startowego, a następnie dostosowuje go tak, aby spełniał wymagania dotyczące infrastruktury IT i zabezpieczeń. Pierwszy punkt odniesienia do wydania to **punkt odniesienia dotyczący oprogramowania MDM** w systemie Windows 10 RS5 firmy Microsoft. Ten punkt odniesienia został stworzony jako ogólna infrastruktura, która umożliwia klientom ostateczne importowanie innych punktów odniesienia w oparciu o standardy CIS, NIST i inne. Obecnie to rozwiązanie jest dostępne dla systemu Windows, a w przyszłości będzie również obejmować systemy iOS i Android.

- Migracja z lokalnych zasad grupy usługi Active Directory do rozwiązania działającego wyłącznie w chmurze przy użyciu usługi Azure Active Directory (AD) w usłudze Microsoft Intune to podróż. Aby ją ułatwić, można korzystać z towarzyszących obiektów zasad grupy dla hybrydowych urządzeń usługi AS i przyłączonych do usługi Azure AD. W razie potrzeby te urządzenia mogą uzyskać ustawienia zarządzania urządzeniami przenośnymi z chmury (usługi Intune), a ustawienia zasad grupy z kontrolerów domeny w środowisku lokalnym.

## <a name="next-steps"></a>Następne kroki
- Zapoznaj się z [ustawieniami punktu odniesienia systemu Windows](security-baseline-settings-windows.md) obsługiwanymi przez usługę Intune.  
- Sprawdź stan oraz monitoruj [punkt odniesienia i profil](security-baselines-monitor.md).
