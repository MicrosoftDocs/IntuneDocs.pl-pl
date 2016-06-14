---
# required metadata

title: Rejestrowanie urządzeń w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestrowanie urządzeń do zarządzania w usłudze Intune
Usługa zarządzania urządzeniami przenośnymi Microsoft Intune (MDM) używa rejestracji urządzeń, która umożliwia zarządzanie urządzeniami i zapewnia dostęp do zasobów. Sposób rejestrowania urządzeń zależy od rodzaju urządzenia, własności i wymaganego poziomu zarządzania. W scenariuszach opartych na strategii „przynieś własne urządzenie” (BYOD) i urządzeniach należących do firmy (COD) wymaga się procesu rejestracji urządzeń. Organizacje korzystające z programu Exchange ActiveSync (lokalnie lub w chmurze) mogą używać lżejszych metod zarządzania, w których nie wymaga się rejestracji urządzeń. Za pomocą oprogramowania klienckiego usługi Intune można również zarządzać komputerami z systemem Windows.

## Włączanie rejestracji urządzeń  
 Rejestracja umożliwia użytkownikom uzyskiwanie dostępu do zasobów firmowych na swoich urządzeniach osobistych. Dzięki niej administrator może upewnić się, że urządzenia są zgodne z zasadami chroniącymi zasoby firmowe. Jest to najlepszy sposób na skorzystanie ze strategii „przynieś własne urządzenie” z usługą Intune. Administrator musi włączyć rejestrację w konsoli usługi Intune. Może to wymagać utworzenia zaufanej relacji z urządzeniem i przypisania licencji do użytkowników. Następnie urządzenie jest rejestrowane, zazwyczaj przez użytkowników, którzy muszą wprowadzić poświadczenia służbowe. Urządzenie otrzymuje zasady z usługi Intune i uzyskuje dostęp do zasobów.

[Przygotowanie do rejestracji urządzeń w usłudze Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Rejestrowanie urządzeń należących do firmy
Urządzeniami należącymi do firmy (COD) można zarządzać za pomocą konsoli usługi Intune. Urządzenia z systemem iOS można zarejestrować bezpośrednio za pomocą narzędzi dostarczonych przez firmę Apple. Wszystkie typy urządzeń mogą być rejestrowane przez administratora lub menedżera za pomocą menedżera rejestracji urządzeń. Urządzenia z numerem IMEI można również zidentyfikować i oznaczyć jako należące do firmy, umożliwiając korzystanie ze scenariuszy COD.

[Rejestrowanie urządzeń należących do firmy](manage-corporate-owned-devices.md)

## Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune
Urządzeniami przenośnymi, które nie są zarejestrowane, ale są połączone z programem Exchange ActiveSync (EAS), można zarządzać za pomocą usługi Intune, korzystając z zasad EAS MDM. Usługa Intune używa łącznika Exchange Connector do komunikowania się z programem EAS (lokalnym lub hostowanym w chmurze).



[Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune  
Usługa Microsoft Intune umożliwia również zarządzanie komputerami z system Windows za pomocą komputerowego oprogramowania klienckiego usługi Intune dla systemu Windows. Komputery z systemem Windows zarządzane za pomocą klienta usługi Intune mogą:

 - Zgłaszać spisy sprzętu i oprogramowania.
 - Instalować aplikacje komputerowe (np. pliki .exe i .msi).
 - Ustawienia zapory

Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą być wybiórczo wyczyszczone lub wycofane. Ponadto nie mogą korzystać z wielu funkcji zarządzania usługi Intune, np. dostępu warunkowego, ustawień połączenia VPN i Wi-Fi lub wdrażania certyfikatów i konfiguracji poczty e-mail.

[Zarządzanie komputerami z systemem Windows przy użyciu usługi Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


