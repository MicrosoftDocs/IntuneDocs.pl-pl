---
title: Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego
description: Utwórz profil sieci Wi-Fi z użyciem klucza wstępnego za pomocą opcji Konfiguracja niestandardowa.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a023b6829b33c3b3bff94021ecd3c90d8b41f30f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="use-a-custom-policy-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego za pomocą zasad niestandardowych

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Oto jak utworzyć profil sieci Wi-Fi z użyciem klucza wstępnego za pomocą opcji **Konfiguracja niestandardowa** usługi Intune. Ten temat zawiera również przykład sposobu tworzenia profilu sieci przy użyciu protokołu EAP.

> [!NOTE]
> -   Być może łatwiej będzie skopiować kod z komputera, który łączy się z tą siecią, zgodnie z poniższym opisem.
> - W przypadku urządzeń z systemem Android można skorzystać z aplikacji [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) wydanej przez Johnathona Biersacka.
> -   Można dodać wiele sieci i kluczy, dodając więcej ustawień OMA-URI.
> -  W przypadku urządzeń z systemem iOS należy skonfigurować profil przy użyciu programu Apple Configurator na komputerze Mac. Można również użyć aplikacji [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) wydanej przez Johnathona Biersacka.


1. Aby utworzyć profil sieci Wi-Fi z użyciem klucza wstępnego dla systemu Android lub Windows albo profil sieci Wi-Fi z użyciem protokołu EAP, podczas tworzenia zasad wybierz opcję **Konfiguracja niestandardowa** dla danej platformy urządzenia zamiast profilu sieci Wi-Fi.

2. Podaj nazwę i opis.
3. Dodaj nowe ustawienie OMA-URI:

   a.   Wprowadź nazwę dla tego ustawienia sieci Wi-Fi.

   b.   Wprowadź opis ustawienia OMA-URI lub pozostaw puste pole.

   c.   **Typ danych**: ustaw wartość „Ciąg (XML)”

   d.   **OMA-URI**:

   - **System Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
   - **System Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

   > [!NOTE]
   > Należy pamiętać o kropce na początku.

   Identyfikator SSID jest identyfikatorem SSID, dla którego tworzysz zasady. Na przykład `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

   e. **Pole wartości**: w tym miejscu należy wkleić kod XML. Przykład: Każdą wartość należy dostosować do ustawień sieciowych. Wskazówki można znaleźć w sekcji komentarzy kodu.
4. Wybierz **OK**, zapisz, a następnie wdróż zasady.

    > [!NOTE]
    > Te zasady można wdrożyć tylko dla grup użytkowników.

Zasady zostaną zastosowane po następnym zaewidencjonowaniu urządzenia, a profil sieci Wi-Fi zostanie utworzony na urządzeniu. Urządzenie będzie mogło automatycznie łączyć się z siecią.
## <a name="android-or-windows-wi-fi-profile"></a>Profil sieci Wi-Fi systemu Android lub Windows

Przykładowy kod XML dla profilu sieci Wi-Fi systemu Android lub Windows:

> [!IMPORTANT]
> 
> `<protected>false</protected>` musi mieć ustawioną wartość **false**, ponieważ wartość **true** może spowodować, że urządzenie będzie oczekiwać zaszyfrowanego hasła i spróbuje je odszyfrować, co z kolei może skutkować tym, że połączenie nie zostanie nawiązane.
> 
>  `<hex>53534944</hex>` musi mieć ustawioną wartość szesnastkową `<name><SSID of wifi profile></name>`.
>  Urządzenia z systemem Windows 10 mogą zwracać fałszywy błąd *0x87D1FDE8 Korygowanie nie powiodło się*, ale nadal będą aprowizowane z profilem.

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
<hex>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>        </SSID>
        <nonBroadcast>false</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication><Type of authentication></authentication>
            <encryption><Type of encryption></encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="eap-based-wi-fi-profile"></a>Profil sieci Wi-Fi z użyciem protokołu EAP
Przykładowy kod XML dla profilu sieci Wi-Fi z użyciem protokołu EAP:

```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                <EapMethod>
                  <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                  <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                  <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                  <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                </EapMethod>
                <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                  <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                    <Type>13</Type>
                    <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                      <CredentialsSource>
                        <CertificateStore>
                          <SimpleCertSelection>true</SimpleCertSelection>
                        </CertificateStore>
                      </CredentialsSource>
                      <ServerValidation>
                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
                        <ServerNames></ServerNames>
                      </ServerValidation>
                      <DifferentUsername>false</DifferentUsername>
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Tworzenie pliku XML z istniejącego połączenia sieci Wi-Fi
Można również utworzyć plik XML z istniejącego połączenia sieci Wi-Fi:
1. Na komputerze połączonym lub niedawno połączonym z siecią bezprzewodową otwórz następujący folder: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.

    Najlepiej użyć komputera, który nie jest połączony z wieloma sieciami, ponieważ w przeciwnym razie trzeba będzie przeszukiwać poszczególne profile, aby znaleźć właściwy.
2. Wyszukaj plik z odpowiednią nazwą wśród plików XML.
3. Po zlokalizowaniu odpowiedniego pliku XML skopiuj i wklej kod XML w polu Dane na stronie ustawień OMA-URI.

## <a name="deploy-the-policy"></a>Wdrożenie zasad

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie wybierz pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady**, wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie wybierz pozycje **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — wybierz pozycję **Anuluj**.

Po wybraniu wdrożonych zasad można wyświetlić więcej informacji dotyczących wdrożenia w dolnej części listy zasad.

### <a name="see-also"></a>Zobacz też
[Połączenia Wi-Fi w usłudze Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
