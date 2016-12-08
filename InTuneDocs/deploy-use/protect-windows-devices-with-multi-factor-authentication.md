---
title: "Uwierzytelnianie wieloskładnikowe dla systemu Windows | Microsoft Intune"
description: "Usługę Intune można zintegrować z usługą uwierzytelniania wieloskładnikowego (MFA), aby zabezpieczyć zasoby firmowe."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 1bfd17f9fcc73049254bc77351eae48da874fb4c


---

# <a name="protect-windows-devices-with-multi-factor-authentication"></a>Protect Windows devices with multi-factor authentication
Usługę Microsoft Intune można zintegrować z usługą MFA, aby zabezpieczyć zasoby firmowe. Usługa MFA wymaga — oprócz nazw użytkowników i haseł— składników uwierzytelniania, takich jak uwierzytelnianie tekstowe. Usługa Intune obsługuje korzystanie z usługi MFA w przypadku rejestracji urządzeń z systemem Windows 8.1 lub nowszym, Windows Phone 8.1 lub Windows 10 Desktop i Mobile.

## <a name="on-premises-infrastructure-requirements-for-adfs-mfa"></a>Wymagania usługi MFA w usłudze AD FS dotyczące infrastruktury lokalnej
Aby skonfigurować uwierzytelnianie wieloskładnikowe, konieczna jest:

-   rejestracja automatyczna opisana w temacie [Konfigurowanie zarządzania urządzeniami z systemem Windows](set-up-windows-device-management-with-microsoft-intune.md).
-   **domena usługi Active Directory, do której jest dołączony serwer AD FS;**

-   **serwer usług Active Directory Federation Services (AD FS) skonfigurowany na potrzeby usługi MFA;** Serwer z systemem Windows Server 2012 R2 i skonfigurowany jako serwer usług AD FS. Aby uzyskać więcej informacji, zobacz: [Secure cloud and on-premises resources using Azure Multi-Factor Authentication Server with Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/) (Zabezpieczanie chmury i zasobów lokalnych za pomocą serwera usługi Azure Multi-Factor Authentication z usługami AD FS systemu Windows Server 2012 R2).

Wszystkie wymienione powyżej serwery muszą spełniać wymagania systemowe podane w temacie [Wymagania systemowe i informacje dotyczące instalacji systemu Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

 


#### <a name="mfa-with-intune"></a>Usługa MFA w usłudze Intune
Jeśli organizacja ma lokalną infrastrukturę IT, która obejmuje domenę usługi Active Directory z usługami Active Directory Federation Services (AD FS), możesz skonfigurować usługę MFA na serwerze federacyjnym, a następnie włączyć je na potrzeby rejestracji w usłudze Intune. Konfigurując usługę MFA w usłudze Intune, umożliwiasz użytkownikom jednokrotne uwierzytelnianie podczas rejestracji, a następnie używanie zasobów firmy bez konieczności użycia usługi MFA za każdym razem.

>[!NOTE]
>Użycie usługi MFA na serwerze usługi AD FS może być wymagane dla poszczególnych użytkowników lub grup.  

#### <a name="mfa-without-intune"></a>Usługa MFA bez usługi Intune
Jeśli skonfigurujesz usługę MFA na serwerze federacyjnym, ale nie włączysz jej na potrzeby rejestracji w usłudze Intune, użytkownicy będą musieli używać usługi MFA za każdym razem, gdy urządzenia będą uzyskiwać dostęp do zasobów firmy (nie tylko podczas rejestracji urządzenia).

Możesz także użyć usługi Azure Active Directory (Azure AD) MFA, aby wymagać uwierzytelniania wieloskładnikowego za każdym razem, gdy użytkownicy uzyskują dostęp do zasobów firmy (to wymaganie można włączyć dla poszczególnych użytkowników). Usługa Azure AD MFA to usługa w chmurze, która nie wymaga żadnej lokalnej infrastruktury IT. Aby dowiedzieć się, jak skonfigurować usługę Azure AD MFA, zobacz [Getting started with Azure Multi-Factor Authentication in the cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/) (Wprowadzenie do korzystania z usługi Azure Multi-Factor Authentication w chmurze).

## <a name="requiring-adfs-mfa-during-enrollment-of-windows-devices"></a>Wymagania usługi MFA w usługach AD FS podczas rejestrowania urządzeń z systemem Windows
Aby dowiedzieć się, jak włączyć usługę MFA w usługach AD FS, zobacz [Zarządzanie ryzykiem przy użyciu dodatkowego uwierzytelniania wieloskładnikowego w przypadku aplikacji poufnych](http://technet.microsoft.com/library/dn280949.aspx).

## <a name="set-up-device-enrollment-mfa-in-intune"></a>Konfigurowanie usługi MFA na potrzeby rejestracji urządzeń w usłudze Intune
>[!Important]  
>Włącz usługę MFA w dzierżawie usługi Azure AD lub w środowisku lokalnym przed wymaganiem uwierzytelniania wieloskładnikowego dla rejestracji w usłudze Intune urządzeń z systemem Windows. W przeciwnym razie użytkownicy będą otrzymywać komunikat o błędzie podczas próby rejestracji urządzeń z systemem Windows lub próby dołączenia urządzeń do usługi Azure AD, jeśli skonfigurowano automatyczną rejestrację podczas dołączania do usługi Azure AD.

1.  W konsoli administracyjnej usługi Intune wybierz pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **Uwierzytelnianie wieloskładnikowe**.

2.  Wybierz pozycję **Skonfiguruj usługę Multi-factor Authentication**, a następnie wybierz pozycję **Włącz usługę Multi-factor Authentication**.



<!--HONumber=Nov16_HO1-->


