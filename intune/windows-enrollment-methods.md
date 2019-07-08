---
title: Metody rejestracji w usłudze Intune dla urządzeń z systemem Windows
titleSuffix: Microsoft Intune
description: Informacje dotyczące różnych sposobów rejestrowania urządzeń z systemem Windows w usłudze Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: b8b1c47e4a2eb46bb8f7190ede351ed77a1bfef4
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494495"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Metody rejestracji w usłudze Intune dla urządzeń z systemem Windows

Aby zarządzać urządzeniami w usłudze Intune, muszą one najpierw zostać zarejestrowane w tej usłudze. Rejestrowanie w celu zarządzania w usłudze Intune jest możliwe zarówno dla urządzeń prywatnych, jak i firmowych. 

Istnieją dwa sposoby rejestrowania urządzeń w usłudze Intune:
- Użytkownicy mogą samodzielnie rejestrować swoje komputery z systemem Windows 
- Administratorzy mogą konfigurować zasady, aby wymusić automatyczne rejestrowanie bez żadnego udziału użytkownika

## <a name="user-self-enrollment-in-intune"></a>Samodzielna rejestracja użytkownika w usłudze Intune

Użytkownicy mogą samodzielnie rejestrować swoje urządzenia z systemem Windows za pomocą jednej z następujących metod:

- [„Przynieś własne urządzenie” (BYOD, bring your own device)](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device): Użytkownicy rejestrują swoje prywatne urządzenia, wybierając połączenie konta **służbowego** z obszaru **Ustawienia** urządzenia. Podczas tego procesu ma miejsce:
    - Rejestrowanie urządzenia w usłudze Azure Active Directory w celu uzyskania dostępu do zasobów firmy, takich jak poczta e-mail.
    - Rejestrowanie urządzenia w usłudze Intune jako urządzenie BYOD.
