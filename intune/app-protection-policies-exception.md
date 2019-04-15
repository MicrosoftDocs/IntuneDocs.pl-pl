---
title: Wyjątki od zasad transferu danych dla aplikacji
titleSuffix: Microsoft Intune
description: Tworzenie wyjątków od zasad transferu danych zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30e1ae80ccfdc94bf352b9596df5ea4b0752d43a
ms.sourcegitcommit: d38ca1bf44e17211097aea481e00b6c1e87effae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2019
ms.locfileid: "59567026"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Jak utworzyć wyjątki od zasad transferu danych zarządzania aplikacjami mobilnymi (MAM) w usłudze Intune

Jako administrator możesz tworzyć wyjątki od zasad transferu danych zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune. Wyjątek pozwala wybrać konkretne niezarządzane aplikacje, które mogą przesyłać dane do i z zarządzanych aplikacji. Niezarządzane aplikacje, które są dodawane do listy wyjątków, muszą być uznane za zaufane przez dział IT. 

>[!WARNING] 
> Użytkownik jest odpowiedzialny za wprowadzanie zmian w zasadach wyjątków transferu danych. Dodatki do tych zasad umożliwiają niezarządzanym aplikacjom (aplikacjom, które nie są zarządzane przez usługę Intune) dostęp do danych chronionych przez aplikacje zarządzane. Ten dostęp do chronionych danych może spowodować przecieki zabezpieczeń danych. Wyjątki transferu danych należy dodawać tylko dla aplikacji, których organizacja musi używać, ale które nie obsługują zasad ochrony aplikacji usługi Intune. Ponadto wyjątki należy dodawać tylko dla aplikacji, w przypadku których uznano, że nie powodują ryzyka wycieku danych.

W ramach zasad ochrony aplikacji usługi Intune ustawienie właściwości **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji** na wartość **Aplikacje zarządzane przez zasady** oznacza, że aplikacja może przesyłać dane tylko do aplikacji, które są zarządzane przez usługę Intune. Jeśli chcesz zezwolić na przesyłanie danych do określonych aplikacji, które nie obsługują zasad ochrony aplikacji usługi Intune, możesz utworzyć wyjątki od tych zasad, korzystając z właściwości **Wybierz aplikacje, które będą wykluczone**. Wykluczenia umożliwiają aplikacjom zarządzanym przez usługę Intune wywoływanie niezarządzanych aplikacji na podstawie protokołu adresu URL (iOS) lub nazwy pakietu (Android). Domyślnie usługa Intune dodaje ważne aplikacje natywne do tej listy wyjątków. 

> [!NOTE]
> Modyfikowanie lub dodawanie do wyjątków zasad przesyłania danych nie wpływa na inne zasady ochrony aplikacji, takie jak ograniczenia wycinania, kopiowania i wklejania. 

## <a name="ios-data-transfer-exceptions"></a>Wyjątki transferu danych w systemie iOS
W przypadku zasad przeznaczonych dla systemu iOS możesz skonfigurować wyjątki transferu danych według protokołu URL. Aby dodać wyjątek, zapoznaj się z dokumentacją dostarczoną przez dewelopera aplikacji, gdzie można znaleźć informacje o obsługiwanych protokołach URL. Aby uzyskać dodatkowe informacje dotyczące wyjątków transferu danych w systemie iOS, zobacz [Ustawienia zasad ochrony aplikacji dla systemu iOS — Wyjątki w transferze danych](app-protection-policy-settings-ios.md#data-transfer-exemptions).

> [!NOTE]
> Firma Microsoft nie dysponuje metodą ręcznego odnajdywania protokołu adresu URL na potrzeby tworzenia wyjątków dla aplikacji innych firm. 

## <a name="android-data-transfer-exceptions"></a>Wyjątki transferu danych w systemie Android
W przypadku zasad przeznaczonych dla systemu Android możesz skonfigurować wyjątki transferu danych według nazwy pakietu aplikacji. Możesz sprawdzić stronę sklepu **Google Play** aplikacji, dla której chcesz dodać wyjątek, aby odnaleźć nazwę pakietu aplikacji. Aby uzyskać dodatkowe informacje dotyczące wyjątków transferu danych w systemie Android, zobacz [Ustawienia zasad ochrony aplikacji dla systemu Android — Wyjątki w transferze danych](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Identyfikator pakietu aplikacji możesz znaleźć, przechodząc do aplikacji w sklepie Google Play. Identyfikator pakietu znajduje się w adresie URL strony aplikacji. Na przykład identyfikator pakietu aplikacji Microsoft Word to **com.microsoft.office.word**.

### <a name="example"></a>Przykład
Po dodaniu pakietu **Webex** jako wyjątku do zasad transferu danych funkcji MAM linki Webex w wiadomości e-mail zarządzanego programu Outlook mogą być otwierane bezpośrednio w aplikacji Webex. Transfer danych jest nadal ograniczony w innych niezarządzanych aplikacjach.

- Przykład pakietu **Webex** w systemie iOS:   Aby zwolnić aplikację **Webex** i umożliwić jej wywoływanie przez aplikacje zarządzane w usłudze Intune, należy dodać wyjątek transferu danych dla następującego ciągu: <code>wbx</code>
    
 - Przykład pakietu **Mapy** w systemie iOS:  aby zwolnić aplikację **Mapy** i umożliwić jej wywoływanie przez aplikacje zarządzane w usłudze Intune, należy dodać wyjątek transferu danych dla następującego ciągu: <code>maps</code>

- Przykład pakietu **Webex** w systemie Android:   Aby zwolnić aplikację **Webex** i umożliwić jej wywoływanie przez aplikacje zarządzane w usłudze Intune, należy dodać wyjątek transferu danych dla następującego ciągu: <code>com.cisco.webex.meetings</code>
    
- Przykład pakietu **SMS** w systemie Android:   Aby zwolnić aplikację **SMS** i umożliwić jej wywoływanie przez aplikacje zarządzane w usłudze Intune w różnych aplikacjach do obsługi wiadomości i na różnych urządzeniach z systemem Android, należy dodać wyjątek transferu danych dla następującego ciągu: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Następne kroki

- [Tworzenie i wdrażanie zasad ochrony aplikacji](app-protection-policies.md)
- [Ustawienia zasad ochrony aplikacji dla systemu iOS — Wyjątki w transferze danych](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Ustawienia zasad ochrony aplikacji dla systemu Android — Wyjątki w transferze danych](app-protection-policy-settings-android.md#data-transfer-exemptions)
