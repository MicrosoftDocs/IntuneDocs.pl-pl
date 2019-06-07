---
title: Używanie punktów odniesienia zabezpieczeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj zalecane ustawienia zabezpieczeń grup w celu ochrony użytkowników i danych na urządzeniach przy użyciu usługi Microsoft Intune w ramach zarządzania urządzeniami przenośnymi. Włącz funkcję BitLocker, skonfiguruj Zaawansowaną ochronę przed zagrożeniami w usłudze Microsoft Defender, kontroluj program Internet Explorer, używaj filtru SmartScreen, ustawiaj lokalne zasady zabezpieczeń, wymagaj hasła, blokuj materiały do pobrania z Internetu i nie tylko.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e4d5c23d598641256c196cd7217797f87f99d1c
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374135"
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

Treść tego artykułu pomoże Ci używać punktów odniesienia zabezpieczeń w celu utworzenia, przypisania i monitorowania profilu.

Artykuł [Windows security baselines](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) (Punkty odniesienia zabezpieczeń systemu Windows) to doskonały zasób, z którego dowiesz się więcej na temat tej funkcji. Artykuł [Mobile device management](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) (Zarządzanie urządzeniami mobilnymi) to doskonały zasób zawierający informacje na temat funkcji MDM i czynności, które można wykonywać na urządzeniach z systemem Windows.

## <a name="available-security-baselines"></a>Dostępne punkty odniesienia zabezpieczeń  

Poniższe punkty odniesienia zabezpieczeń są dostępne do użycia z usługą Intune.
- **Wersja zapoznawcza: punkt odniesienia rozwiązania MDM z października 2018 r.**  
  [Wyświetl ustawienia](security-baseline-settings-windows.md)

- **WERSJA ZAPOZNAWCZA: punkt odniesienia usługi Windows Defender ATP**  
  [Wyświetl ustawienia](security-baseline-settings-defender-atp.md)  
  *(Ten punkt odniesienia jest dostępny, jeśli środowisko spełnia wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](advanced-threat-protection.md#prerequisites))*.


## <a name="prerequisites"></a>Wymagania wstępne
Aby móc zarządzać planami bazowymi w usłudze Intune, Twoje konto musi mieć wbudowaną rolę [Menedżer zasad i profilów](role-based-access-control.md#built-in-roles).


## <a name="co-managed-devices"></a>Urządzenia współzarządzane

Punkty odniesienia zabezpieczeń na urządzeniach zarządzanych przez usługę Intune są podobne do urządzeń współzarządzanych w programie Configuration Manager. Urządzenia współzarządzane używają programu System Center Configuration Manager i usługi Microsoft Intune do równoczesnego zarządzania urządzeniami z systemem Windows 10. Pozwala to na łączenie istniejących inwestycji związanych z programem Configuration Manager z korzyściami dotyczącymi usługi Intune w chmurze. Artykuł [Co-management overview](https://docs.microsoft.com/sccm/comanage/overview) (Omówienie współzarządzania) to doskonały zasób, jeśli używasz programu Configuration Manager i chcesz korzystać z zalet chmury.

W przypadku używania urządzeń współzarządzanych musisz przełączyć obciążenie **Konfiguracja urządzenia** (jego ustawienia) do usługi Intune. Dalsze informacje można znaleźć w części [Device configuration workloads](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) (Obciążenia konfiguracji urządzenia).

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=20909), a następnie wybierz pozycje **Bezpieczeństwo urządzeń** > **Punkty odniesienia zabezpieczeń (wersja zapoznawcza)**. Zostanie wyświetlona lista dostępnych punktów odniesienia. 

    ![Wybór puntu odniesienia zabezpieczeń do skonfigurowania](./media/security-baselines/available-baselines.png)

   >[!TIP]  
   > Punkt odniesienia usługi Windows Defender ATP jest dostępny, jeśli środowisko spełnia wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender](advanced-threat-protection.md#prerequisites).
2. Wybierz punkt odniesienia, którego chcesz użyć, a następnie wybierz opcję **Utwórz profil**.  

3. Na karcie **Podstawowe** określ następujące właściwości:

    - **Nazwa**: wprowadź nazwę profilu punktu odniesienia zabezpieczeń. Na przykład *Profil standardowy dla usługi Defender ATP*.
    - **Opis**: wprowadź tekst opisujący zadania wykonywane przez dany punkt odniesienia. W polu opisu możesz wprowadzić dowolny wybrany tekst. Jest to opcjonalne, ale zdecydowanie zalecane.

4. Wybierz kartę **Konfiguracja**, aby wyświetlić dostępne grupy **ustawień** w tym punkcie odniesienia. Wybierz grupę, aby ją rozwinąć i wyświetlić poszczególne ustawienia, które zawiera. Ustawienia mają domyślne konfiguracje dla punktu odniesienia zabezpieczeń. Zmień ustawienia domyślne stosownie do swoich potrzeb biznesowych.  

    ![Rozwijanie grupy w celu wyświetlenia ustawień dla tej grupy](./media/security-baselines/sample-list-of-settings.png)

5. Wybierz kartę **Przypisania**, aby przypisać punkt odniesienia do grup. Aby ukończyć konfigurację, przypisz punkt odniesienia do istniejącej grupy lub utwórz nową grupę za pomocą standardowego procesu w konsoli usługi Intune.  

   ![Przypisywanie profilu](./media/security-baselines/assignments.png)
  
6. Gdy wszystko będzie gotowe do wdrożenia punktu odniesienia, wybierz kartę **Przeglądanie + tworzenie**, aby przejrzeć szczegóły punktu odniesienia. Następnie wybierz opcję **Zapisz profil**, aby zapisać i wdrożyć profil. 

   ![Przegląd punktu odniesienia](./media/security-baselines/review.png) 

   Po zapisaniu profil będzie wypychany do urządzeń w momencie ich zaewidencjonowania w usłudze Intune. Może więc zdarzyć się to natychmiast.

   > [!TIP]  
   > Można zapisać profil bez wcześniejszego przypisania go do grup. Profil można edytować później, aby dodać grupy. 

7. Po utworzeniu profilu można go edytować. W tym celu przejdź do opcji **Bezpieczeństwo urządzeń** > **Punkty odniesienia zabezpieczeń**, wybierz skonfigurowany punkt odniesienia, a następnie wybierz opcję **Profile**.  Wybierz profil, wybierz pozycję **Właściwości**, aby edytować ustawienia, a następnie wybierz pozycję **Przypisania**, aby edytować grupy, które otrzymują ten punkt odniesienia. 

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
