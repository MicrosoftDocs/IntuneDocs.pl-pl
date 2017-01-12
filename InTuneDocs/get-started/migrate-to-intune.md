---
title: "Migracja do usługi Intune | Microsoft Docs"
description: "Migracja do usługi Intune z istniejącego rozwiązania do zarządzania Enterprise Mobility może zostać wykonana zgodnie z poniższą ogólną sekwencją kroków."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d92b8b03c1c71898a15b1d1f0a1ee5e1f288dc2e
ms.openlocfilehash: 759e5b7d04ccbbfb338d182bad03e0b0218cdeca


---

# <a name="migrate-to-intune"></a>Migracja do usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Migracja do usługi Intune z istniejącego rozwiązania do zarządzania Enterprise Mobility może być wykonana zgodnie z poniższą ogólną sekwencją kroków:

![Kroki migracji do usługi Intune](./media/migrate-intune-steps.png)

## <a name="notify-users"></a>Powiadomienie użytkowników

Jeśli wdrożenie pilotażowe usługi Intune spełniło Twoje oczekiwania, przekaż swoim użytkownikom informacje o nadchodzącej migracji ich urządzeń do usługi Intune. Wiadomości e-mail, instrukcje i [plakaty](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) mogą pomóc w ustaleniu oczekiwań i przekazaniu informacji o rejestracji dotyczących kroków, które będą musieli wykonać użytkownicy, aby zachować nieprzerwaną łączność z zasobami i aplikacjami firmy. Upewnij się, że zespół wsparcia technicznego jest gotowy do świadczenia użytkownikom pomocy w procesie migracji.

## <a name="modify-your-existing-enterprise-mobility-management-solution"></a>Zmodyfikowanie istniejącego rozwiązania do zarządzania Enterprise Mobility

W zależności od Twoich planów dotyczących obsługi zasad dostępu warunkowego między istniejącym rozwiązaniem do zarządzania Enterprise Mobility i usługą Intune możliwe, że będzie konieczne wyłączenie istniejących zasad dostępu warunkowego. Należy wyłączyć istniejące zasady dostępu warunkowego LUB zmienić zakres istniejących zasad dostępu warunkowego, aby nie uwzględniały użytkowników/urządzeń, które będą migrowane do usługi Intune.  Należy unikać sytuacji, w której usługa Intune i istniejące rozwiązanie do zarządzania Enterprise Mobility stosują zasady dostępu warunkowego wobec tych samych użytkowników/urządzeń.

## <a name="enable-intune-conditional-access-policy-optional"></a>Włączenie zasad dostępu warunkowego usługi Intune (opcjonalnie)

Jeśli zdecydujesz o natychmiastowym wymuszeniu zasad dostępu warunkowego bez okresu prolongaty dla migrowanych urządzeń, włącz w tym kroku zasady dostępu warunkowego w usłudze Intune.  Upewnij się, że informacje o decyzji zostały wyraźnie przekazane użytkownikom i zespołowi pomocy technicznej.  Jeśli urządzenia nie są zarejestrowane w usłudze Intune i nie są zgodne z zasadami usługi Intune, użytkownicy nie będą mogli uzyskiwać dostępu do zasobów firmowych do czasu zarejestrowania się w usłudze Intune i osiągnięcia zgodności ich urządzeń z zasadami usługi Intune.

## <a name="unenrolling-devices-from-your-existing-enterprise-mobility-management-solution"></a>Wyrejestrowanie urządzeń z istniejącego rozwiązania do zarządzania Enterprise Mobility

Urządzenia muszą zostać wyrejestrowane z istniejącego rozwiązania do zarządzania Enterprise Mobility przed ich rejestracją w usłudze Intune. Zalecamy, aby użytkownicy mogli wyrejestrowywać urządzenia własnoręcznie. Da to użytkownikom największą wygodę w tym zakresie.  Należy postępować zgodnie ze wskazówkami dotyczącymi wyrejestrowywania od dostawcy rozwiązania, aby zapewnić prawidłowe usuwanie użytkowników i urządzeń z platformy i zminimalizować zakłócenia po stronie użytkowników końcowych.

