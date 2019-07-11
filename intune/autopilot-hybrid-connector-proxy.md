---
title: Konfigurowanie ustawień serwera proxy na potrzeby łącznika usługi Intune dla usługi Active Directory
description: Opisano tu sposób konfigurowania łącznika usługi Intune dla usługi Active Directory do pracy z istniejącymi lokalnymi serwerami proxy.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: f91ec3124d8fab067ec32194a68508762c6cef33
ms.sourcegitcommit: 1dc9d4e1d906fab3fc46b291c67545cfa2231660
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735262"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Praca z istniejącymi lokalnymi serwerami proxy

W tym artykule wyjaśniono sposób konfigurowania łącznika usługi Intune dla usługi Active Directory do pracy z serwerami proxy ruchu wychodzącego. Ten artykuł jest przeznaczony dla klientów mających serwery proxy w swoich środowiskach sieciowych.

Aby uzyskać więcej informacji na temat działania łączników, zobacz [Understand Azure AD Application Proxy connectors (Omówienie łączników serwerów proxy aplikacji usługi Azure AD)](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Pomijanie serwerów proxy ruchu wychodzącego

Łączniki mają bazowe składniki systemu operacyjnego, które wysyłają żądania wychodzące. Te składniki automatycznie podejmują próby zlokalizowania serwera proxy w sieci przy użyciu usługi autowykrywania serwera proxy w sieci (WPAD).

Składniki systemu operacyjnego próbują zlokalizować serwer proxy, przeprowadzając wyszukiwania DNS dla domeny wpad.domainsuffix. Jeśli wyszukiwanie zostanie rozwiązane w systemie DNS, wysyłane jest żądanie HTTP na adres IP domeny wpad.dat. To żądanie staje się skryptem konfiguracji serwera proxy w danym środowisku. Łącznik używa tego skryptu w celu wybrania serwera proxy ruchu wychodzącego. Jednak ruch łącznika może nadal nie być przepuszczany z powodu braku dodatkowych ustawień konfiguracji wymaganych na tym serwerze proxy.

Łącznik można skonfigurować w taki sposób, aby pomijał lokalny serwer proxy w celu zapewnienia korzystania z bezpośredniej łączności z usługami platformy Azure. Zalecamy takie podejście, jeśli tylko zezwalają na to zasady sieci, ponieważ w ten sposób zostanie zmniejszona o jedną liczba obsługiwanych konfiguracji.

Aby wyłączyć używanie serwera proxy ruchu wychodzącego przez łącznik, zmodyfikuj plik :\Program Files\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config przez dodanie adresu oraz portu serwera proxy w sekcji pokazanej w poniższym przykładzie kodu:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```

Aby się upewnić, że usługa Aktualizator łączników również pomija serwer proxy, dokonaj podobnej zmiany w pliku C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Pamiętaj o utworzeniu kopii oryginalnych plików. W ten sposób będzie można przywrócić domyślne pliki .config, jeśli zajdzie taka potrzeba.

Po zmodyfikowaniu plików konfiguracji będzie konieczne ponowne uruchomienie łącznika usługi Intune. 

1. Otwórz program **services.msc**.
2. Znajdź i zaznacz pozycję **Usługa Intune ODJConnector**.
3. Wybierz polecenie **Uruchom ponownie**.

![Zrzut ekranu przedstawiający ponowne uruchomienie usługi](media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Następne kroki

[Zarządzanie urządzeniami](device-management.md)