Jeśli administrator skonfigurował automatyczne rejestrowanie (dostępne w przypadku subskrypcji Premium usługi Azure AD), użytkownik musi tylko raz wprowadzić swoje poświadczenia. W przeciwnym razie konieczne będzie wykonanie osobnej rejestracji tylko dla funkcji MDM i ponowne wprowadzenie poświadczeń.  
- **Rejestracja tylko dla funkcji MDM** umożliwia użytkownikom rejestrowanie w usłudze Intune istniejącej grupy roboczej, usługi Active Directory lub komputera przyłączonego do usługi Azure Active Directory. Użytkownicy rejestrują się z poziomu ustawień na istniejącym komputerze z systemem Windows. Ta metoda nie jest zalecana, ponieważ nie powoduje zarejestrowania urządzenia w usłudze Azure Active Directory. Uniemożliwia ona również korzystanie z takich funkcji jak dostęp warunkowy.
- [Przyłączanie do usługi Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) — przyłącza urządzenie do usługi Azure Active Directory i umożliwia użytkownikom logowanie się do systemu Windows przy użyciu poświadczeń usługi Azure AD. Jeśli włączono rejestrację automatyczną, urządzenie jest automatycznie rejestrowane w usłudze Intune. Zaletą rejestracji automatycznej jest proces wymagający wykonania tylko jednego kroku przez użytkownika. W przeciwnym razie konieczne będzie wykonanie osobnej rejestracji tylko dla funkcji MDM i ponowne wprowadzenie poświadczeń. Użytkownicy rejestrują się w ten sposób z poziomu ustawień lub podczas początkowego procesu OOBE w systemie Windows. Urządzenie jest oznaczone jako firmowe w usłudze Intune.
- [Rozwiązanie Autopilot](enrollment-autopilot.md) — automatyzuje dołączanie do usługi Azure AD i rejestruje nowe urządzenia firmowe w usłudze Intune. Ta metoda upraszcza proces OOBE (Out-of-Box Experience) i eliminuje konieczność stosowania niestandardowych obrazów systemów operacyjnych na urządzeniach. Jeśli do zarządzania urządzeniami z rozwiązaniem Autopilot administratorzy używają usługi Intune, mogą zarządzać zasadami, profilami, aplikacjami i nie tylko po ich zarejestrowaniu.  Istnieją cztery typy wdrażania w rozwiązaniu Autopilot: [Tryb samodzielnego wdrażania](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (w przypadku kiosków, znakowania cyfrowego lub udostępnionego urządzenia) i [tryb sterowany przez użytkownika](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (dla tradycyjnych użytkowników), [White Glove] (https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) umożliwia partnerom lub personelowi działu IT wstępną aprowizację komputera z systemem Windows 10, aby był w pełni skonfigurowany i gotowy do użytku w firmie oraz [rozwiązanie Autopilot dla istniejących urządzeń] (https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) umożliwia łatwe wdrażanie najnowszej wersji systemu Windows 10 na istniejących urządzeniach.

## <a name="administrator-based-enrollment-in-intune"></a>Rejestracja w usłudze Intune wykonywana przez administratorów

Administratorzy mogą skonfigurować następujące metody rejestracji, które nie wymagają interakcji z użytkownikiem:

- [Dołączenie do hybrydowej usługi Azure AD](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) umożliwia administratorom konfigurowanie zasad grupy usługi Active Directory w celu automatycznego rejestrowania urządzeń dołączonych do hybrydowej usługi Azure AD. 
- [Współzarządzanie w programie Configuration Manager](https://docs.microsoft.com/sccm/comanage/overview) umożliwia administratorom rejestrowanie istniejących urządzeń zarządzanych przez program Configuration Manager w usłudze Intune w celu uzyskanie korzyści zarówno z usługi Intune, jak i programu Configuration Manager. 
- [Menedżer rejestracji urządzeń](device-enrollment-manager-enroll.md) (DEM, Device Enrollment Manager) to specjalne konto usługi. Konta DEM mają uprawnienia, które umożliwiają autoryzowanym użytkownikom rejestrowanie wielu urządzeń firmowych i zarządzanie nimi. Tego rodzaju urządzenia nadają się do wykorzystania w punktach sprzedaży lub na potrzeby użycia aplikacji narzędziowych, ale są złym rozwiązaniem dla użytkowników, którzy potrzebują dostępu do poczty e-mail lub zasobów firmowych. Ta metoda nie zezwala na używanie funkcji, takich jak dostęp warunkowy. 
- [Rejestrowanie zbiorcze](windows-bulk-enroll.md) umożliwia autoryzowanemu użytkownikowi dołączenie dużej liczby nowych urządzeń firmowych do usług Azure Active Directory i Intune. Pakiet aprowizacyjny jest tworzony przy użyciu aplikacji Windows Configuration Designer (WCD). Następnie przy użyciu nośnika USB podczas początkowego procesu OOBE w systemie Windows lub z poziomu istniejącego komputera z systemu Windows instalowany jest pakiet aprowizacyjny służący do automatycznego rejestrowania urządzeń w usłudze Intune. Ta metoda nie zezwala na używanie dostępu warunkowego. 
- [Rejestrowanie urządzeń z systemem Windows IoT Core](https://docs.microsoft.com/windows/iot-core/manage-your-device/intunedeviceenrollment) odbywa się przez przygotowanie urządzenia za pomocą pulpitu nawigacyjnego systemu Windows IoT Core, a następnie utworzenie pakietu aprowizacyjnego przy użyciu rozwiązania Windows Configuration Designer. Następnie — za pomocą plików multimedialnych na karcie SD podczas początkowego rozruchu — pakiet aprowizacyjny jest instalowany w celu automatycznego rejestrowania urządzeń w usłudze Intune.

## <a name="next-steps"></a>Następne kroki

[Dowiedz się więcej o możliwościach metod rejestracji systemu Windows](enrollment-method-capab.md)
