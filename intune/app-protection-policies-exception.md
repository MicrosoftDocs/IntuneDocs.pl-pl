---
title: "Wyjątki od zasad transferu danych dla aplikacji"
titleSuffix: Microsoft Intune
description: "Tworzenie wyjątków od zasad transferu danych zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1e37e78f7272b0f53f974eccb20c7e02574a9a9
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Jak utworzyć wyjątki od zasad transferu danych zarządzania aplikacjami mobilnymi (MAM) w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator możesz tworzyć wyjątki od zasad transferu danych zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune. Wyjątek pozwala wybrać konkretne niezarządzane aplikacje, które mogą przesyłać dane do i z zarządzanych aplikacji. Niezarządzane aplikacje, które zostały dodane do listy wyjątków, muszą być uznane za zaufane przez dział IT. 

>[!WARNING] 
> Użytkownik jest odpowiedzialny za wprowadzanie zmian w zasadach wyjątków transferu danych. Dodatki do tych zasad umożliwiają niezarządzanym aplikacjom (aplikacjom, które nie są zarządzane przez usługę Intune) dostęp do danych chronionych przez aplikacje zarządzane. Ten dostęp do chronionych danych może spowodować przecieki zabezpieczeń danych. Wyjątki transferu danych należy dodawać tylko dla aplikacji, których organizacja musi używać, ale które nie obsługują zasad ochrony aplikacji usługi Intune. Ponadto wyjątki należy dodawać tylko dla aplikacji, w przypadku których uznano, że nie powodują ryzyka wycieku danych.

Ta funkcja ma zastosowanie w przypadku tworzenia zasad ochrony aplikacji usługi Intune z transferem danych ustawionym na **Tylko aplikacje zarządzane**. Poza utworzonymi wyjątkami, gdy zasady transferu danych mają ustawienie **Tylko aplikacje zarządzane**, transfer danych nadal będzie ograniczony do aplikacji, które są zarządzane przez usługę Intune. Ograniczenia można tworzyć za pomocą protokołów (system iOS) lub pakietów (system Android).

Tę funkcję możesz skonfigurować, aby włączyć wyjątki dla zasad ochrony aplikacji zarządzania aplikacjami mobilnymi usługi Intune powodujących **ograniczenia transferu danych**. Te zasady są wymagane tylko wtedy, gdy chcesz zezwolić na transfer danych do aplikacji, która nie obsługuje zasad ochrony aplikacji usługi Intune. Te zasady umożliwiają aplikacjom zarządzanym przez usługę Intune i mającym ustawienia transferu danych określone na **Tylko aplikacje zarządzane** na wywoływanie niezarządzanych aplikacji na podstawie protokołu URL (iOS) lub nazwy pakietu (Android). Usługa Intune dodaje ważne aplikacje natywne do domyślnej listy wyjątków. 

## <a name="ios-data-transfer-exceptions"></a>Wyjątki transferu danych w systemie iOS
W przypadku zasad przeznaczonych dla systemu iOS możesz skonfigurować wyjątki transferu danych według protokołu URL. Aby dodać wyjątek, zapoznaj się z dokumentacją dostarczoną przez dewelopera aplikacji, gdzie można znaleźć informacje o obsługiwanych protokołach URL. Aby uzyskać dodatkowe informacje dotyczące wyjątków transferu danych w systemie iOS, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — Wyjątki w transferze danych](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Wyjątki transferu danych w systemie Android
W przypadku zasad przeznaczonych dla systemu Android możesz skonfigurować wyjątki transferu danych według nazwy pakietu aplikacji. Możesz sprawdzić stronę sklepu **Google Play** aplikacji, dla której chcesz dodać wyjątek, aby odnaleźć nazwę pakietu aplikacji. Aby uzyskać dodatkowe informacje dotyczące wyjątków transferu danych w systemie Android, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — Wyjątki w transferze danych](app-protection-policy-settings-android.md#data-transfer-exemptions).

### <a name="example"></a>Przykład
Po dodaniu pakietu **Webex** jako wyjątku do zasad transferu danych funkcji MAM linki Webex w wiadomości e-mail zarządzanego programu Outlook mogą być otwierane bezpośrednio w aplikacji Webex. Transfer danych jest nadal ograniczony w innych niezarządzanych aplikacjach.

- Przykład pakietu **Webex** w systemie iOS: aby wykluczyć aplikację **Webex** tak, aby mogła być wywoływana przez zarządzane aplikacje usługi Intune, musisz dodać wyjątek transferu danych dla następującego ciągu: <code>wbx</code>.

- Przykład pakietu **Webex** w systemie Android: aby wykluczyć aplikację **Webex** tak, aby mogła być wywoływana przez zarządzane aplikacje usługi Intune, musisz dodać wyjątek transferu danych dla następującego ciągu: <code>com.cisco.webex.meetings</code>. 

## <a name="next-steps"></a>Następne kroki

- [Tworzenie i wdrażanie zasad ochrony aplikacji](app-protection-policies.md)
- [Ustawienia zasad ochrony aplikacji dla systemu iOS — Wyjątki w transferze danych](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Ustawienia zasad ochrony aplikacji dla systemu Android — Wyjątki w transferze danych](app-protection-policy-settings-android.md#data-transfer-exemptions)
