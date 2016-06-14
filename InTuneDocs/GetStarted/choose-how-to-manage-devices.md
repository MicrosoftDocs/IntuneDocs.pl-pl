---
# required metadata

title: Wybieranie metody zarządzania urządzeniami w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wybieranie metody zarządzania urządzeniami
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] umożliwia zarządzanie różnymi urządzeniami przez *zarejestrowanie* ich w usłudze. Użytkownicy mogą następnie korzystać z *portalu firmy*, aby wykonywać szereg operacji, takich jak rejestrowanie swoich urządzeń, przeglądanie i instalowanie aplikacji, upewnianie się, że urządzenie jest zgodne z zasadami firmy i kontaktowanie się z pomocą techniczną IT.

## Metody zarządzania urządzeniami przenośnymi
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] umożliwia zarządzanie następującymi platformami urządzeń:

- System Apple iOS 7.1 i nowsze
- System Google Android 4.0 lub nowszy (w tym Samsung KNOX)
- System Windows Phone 8,0 lub nowszy
- Urządzenia z systemami Windows RT i Windows 8.1 RT
- Komputery z systemem Windows 8.1 lub nowszym
- System Mac OS X 10.9 lub nowszy

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Porada</h5>
  <p>Jeśli urządzenia z wersją systemu iOS starszą niż podana powyżej obsługiwana wersja zostały już zarejestrowane wcześniej, pozostaną one zarejestrowane. Jednak sprawdź w dokumentacji poszczególnych wersji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], czy dana wersja systemu iOS jest obsługiwana przez daną funkcję.</p>
</div>

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] umożliwia zarządzanie urządzeniami użytkowników. Ta strategia jest ogólnie znana jako „przynieś własne urządzenie” (BYOD, Bring Your Own Device). Pozwala ona również na zarządzanie urządzeniami należącymi do firmy, w tym scenariuszami, w których firmy przedstawiają użytkownikom listę urządzeń do wyboru. Ta strategia jest znana jako „Wybierz własne urządzenie” (CYOD, Choose Your Own Device).

### Rejestrowanie urządzeń do zarządzania
W przypadku systemów operacyjnych dla urządzeń przenośnych, takich jak iOS, Android i Windows Phone, zawsze musisz zarejestrować urządzenia. Jednak sposób rejestrowania urządzeń zależy od potrzeb organizacji:

|Typ rejestracji|„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)|„Wybierz własne urządzenie” (CYOD, Choose Your Own Device)|Urządzenie udostępnione z kontem menedżera|Urządzenie udostępnione bez konta użytkownika|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Opis**|Osobiste urządzenie zarejestrowane przy użyciu usługi Microsoft Intune|Urządzenie dla jednego użytkownika należące do firmy|Urządzenie należące do firmy, które jest zarządzane przy użyciu konta menedżera udostępnionego dla wielu użytkowników|Urządzenie bez użytkownika należące do firmy, z którego korzysta wielu użytkowników.|
|**Użytkownik urządzenia**|Właściciel|Przypisany użytkownik|Bez konta określonego użytkownika|Bez określonego użytkownika|
|**Użytkownik rejestrujący**|Właściciel|Administrator|Menedżer urządzeń|Dowolny użytkownik|
|**Użytkownik wyrejestrowywujący**|Właściciel lub administrator|Administrator|Administrator|Administrator|
|**Użytkownik z uprawnieniami do resetowania**|Właściciel lub administrator|Administrator|Administrator|Administrator|

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Porada</h5>
  <p>Aby uzyskać pełną listę funkcji dostępnych po zarejestrowaniu urządzeń, zobacz [Możliwości zarządzania urządzeniami przenośnymi](mobile-device-management-capabilities-in-microsoft-intune.md).</p>
</div>



## Metody zarządzania komputerami z systemem Windows
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] umożliwia zarządzanie komputerami z systemem Windows Vista i z nowszymi wersjami systemu Windows za pomocą klienta komputerowego usługi Intune. Jednak w przypadku komputerów z systemem Windows możesz wybrać pomiędzy ich zarejestrowaniem a zainstalowaniem oprogramowania klienckiego usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], które zawiera kilka funkcji niedostępnych po zarejestrowaniu urządzeń. W większości przypadków będziesz rejestrować urządzenie z systemem Windows za pomocą usługi Intune, która zapewnia dostęp do szerszego zestawu możliwości niż w przypadku klienta komputerowego.

Rozważ użycie klienta komputerowego usługi Intune, gdy chcesz:
<ul>
<li>Użyć dowolnej z funkcji włączonych w kliencie komputerowym usługi Microsoft Intune do zarządzania komputerami z systemem Windows.</li>
<li>Zarządzać komputerem z systemem operacyjnym Windows, który nie jest obsługiwany w przypadku rejestracji.</li>
</ul>

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Porada</h5>
  <p>Aby uzyskać pełną listę funkcji dostępnych po zainstalowaniu klienta komputerowego usługi Intune na komputerach z obsługiwanym systemem Windows, zobacz [Możliwości zarządzania komputerami z systemem Windows](windows-pc-management-capabilities-in-microsoft-intune.md).</p>
</div>

## Zarządzanie przy użyciu programu Exchange ActiveSync
Urządzeniami możesz również zarządzać za pomocą programu Exchange ActiveSync. Wymaga to zainstalowania łącznika On-Premises Connector albo użycia wbudowanego łącznika Service to Service Connector w celu nawiązania połączenia z programem Exchange Server.

Aby dowiedzieć się więcej o wymaganiach dotyczących sprzętu i oprogramowania w przypadku instalowania łącznika On-Premises Connector, zobacz [Wymagania dotyczące łącznika On-Premises Connector](/Intune/network-infrastructure-requirements-for-microsoft-intune.md).

Aby dowiedzieć się więcej o używaniu łącznika On-Premises Connector lub łącznika Service to Service Connector z programem Exchange, zobacz [Zarządzanie urządzeniami przenośnymi za pomocą programu Exchange ActiveSync i usługi Microsoft Intune](/Intune/get-started/mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).



## Następne kroki
Teraz, gdy znasz już niektóre funkcje, których możesz używać po zarejestrowaniu urządzeń w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], musisz [przygotować się do zarejestrowania swoich urządzeń](/Intune/get-started/get-ready-to-enroll-devices-in-microsoft-intune.md). Po zarejestrowaniu swoich urządzeń możesz korzystać ze wszystkich funkcji, które zostały przedstawione w tym temacie. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->


<!--HONumber=May16_HO1-->


