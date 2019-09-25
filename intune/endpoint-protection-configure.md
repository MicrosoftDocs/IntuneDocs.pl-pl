---
title: Konfigurowanie ustawień programu Endpoint Protection w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz ustawienia programu Endpoint Protection podczas tworzenia profilu urządzenia z systemem macOS lub Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: 8248991e1facc78def580d75a5b7e7e6ba353c98
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163682"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Dodawanie ustawień programu Endpoint Protection w usłudze Intune  

W usłudze Intune można używać profilów konfiguracji urządzeń do zarządzania typowymi funkcjami zabezpieczeń programu Endpoint Protection na urządzeniach, takimi jak:  
- Zapora   
- Funkcja BitLocker  
- Zezwalanie na aplikacje i ich blokowanie  
- Usługa Windows Defender i szyfrowanie  

Na przykład możesz utworzyć profil programu Endpoint Protection, który umożliwia użytkownikom systemu macOS instalowanie aplikacji wyłącznie ze sklepu Mac App Store. Możesz też włączyć funkcję Windows SmartScreen w przypadku uruchamiania aplikacji na urządzeniach z systemem Windows 10.  

Przed utworzeniem profilu zapoznaj się z następującymi artykułami ze szczegółami ustawień programu Endpoint Protection, którymi usługa Intune może zarządzać dla każdej z obsługiwanych platform:  
   - [macOS settings](endpoint-protection-macos.md) (Ustawienia systemu macOS)  
   - [Windows 10 settings](endpoint-protection-windows-10.md) (Ustawienia systemu Windows 10)  

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia programu Endpoint Protection  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.  
4. Wprowadź **Nazwę** i **Opis** dla profilu programu Endpoint Protection.  
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia niestandardowe. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:  
   - **macOS**  
   - **Windows 10 lub nowszy**  
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Endpoint Protection**.  
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Zobacz:  
   - [macOS settings](endpoint-protection-macos.md) (Ustawienia systemu macOS)  
   - [Windows 10 settings](endpoint-protection-windows-10.md) (Ustawienia systemu Windows 10)  

8. Po skonfigurowaniu odpowiednich ustawień wybierz pozycję **Utwórz** na stronie **Tworzenie profilu**.  

   Profil zostanie utworzony i wyświetlony na stronie listy profilów. Aby przypisać ten profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).  

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Dodawanie niestandardowych reguł zapory dla urządzeń z systemem Windows 10  

Podczas konfigurowania zapory Windows Defender w ramach profilu zawierającego reguły ochrony punktu końcowego dla systemu Windows 10 można skonfigurować niestandardowe reguły dla zapór. Reguły niestandardowe umożliwiają rozszerzenie wstępnie zdefiniowanego zestawu reguł zapory obsługiwanego w systemie Windows 10.  

Planując profile z niestandardowymi regułami zapory, należy wziąć pod uwagę następujące informacje, które mogą mieć wpływ na sposób grupowania reguł zapory w profilach:  
- Każdy profil obsługuje do 150 reguł zapory. Jeśli masz więcej niż 150 reguł, utwórz dodatkowe profile, z których każdy może obejmować 150 reguł.  
- W przypadku każdego profilu obowiązuje zasada, że jeśli chociaż jedna reguła nie zostanie zastosowana, wszystkie reguły w profilu zakończą się niepowodzeniem i żadna z nich nie zostanie zastosowana na urządzeniu.  
- Jeśli zastosowanie reguły zakończy się niepowodzeniem, stan niepowodzenia jest zgłaszany dla wszystkich reguł w profilu. Usługa Intune nie może określić, która konkretna reguła zakończyła się niepowodzeniem.  

Reguły zapory, które mogą być zarządzane przez usługę Intune, są szczegółowo opisane w artykule dotyczącym [dostawcy usług konfiguracji zapory]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) (CSP) systemu Windows. Aby zapoznać się z listą obsługiwanych przez usługę Intune niestandardowych ustawień zapory dla urządzeń z systemem Windows 10, zobacz [Niestandardowe reguły zapory](endpoint-protection-windows-10.md#firewall-rules).  

### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Aby dodać niestandardowe reguły zapory do profilu ochrony punktu końcowego  

1. W usłudze Intune przejdź do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.  

2. W polu *Platforma* wybierz pozycję **Windows 10 i nowsze**, a następnie w obszarze *Typ profilu* wybierz pozycję **Ochrona punktu końcowego**.  

3. Wybierz pozycję **Zapora Windows Defender**, aby otworzyć stronę konfiguracji, a następnie w obszarze *Reguły zapory* wybierz pozycję **Dodaj**, aby otworzyć stronę **Utwórz regułę**.  

4. Określ ustawienia reguły zapory, a następnie wybierz przycisk **OK**, aby je zapisać. Aby zapoznać się z dostępnymi opcjami niestandardowych reguł zapory w dokumentacji, zobacz [Niestandardowe reguły zapory](endpoint-protection-windows-10.md#firewall-rules).  

5. Po zapisaniu reguły zostanie ona wyświetlona na stronie *Zapora Windows Defender* na liście reguł.  

6. Aby zmodyfikować regułę, wybierz ją z listy, co spowoduje otwarcie strony **Edytuj regułę**.  

7. Aby usunąć regułę z profilu, wybierz wielokropek **(...)** obok reguły, a następnie wybierz polecenie **Usuń**.  

8. Aby zmienić kolejność wyświetlania reguł, wybierz ikonę *strzałki w górę i strzałki w dół* w górnej części listy reguł.  


## <a name="next-steps"></a>Następne kroki  

Aby przypisać profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).  