## <a name="enrolling-devices-in-intune"></a>Rejestrowanie urządzeń w usłudze Intune

Użytkownicy zaplanowani do migracji powinni natychmiast rejestrować się w usłudze Intune, aby odzyskać dostęp lub zapobiec utracie dostępu do firmowych zasobów, poczty e-mail i aplikacji. Jeśli skonfigurowano dostęp warunkowy, a użytkownicy spróbują połączyć się z pocztą e-mail przed zarejestrowaniem w usłudze Intune, ich dostęp zostanie zablokowany, po czym otrzymają wiadomość e-mail dotyczącą rejestracji. Ta wiadomość e-mail przeprowadzi użytkowników przez proces rejestracji urządzenia w usłudze Intune.  Alternatywnie użytkownicy mogą rejestrować się w usłudze Intune za pomocą aplikacji Portal firmy usługi Intune lub natywnie przez system operacyjny Windows 8.1 i Windows 10 Mobile. Zapoznaj się z tematem [Co mówić użytkownikom końcowym na temat korzystania z usługi Microsoft Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune), aby uzyskać dodatkowe porady dotyczące kroków związanych z rejestracją dla każdej platformy.

## <a name="configure-intune-conditional-access-optional"></a>Konfigurowanie dostępu warunkowego usługi Intune (opcjonalnie)

Jeżeli zezwolono na okres prolongaty dla wymuszenia dostępu warunkowego, włącz zasady dostępu warunkowego w usłudze Intune, aby rozpocząć wymuszanie po zakończeniu okresu prolongaty, o którym poinformowano użytkowników. Wymaga to natychmiastowego spełnienia wymagań zasad dostępu warunkowego usługi Intune przez wszystkie urządzenia.

## <a name="enroll-remaining-devices-and-users"></a>Rejestrowanie pozostałych urządzeń i użytkowników

Teraz, po włączeniu dostępu warunkowego, wszyscy użytkownicy muszą zarejestrować się w usłudze Intune i spełnić wymagania zasad zgodności organizacji, aby uzyskać dostęp do zasobów firmowych. Jeśli migracja użytkowników oparta była na rejestracji etapowej (nie dotyczyła wszystkich użytkowników jednocześnie), powtarzaj powyższe kroki, aż wszystkie urządzenia i wszyscy użytkownicy będą zarejestrowani i zarządzani w usłudze Intune.

## <a name="retire-the-previous-enterprise-mobility-management-solution"></a>Wycofanie poprzedniego rozwiązania do zarządzania Enterprise Mobility

Po migracji wszystkich użytkowników i urządzeń do usługi Intune oraz upewnieniu się, że migracja do usługi Intune przebiegła pomyślnie, można wycofać poprzednie rozwiązanie do zarządzania Enterprise Mobility i/lub anulować subskrypcję usługi. Należy postępować zgodnie ze wskazówkami dostawcy rozwiązania, aby zapewnić prawidłowe usunięcie wszystkich zbędnych wymagań dotyczących infrastruktury i anulowanie wszelkich subskrypcji/licencji.

## <a name="additional-migration-resources"></a>Dodatkowe zasoby związane z migracją

Potrzebujesz dodatkowej pomocy związanej z migracją do usługi Intune? Firma Microsoft zapewnia specjalistyczną pomoc, aby upewnić się, że proces migracji będzie przebiegać bezproblemowo:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Usługi konsultingowe firmy Microsoft](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Pomoc techniczna i nietechniczna dotycząca usługi Intune](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Forum TechNet dotyczące usługi Microsoft Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## <a name="get-a-downloadable-copy-of-this-guide"></a>Uzyskaj kopię do pobrania tego przewodnika

W celu uzyskania kopii całego przewodnika do pobrania odwiedź witrynę [Galeria TechNet](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).



<!--HONumber=Dec16_HO3-->


