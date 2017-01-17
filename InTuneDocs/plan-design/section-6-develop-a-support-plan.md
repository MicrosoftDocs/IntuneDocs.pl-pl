---
title: "Opracowywanie planu pomocy technicznej usługi Intune | Microsoft Docs"
description: "W tym artykule zawarto wskazówki ułatwiające opracowanie planu pomocy technicznej usługi Intune dotyczącego projektowania i wdrażania usługi Microsoft Intune opartego tylko na chmurze."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b9428769-4333-4778-b677-f23dea1f74da
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 874146573898e8a28de83ed599dbd4829ea8f335
ms.openlocfilehash: fb72b74d922cef8659c34ef9d3d36e14b1a22ac1


---

# <a name="develop-an-intune-support-plan"></a>Opracowywanie planu pomocy technicznej usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Opracowanie planu pomocy technicznej usługi Intune może być korzystne dzięki efektywniejszemu identyfikowaniu problemów związanych z usługą Intune i ich rozwiązywaniu oraz poprawieniu ogólnego sposobu obsługi środowiska Intune przez użytkownika końcowego. Poniżej zamieszczono kilka pytań, które należy wziąć pod uwagę podczas opracowywania planu pomocy technicznej usługi Intune:

-   Które zespoły będą odpowiedzialne za świadczenie pomocy technicznej usługi Intune?

-   Jeśli obsługująca organizacja ma wiele warstw (np. warstwa 1–3), jaką odpowiedzialność w zakresie pomocy technicznej usługi Intune mają poszczególne warstwy?

-   Jaki proces będzie wykorzystywany na potrzeby świadczenia pomocy technicznej usługi Intune?

-   W jaki sposób planuje się przeprowadzanie szkoleń dotyczących pomocy technicznej usługi Intune?

-   Jakie są możliwości wczesnego zaangażowania zespołu pomocy technicznej w proces wdrażania usługi Intune?

Opiszmy dokładniej każdy z tych obszarów.

## <a name="which-teams-are-responsible-for-providing-support"></a>Które zespoły są odpowiedzialne za świadczenie pomocy technicznej?

Organizacje mogą mieć różne warstwy/poziomy (1–3) pomocy technicznej. Na przykład warstwy 1 i 2 mogą być częścią zespołu pomocy technicznej, a warstwa 3 obejmuje członków zespołu zarządzania urządzeniami przenośnymi odpowiedzialnego za wdrożenie usługi Intune.

## <a name="what-is-the-support-process"></a>Co to jest proces pomocy technicznej?

Warstwa 1 jest zwykle pierwszym poziomem pomocy technicznej i zazwyczaj pierwszą warstwą, z którą kontaktuje się użytkownik żądający obsługi. Jeśli warstwa 1 nie jest w stanie rozwiązać problemu użytkownika końcowego, zostaje on przekazany do warstwy 2, która z kolei przekaże go do warstwy 3, jeśli zajdzie taka konieczność. Ponadto pomoc techniczna firmy Microsoft może być uważana za warstwę 4.

-   Dowiedz się więcej o [pomocy technicznej usługi Intune](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

W przypadku początkowych faz wdrożenia produkcyjnego w organizacjach do obsługi rozmów pomostowych lub rozmów przez Skype'a mogą być wykorzystywane wszystkie trzy warstwy. Poniżej przedstawiono przykładowy sposób implementacji przepływu pracy wsparcia informatycznego/pomocy technicznej w organizacji:

1.  Użytkownik końcowy kontaktuje się z warstwą 1 wsparcia informatycznego/pomocy technicznej w sprawie problemu dotyczącego rejestracji.

2.  Warstwa 1 wsparcia informatycznego/pomocy technicznej nie potrafi określić głównej przyczyny i przekazuje problem do warstwy 2.

3.  Warstwa 2 wsparcia informatycznego/pomocy technicznej bada problem, ale nie może go rozwiązać i przekazuje go do warstwy 3 razem z dodatkowymi informacjami uzyskanymi podczas badania.

4.  Warstwa 3 wsparcia informatycznego/pomocy technicznej prowadzi dalsze badania, określa główną przyczynę i przekazuje rozwiązanie do warstw 2 i 1.

5.  Warstwa 1 wsparcia informatycznego/pomocy technicznej kontaktuje się następnie z klientem i rozwiązuje jego problem.

Takie podejście (szczególnie we wczesnych etapach wdrażania usługi Intune) przynosi wiele korzyści, na przykład:

-   Wspomaganie podczas poznawania technologii i zwiększania obciążenia.

-   Szybkie identyfikowanie problemów i ich rozwiązywanie.

-   Ulepszanie ogólnego środowiska użytkownika.

## <a name="how-you-plan-to-provide-intune-support-training"></a>W jaki sposób planuje się przeprowadzanie szkoleń dotyczących pomocy technicznej usługi Intune?

Ważną rzeczą jest zapewnienie szkolenia technicznego dotyczącego usługi Intune przeznaczonego dla pracowników wsparcia informatycznego/pomocy technicznej, które zostanie przeprowadzone na odpowiednim poziomie oraz będzie miało zastosowanie do konkretnej warstwy pomocy technicznej i obowiązków. W organizacjach takim szkoleniem przeprowadzonym przez zespół zarządzania urządzeniami przenośnymi w usłudze Intune mogą być objęci kierownicy zespołów pomocy technicznej (szkolenie trenera), a następnie ci kierownicy mogą przeszkolić członków swoich zespołów pomocy technicznej. Takie szkolenie trwa zwykle 2–3 godziny i obejmuje wykłady i ćwiczenia laboratoryjne.

Poniżej zamieszczono przykładowy plan szkolenia pracowników pomocy technicznej usługi Intune.

-   Przegląd planu pomocy technicznej usługi Intune

-   Omówienie usługi Intune

-   Rozwiązywanie typowych problemów

-   Narzędzia i zasoby

-   Pytania i odpowiedzi

>[!TIP]
> W sekcji [Additional resources](additional-resources.md) (Dodatkowe zasoby) udostępniono techniczne zasoby, które mogą się okazać przydatne dla zespołu pomocy technicznej podczas zwiększania obciążenia usługi Microsoft Intune.

## <a name="what-opportunities-are-there-to-involve-the-support-team-earlier"></a>Jakie możliwości daje wczesne zaangażowanie zespołu pomocy technicznej?

Zaangażowanie pracowników wsparcia informatycznego/pomocy technicznej na wczesnych etapach planowania i pilotowania wdrażania usługi Intune może być bardzo korzystne dla organizacji. Dzięki temu pracownicy pomocy technicznej mają możliwość zapoznania się z rozwiązaniem i zdobycia cennego doświadczenia. Ułatwia to również przygotowanie pracowników wsparcia informatycznego/pomocy technicznej do obsługi pełnego wdrożenia produkcyjnego organizacji.

## <a name="next-section"></a>Następna sekcja

W następnej sekcji znajdują się wskazówki dotyczące [projektowania usługi Intune](section-7-create-an-intune-design.md).



<!--HONumber=Jan17_HO3-->


