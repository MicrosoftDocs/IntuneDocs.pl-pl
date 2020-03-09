---
title: Interfejsy Graph API do konfigurowania urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Zapoznaj się z listą wszystkich jednostek interfejsów Graph API oraz pasujących dostawców usług konfiguracji systemu Windows i identyfikatorów URI przesunięcia na urządzeniach z systemem Windows 10 lub nowszym, używanych podczas konfigurowania urządzeń w usłudze Microsoft Intune. Zobacz pasujące interfejsy API i dostawców usług konfiguracji dla komputerów udostępnionych, programu Endpoint Protection, usługi Microsoft Defender Advanced Threat Protection, usługi Identity Protection, zespołów systemu Windows 10, kiosku i usługi Windows Update dla firm.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c99c166713b9e3d8614ebe8f2756a586356c5b3b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "77687820"
---
# <a name="graph-apis-and-matching-windows-10-csps-used-in-intune"></a>Interfejsy API programu Graph i pasujący dostawcy usług konfiguracji (CSP) systemu Windows 10 używani w usłudze Intune

Usługa Microsoft Intune używa [jednostek interfejsów Graph API](https://docs.microsoft.com/graph/api/resources/intune-graph-overview) (powoduje otwarcie innej witryny Docs) w celu skonfigurowania urządzeń (**Intune** > **Konfiguracja urządzenia**) z systemem Windows 10 lub nowszym. Interfejs Graph API używa dostawców usług konfiguracji do odczytywania, ustawiania, zmiany i/lub usuwania ustawień konfiguracji na urządzeniach.

Ta lista dotyczy systemu:

- Windows 10 lub nowszym

Ten artykuł zawiera listę jednostek usługi Graph oraz pasujących dostawców usług konfiguracji systemu Windows 10 i identyfikatorów URI przesunięcia.

Te informacje są przydatne w różnych scenariuszach. Na przykład można zobaczyć, co jest używane przez usługę Intune, zobaczyć ustawienia do uwzględnienia w niestandardowych konfiguracjach OMA-URI i tak dalej. 

## <a name="windows-10-csps"></a>Dostawcy usług konfiguracji systemu Windows 10

Aby uzyskać więcej informacji na temat dostawców usług konfiguracji systemu Windows 10, zapoznaj się z artykułem [Configuration service provider reference (Informacje dotyczące dostawcy usług konfiguracji)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (powoduje otwarcie innej witryny Docs).

## <a name="graph-api-properties-to-csp-mapping"></a>Mapowanie właściwości interfejsu Graph API na dostawców usług konfiguracji

Na poniższej liście przedstawiono większość jednostek interfejsów Graph API używanych przez usługę Microsoft Intune do konfiguracji urządzeń z systemem Windows 10. Zawiera ona również odpowiednich dostawców usług konfiguracji systemu Windows 10 i identyfikatory URI przesunięcia.

Aby zobaczyć wersje systemu Windows 10, do których mają zastosowanie poniższe interfejsy API, skorzystaj z [dokumentacji dostawcy usług konfiguracji](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) systemu Windows 10 (powoduje otwarcie innej witryny Docs).

### <a name="editionupgradeconfigurationlicense"></a>EditionUpgradeConfiguration.License 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsLicensing  
**Identyfikator URI przesunięcia**: /UpgradeEditionWithLicense

### <a name="editionupgradeconfigurationlicensetype"></a>EditionUpgradeConfiguration.LicenseType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsLicensing  
**Identyfikator URI przesunięcia**: /LicenseKeyType

### <a name="editionupgradeconfigurationproductkey"></a>EditionUpgradeConfiguration.ProductKey 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsLicensing  
**Identyfikator URI przesunięcia**: /UpgradeEditionWithProductKey

### <a name="editionupgradeconfigurationwindowssmode"></a>EditionUpgradeConfiguration.WindowsSMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsLicensing  
**Identyfikator URI przesunięcia**: /SMode/SwitchingPolicy

### <a name="sharedpcconfigurationaccountmanagerpolicy"></a>SharedPCConfiguration.AccountManagerPolicy 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /DeletionPolicy, /DiskLevelCaching, /InactiveThreshold, /DiskLevelDeletion

### <a name="sharedpcconfigurationaccountmanagerpolicy-windows-holographic-for-business-edition-targeted-devices"></a>SharedPCConfiguration.AccountManagerPolicy (urządzenia z systemem Windows Holographic for Business) 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/AccountManagement  
**Dostawca usług konfiguracji**: /DeletionPolicy, /StorageCapacityStartDeletion, /StorageCapacityStopDeletion, /ProfileInactivityThreshold

### <a name="sharedpcconfigurationallowedaccounts"></a>SharedPCConfiguration.AllowedAccounts 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /AccountModel

### <a name="sharedpcconfigurationallowlocalstorage"></a>SharedPCConfiguration.AllowLocalStorage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /RestrictLocalStorage

### <a name="sharedpcconfigurationdisableaccountmanager"></a>SharedPCConfiguration.DisableAccountManager 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /EnableAccountManager

### <a name="sharedpcconfigurationdisableedupolicies"></a>SharedPCConfiguration.DisableEduPolicies 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /SetEduPolicies

### <a name="sharedpcconfigurationdisablepowerpolicies"></a>SharedPCConfiguration.DisablePowerPolicies 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /SetPowerPolicies

### <a name="sharedpcconfigurationdisablesigninonresume"></a>SharedPCConfiguration.DisableSignInOnResume 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /SignInOnResume

### <a name="sharedpcconfigurationenabled"></a>SharedPCConfiguration.Enabled 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /EnableSharedPCMode

### <a name="sharedpcconfigurationidletimebeforesleepinseconds"></a>SharedPCConfiguration.IdleTimeBeforeSleepInSeconds 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /InactiveThreshold

### <a name="sharedpcconfigurationkioskappdisplayname"></a>SharedPCConfiguration.KioskAppDisplayName 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /KioskModeUserTileDisplayText

### <a name="sharedpcconfigurationkioskappusermodelid"></a>SharedPCConfiguration.KioskAppUserModelId 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /KioskModeAUMID

### <a name="sharedpcconfigurationlocalstorage"></a>SharedPCConfiguration.LocalStorage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /RestrictLocalStorage

### <a name="sharedpcconfigurationmaintenancestarttime"></a>SharedPCConfiguration.MaintenanceStartTime 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /MaintenanceStartTime

### <a name="sharedpcconfigurationsetaccountmanager"></a>SharedPCConfiguration.SetAccountManager
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /EnableAccountManager

### <a name="sharedpcconfigurationsetedupolicies"></a>SharedPCConfiguration.SetEduPolicies 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /SetEduPolicies

### <a name="sharedpcconfigurationsetpowerpolicies"></a>SharedPCConfiguration.SetPowerPolicies 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /SetPowerPolicies

### <a name="sharedpcconfigurationsigninonresume"></a>SharedPCConfiguration.SignInOnResume 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SharedPC  
**Identyfikator URI przesunięcia**: /SignInOnResume

### <a name="windows10endpointconfigurationsmartscreenblockoverrideforfiles"></a>Windows10endpointconfiguration.smartScreenBlockOverrideForFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/SmartScreen/PreventOverrideForFilesInShell

### <a name="windows10endpointprotectionconfigurationapplicationguardallowfilesaveonhost"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowFileSaveOnHost 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/SaveFilesToHost

### <a name="windows10endpointprotectionconfigurationapplicationguardallowpersistence"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPersistence 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/AllowPersistence

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttolocalprinters"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToLocalPrinters 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/PrintingSettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttonetworkprinters"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToNetworkPrinters 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/PrintingSettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttopdf"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToPDF 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/PrintingSettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttoxps"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowPrintToXPS 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/PrintingSettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowvirtualgpu"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardAllowVirtualGPU 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/AllowVirtualGPU

### <a name="windows10endpointprotectionconfigurationapplicationguardblockclipboardsharing"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardBlockClipboardSharing 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/ClipboardSettings

### <a name="windows10endpointprotectionconfigurationapplicationguardblockfiletransfer"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardBlockFileTransfer 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/ClipboardFileType

### <a name="windows10endpointprotectionconfigurationapplicationguardblocknonenterprisecontent"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardBlockNonEnterpriseContent 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/BlockNonEnterpriseContent

### <a name="windows10endpointprotectionconfigurationapplicationguardenabled"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardEnabled 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Settings/AllowWindowsDefenderApplicationGuard

### <a name="windows10endpointprotectionconfigurationapplicationguardforceauditing"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardForceAuditing 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsDefenderApplicationGuard  
**Identyfikator URI przesunięcia**: /Audit/AuditApplicationGuard

### <a name="windows10endpointprotectionconfigurationbitlockerallowstandarduserencryption"></a>Windows10EndpointProtectionConfiguration.BitLockerAllowStandardUserEncryption 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /AllowStandardUserEncryption

### <a name="windows10endpointprotectionconfigurationbitlockerdisablewarningforotherdiskencryption"></a>Windows10EndpointProtectionConfiguration.BitLockerDisableWarningForOtherDiskEncryption 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /AllowWarningForOtherDiskEncryption

### <a name="windows10endpointprotectionconfigurationbitlockerenablestoragecardencryptiononmobile"></a>Windows10EndpointProtectionConfiguration.BitLockerEnableStorageCardEncryptionOnMobile 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /RequireStorageCardEncryption

### <a name="windows10endpointprotectionconfigurationbitlockerencryptdevice"></a>Windows10EndpointProtectionConfiguration.BitLockerEncryptDevice 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /RequireDeviceEncryption

### <a name="windows10endpointprotectionconfigurationbitlockerfixeddrivepolicy"></a>Windows10EndpointProtectionConfiguration.BitLockerFixedDrivePolicy 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /EncryptionMethodByDriveType, /FixedDrivesRequireEncryption, /FixedDrivesRecoveryOptions

### <a name="windows10endpointprotectionconfigurationbitlockerremovabledrivepolicy"></a>Windows10EndpointProtectionConfiguration.BitLockerRemovableDrivePolicy 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /EncryptionMethodByDriveType, /RemovableDrivesRequireEncryption

### <a name="windows10endpointprotectionconfigurationbitlockersystemdrivepolicy"></a>Windows10EndpointProtectionConfiguration.BitLockerSystemDrivePolicy 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/BitLocker  
**Identyfikator URI przesunięcia**: /EncryptionMethodByDriveType, /SystemDrivesRequireStartupAuthentication, /SystemDrivesMinimumPINLength, /SystemDrivesRecoveryMessage, /SystemDrivesRecoveryOptions

### <a name="windows10endpointprotectionconfigurationclientconnectionencryptionlevel"></a>windows10endpointprotectionconfiguration.clientConnectionEncryptionLevel 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteDesktopServices/ClientConnectionEncryptionLevel

### <a name="windows10endpointprotectionconfigurationconfiguresmbv1clientdriver"></a>windows10endpointprotectionconfiguration.configureSMBV1ClientDriver 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/ConfigureSMBV1ClientDriver

### <a name="windows10endpointprotectionconfigurationconnectivitydownloadingofprintdriversoverhttp"></a>Windows10EndpointProtectionConfiguration.ConnectivityDownloadingOfPrintDriversOverHttp 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/DisableDownloadingOfPrintDriversOverHTTP

### <a name="windows10endpointprotectionconfigurationconnectivityhardeneduncpaths"></a>Windows10EndpointProtectionConfiguration.ConnectivityHardenedUncPaths 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/HardenedUNCPaths

### <a name="windows10endpointprotectionconfigurationconnectivityinternetdownloadforwebpublishingandonlineorderingwizards"></a>Windows10EndpointProtectionConfiguration.ConnectivityInternetDownloadForWebPublishingAndOnlineOrderingWizards 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards

### <a name="windows10endpointprotectionconfigurationconnectivityprintingoverhttp"></a>Windows10EndpointProtectionConfiguration.ConnectivityPrintingOverHttp 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/DiablePrintingOverHTTP

### <a name="windows10endpointprotectionconfigurationcredentialsuienumerateadministrators"></a>Windows10EndpointProtectionConfiguration.CredentialsUIEnumerateAdministrators 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/CredentialsUI/EnumerateAdministrators

### <a name="windows10endpointprotectionconfigurationdefenderadditionalguardedfolders"></a>Windows10EndpointProtectionConfiguration.DefenderAdditionalGuardedFolders 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/Defender/ControlledFolderAccessProtectedFolders

### <a name="windows10endpointprotectionconfigurationdefenderadvancedransomewareprotectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderAdvancedRansomewareProtectionType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderattacksurfacereductionexcludedpaths"></a>Windows10EndpointProtectionConfiguration.DefenderAttackSurfaceReductionExcludedPaths 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionOnlyExclusions

### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecution"></a>Windows10EndpointProtectionConfiguration.DefenderEmailContentExecution 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowEmailScanning

### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecutiontype"></a>Windows10EndpointProtectionConfiguration.DefenderEmailContentExecutionType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxml"></a>Windows10EndpointProtectionConfiguration.DefenderExploitProtectionXml 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/ExploitGuard/ExploitProtectionSettings

### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxmlfilename"></a>Windows10EndpointProtectionConfiguration.DefenderExploitProtectionXmlFileName 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ExploitGuard/ExploitProtectionSettings

### <a name="windows10endpointprotectionconfigurationdefenderguardedfoldersallowedapppaths"></a>Windows10EndpointProtectionConfiguration.DefenderGuardedFoldersAllowedAppPaths 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/Defender/ControlledFolderAccessAllowedApplications

### <a name="windows10endpointprotectionconfigurationdefenderguardmyfolderstype"></a>Windows10EndpointProtectionConfiguration.DefenderGuardMyFoldersType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/EnableControlledFolderAccess

### <a name="windows10endpointprotectionconfigurationdefendernetworkprotectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderNetworkProtectionType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/Defender/EnableNetworkProtection

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunch"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsExecutableContentCreationOrLaunch 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunchtype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsExecutableContentCreationOrLaunchType
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocess"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsLaunchChildProcess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocesstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsLaunchChildProcessType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjection"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsOtherProcessInjection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjectiontype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeAppsOtherProcessInjectionType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType 

### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32imports"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32Imports 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32importstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32ImportsType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefenderpreventcredentialstealingtype"></a>Windows10EndpointProtectionConfiguration.DefenderPreventCredentialStealingType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefenderprocesscreation"></a>Windows10EndpointProtectionConfiguration.DefenderProcessCreation 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderprocesscreationtype"></a>Windows10EndpointProtectionConfiguration.DefenderProcessCreationType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderprotectagainstpotentiallyunwantedapplications"></a>Windows10EndpointProtectionConfiguration.DefenderProtectAgainstPotentiallyUnwantedApplications 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications

### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecution"></a>Windows10EndpointProtectionConfiguration.DefenderScriptDownloadedPayloadExecution 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecutiontype"></a>Windows10EndpointProtectionConfiguration.DefenderScriptDownloadedPayloadExecutionType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocode"></a>Windows10EndpointProtectionConfiguration.DefenderScriptObfuscatedMacroCode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocodetype"></a>Windows10EndpointProtectionConfiguration.DefenderScriptObfuscatedMacroCodeType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterblockexploitprotectionoverride"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterBlockExploitProtectionOverride 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableaccountui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableAccountUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisableAccountProtectionUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableappbrowserui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableAppBrowserUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisableAppBrowserUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablefamilyui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableFamilyUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisableFamilyUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablehealthui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableHealthUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisableHealthUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablenetworkui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableNetworkUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisableNetworkUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablesecurebootui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableSecureBootUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/HideSecureBoot

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisabletroubleshootingui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableTroubleshootingUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/HideTPMTroubleshooting

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablevirusui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableVirusUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/DisableVirusUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpemail"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpEmail 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/Email

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpphone"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpPhone 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/Phone

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpurl"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterHelpURL 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/URL

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenteritcontactdisplay"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterITContactDisplay 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /WindowsDefenderSecurityCenter/EnableCustomizedToasts, /WindowsDefenderSecurityCenter/EnableInAppCustomization

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenternotificationsfromapp"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterNotificationsFromApp 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/HideWindowsSecurityNotificationAreaControl

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterorganizationdisplayname"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterOrganizationDisplayName 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsDefenderSecurityCenter/CompanyName

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutable"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedExecutable 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutabletype"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedExecutableType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocess"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedUSBProcess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocesstype"></a>Windows10EndpointProtectionConfiguration.DefenderUntrustedUSBProcessType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AttackSurfaceReductionRules (dostawca usług konfiguracji/konfiguracja wymaga właściwości usługi Graph: windows10endpointprotection/Configuration.defenderOfficeAppsOtherProcessInjectionType, windows10endpointprotection/Configuration.defenderOfficeAppsExecutableContentCreationOrLaunchType, windows10endpointprotection/Configuration.defenderOfficeAppsLaunchChildProcessType, windows10endpointprotection/Configuration.defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration.defenderScriptObfuscatedMacroCodeType, windows10endpointprotection/Configuration.defenderScriptDownloadedPayloadExecutionType, windows10endpointprotection/Configuration.defenderEmailContentExecutionType, windows10endpointprotection/Configuration.defenderPreventCredentialStealingType, windows10endpointprotection/Configuration.defenderUntrustedUSBProcessType

### <a name="windows10endpointprotectionconfigurationdeviceguardenablesecurebootwithdma"></a>Windows10EndpointProtectionConfiguration.DeviceGuardEnableSecureBootWithDMA 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceGuard/RequirePlatformSecurityFeatures

### <a name="windows10endpointprotectionconfigurationdeviceguardenablevirtualizationbasedsecurity"></a>Windows10EndpointProtectionConfiguration.DeviceGuardEnableVirtualizationBasedSecurity 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/DeviceGuard/EnableVirtualizationBasedSecurity

### <a name="windows10endpointprotectionconfigurationdeviceguardlaunchsystemguard"></a>Windows10EndpointProtectionConfiguration.DeviceGuardLaunchSystemGuard 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceGuard/ConfigureSystemGuardLaunch

### <a name="windows10endpointprotectionconfigurationdeviceguardlocalsystemauthoritycredentialguardsettings"></a>Windows10EndpointProtectionConfiguration.DeviceGuardLocalSystemAuthorityCredentialGuardSettings 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceGuard/LsaCfgFlags

### <a name="windows10endpointprotectionconfigurationdmaguarddeviceenumerationpolicy"></a>Windows10EndpointProtectionConfiguration.DmaGuardDeviceEnumerationPolicy 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DmaGuard/DeviceEnumerationPolicy

### <a name="windows10endpointprotectionconfigurationeventlogserviceapplicationlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceApplicationLogMaximumFileSizeInKb 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EventLogService/SpecifyMaximumFileSizeApplicationLog

### <a name="windows10endpointprotectionconfigurationeventlogservicesecuritylogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceSecurityLogMaximumFileSizeInKb 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EventLogService/SpecifyMaximumFileSizeSecurityLog

### <a name="windows10endpointprotectionconfigurationeventlogservicesystemlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceSystemLogMaximumFileSizeInKb 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EventLogService/SpecifyMaximumFileSizeSystemLog

### <a name="windows10endpointprotectionconfigurationexplorerdataexecutionprevention"></a>Windows10EndpointProtectionConfiguration.ExplorerDataExecutionPrevention 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/FileExplorer/TurnOffDataExecutionPreventionForExplorer

### <a name="windows10endpointprotectionconfigurationexplorerheapterminationoncorruption"></a>Windows10EndpointProtectionConfiguration.ExplorerHeapTerminationOnCorruption 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/FileExplorer/TurnOffHeapTerminationOnCorruption

### <a name="windows10endpointprotectionconfigurationfirewallblockstatefulftp"></a>Windows10EndpointProtectionConfiguration.FirewallBlockStatefulFTP 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/DisableStatefulFtp

### <a name="windows10endpointprotectionconfigurationfirewallcertificaterevocationlistcheckmethod"></a>Windows10EndpointProtectionConfiguration.FirewallCertificateRevocationListCheckMethod 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/CRLcheck

### <a name="windows10endpointprotectionconfigurationfirewallidletimeoutforsecurityassociationinseconds"></a>Windows10EndpointProtectionConfiguration.FirewallIdleTimeoutForSecurityAssociationInSeconds 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/SaIdleTime

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowdhcp"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowDHCP 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/IPsecExempt

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowicmp"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowICMP 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/IPsecExempt

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowneighbordiscovery"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowNeighborDiscovery 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/IPsecExempt

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowrouterdiscovery"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowRouterDiscovery 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/IPsecExempt

### <a name="windows10endpointprotectionconfigurationfirewallmergekeyingmodulesettings"></a>Windows10EndpointProtectionConfiguration.FirewallMergeKeyingModuleSettings 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/OpportunisticallyMatchAuthSetPerKM

### <a name="windows10endpointprotectionconfigurationfirewallpacketqueueingmethod"></a>Windows10EndpointProtectionConfiguration.FirewallPacketQueueingMethod 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/EnablePacketQueue

### <a name="windows10endpointprotectionconfigurationfirewallpresharedkeyencodingmethod"></a>Windows10EndpointProtectionConfiguration.FirewallPreSharedKeyEncodingMethod 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/Global/PresharedKeyEncoding

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomain"></a>Windows10EndpointProtectionConfiguration.FirewallProfileDomain 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /EnableFirewall, /DisableStealthMode, /Shielded, /DisableUnicastResponsesToMulticastBroadcast, /DisableInboundNotifications, /AuthAppsAllowUserPrefMerge, /GlobalPortsAllowUserPrefMerge, /AllowLocalPolicyMerge, /DefaultOutboundAction, /DefaultInboundAction, /DisableStealthModeIpsecSecuredPacketExemption, /AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.inboundConnectionsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/DomainProfile/DefaultInboundAction

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.inboundNotificationsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/DomainProfile/DisableInboundNotifications

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.inboundNotificationsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/DomainProfile/EnableFirewall

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomainoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfileDomain.outboundConnectionsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/DomainProfile/DefaultOutboundAction

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivate"></a>Windows10EndpointProtectionConfiguration.FirewallProfilePrivate 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /EnableFirewall, /DisableStealthMode, /Shielded, /DisableUnicastResponsesToMulticastBroadcast, /DisableInboundNotifications, /AuthAppsAllowUserPrefMerge, /GlobalPortsAllowUserPrefMerge, /AllowLocalPolicyMerge, /DefaultOutboundAction, /DefaultInboundAction, /DisableStealthModeIpsecSecuredPacketExemption, /AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivatefirewallenabled"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.firewallEnabled 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PrivateProfile/EnableFirewall

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.inboundConnectionsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PrivateProfile/DefaultInboundAction

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.inboundNotificationsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PrivateProfile/DisableInboundNotifications

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePrivate.outboundConnectionsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PrivateProfile/DefaultOutboundAction

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublic"></a>Windows10EndpointProtectionConfiguration.FirewallProfilePublic 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /EnableFirewall, /DisableStealthMode, /Shielded, /DisableUnicastResponsesToMulticastBroadcast, /DisableInboundNotifications, /AuthAppsAllowUserPrefMerge, /GlobalPortsAllowUserPrefMerge, /AllowLocalPolicyMerge, /DefaultOutboundAction, /DefaultInboundAction, /DisableStealthModeIpsecSecuredPacketExemption, /AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicconnectionsecurityrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.connectionSecurityRulesFromGroupPolicyMerged 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PublicProfile/AllowLocalIpsecPolicyMerge

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicfirewallenabled"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.firewallEnabled 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PublicProfile/EnableFirewall

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.inboundConnectionsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PublicProfile/DefaultInboundAction

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.inboundNotificationsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PublicProfile/DisableInboundNotifications

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.outboundConnectionsBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PublicProfile/DefaultOutboundAction

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicpolicyrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration.firewallProfilePublic.policyRulesFromGroupPolicyMerged 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Firewall  
**Identyfikator URI przesunięcia**: /MdmStore/PublicProfile/AllowLocalPolicyMerge

### <a name="windows10endpointprotectionconfigurationlanmanagerauthenticationlevel"></a>Windows10EndpointProtectionConfiguration.LanManagerAuthenticationLevel 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_LANManagerAuthenticationLevel

### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationdisableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration.LanManagerWorkstationDisableInsecureGuestLogons 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LanmanWorkstation/EnableInsecureGuestLogons

### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationenableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration.LanManagerWorkstationEnableInsecureGuestLogons 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LanmanWorkstation/EnableInsecureGuestLogons

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratoraccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAdministratorAccountName 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_RenameAdministratorAccount

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratorelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAdministratorElevationPromptBehavior
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_BehaviorOfTheElevationPromptForAdministrators

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowanonymousenumerationofsamaccountsandshares"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowAnonymousEnumerationOfSAMAccountsAndShares 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowpku2uauthenticationrequests"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowPKU2UAuthenticationRequests 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_AllowPKU2UAuthenticationRequests

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanager"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowRemoteCallsToSecurityAccountsManager 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_RestrictClientsAllowedToMakeRemoteCallsToSAM

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanagerhelperbool"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowRemoteCallsToSecurityAccountsManagerHelperBool 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_RestrictClientsAllowedToMakeRemoteCallsToSAM

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowsystemtobeshutdownwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowSystemToBeShutDownWithoutHavingToLogOn 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Shutdown\_AllowSystemToBeShutDownWithoutHavingToLogOn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUIAccessApplicationElevation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_AllowUIAccessApplicationsToPromptForElevation

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationsforsecurelocations"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUIAccessApplicationsForSecureLocations 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowundockwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUndockWithoutHavingToLogon 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Devices\_AllowUndockWithoutHavingToLogon

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockmicrosoftaccounts"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockMicrosoftAccounts 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_BlockMicrosoftAccounts

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremotelogonwithblankpassword"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockRemoteLogonWithBlankPassword 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremoteopticaldriveaccess"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockRemoteOpticalDriveAccess 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Devices\_RestrictCDROMAccessToLocallyLoggedOnUserOnly

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockusersinstallingprinterdrivers"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockUsersInstallingPrinterDrivers 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Devices\_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclearvirtualmemorypagefile"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClearVirtualMemoryPageFile 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Shutdown\_ClearVirtualMemoryPageFile

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClientDigitallySignCommunicationsAlways 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient\_DigitallySignCommunicationsAlways

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientsendunencryptedpasswordtothirdpartysmbservers"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsClientSendUnencryptedPasswordToThirdPartySMBServers 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient\_SendUnencryptedPasswordToThirdPartySMBServers

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdetectapplicationinstallationsandpromptforelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDetectApplicationInstallationsAndPromptForElevation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_DetectApplicationInstallationsAndPromptForElevation

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableadministratoraccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableAdministratorAccount 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableAdministratorAccountStatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableclientdigitallysigncommunicationsifserveragrees"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableClientDigitallySignCommunicationsIfServerAgrees 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient\_DigitallySignCommunicationsIfServerAgrees

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableguestaccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableGuestAccount 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableGuestAccountStatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableServerDigitallySignCommunicationsAlways 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkServer\_DigitallySignCommunicationsAlways

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsifclientagrees"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableServerDigitallySignCommunicationsIfClientAgrees 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/MicrosoftNetworkServer\_DigitallySignCommunicationsIfClientAgrees

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotallowanonymousenumerationofsamaccounts"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotAllowAnonymousEnumerationOfSAMAccounts 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_DoNotAllowAnonymousEnumerationOfSAMAccounts

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotrequirectrlaltdel"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotRequireCtrlAltDel 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DoNotRequireCTRLALTDEL

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotstorelanmanagerhashvalueonnextpasswordchange"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotStoreLANManagerHashValueOnNextPasswordChange 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_DoNotStoreLANManagerHashValueOnNextPasswordChange

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableadministratoraccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsEnableAdministratorAccount 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableAdministratorAccountStatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableguestaccount"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsEnableGuestAccount 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_EnableGuestAccountStatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsformatandejectofremovablemediaalloweduser"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsFormatAndEjectOfRemovableMediaAllowedUser 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Devices\_AllowedToFormatAndEjectRemovableMedia

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsguestaccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsGuestAccountName 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/Accounts\_RenameGuestAccount

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshidelastsignedinuser"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsHideLastSignedInUser 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DoNotDisplayLastSignedIn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshideusernameatsignin"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsHideUsernameAtSignIn 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DoNotDisplayUsernameAtSignIn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationdisplayedonlockscreen"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsInformationDisplayedOnLockScreen 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DisplayUserInformationWhenTheSessionIsLocked

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationshownonlockscreen"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsInformationShownOnLockScreen 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_DisplayUserInformationWhenTheSessionIsLocked

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetext"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsLogOnMessageText 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MessageTextForUsersAttemptingToLogOn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetitle"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsLogOnMessageTitle 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MessageTitleForUsersAttemptingToLogOn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimit"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMachineInactivityLimit 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MachineInactivityLimit

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimitinminutes"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMachineInactivityLimitInMinutes 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_MachineInactivityLimit

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedclients"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedClients 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_MinimumSessionSecurityForNTLMSSPBasedClients

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedservers"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedServers 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkSecurity\_MinimumSessionSecurityForNTLMSSPBasedServers

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsonlyelevatesignedexecutables"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsOnlyElevateSignedExecutables 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_OnlyElevateExecutableFilesThatAreSignedAndValidated

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsrestrictanonymousaccesstonamedpipesandshares"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsRestrictAnonymousAccessToNamedPipesAndShares 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/NetworkAccess\_RestrictAnonymousAccessToNamedPipesAndShares

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionssmartcardremovalbehavior"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsSmartCardRemovalBehavior 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/InteractiveLogon\_SmartCardRemovalBehavior

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsstandarduserelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsStandardUserElevationPromptBehavior 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_BehaviorOfTheElevationPromptForStandardUsers

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsswitchtosecuredesktopwhenpromptingforelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsSwitchToSecureDesktopWhenPromptingForElevation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_SwitchToTheSecureDesktopWhenPromptingForElevation

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmode"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsUseAdminApprovalMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_UseAdminApprovalMode

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmodeforadministrators"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsUseAdminApprovalModeForAdministrators 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_RunAllAdministratorsInAdminApprovalMode

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsvirtualizefileandregistrywritefailurestoperuserlocations"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsVirtualizeFileAndRegistryWriteFailuresToPerUserLocations 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/LocalPoliciesSecurityOptions/UserAccountControl\_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations

### <a name="windows10endpointprotectionconfigurationnetworkicmpredirectsoverrideospfgeneratedroutes"></a>Windows10EndpointProtectionConfiguration.NetworkIcmpRedirectsOverrideOspfGeneratedRoutes 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSLegacy/AllowICMPRedirectsToOverrideOSPFGeneratedRoutes

### <a name="windows10endpointprotectionconfigurationnetworkignorenetbiosnamereleaserequestsexceptfromwinsservers"></a>Windows10EndpointProtectionConfiguration.NetworkIgnoreNetBiosNameReleaseRequestsExceptFromWinsServers 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSLegacy/AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers

### <a name="windows10endpointprotectionconfigurationnetworkipsourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration.NetworkIpSourceRoutingProtectionLevel 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSLegacy/IPSourceRoutingProtectionLevel

### <a name="windows10endpointprotectionconfigurationnetworkipv6sourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration.NetworkIpV6SourceRoutingProtectionLevel 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSLegacy/IPv6SourceRoutingProtectionLevel

### <a name="windows10endpointprotectionconfigurationpasswordpinlogon"></a>Windows10EndpointProtectionConfiguration.PasswordPinLogOn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/CredentialProviders/AllowPINLogon

### <a name="windows10endpointprotectionconfigurationpowershellshellscriptblocklogging"></a>Windows10EndpointProtectionConfiguration.PowerShellShellScriptBlockLogging 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsPowerShell/TurnOnPowerShellScriptBlockLogging

### <a name="windows10endpointprotectionconfigurationremoteassistancesolicitedsetting"></a>Windows10EndpointProtectionConfiguration.RemoteAssistanceSolicitedSetting 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/HardenedUNCPaths

### <a name="windows10endpointprotectionconfigurationremotedesktopservicesclientconnectionencryptionlevel"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesClientConnectionEncryptionLevel 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteDesktopServices/ClientConnectionEncryptionLevel

### <a name="windows10endpointprotectionconfigurationremotedesktopservicesdriveredirection"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesDriveRedirection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteDesktopServices/DoNotAllowDriveRedirection

### <a name="windows10endpointprotectionconfigurationremotedesktopservicespasswordsaving"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesPasswordSaving 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteDesktopServices/DoNotAllowPasswordSaving

### <a name="windows10endpointprotectionconfigurationremotedesktopservicespromptforpassworduponconnection"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesPromptForPasswordUponConnection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteDesktopServices/PromptForPasswordUponConnection

### <a name="windows10endpointprotectionconfigurationremotedesktopservicessecurerpccommunication"></a>Windows10EndpointProtectionConfiguration.RemoteDesktopServicesSecureRpcCommunication 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteDesktopServices/RequireSecureRPCCommunication

### <a name="windows10endpointprotectionconfigurationremotehostdelegationofnonexportablecredentials"></a>Windows10EndpointProtectionConfiguration.RemoteHostDelegationOfNonExportableCredentials 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/CredentialsDelegation/RemoteHostAllowsDelegationOfNonExportableCredentials

### <a name="windows10endpointprotectionconfigurationremotemanagementclientbasicauthentication"></a>Windows10EndpointProtectionConfiguration.RemoteManagementClientBasicAuthentication 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteManagement/AllowBasicAuthentication\_Client

### <a name="windows10endpointprotectionconfigurationremotemanagementclientdigestauthentication"></a>Windows10EndpointProtectionConfiguration.RemoteManagementClientDigestAuthentication 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteManagement/DisallowDigestAuthentication

### <a name="windows10endpointprotectionconfigurationremotemanagementclientunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration.RemoteManagementClientUnencryptedTraffic 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteManagement/AllowUnencryptedTraffic\_Client

### <a name="windows10endpointprotectionconfigurationremotemanagementservicebasicauthentication"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceBasicAuthentication 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteManagement/AllowBasicAuthentication\_Service

### <a name="windows10endpointprotectionconfigurationremotemanagementservicestoringrunascredentials"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceStoringRunAsCredentials 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteManagement/DisallowStoringOfRunAsCredentials

### <a name="windows10endpointprotectionconfigurationremotemanagementserviceunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceUnencryptedTraffic 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteManagement/AllowUnencryptedTraffic\_Service

### <a name="windows10endpointprotectionconfigurationrpcunauthenticatedclientoptions"></a>Windows10EndpointProtectionConfiguration.RpcUnauthenticatedClientOptions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteProcedureCall/RestrictUnauthenticatedRPCClients

### <a name="windows10endpointprotectionconfigurationsecurityguideapplyuacrestrictionstolocalaccountsonnetworklogon"></a>Windows10EndpointProtectionConfiguration.SecurityGuideApplyUacRestrictionsToLocalAccountsOnNetworkLogon 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/ApplyUACRestrictionsToLocalAccountsOnNetworkLogon

### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1clientdriverstartconfiguration"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1ClientDriverStartConfiguration 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/ConfigureSMBV1ClientDriver

### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1server"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1Server 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/ConfigureSMBV1Server

### <a name="windows10endpointprotectionconfigurationsecurityguidestructuredexceptionhandlingoverwriteprotection"></a>Windows10EndpointProtectionConfiguration.SecurityGuideStructuredExceptionHandlingOverwriteProtection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/EnableStructuredExceptionHandlingOverwriteProtection

### <a name="windows10endpointprotectionconfigurationsecurityguidewdigestauthentication"></a>Windows10EndpointProtectionConfiguration.SecurityGuideWDigestAuthentication 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/MSSecurityGuide/WDigestAuthentication

### <a name="windows10endpointprotectionconfigurationsmartscreenblockoverrideforfiles"></a>Windows10EndpointProtectionConfiguration.SmartScreenBlockOverrideForFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/DeviceGuard/RequirePlatformSecurityFeatures

### <a name="windows10endpointprotectionconfigurationsmartscreenenableinshell"></a>Windows10EndpointProtectionConfiguration.SmartScreenEnableInShell 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/SmartScreen/EnableSmartScreenInShell

### <a name="windows10endpointprotectionconfigurationsolicitedremoteassistance"></a>windows10endpointprotectionconfiguration.solicitedRemoteAssistance 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/RemoteAssistance/SolicitedRemoteAssistance

### <a name="windows10endpointprotectionconfigurationuserrightsaccesscredentialmanagerastrustedcaller"></a>Windows10EndpointProtectionConfiguration.UserRightsAccessCredentialManagerAsTrustedCaller 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/AccessCredentialManagerAsTrustedCaller

### <a name="windows10endpointprotectionconfigurationuserrightsaccessfromnetwork"></a>windows10EndpointProtectionConfiguration.UserRightsAccessFromNetwork 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/AccessFromNetwork

### <a name="windows10endpointprotectionconfigurationuserrightsactaspartoftheoperatingsystem"></a>Windows10EndpointProtectionConfiguration.userRightsActAsPartOfTheOperatingSystem 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ActAsPartOfTheOperatingSystem

### <a name="windows10endpointprotectionconfigurationuserrightsallowaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration.UserRightsAllowAccessFromNetwork 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/AccessFromNetwork

### <a name="windows10endpointprotectionconfigurationuserrightsbackupdata"></a>Windows10EndpointProtectionConfiguration.UserRightsBackupData 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/BackupFilesAndDirectories

### <a name="windows10endpointprotectionconfigurationuserrightsblockaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration.UserRightsBlockAccessFromNetwork 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/DenyAccessFromNetwork

### <a name="windows10endpointprotectionconfigurationuserrightschangesystemtime"></a>Windows10EndpointProtectionConfiguration.UserRightsChangeSystemTime 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ChangeSystemTime

### <a name="windows10endpointprotectionconfigurationuserrightscreateglobalobjects"></a>Windows10EndpointProtectionConfiguration.UserRightsCreateGlobalObjects 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/CreateGlobalObjects

### <a name="windows10endpointprotectionconfigurationuserrightscreatepagefile"></a>Windows10EndpointProtectionConfiguration.UserRightsCreatePageFile 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/CreatePageFile

### <a name="windows10endpointprotectionconfigurationuserrightscreatepermanentsharedobjects"></a>Windows10EndpointProtectionConfiguration.UserRightsCreatePermanentSharedObjects 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/CreatePermanentSharedObjects

### <a name="windows10endpointprotectionconfigurationuserrightscreatesymboliclinks"></a>Windows10EndpointProtectionConfiguration.UserRightsCreateSymbolicLinks 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/CreateSymbolicLinks

### <a name="windows10endpointprotectionconfigurationuserrightscreatetoken"></a>Windows10EndpointProtectionConfiguration.UserRightsCreateToken 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/CreateToken

### <a name="windows10endpointprotectionconfigurationuserrightsdebugprograms"></a>Windows10EndpointProtectionConfiguration.UserRightsDebugPrograms 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/DebugPrograms

### <a name="windows10endpointprotectionconfigurationuserrightsdelegation"></a>Windows10EndpointProtectionConfiguration.UserRightsDelegation 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/EnableDelegation

### <a name="windows10endpointprotectionconfigurationuserrightsdenyaccessfromnetwork"></a>windows10EndpointProtectionConfiguration.UserRightsDenyAccessFromNetwork 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/DenyAccessFromNetwork

### <a name="windows10endpointprotectionconfigurationuserrightsgeneratesecurityaudits"></a>Windows10EndpointProtectionConfiguration.UserRightsGenerateSecurityAudits 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/GenerateSecurityAudits

### <a name="windows10endpointprotectionconfigurationuserrightsimpersonateclient"></a>Windows10EndpointProtectionConfiguration.UserRightsImpersonateClient 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ImpersonateClient

### <a name="windows10endpointprotectionconfigurationuserrightsincreaseschedulingpriority"></a>Windows10EndpointProtectionConfiguration.UserRightsIncreaseSchedulingPriority 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/IncreaseSchedulingPriority

### <a name="windows10endpointprotectionconfigurationuserrightsloadunloaddrivers"></a>Windows10EndpointProtectionConfiguration.UserRightsLoadUnloadDrivers 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/LoadUnloadDeviceDrivers

### <a name="windows10endpointprotectionconfigurationuserrightslocallogon"></a>Windows10EndpointProtectionConfiguration.UserRightsLocalLogOn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/AllowLocalLogOn

### <a name="windows10endpointprotectionconfigurationuserrightslockmemory"></a>Windows10EndpointProtectionConfiguration.UserRightsLockMemory 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/LockMemory

### <a name="windows10endpointprotectionconfigurationuserrightsmanageauditingandsecuritylogs"></a>Windows10EndpointProtectionConfiguration.UserRightsManageAuditingAndSecurityLogs 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ManageAuditingAndSecurityLog

### <a name="windows10endpointprotectionconfigurationuserrightsmanagevolumes"></a>Windows10EndpointProtectionConfiguration.UserRightsManageVolumes 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ManageVolume

### <a name="windows10endpointprotectionconfigurationuserrightsmodifyfirmwareenvironment"></a>Windows10EndpointProtectionConfiguration.UserRightsModifyFirmwareEnvironment 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ModifyFirmwareEnvironment

### <a name="windows10endpointprotectionconfigurationuserrightsmodifyobjectlabels"></a>Windows10EndpointProtectionConfiguration.UserRightsModifyObjectLabels 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ModifyObjectLabel

### <a name="windows10endpointprotectionconfigurationuserrightsprofilesingleprocess"></a>Windows10EndpointProtectionConfiguration.UserRightsProfileSingleProcess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/ProfileSingleProcess

### <a name="windows10endpointprotectionconfigurationuserrightsregisterprocessasservice"></a>Windows10EndpointProtectionConfiguration.UserRightsRegisterProcessAsService 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/DenyLocalLogOn

### <a name="windows10endpointprotectionconfigurationuserrightsremotedesktopserviceslogon"></a>Windows10EndpointProtectionConfiguration.UserRightsRemoteDesktopServicesLogOn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/DenyRemoteDesktopServicesLogOn

### <a name="windows10endpointprotectionconfigurationuserrightsremoteshutdown"></a>Windows10EndpointProtectionConfiguration.UserRightsRemoteShutdown 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/RemoteShutdown

### <a name="windows10endpointprotectionconfigurationuserrightsrestoredata"></a>Windows10EndpointProtectionConfiguration.UserRightsRestoreData 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/RestoreFilesAndDirectories

### <a name="windows10endpointprotectionconfigurationuserrightstakeownership"></a>Windows10EndpointProtectionConfiguration.UserRightsTakeOwnership 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/UserRights/TakeOwnership

### <a name="windows10endpointprotectionconfigurationwindowsconnectionmanagerconnectiontonondomainnetworks"></a>Windows10EndpointProtectionConfiguration.WindowsConnectionManagerConnectionToNonDomainNetworks 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsConnectionManager/ProhitConnectionToNonDomainNetworksWhenConnectedToDomainAuthenticatedNetwork

### <a name="windows10endpointprotectionconfigurationwindowslogonsigninlastinteractiveuseraftersysteminitiatedrestart"></a>Windows10EndpointProtectionConfiguration.WindowsLogOnSignInLastInteractiveUserAfterSystemInitiatedRestart 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsLogon/SignInLastInteractiveUserAutomaticallyAfterASystemInitiatedRestart

### <a name="windows10endpointprotectionconfigurationxboxservicesaccessorymanagementservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesAccessoryManagementServiceStartupMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/SystemServices/ConfigureXboxAccessoryManagementServiceStartupMode

### <a name="windows10endpointprotectionconfigurationxboxservicesenablexboxgamesavetask"></a>Windows10EndpointProtectionConfiguration.XboxServicesEnableXboxGameSaveTask 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/TaskScheduler/EnableXboxGameSaveTask

### <a name="windows10endpointprotectionconfigurationxboxservicesliveauthmanagerservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveAuthManagerServiceStartupMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/SystemServices/ConfigureXboxLiveAuthManagerServiceStartupMode

### <a name="windows10endpointprotectionconfigurationxboxserviceslivegamesaveservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveGameSaveServiceStartupMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/SystemServices/XboxServicesLiveGameSaveServiceStartupMode

### <a name="windows10endpointprotectionconfigurationxboxserviceslivenetworkingservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveNetworkingServiceStartupMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/SystemServices/ConfigureXboxLiveNetworkingServiceStartupMode

### <a name="windows10enterprisemodernappmanagementconfigurationuninstallbuiltinapps"></a>Windows10EnterpriseModernAppManagementConfiguration.UninstallBuiltInApps
**Dostawca usług konfiguracji**: Nie dotyczy — tylko wywołanie interfejsu Graph API **Identyfikator URI przesunięcia**: Tylko wywołanie interfejsu Graph API

### <a name="windows10generalconfigurationaccountsblockaddingnonmicrosoftaccountemail"></a>Windows10GeneralConfiguration.AccountsBlockAddingNonMicrosoftAccountEmail 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Accounts/AllowAddingNonMicrosoftAccountsManually

### <a name="windows10generalconfigurationantitheftmodeblocked"></a>Windows10GeneralConfiguration.AntiTheftModeBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Security/AntiTheftMode

### <a name="windows10generalconfigurationappmanagementmsiallowusercontroloverinstall"></a>Windows10GeneralConfiguration.AppManagementMSIAllowUserControlOverInstall 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/MSIAllowUserControlOverInstall

### <a name="windows10generalconfigurationappmanagementmsialwaysinstallwithelevatedprivileges"></a>Windows10GeneralConfiguration.AppManagementMSIAlwaysInstallWithElevatedPrivileges 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges

### <a name="windows10generalconfigurationappsallowtrustedappssideloading"></a>Windows10GeneralConfiguration.AppsAllowTrustedAppsSideloading 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/AllowAllTrustedApps

### <a name="windows10generalconfigurationappsblockwindowsstoreoriginatedapps"></a>Windows10GeneralConfiguration.AppsBlockWindowsStoreOriginatedApps 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/DisableStoreOriginatedApps

### <a name="windows10generalconfigurationappsmicrosoftaccountsoptional"></a>Windows10GeneralConfiguration.AppsMicrosoftAccountsOptional 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/AppRuntime/AllowMicrosoftAccountsToBeOptional

### <a name="windows10generalconfigurationassignedaccessmultimodeprofiles"></a>Windows10GeneralConfiguration.AssignedAccessMultiModeProfiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/AssignedAccess  
**Identyfikator URI przesunięcia**: /Configuration

### <a name="windows10generalconfigurationassignedaccesssinglemodeappusermodelid"></a>Windows10GeneralConfiguration.AssignedAccessSingleModeAppUserModelId 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/AssignedAccess  
**Identyfikator URI przesunięcia**: /Configuration

### <a name="windows10generalconfigurationassignedaccesssinglemodeusername"></a>Windows10GeneralConfiguration.AssignedAccessSingleModeUserName 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/AssignedAccess  
**Identyfikator URI przesunięcia**: /Configuration

### <a name="windows10generalconfigurationauthenticationallowfidodevice"></a>Windows10GeneralConfiguration.AuthenticationAllowFIDODevice 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Authentication/AllowFidoDeviceSignon

### <a name="windows10generalconfigurationauthenticationallowsecondarydevice"></a>Windows10GeneralConfiguration.AuthenticationAllowSecondaryDevice 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Authentication/AllowSecondaryAuthenticationDevice

### <a name="windows10generalconfigurationauthenticationpreferredazureadtenantdomainname"></a>Windows10GeneralConfiguration.AuthenticationPreferredAzureADTenantDomainName 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Authentication/PreferredAadTenantDomainName

### <a name="windows10generalconfigurationauthenticationwebsignin"></a>Windows10GeneralConfiguration.AuthenticationWebSignIn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Authentication/EnableWebSignIn

### <a name="windows10generalconfigurationautoplaydefaultautorunbehavior"></a>Windows10GeneralConfiguration.AutoPlayDefaultAutoRunBehavior 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Autoplay/SetDefaultAutoRunBehavior

### <a name="windows10generalconfigurationautoplayfornonvolumedevices"></a>Windows10GeneralConfiguration.AutoPlayForNonVolumeDevices 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Autoplay/DisallowAutoplayForNonVolumeDevices

### <a name="windows10generalconfigurationautoplaymode"></a>Windows10GeneralConfiguration.AutoPlayMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Autoplay/TurnOffAutoPlay

### <a name="windows10generalconfigurationbluetoothallowedservices"></a>Windows10GeneralConfiguration.BluetoothAllowedServices 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Bluetooth/ServicesAllowedList

### <a name="windows10generalconfigurationbluetoothblockadvertising"></a>Windows10GeneralConfiguration.BluetoothBlockAdvertising 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Bluetooth/AllowAdvertising

### <a name="windows10generalconfigurationbluetoothblockdiscoverablemode"></a>Windows10GeneralConfiguration.BluetoothBlockDiscoverableMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Bluetooth/AllowDiscoverableMode

### <a name="windows10generalconfigurationbluetoothblocked"></a>Windows10GeneralConfiguration.BluetoothBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowBluetooth

### <a name="windows10generalconfigurationbluetoothblockprepairing"></a>Windows10GeneralConfiguration.BluetoothBlockPrePairing 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Bluetooth/AllowPrepairing

### <a name="windows10generalconfigurationbluetoothblockpromptedproximalconnections"></a>Windows10GeneralConfiguration.BluetoothBlockPromptedProximalConnections 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Bluetooth/AllowPromptedProximalConnections

### <a name="windows10generalconfigurationbluetoothdevicename"></a>Windows10GeneralConfiguration.BluetoothDeviceName 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Bluetooth/LocalDeviceName

### <a name="windows10generalconfigurationbootstartdriverinitialization"></a>windows10generalconfiguration.bootStartDriverInitialization 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/BootStartDriverInitialization

### <a name="windows10generalconfigurationcamerablocked"></a>Windows10GeneralConfiguration.CameraBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Camera/AllowCamera

### <a name="windows10generalconfigurationcellularblockdatawhenroaming"></a>Windows10GeneralConfiguration.CellularBlockDataWhenRoaming 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowCellularDataRoaming

### <a name="windows10generalconfigurationcellularblockvpn"></a>Windows10GeneralConfiguration.CellularBlockVpn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowVPNOverCellular

### <a name="windows10generalconfigurationcellularblockvpnwhenroaming"></a>Windows10GeneralConfiguration.CellularBlockVpnWhenRoaming 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowVPNRoamingOverCellular

### <a name="windows10generalconfigurationcellulardata"></a>Windows10GeneralConfiguration.CellularData 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowCellularData

### <a name="windows10generalconfigurationcertificatesblockmanualrootcertificateinstallation"></a>Windows10GeneralConfiguration.CertificatesBlockManualRootCertificateInstallation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Security/AllowManualRootCertificateInstallation

### <a name="windows10generalconfigurationconnecteddevicesserviceblocked"></a>Windows10GeneralConfiguration.ConnectedDevicesServiceBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowConnectedDevices

### <a name="windows10generalconfigurationcopypasteblocked"></a>Windows10GeneralConfiguration.CopyPasteBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowCopyPaste

### <a name="windows10generalconfigurationcortanablocked"></a>Windows10GeneralConfiguration.CortanaBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/AboveLock/AllowCortanaAboveLock

### <a name="windows10generalconfigurationcryptographyallowfipsalgorithmpolicy"></a>Windows10GeneralConfiguration.CryptographyAllowFipsAlgorithmPolicy 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Cryptography/AllowFipsAlgorithmPolicy

### <a name="windows10generalconfigurationdataprotectionblockdirectmemoryaccess"></a>Windows10GeneralConfiguration.DataProtectionBlockDirectMemoryAccess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DataProtection/AllowDirectMemoryAccess

### <a name="windows10generalconfigurationdefenderblockenduseraccess"></a>Windows10GeneralConfiguration.DefenderBlockEndUserAccess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowUserUIAccess

### <a name="windows10generalconfigurationdefenderblockonaccessprotection"></a>Windows10GeneralConfiguration.DefenderBlockOnAccessProtection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowOnAccessProtection

### <a name="windows10generalconfigurationdefendercloudblocklevel"></a>Windows10GeneralConfiguration.DefenderCloudBlockLevel 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/CloudBlockLevel

### <a name="windows10generalconfigurationdefendercloudextendedtimeout"></a>Windows10GeneralConfiguration.DefenderCloudExtendedTimeout 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/CloudExtendedTimeout

### <a name="windows10generalconfigurationdefendercloudextendedtimeoutinseconds"></a>Windows10GeneralConfiguration.DefenderCloudExtendedTimeoutInSeconds 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/CloudExtendedTimeout

### <a name="windows10generalconfigurationdefenderdaysbeforedeletingquarantinedmalware"></a>Windows10GeneralConfiguration.DefenderDaysBeforeDeletingQuarantinedMalware 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/DaysToRetainCleanedMalware

### <a name="windows10generalconfigurationdefenderdetectedmalwareactions"></a>Windows10GeneralConfiguration.DefenderDetectedMalwareActions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ThreatSeverityDefaultAction

### <a name="windows10generalconfigurationdefenderfileextensionstoexclude"></a>Windows10GeneralConfiguration.DefenderFileExtensionsToExclude 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ExcludedExtensions

### <a name="windows10generalconfigurationdefenderfilesandfolderstoexclude"></a>Windows10GeneralConfiguration.DefenderFilesAndFoldersToExclude 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ExcludedPaths

### <a name="windows10generalconfigurationdefendermonitorfileactivity"></a>Windows10GeneralConfiguration.DefenderMonitorFileActivity 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowRealtimeMonitoring

### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappaction"></a>Windows10GeneralConfiguration.DefenderPotentiallyUnwantedAppAction 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/PUAProtection

### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappactionsetting"></a>Windows10GeneralConfiguration.DefenderPotentiallyUnwantedAppActionSetting 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/PUAProtection

### <a name="windows10generalconfigurationdefenderprocessestoexclude"></a>Windows10GeneralConfiguration.DefenderProcessesToExclude 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ExcludedProcesses

### <a name="windows10generalconfigurationdefenderpromptforsamplesubmission"></a>Windows10GeneralConfiguration.DefenderPromptForSampleSubmission 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/SubmitSamplesConsent

### <a name="windows10generalconfigurationdefenderrequirebehaviormonitoring"></a>Windows10GeneralConfiguration.DefenderRequireBehaviorMonitoring 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowBehaviorMonitoring

### <a name="windows10generalconfigurationdefenderrequirecloudprotection"></a>Windows10GeneralConfiguration.DefenderRequireCloudProtection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowCloudProtection

### <a name="windows10generalconfigurationdefenderrequirenetworkinspectionsystem"></a>Windows10GeneralConfiguration.DefenderRequireNetworkInspectionSystem 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowIntrusionPreventionSystem

### <a name="windows10generalconfigurationdefenderrequirerealtimemonitoring"></a>Windows10GeneralConfiguration.DefenderRequireRealTimeMonitoring 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowRealtimeMonitoring

### <a name="windows10generalconfigurationdefenderscanarchivefiles"></a>Windows10GeneralConfiguration.DefenderScanArchiveFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowArchiveScanning

### <a name="windows10generalconfigurationdefenderscandownloads"></a>Windows10GeneralConfiguration.DefenderScanDownloads 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowIOAVProtection

### <a name="windows10generalconfigurationdefenderscanincomingmail"></a>Windows10GeneralConfiguration.DefenderScanIncomingMail 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowScanningNetworkFiles

### <a name="windows10generalconfigurationdefenderscanmappednetworkdrivesduringfullscan"></a>Windows10GeneralConfiguration.DefenderScanMappedNetworkDrivesDuringFullScan 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowFullScanOnMappedNetworkDrives

### <a name="windows10generalconfigurationdefenderscanmaxcpu"></a>Windows10GeneralConfiguration.DefenderScanMaxCpu 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AvgCPULoadFactor

### <a name="windows10generalconfigurationdefenderscannetworkfiles"></a>Windows10GeneralConfiguration.DefenderScanNetworkFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowScanningNetworkFiles

### <a name="windows10generalconfigurationdefenderscanremovabledrivesduringfullscan"></a>Windows10GeneralConfiguration.DefenderScanRemovableDrivesDuringFullScan 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowFullScanRemovableDriveScanning

### <a name="windows10generalconfigurationdefenderscanscriptsloadedininternetexplorer"></a>Windows10GeneralConfiguration.DefenderScanScriptsLoadedInInternetExplorer 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/AllowScriptScanning

### <a name="windows10generalconfigurationdefenderscantype"></a>Windows10GeneralConfiguration.DefenderScanType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ScanParameter

### <a name="windows10generalconfigurationdefenderscheduledquickscantime"></a>Windows10GeneralConfiguration.DefenderScheduledQuickScanTime 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ScheduleQuickScanTime

### <a name="windows10generalconfigurationdefenderscheduledscantime"></a>Windows10GeneralConfiguration.DefenderScheduledScanTime 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ScheduleScanTime

### <a name="windows10generalconfigurationdefenderschedulescanday"></a>Windows10GeneralConfiguration.DefenderScheduleScanDay 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ScheduleScanDay

### <a name="windows10generalconfigurationdefendersignatureupdateintervalinhours"></a>Windows10GeneralConfiguration.DefenderSignatureUpdateIntervalInHours 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/SignatureUpdateInterval

### <a name="windows10generalconfigurationdefendersubmitsamplesconsenttype"></a>Windows10GeneralConfiguration.DefenderSubmitSamplesConsentType 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/SubmitSamplesConsent

### <a name="windows10generalconfigurationdefendersystemscanschedule"></a>Windows10GeneralConfiguration.DefenderSystemScanSchedule 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Defender/ScheduleScanDay

### <a name="windows10generalconfigurationdeveloperunlocksetting"></a>Windows10GeneralConfiguration.DeveloperUnlockSetting 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/AllowDeveloperUnlock

### <a name="windows10generalconfigurationdevicemanagementblockfactoryresetonmobile"></a>Windows10GeneralConfiguration.DeviceManagementBlockFactoryResetOnMobile 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/AllowUserToResetPhone

### <a name="windows10generalconfigurationdevicemanagementblockmanualunenroll"></a>Windows10GeneralConfiguration.DeviceManagementBlockManualUnenroll 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowManualMDMUnenrollment

### <a name="windows10generalconfigurationdiagnosticsdatasubmissionmode"></a>Windows10GeneralConfiguration.DiagnosticsDataSubmissionMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/AllowTelemetry

### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedoff"></a>Windows10GeneralConfiguration.DisplayAppListWithGdiDPIScalingTurnedOff 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Display/TurnOffGdiDPIScalingForApps

### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedon"></a>Windows10GeneralConfiguration.DisplayAppListWithGdiDPIScalingTurnedOn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Display/TurnOnGdiDPIScalingForApps

### <a name="windows10generalconfigurationedgeallowstartpagesmodification"></a>Windows10GeneralConfiguration.EdgeAllowStartPagesModification 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/HomePages

### <a name="windows10generalconfigurationedgeblockaccesstoaboutflags"></a>Windows10GeneralConfiguration.EdgeBlockAccessToAboutFlags 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventAccessToAboutFlagsInMicrosoftEdge

### <a name="windows10generalconfigurationedgeblockaddressbardropdown"></a>Windows10GeneralConfiguration.EdgeBlockAddressBarDropdown 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowAddressBarDropdown

### <a name="windows10generalconfigurationedgeblockautofill"></a>Windows10GeneralConfiguration.EdgeBlockAutofill 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowAutofill

### <a name="windows10generalconfigurationedgeblockcompatibilitylist"></a>Windows10GeneralConfiguration.EdgeBlockCompatibilityList 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowMicrosoftCompatibilityList

### <a name="windows10generalconfigurationedgeblockdevelopertools"></a>Windows10GeneralConfiguration.EdgeBlockDeveloperTools 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowDeveloperTools

### <a name="windows10generalconfigurationedgeblocked"></a>Windows10GeneralConfiguration.EdgeBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowBrowser

### <a name="windows10generalconfigurationedgeblockeditfavorites"></a>Windows10GeneralConfiguration.EdgeBlockEditFavorites 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/LockdownFavorites

### <a name="windows10generalconfigurationedgeblockextensions"></a>Windows10GeneralConfiguration.EdgeBlockExtensions 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowExtensions

### <a name="windows10generalconfigurationedgeblockfullscreenmode"></a>Windows10GeneralConfiguration.EdgeBlockFullScreenMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowFullScreenMode

### <a name="windows10generalconfigurationedgeblockinprivatebrowsing"></a>Windows10GeneralConfiguration.EdgeBlockInPrivateBrowsing 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowInPrivate

### <a name="windows10generalconfigurationedgeblocklivetiledatacollection"></a>Windows10GeneralConfiguration.EdgeBlockLiveTileDataCollection 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventLiveTileDataCollection

### <a name="windows10generalconfigurationedgeblockpasswordmanager"></a>Windows10GeneralConfiguration.EdgeBlockPasswordManager 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowPasswordManager

### <a name="windows10generalconfigurationedgeblockpopups"></a>Windows10GeneralConfiguration.EdgeBlockPopups 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowPopups

### <a name="windows10generalconfigurationedgeblockprelaunch"></a>Windows10GeneralConfiguration.EdgeBlockPrelaunch 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowPrelaunch

### <a name="windows10generalconfigurationedgeblockprinting"></a>Windows10GeneralConfiguration.EdgeBlockPrinting 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowPrinting

### <a name="windows10generalconfigurationedgeblocksavinghistory"></a>Windows10GeneralConfiguration.EdgeBlockSavingHistory 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowSavingHistory

### <a name="windows10generalconfigurationedgeblocksearchsuggestions"></a>Windows10GeneralConfiguration.EdgeBlockSearchSuggestions 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowSearchSuggestionsinAddressBar

### <a name="windows10generalconfigurationedgeblocksendingdonottrackheader"></a>Windows10GeneralConfiguration.EdgeBlockSendingDoNotTrackHeader 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowDoNotTrack

### <a name="windows10generalconfigurationedgeblocksendingintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration.EdgeBlockSendingIntranetTrafficToInternetExplorer 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SendIntranetTraffictoInternetExplorer

### <a name="windows10generalconfigurationedgeblocksideloadingextensions"></a>Windows10GeneralConfiguration.EdgeBlockSideloadingExtensions 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowSideloadingOfExtensions

### <a name="windows10generalconfigurationedgeblocktabpreloading"></a>Windows10GeneralConfiguration.EdgeBlockTabPreloading 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowTabPreloading

### <a name="windows10generalconfigurationedgeblockwebcontentonnewtabpage"></a>Windows10GeneralConfiguration.EdgeBlockWebContentOnNewTabPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowWebContentOnNewTabPage

### <a name="windows10generalconfigurationedgeclearbrowsingdataonexit"></a>Windows10GeneralConfiguration.EdgeClearBrowsingDataOnExit 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ClearBrowsingDataOnExit

### <a name="windows10generalconfigurationedgecookiepolicy"></a>Windows10GeneralConfiguration.EdgeCookiePolicy 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowCookies

### <a name="windows10generalconfigurationedgedisablefirstrunpage"></a>Windows10GeneralConfiguration.EdgeDisableFirstRunPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventFirstRunPage

### <a name="windows10generalconfigurationedgeenterprisemodesitelistlocation"></a>Windows10GeneralConfiguration.EdgeEnterpriseModeSiteListLocation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/EnterpriseSiteListServiceUrl

### <a name="windows10generalconfigurationedgefavoritesbarvisibility"></a>Windows10GeneralConfiguration.EdgeFavoritesBarVisibility 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ConfigureFavoritesBar

### <a name="windows10generalconfigurationedgefavoriteslistlocation"></a>Windows10GeneralConfiguration.EdgeFavoritesListLocation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ProvisionFavorites

### <a name="windows10generalconfigurationedgefirstrunurl"></a>Windows10GeneralConfiguration.EdgeFirstRunUrl 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/FirstRunURL

### <a name="windows10generalconfigurationedgehomebuttonconfiguration"></a>Windows10GeneralConfiguration.EdgeHomeButtonConfiguration 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SetHomeButtonURL

### <a name="windows10generalconfigurationedgehomebuttonconfigurationenabled"></a>Windows10GeneralConfiguration.EdgeHomeButtonConfigurationEnabled 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ConfigureHomeButton

### <a name="windows10generalconfigurationedgehomepageurls"></a>Windows10GeneralConfiguration.EdgeHomepageUrls 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SetHomeButtonURL

### <a name="windows10generalconfigurationedgenewtabpageurl"></a>Windows10GeneralConfiguration.EdgeNewTabPageURL 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SetNewTabPageURL

### <a name="windows10generalconfigurationedgeopenswith"></a>Windows10GeneralConfiguration.EdgeOpensWith 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ConfigureOpenMicrosoftEdgeWith

### <a name="windows10generalconfigurationedgepreventcertificateerroroverride"></a>Windows10GeneralConfiguration.EdgePreventCertificateErrorOverride 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventCertErrorOverrides

### <a name="windows10generalconfigurationedgerequiresmartscreen"></a>Windows10GeneralConfiguration.EdgeRequireSmartScreen 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/AllowSmartScreen

### <a name="windows10generalconfigurationedgesearchengine"></a>Windows10GeneralConfiguration.EdgeSearchEngine 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SetDefaultSearchEngine

### <a name="windows10generalconfigurationedgesendintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration.EdgeSendIntranetTrafficToInternetExplorer 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SendIntranetTraffictoInternetExplorer

### <a name="windows10generalconfigurationedgeshowmessagewhenopeninginternetexplorersites"></a>Windows10GeneralConfiguration.EdgeShowMessageWhenOpeningInternetExplorerSites 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ShowMessageWhenOpeningSitesInInternetExplorer

### <a name="windows10generalconfigurationedgesyncfavoriteswithinternetexplorer"></a>Windows10GeneralConfiguration.EdgeSyncFavoritesWithInternetExplorer 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/SyncFavoritesBetweenIEAndMicrosoftEdge

### <a name="windows10generalconfigurationedgetelemetryformicrosoft365analytics"></a>Windows10GeneralConfiguration.EdgeTelemetryForMicrosoft365Analytics 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ConfigureTelemetryForMicrosoft365Analytics

### <a name="windows10generalconfigurationenableautomaticredeployment"></a>Windows10GeneralConfiguration.EnableAutomaticRedeployment 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/CredentialProviders/DisableAutomaticReDeploymentCredentials

### <a name="windows10generalconfigurationenterprisecloudprintdiscoveryendpoint"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintDiscoveryEndPoint 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EnterpriseCloudPrint/CloudPrinterDiscoveryEndPoint

### <a name="windows10generalconfigurationenterprisecloudprintdiscoverymaxlimit"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintDiscoveryMaxLimit 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EnterpriseCloudPrint/DiscoveryMaxPrinterLimit

### <a name="windows10generalconfigurationenterprisecloudprintmopriadiscoveryresourceidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintMopriaDiscoveryResourceIdentifier 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EnterpriseCloudPrint/MopriaDiscoveryResourceId

### <a name="windows10generalconfigurationenterprisecloudprintoauthauthority"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintOAuthAuthority 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EnterpriseCloudPrint/CloudPrintOAuthAuthority

### <a name="windows10generalconfigurationenterprisecloudprintoauthclientidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintOAuthClientIdentifier 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EnterpriseCloudPrint/CloudPrintOAuthAuthority

### <a name="windows10generalconfigurationenterprisecloudprintresourceidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintResourceIdentifier 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/EnterpriseCloudPrint/CloudPrintResourceId

### <a name="windows10generalconfigurationexperienceblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration.ExperienceBlockConsumerSpecificFeatures 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsConsumerFeatures

### <a name="windows10generalconfigurationexperienceblockdevicediscovery"></a>Windows10GeneralConfiguration.ExperienceBlockDeviceDiscovery 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowDeviceDiscovery

### <a name="windows10generalconfigurationexperienceblockerrordialogwhennosim"></a>Windows10GeneralConfiguration.ExperienceBlockErrorDialogWhenNoSIM 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowSIMErrorDialogPromptWhenNoSIM

### <a name="windows10generalconfigurationexperienceblocktaskswitcher"></a>Windows10GeneralConfiguration.ExperienceBlockTaskSwitcher 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowTaskSwitcher

### <a name="windows10generalconfigurationexperienceblockwindowsspotlight"></a>Windows10GeneralConfiguration.ExperienceBlockWindowsSpotlight 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsSpotlight

### <a name="windows10generalconfigurationexperiencedonotsyncbrowsersettings"></a>Windows10GeneralConfiguration.ExperienceDoNotSyncBrowserSettings 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/DoNotSyncBrowserSettings

### <a name="windows10generalconfigurationgamedvrblocked"></a>Windows10GeneralConfiguration.GameDvrBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/AllowGameDVR

### <a name="windows10generalconfigurationhardwaredeviceinstallationbydeviceidentifiers"></a>Windows10GeneralConfiguration.HardwareDeviceInstallationByDeviceIdentifiers 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceIDs

### <a name="windows10generalconfigurationhardwaredeviceinstallationbysetupclasses"></a>Windows10GeneralConfiguration.HardwareDeviceInstallationBySetupClasses 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceSetupClasses

### <a name="windows10generalconfigurationinkworkspaceaccess"></a>Windows10GeneralConfiguration.InkWorkspaceAccess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsInkWorkspace/AllowWindowsInkWorkspace

### <a name="windows10generalconfigurationinkworkspaceaccessstate"></a>Windows10GeneralConfiguration.InkWorkspaceAccessState 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsInkWorkspace/AllowWindowsInkWorkspace

### <a name="windows10generalconfigurationinkworkspaceblocksuggestedapps"></a>Windows10GeneralConfiguration.InkWorkspaceBlockSuggestedApps 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsInkWorkspace/AllowSuggestedAppsInWindowsInkWorkspace

### <a name="windows10generalconfigurationinternetexploreractivexcontrolsinprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerActiveXControlsInProtectedMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DoNotAllowActiveXControlsInProtectedMode

### <a name="windows10generalconfigurationinternetexplorerautocomplete"></a>Windows10GeneralConfiguration.InternetExplorerAutoComplete 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/AllowAutoComplete

### <a name="windows10generalconfigurationinternetexplorerblockoutdatedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerBlockOutdatedActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DoNotBlockOutdatedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarnings"></a>Windows10GeneralConfiguration.InternetExplorerBypassSmartScreenWarnings 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableBypassOfSmartScreenWarnings

### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarningsaboutuncommonfiles"></a>Windows10GeneralConfiguration.InternetExplorerBypassSmartScreenWarningsAboutUncommonFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableBypassOfSmartScreenWarningsAboutUncommonFiles

### <a name="windows10generalconfigurationinternetexplorercertificateaddressmismatchwarning"></a>Windows10GeneralConfiguration.InternetExplorerCertificateAddressMismatchWarning 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/AllowCertificateAddressMismatchWarning

### <a name="windows10generalconfigurationinternetexplorercheckservercertificaterevocation"></a>Windows10GeneralConfiguration.InternetExplorerCheckServerCertificateRevocation 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/CheckServerCertificateRevocation

### <a name="windows10generalconfigurationinternetexplorerchecksignaturesondownloadedprograms"></a>Windows10GeneralConfiguration.InternetExplorerCheckSignaturesOnDownloadedPrograms 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/CheckSignaturesOnDownloadedPrograms

### <a name="windows10generalconfigurationinternetexplorercrashdetection"></a>Windows10GeneralConfiguration.InternetExplorerCrashDetection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableCrashDetection

### <a name="windows10generalconfigurationinternetexplorerdisableprocessesinenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerDisableProcessesInEnhancedProtectedMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableProcessesInEnhancedProtectedMode

### <a name="windows10generalconfigurationinternetexplorerdownloadenclosures"></a>Windows10GeneralConfiguration.InternetExplorerDownloadEnclosures 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableEnclosureDownloading

### <a name="windows10generalconfigurationinternetexplorerencryptionsupport"></a>Windows10GeneralConfiguration.InternetExplorerEncryptionSupport 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableEncryptionSupport

### <a name="windows10generalconfigurationinternetexplorerenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerEnhancedProtectedMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/AllowEnhancedProtectedMode

### <a name="windows10generalconfigurationinternetexplorerfallbacktossl3"></a>Windows10GeneralConfiguration.InternetExplorerFallbackToSsl3 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/AllowFallbackToSSL3

### <a name="windows10generalconfigurationinternetexplorerignorecertificateerrors"></a>Windows10GeneralConfiguration.InternetExplorerIgnoreCertificateErrors 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableIgnoringCertificateErrors

### <a name="windows10generalconfigurationinternetexplorerincludeallnetworkpaths"></a>Windows10GeneralConfiguration.InternetExplorerIncludeAllNetworkPaths 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/IncludeAllNetworkPaths

### <a name="windows10generalconfigurationinternetexplorerinternetzoneaccesstodatasources"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAccessToDataSources 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowAccessToDataSources

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowvbscripttorun"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowVBScriptToRun 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowVBScriptToRunInInternetExplorer

### <a name="windows10generalconfigurationinternetexplorerinternetzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAutomaticPromptForFileDownloads 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowAutomaticPromptingForFileDownloads

### <a name="windows10generalconfigurationinternetexplorerinternetzonecopyandpasteviascript"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneCopyAndPasteViaScript 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowCopyPasteViaScript

### <a name="windows10generalconfigurationinternetexplorerinternetzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneCrossSiteScriptingFilter 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneEnableCrossSiteScriptingFilter

### <a name="windows10generalconfigurationinternetexplorerinternetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDoNotRunAntimalwareAgainstActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDotNetFrameworkReliantComponents 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowNETFrameworkReliantComponents

### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadSignedActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneDownloadSignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadUnsignedActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneDownloadUnsignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragAndDropOrCopyAndPasteFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowDragAndDropCopyAndPasteFiles

### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragContentFromDifferentDomainsAcrossWindows 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragContentFromDifferentDomainsWithinWindows 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

### <a name="windows10generalconfigurationinternetexplorerinternetzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneIncludeLocalPathWhenUploadingFilesToServer 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneIncludeLocalPathWhenUploadingFilesToServer

### <a name="windows10generalconfigurationinternetexplorerinternetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneJavaPermissions


### <a name="windows10generalconfigurationinternetexplorerinternetzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLaunchApplicationsAndFilesInAnIFrame 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneLaunchingApplicationsAndFilesInIFRAME

### <a name="windows10generalconfigurationinternetexplorerinternetzonelessprivilegedsites"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLessPrivilegedSites 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowLessPrivilegedSites

### <a name="windows10generalconfigurationinternetexplorerinternetzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLoadingOfXamlFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowLoadingOfXAMLFiles

### <a name="windows10generalconfigurationinternetexplorerinternetzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLogonOptions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneLogonOptions

### <a name="windows10generalconfigurationinternetexplorerinternetzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneNavigateWindowsAndFramesAcrossDifferentDomains 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneNavigateWindowsAndFrames

### <a name="windows10generalconfigurationinternetexplorerinternetzonepopupblocker"></a>Windows10GeneralConfiguration.InternetExplorerInternetZonePopupBlocker 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneUsePopupBlocker

### <a name="windows10generalconfigurationinternetexplorerinternetzoneprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneProtectedMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneEnableProtectedMode

### <a name="windows10generalconfigurationinternetexplorerinternetzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneRunDotNetFrameworkReliantComponentsSignedWithAuthenticode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneScriptingOfWebBrowserControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowScriptingOfInternetExplorerWebBrowserControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneScriptInitiatedWindows 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowScriptInitiatedWindows

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptlets"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneScriptlets 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowScriptlets

### <a name="windows10generalconfigurationinternetexplorerinternetzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneSecurityWarningForPotentiallyUnsafeFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles

### <a name="windows10generalconfigurationinternetexplorerinternetzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneSmartScreen 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowSmartScreenIE

### <a name="windows10generalconfigurationinternetexplorerinternetzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneUpdatesToStatusBarViaScript 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowUpdatesToStatusBarViaScript

### <a name="windows10generalconfigurationinternetexplorerinternetzoneuserdatapersistence"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneUserDataPersistence 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/InternetZoneAllowUserDataPersistence

### <a name="windows10generalconfigurationinternetexplorerintranetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneDoNotRunAntimalwareAgainstActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/IntranetZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerintranetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/IntranetZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorerintranetzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/IntranetZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerLocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLocalMachineZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LocalMachineZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddowninternetzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownInternetZoneSmartScreen 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LockedDownInternetZoneAllowSmartScreenIE

### <a name="windows10generalconfigurationinternetexplorerlockeddownintranetzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownIntranetZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LockedDownIntranetJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddownlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownLocalMachineZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LockedDownLocalMachineZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownRestrictedZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LockedDownRestrictedSitesZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownRestrictedZoneSmartScreen 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LockedDownRestrictedSitesZoneAllowSmartScreenIE

### <a name="windows10generalconfigurationinternetexplorerlockeddowntrustedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerLockedDownTrustedZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/LockedDownTrustedSitesZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerpreventmanagingsmartscreenfilter"></a>Windows10GeneralConfiguration.InternetExplorerPreventManagingSmartScreenFilter 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/PreventManagingSmartScreenFilter

### <a name="windows10generalconfigurationinternetexplorerpreventperuserinstallationofactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerPreventPerUserInstallationOfActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/PreventPerUserInstallationOfActiveXControls

### <a name="windows10generalconfigurationinternetexplorerprocessesconsistentmimehandling"></a>Windows10GeneralConfiguration.InternetExplorerProcessesConsistentMimeHandling 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/ConsistentMimeHandlingInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesmimesniffingsafetyfeature"></a>Windows10GeneralConfiguration.InternetExplorerProcessesMimeSniffingSafetyFeature 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/MimeSniffingSafetyFeatureInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesmkprotocolsecurityrestriction"></a>Windows10GeneralConfiguration.InternetExplorerProcessesMKProtocolSecurityRestriction 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/MKProtocolSecurityRestrictionInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesnotificationbar"></a>Windows10GeneralConfiguration.InternetExplorerProcessesNotificationBar 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/NotificationBarInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesprotectionfromzoneelevation"></a>Windows10GeneralConfiguration.InternetExplorerProcessesProtectionFromZoneElevation 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/ProtectionFromZoneElevationInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictactivexinstall"></a>Windows10GeneralConfiguration.InternetExplorerProcessesRestrictActiveXInstall 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictActiveXInstallInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictfiledownload"></a>Windows10GeneralConfiguration.InternetExplorerProcessesRestrictFileDownload 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictFileDownloadInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesscriptedwindowsecurityrestrictions"></a>Windows10GeneralConfiguration.InternetExplorerProcessesScriptedWindowSecurityRestrictions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/ScriptedWindowSecurityRestrictionsInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerremoverunthistimebuttonforoutdatedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRemoveRunThisTimeButtonForOutdatedActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RemoveRunThisTimeButtonForOutdatedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneaccesstodatasources"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAccessToDataSources 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowAccessToDataSources

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneactivescripting"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneActiveScripting 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowActiveScripting

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowOnlyApprovedDomainsToUseActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowvbscripttorun"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowVBScriptToRun 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowVBScriptToRunInInternetExplorer

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAutomaticPromptForFileDownloads 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowAutomaticPromptingForFileDownloads

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonebinaryandscriptbehaviors"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneBinaryAndScriptBehaviors 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowBinaryAndScriptBehaviors

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecopyandpasteviascript"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneCopyAndPasteViaScript 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowCopyPasteViaScript

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneCrossSiteScriptingFilter 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneEnableCrossSiteScriptingFilter

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDoNotRunAntimalwareAgainstActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDotNetFrameworkReliantComponents 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowNETFrameworkReliantComponents

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadSignedActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneDownloadSignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadUnsignedActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneDownloadUnsignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragAndDropOrCopyAndPasteFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowDragAndDropCopyAndPasteFiles

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragContentFromDifferentDomainsAcrossWindows 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragContentFromDifferentDomainsWithinWindows 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonefiledownloads"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneFileDownloads 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowFileDownloads

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneIncludeLocalPathWhenUploadingFilesToServer 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneIncludeLocalPathWhenUploadingFilesToServer

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLaunchApplicationsAndFilesInAnIFrame 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneLaunchingApplicationsAndFilesInIFRAME

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelessprivilegedsites"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLessPrivilegedSites 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowLessPrivilegedSites

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLoadingOfXamlFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowLoadingOfXAMLFiles

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLogonOptions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneLogonOptions

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonemetarefresh"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneMetaRefresh 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowMETAREFRESH

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneNavigateWindowsAndFramesAcrossDifferentDomains 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneNavigateWindowsAndFrames

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonepopupblocker"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZonePopupBlocker 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneUsePopupBlocker

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneProtectedMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneTurnOnProtectedMode

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerunactivexcontrolsandplugins"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneRunActiveXControlsAndPlugins 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneRunActiveXControlsAndPlugins

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneRunDotNetFrameworkReliantComponentsSignedWithAuthenticode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptactivexcontrolsmarkedsafeforscripting"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptActiveXControlsMarkedSafeForScripting 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofjavaapplets"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptingOfJavaApplets 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneScriptingOfJavaApplets

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptingOfWebBrowserControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowScriptingOfInternetExplorerWebBrowserControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptInitiatedWindows 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowScriptInitiatedWindows

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptlets"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptlets 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowScriptlets

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneSecurityWarningForPotentiallyUnsafeFiles 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneSmartScreen 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowSmartScreenIE

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneUpdatesToStatusBarViaScript 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowUpdatesToStatusBarViaScript

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneuserdatapersistence"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneUserDataPersistence 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/RestrictedSitesZoneAllowUserDataPersistence

### <a name="windows10generalconfigurationinternetexplorersecuritysettingscheck"></a>Windows10GeneralConfiguration.InternetExplorerSecuritySettingsCheck 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DisableSecuritySettingsCheck

### <a name="windows10generalconfigurationinternetexplorersecurityzonesuseonlymachinesettings"></a>Windows10GeneralConfiguration.InternetExplorerSecurityZonesUseOnlyMachineSettings 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/SecurityZonesUseOnlyMachineSettings

### <a name="windows10generalconfigurationinternetexplorersoftwarewhensignatureisinvalid"></a>Windows10GeneralConfiguration.InternetExplorerSoftwareWhenSignatureIsInvalid 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/AllowSoftwareWhenSignatureIsInvalid

### <a name="windows10generalconfigurationinternetexplorertrustedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneDoNotRunAntimalwareAgainstActiveXControls 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorertrustedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/TrustedSitesZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorertrustedzonejavapermissions"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneJavaPermissions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/TrustedSitesZoneJavaPermissions

### <a name="windows10generalconfigurationinternetexploreruseactivexinstallerservice"></a>Windows10GeneralConfiguration.InternetExplorerUseActiveXInstallerService 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/SpecifyUseOfActiveXInstallerService

### <a name="windows10generalconfigurationinternetexplorerusersaddingsites"></a>Windows10GeneralConfiguration.InternetExplorerUsersAddingSites 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DoNotAllowUsersToAddSites

### <a name="windows10generalconfigurationinternetexploreruserschangingpolicies"></a>Windows10GeneralConfiguration.InternetExplorerUsersChangingPolicies 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/InternetExplorer/DoNotAllowUsersToChangePolicies

### <a name="windows10generalconfigurationinternetsharingblocked"></a>Windows10GeneralConfiguration.InternetSharingBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WiFi/AllowInternetSharing

### <a name="windows10generalconfigurationlocationservicesblocked"></a>Windows10GeneralConfiguration.LocationServicesBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/AllowLocation

### <a name="windows10generalconfigurationlockscreenallowtimeoutconfiguration"></a>Windows10GeneralConfiguration.LockScreenAllowTimeoutConfiguration 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/AllowScreenTimeoutWhileLockedUser/Config

### <a name="windows10generalconfigurationlockscreenblockactioncenternotifications"></a>Windows10GeneralConfiguration.LockScreenBlockActionCenterNotifications 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/AboveLock/AllowActionCenterNotifications

### <a name="windows10generalconfigurationlockscreenblockcortana"></a>Windows10GeneralConfiguration.LockScreenBlockCortana 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/AboveLock/AllowCortanaAboveLock

### <a name="windows10generalconfigurationlockscreenblocktoastnotifications"></a>Windows10GeneralConfiguration.LockScreenBlockToastNotifications 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/AboveLock/AllowToasts

### <a name="windows10generalconfigurationlockscreencamera"></a>Windows10GeneralConfiguration.LockScreenCamera 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/PreventEnablingLockScreenCamera

### <a name="windows10generalconfigurationlockscreenhidenetworkselectionui"></a>Windows10GeneralConfiguration.LockScreenHideNetworkSelectionUI 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsLogon/DontDisplayNetworkSelectionUI

### <a name="windows10generalconfigurationlockscreenslideshow"></a>Windows10GeneralConfiguration.LockScreenSlideShow 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/PreventLockScreenSlideShow

### <a name="windows10generalconfigurationlockscreentimeoutinseconds"></a>Windows10GeneralConfiguration.LockScreenTimeoutInSeconds 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/ScreenTimeoutWhileLocked

### <a name="windows10generalconfigurationlogonblockfastuserswitching"></a>Windows10GeneralConfiguration.LogonBlockFastUserSwitching 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsLogon/HideFastUserSwitching

### <a name="windows10generalconfigurationmessagingblockmms"></a>Windows10GeneralConfiguration.MessagingBlockMMS 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Messaging/AllowMMS

### <a name="windows10generalconfigurationmessagingblockrichcommunicationservices"></a>Windows10GeneralConfiguration.MessagingBlockRichCommunicationServices 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Messaging/AllowRCS

### <a name="windows10generalconfigurationmessagingblocksync"></a>Windows10GeneralConfiguration.MessagingBlockSync 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Messaging/AllowMessageSync

### <a name="windows10generalconfigurationmicrosoftaccountblocked"></a>Windows10GeneralConfiguration.MicrosoftAccountBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Accounts/AllowMicrosoftAccountConnection

### <a name="windows10generalconfigurationmicrosoftaccountblocksettingssync"></a>Windows10GeneralConfiguration.MicrosoftAccountBlockSettingsSync 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowSyncMySettings

### <a name="windows10generalconfigurationmicrosoftaccountsigninassistantsettings"></a>Windows10GeneralConfiguration.MicrosoftAccountSignInAssistantSettings 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Accounts  
**Identyfikator URI przesunięcia**: /AllowMicrosoftAccountSignInAssistant

### <a name="windows10generalconfigurationnetworkproxyapplysettingsdevicewide"></a>Windows10GeneralConfiguration.NetworkProxyApplySettingsDeviceWide 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/NetworkProxy  
**Identyfikator URI przesunięcia**: /ProxySettingsPerUser

### <a name="windows10generalconfigurationnetworkproxyautomaticconfigurationurl"></a>Windows10GeneralConfiguration.NetworkProxyAutomaticConfigurationUrl 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/NetworkProxy  
**Identyfikator URI przesunięcia**: /SetupScriptUrl

### <a name="windows10generalconfigurationnetworkproxydisableautodetect"></a>Windows10GeneralConfiguration.NetworkProxyDisableAutoDetect 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/NetworkProxy  
**Identyfikator URI przesunięcia**: /AutoDetect

### <a name="windows10generalconfigurationnetworkproxyserver"></a>Windows10GeneralConfiguration.NetworkProxyServer 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/NetworkProxy  
**Identyfikator URI przesunięcia**: /ProxyAddress, /Exceptions i /UseProxyForLocalAddresses

### <a name="windows10generalconfigurationnfcblocked"></a>Windows10GeneralConfiguration.NfcBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowNFC

### <a name="windows10generalconfigurationonedrivedisablefilesync"></a>Windows10GeneralConfiguration.OneDriveDisableFileSync 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/DisableOneDriveFileSync

### <a name="windows10generalconfigurationpasswordblocksimple"></a>Windows10GeneralConfiguration.PasswordBlockSimple 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/AllowSimpleDevicePassword

### <a name="windows10generalconfigurationpasswordexpirationdays"></a>Windows10GeneralConfiguration.PasswordExpirationDays 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/DevicePasswordExpiration

### <a name="windows10generalconfigurationpasswordminimumageindays"></a>Windows10GeneralConfiguration.PasswordMinimumAgeInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/MinimumPasswordAge

### <a name="windows10generalconfigurationpasswordminimumcharactersetcount"></a>Windows10GeneralConfiguration.PasswordMinimumCharacterSetCount 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/MinDevicePasswordComplexCharacters

### <a name="windows10generalconfigurationpasswordminimumlength"></a>Windows10GeneralConfiguration.PasswordMinimumLength 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/MinDevicePasswordLength

### <a name="windows10generalconfigurationpasswordminutesofinactivitybeforescreentimeout"></a>Windows10GeneralConfiguration.PasswordMinutesOfInactivityBeforeScreenTimeout 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/MaxInactivityTimeDeviceLock

### <a name="windows10generalconfigurationpasswordpreviouspasswordblockcount"></a>Windows10GeneralConfiguration.PasswordPreviousPasswordBlockCount 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/DevicePasswordHistory

### <a name="windows10generalconfigurationpasswordrequired"></a>Windows10GeneralConfiguration.PasswordRequired 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/DevicePasswordEnabled

### <a name="windows10generalconfigurationpasswordrequiredtype"></a>Windows10GeneralConfiguration.PasswordRequiredType 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/AlphanumericDevicePasswordRequired

### <a name="windows10generalconfigurationpasswordrequirewhenresumefromidlestate"></a>Windows10GeneralConfiguration.PasswordRequireWhenResumeFromIdleState 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/AllowIdleReturnWithoutPassword

### <a name="windows10generalconfigurationpasswordsigninfailurecountbeforefactoryreset"></a>Windows10GeneralConfiguration.PasswordSignInFailureCountBeforeFactoryReset 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceLock/MaxDevicePasswordFailedAttempts

### <a name="windows10generalconfigurationpersonalizationdesktopimageurl"></a>Windows10GeneralConfiguration.PersonalizationDesktopImageUrl 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Personalization  
**Identyfikator URI przesunięcia**: /DesktopImageUrl

### <a name="windows10generalconfigurationpersonalizationlockscreenimageurl"></a>Windows10GeneralConfiguration.PersonalizationLockScreenImageUrl 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Personalization  
**Identyfikator URI przesunięcia**: /LockScreenImageUrl

### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhileonbattery"></a>Windows10GeneralConfiguration.PowerRequirePasswordOnWakeWhileOnBattery 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Power/RequirePasswordWhenComputerWakesOnBattery

### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhilepluggedin"></a>Windows10GeneralConfiguration.PowerRequirePasswordOnWakeWhilePluggedIn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Power/RequirePasswordWhenComputerWakesPluggedIn

### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhileonbattery"></a>Windows10GeneralConfiguration.PowerStandbyStatesWhenSleepingWhileOnBattery 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Power/AllowStandbyStatesWhenSleepingOnBattery

### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhilepluggedin"></a>Windows10GeneralConfiguration.PowerStandbyStatesWhenSleepingWhilePluggedIn 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Power/AllowStandbyWhenSleepingPluggedIn

### <a name="windows10generalconfigurationpreventinstallationofmatchingdeviceids"></a>windows10generalconfiguration.preventInstallationOfMatchingDeviceIDs 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceIDs

### <a name="windows10generalconfigurationpreventinstallationofmatchingdevicesetupclasses"></a>windows10generalconfiguration.preventInstallationOfMatchingDeviceSetupClasses 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeviceInstallation/PreventInstallationOfMatchingDeviceSetupClasses

### <a name="windows10generalconfigurationprinterblockaddition"></a>Windows10GeneralConfiguration.PrinterBlockAddition 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Education/PreventAddingNewPrinters

### <a name="windows10generalconfigurationprinterdefaultname"></a>Windows10GeneralConfiguration.PrinterDefaultName 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Education/DefaultPrinterName

### <a name="windows10generalconfigurationprinternames"></a>Windows10GeneralConfiguration.PrinterNames 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Education/PrinterNames

### <a name="windows10generalconfigurationprivacyadvertisingid"></a>Windows10GeneralConfiguration.PrivacyAdvertisingId 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Privacy/DisableAdvertisingID

### <a name="windows10generalconfigurationprivacyautoacceptpairingandconsentprompts"></a>Windows10GeneralConfiguration.PrivacyAutoAcceptPairingAndConsentPrompts 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Privacy/AllowAutoAcceptPairingAndPrivacyConsentPrompts

### <a name="windows10generalconfigurationprivacyblockactivityfeed"></a>Windows10GeneralConfiguration.PrivacyBlockActivityFeed 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Privacy/EnableActivityFeed

### <a name="windows10generalconfigurationprivacyblockinputpersonalization"></a>Windows10GeneralConfiguration.PrivacyBlockInputPersonalization 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Privacy/AllowInputPersonalization

### <a name="windows10generalconfigurationprivacyblockpublishuseractivities"></a>Windows10GeneralConfiguration.PrivacyBlockPublishUserActivities 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Privacy/PublishUserActivities

### <a name="windows10generalconfigurationsafesearchfilter"></a>Windows10GeneralConfiguration.SafeSearchFilter 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/SafeSearchPermissions

### <a name="windows10generalconfigurationscreencaptureblocked"></a>Windows10GeneralConfiguration.ScreenCaptureBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowScreenCapture

### <a name="windows10generalconfigurationsearchblockdiacritics"></a>Windows10GeneralConfiguration.SearchBlockDiacritics 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/AllowUsingDiacritics

### <a name="windows10generalconfigurationsearchblockwebresults"></a>Windows10GeneralConfiguration.SearchBlockWebResults 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/DoNotUseWebResults

### <a name="windows10generalconfigurationsearchdisableautolanguagedetection"></a>Windows10GeneralConfiguration.SearchDisableAutoLanguageDetection 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/AlwaysUseAutoLangDetection

### <a name="windows10generalconfigurationsearchdisableindexerbackoff"></a>Windows10GeneralConfiguration.SearchDisableIndexerBackoff 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/DisableBackoff

### <a name="windows10generalconfigurationsearchdisableindexingencrypteditems"></a>Windows10GeneralConfiguration.SearchDisableIndexingEncryptedItems 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/AllowIndexingEncryptedStoresOrItems

### <a name="windows10generalconfigurationsearchdisableindexingremovabledrive"></a>Windows10GeneralConfiguration.SearchDisableIndexingRemovableDrive 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/DisableRemovableDriveIndexing

### <a name="windows10generalconfigurationsearchdisablelocation"></a>Windows10GeneralConfiguration.SearchDisableLocation 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/AllowSearchToUseLocation

### <a name="windows10generalconfigurationsearchdisableuselocation"></a>Windows10GeneralConfiguration.SearchDisableUseLocation 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/AllowSearchToUseLocation

### <a name="windows10generalconfigurationsearchenableautomaticindexsizemanangement"></a>Windows10GeneralConfiguration.SearchEnableAutomaticIndexSizeManangement 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/PreventIndexingLowDiskSpaceMB

### <a name="windows10generalconfigurationsearchenableremotequeries"></a>Windows10GeneralConfiguration.SearchEnableRemoteQueries 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Search/PreventRemoteQueries

### <a name="windows10generalconfigurationsecurityblockazureadjoineddevicesautoencryption"></a>Windows10GeneralConfiguration.SecurityBlockAzureADJoinedDevicesAutoEncryption 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices

### <a name="windows10generalconfigurationsettingsblockaccountspage"></a>Windows10GeneralConfiguration.SettingsBlockAccountsPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockaddprovisioningpackage"></a>Windows10GeneralConfiguration.SettingsBlockAddProvisioningPackage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Security/AllowAddProvisioningPackage

### <a name="windows10generalconfigurationsettingsblockappspage"></a>Windows10GeneralConfiguration.SettingsBlockAppsPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockchangelanguage"></a>Windows10GeneralConfiguration.SettingsBlockChangeLanguage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/AllowLanguage

### <a name="windows10generalconfigurationsettingsblockchangepowersleep"></a>Windows10GeneralConfiguration.SettingsBlockChangePowerSleep 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/AllowPowerSleep

### <a name="windows10generalconfigurationsettingsblockchangeregion"></a>Windows10GeneralConfiguration.SettingsBlockChangeRegion 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/AllowRegion

### <a name="windows10generalconfigurationsettingsblockchangesystemtime"></a>Windows10GeneralConfiguration.SettingsBlockChangeSystemTime 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/AllowDateTime

### <a name="windows10generalconfigurationsettingsblockdevicespage"></a>Windows10GeneralConfiguration.SettingsBlockDevicesPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockeaseofaccesspage"></a>Windows10GeneralConfiguration.SettingsBlockEaseOfAccessPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockeditdevicename"></a>Windows10GeneralConfiguration.SettingsBlockEditDeviceName 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/AllowEditDeviceName

### <a name="windows10generalconfigurationsettingsblockgamingpage"></a>Windows10GeneralConfiguration.SettingsBlockGamingPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblocknetworkinternetpage"></a>Windows10GeneralConfiguration.SettingsBlockNetworkInternetPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockpersonalizationpage"></a>Windows10GeneralConfiguration.SettingsBlockPersonalizationPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockprivacypage"></a>Windows10GeneralConfiguration.SettingsBlockPrivacyPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockremoveprovisioningpackage"></a>Windows10GeneralConfiguration.SettingsBlockRemoveProvisioningPackage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Security/AllowRemoveProvisioningPackage

### <a name="windows10generalconfigurationsettingsblocksystempage"></a>Windows10GeneralConfiguration.SettingsBlockSystemPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblocktimelanguagepage"></a>Windows10GeneralConfiguration.SettingsBlockTimeLanguagePage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationsettingsblockupdatesecuritypage"></a>Windows10GeneralConfiguration.SettingsBlockUpdateSecurityPage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Settings/PageVisibilityList

### <a name="windows10generalconfigurationshareduserappdataallowed"></a>Windows10GeneralConfiguration.SharedUserAppDataAllowed 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/AllowSharedUserAppData

### <a name="windows10generalconfigurationsmartscreenblockpromptoverride"></a>Windows10GeneralConfiguration.SmartScreenBlockPromptOverride 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventSmartScreenPromptOverride

### <a name="windows10generalconfigurationsmartscreenblockpromptoverrideforfiles"></a>Windows10GeneralConfiguration.SmartScreenBlockPromptOverrideForFiles 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventSmartScreenPromptOverrideForFiles

### <a name="windows10generalconfigurationsmartscreenenableappinstallcontrol"></a>Windows10GeneralConfiguration.SmartScreenEnableAppInstallControl 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/SmartScreen/EnableAppInstallControl

### <a name="windows10generalconfigurationstartblockunpinningappsfromtaskbar"></a>Windows10GeneralConfiguration.StartBlockUnpinningAppsFromTaskbar 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/NoPinningToTaskbar

### <a name="windows10generalconfigurationstartmenuapplistvisibility"></a>Windows10GeneralConfiguration.StartMenuAppListVisibility 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideAppList

### <a name="windows10generalconfigurationstartmenuhidechangeaccountsettings"></a>Windows10GeneralConfiguration.StartMenuHideChangeAccountSettings 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideChangeAccountSettings

### <a name="windows10generalconfigurationstartmenuhidefrequentlyusedapps"></a>Windows10GeneralConfiguration.StartMenuHideFrequentlyUsedApps 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideFrequentlyUsedApps

### <a name="windows10generalconfigurationstartmenuhidehibernate"></a>Windows10GeneralConfiguration.StartMenuHideHibernate 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideHibernate

### <a name="windows10generalconfigurationstartmenuhidelock"></a>Windows10GeneralConfiguration.StartMenuHideLock 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideLock

### <a name="windows10generalconfigurationstartmenuhidepowerbutton"></a>Windows10GeneralConfiguration.StartMenuHidePowerButton 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HidePowerButton

### <a name="windows10generalconfigurationstartmenuhiderecentjumplists"></a>Windows10GeneralConfiguration.StartMenuHideRecentJumpLists 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideRecentJumplists

### <a name="windows10generalconfigurationstartmenuhiderecentlyaddedapps"></a>Windows10GeneralConfiguration.StartMenuHideRecentlyAddedApps 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideRecentlyAddedApps

### <a name="windows10generalconfigurationstartmenuhiderestartoptions"></a>Windows10GeneralConfiguration.StartMenuHideRestartOptions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideRestart

### <a name="windows10generalconfigurationstartmenuhideshutdown"></a>Windows10GeneralConfiguration.StartMenuHideShutDown 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideShutDown

### <a name="windows10generalconfigurationstartmenuhidesignout"></a>Windows10GeneralConfiguration.StartMenuHideSignOut 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideSignOut

### <a name="windows10generalconfigurationstartmenuhidesleep"></a>Windows10GeneralConfiguration.StartMenuHideSleep 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideSleep

### <a name="windows10generalconfigurationstartmenuhideswitchaccount"></a>Windows10GeneralConfiguration.StartMenuHideSwitchAccount 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideSwitchAccount

### <a name="windows10generalconfigurationstartmenuhideusertile"></a>Windows10GeneralConfiguration.StartMenuHideUserTile 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/HideUserTile

### <a name="windows10generalconfigurationstartmenulayoutedgeassetsxml"></a>Windows10GeneralConfiguration.StartMenuLayoutEdgeAssetsXml 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/ImportEdgeAssets

### <a name="windows10generalconfigurationstartmenulayoutxml"></a>Windows10GeneralConfiguration.StartMenuLayoutXml 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/StartLayout

### <a name="windows10generalconfigurationstartmenumode"></a>Windows10GeneralConfiguration.StartMenuMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/ForceStartSize

### <a name="windows10generalconfigurationstartmenupinnedfolderdocuments"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderDocuments 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderDocuments

### <a name="windows10generalconfigurationstartmenupinnedfolderdownloads"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderDownloads 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderDownloads

### <a name="windows10generalconfigurationstartmenupinnedfolderfileexplorer"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderFileExplorer 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderFileExplorer

### <a name="windows10generalconfigurationstartmenupinnedfolderhomegroup"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderHomeGroup 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderHomeGroup

### <a name="windows10generalconfigurationstartmenupinnedfoldermusic"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderMusic 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderMusic

### <a name="windows10generalconfigurationstartmenupinnedfoldernetwork"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderNetwork 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderNetwork

### <a name="windows10generalconfigurationstartmenupinnedfolderpersonalfolder"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderPersonalFolder 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderPersonalFolder

### <a name="windows10generalconfigurationstartmenupinnedfolderpictures"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderPictures 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderPictures

### <a name="windows10generalconfigurationstartmenupinnedfoldersettings"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderSettings 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderSettings

### <a name="windows10generalconfigurationstartmenupinnedfoldervideos"></a>Windows10GeneralConfiguration.StartMenuPinnedFolderVideos 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Start/AllowPinnedFolderVideos

### <a name="windows10generalconfigurationstorageblockremovablestorage"></a>Windows10GeneralConfiguration.StorageBlockRemovableStorage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/AllowStorageCard

### <a name="windows10generalconfigurationstoragerequiremobiledeviceencryption"></a>Windows10GeneralConfiguration.StorageRequireMobileDeviceEncryption 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Security/RequireDeviceEncryption

### <a name="windows10generalconfigurationstoragerestrictappdatatosystemvolume"></a>Windows10GeneralConfiguration.StorageRestrictAppDataToSystemVolume 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/RestrictAppDataToSystemVolume

### <a name="windows10generalconfigurationstoragerestrictappinstalltosystemvolume"></a>Windows10GeneralConfiguration.StorageRestrictAppInstallToSystemVolume 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/RestrictAppToSystemVolume

### <a name="windows10generalconfigurationsystembootstartdriverinitialization"></a>Windows10GeneralConfiguration.SystemBootStartDriverInitialization 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/BootStartDriverInitialization

### <a name="windows10generalconfigurationsystemtelemetryproxyserver"></a>Windows10GeneralConfiguration.SystemTelemetryProxyServer 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/System/TelemetryProxy

### <a name="windows10generalconfigurationtaskmanagerblockendtask"></a>Windows10GeneralConfiguration.TaskManagerBlockEndTask 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/TaskManager/AllowEndTask

### <a name="windows10generalconfigurationtenantlockdownrequirenetworkduringoutofboxexperience"></a>Windows10GeneralConfiguration.TenantLockdownRequireNetworkDuringOutOfBoxExperience 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/TenantLockdown  
**Identyfikator URI przesunięcia**: /RequireNetworkInOOBE

### <a name="windows10generalconfigurationusbblocked"></a>Windows10GeneralConfiguration.UsbBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Connectivity/AllowUSBConnection

### <a name="windows10generalconfigurationvoicerecordingblocked"></a>Windows10GeneralConfiguration.VoiceRecordingBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowVoiceRecording

### <a name="windows10generalconfigurationwebrtcblocklocalhostipaddress"></a>Windows10GeneralConfiguration.WebRtcBlockLocalhostIpAddress 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/PreventUsingLocalHostIPAddressForWebRTC

### <a name="windows10generalconfigurationwifiblockautomaticconnecthotspots"></a>Windows10GeneralConfiguration.WiFiBlockAutomaticConnectHotspots 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WiFi/AllowAutoConnectToWiFiSenseHotspots

### <a name="windows10generalconfigurationwifiblocked"></a>Windows10GeneralConfiguration.WiFiBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Wifi/AllowWiFi

### <a name="windows10generalconfigurationwifiblockmanualconfiguration"></a>Windows10GeneralConfiguration.WiFiBlockManualConfiguration 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WiFi/AllowManualWiFi/Configuration

### <a name="windows10generalconfigurationwifiscaninterval"></a>Windows10GeneralConfiguration.WiFiScanInterval 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WiFi/WLANScanMode

### <a name="windows10generalconfigurationwindowslogonlocalusersondomainjoinedcomputers"></a>Windows10GeneralConfiguration.WindowsLogOnLocalUsersOnDomainJoinedComputers 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WindowsLogon/EnumerateLocalUsersOnDomainJoinedComputers

### <a name="windows10generalconfigurationwindowsspotlightblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockConsumerSpecificFeatures 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsConsumerFeatures

### <a name="windows10generalconfigurationwindowsspotlightblocked"></a>Windows10GeneralConfiguration.WindowsSpotlightBlocked 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsSpotlight

### <a name="windows10generalconfigurationwindowsspotlightblockonactioncenter"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockOnActionCenter 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsSpotlightOnActionCenter

### <a name="windows10generalconfigurationwindowsspotlightblocktailoredexperiences"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockTailoredExperiences 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowTailoredExperiencesWithDiagnosticData

### <a name="windows10generalconfigurationwindowsspotlightblockthirdpartynotifications"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockThirdPartyNotifications 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowThirdPartySuggestionsInWindowsSpotlight

### <a name="windows10generalconfigurationwindowsspotlightblockwelcomeexperience"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockWelcomeExperience 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsSpotlightWindowsWelcomeExperience

### <a name="windows10generalconfigurationwindowsspotlightblockwindowstips"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockWindowsTips 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/AllowWindowsTips

### <a name="windows10generalconfigurationwindowsspotlightconfigureonlockscreen"></a>Windows10GeneralConfiguration.WindowsSpotlightConfigureOnLockScreen 
**Dostawca usług konfiguracji**: ./User/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Experience/ConfigureWindowsSpotlightOnLockScreen

### <a name="windows10generalconfigurationwindowsstoreblockautoupdate"></a>Windows10GeneralConfiguration.WindowsStoreBlockAutoUpdate 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/AllowAppStoreAutoUpdate

### <a name="windows10generalconfigurationwindowsstoreblocked"></a>Windows10GeneralConfiguration.WindowsStoreBlocked 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/AllowStore

### <a name="windows10generalconfigurationwindowsstoreenableprivatestoreonly"></a>Windows10GeneralConfiguration.WindowsStoreEnablePrivateStoreOnly 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ApplicationManagement/RequirePrivateStoreOnly

### <a name="windows10generalconfigurationwirelessdisplayblockprojectiontothisdevice"></a>Windows10GeneralConfiguration.WirelessDisplayBlockProjectionToThisDevice 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WirelessDisplay/AllowProjectionToPC

### <a name="windows10generalconfigurationwirelessdisplayblockuserinputfromreceiver"></a>Windows10GeneralConfiguration.WirelessDisplayBlockUserInputFromReceiver 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WirelessDisplay/AllowUserInputFromWirelessDisplayReceiver

### <a name="windows10generalconfigurationwirelessdisplayrequirepinforpairing"></a>Windows10GeneralConfiguration.WirelessDisplayRequirePinForPairing 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/WirelessDisplay/RequirePINForPairing

### <a name="windows10networkboundaryconfigurationwindowsnetworkisolationpolicy"></a>Windows10NetworkBoundaryConfiguration.WindowsNetworkIsolationPolicy 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/NetworkIsolation/EnterpriseCloudResources, /Config/NetworkIsolation/EnterpriseIPRange, /Config/NetworkIsolation/EnterpriseIPRangesAreAuthoritative, /Config/NetworkIsolation/EnterpriseInternalProxyServers, /Config/NetworkIsolation/EnterpriseNetworkDomainNames, /Config/NetworkIsolation/EnterpriseProxyServers, /Config/NetworkIsolation/EnterpriseProxyServersAreAuthoritative, /Config/NetworkIsolation/NeutralResources

### <a name="windows10policyoverrideconfigurationprefermdmovergrouppolicy"></a>Windows10PolicyOverrideConfiguration.PreferMdmOverGroupPolicy 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/ControlPolicyConflict/MDMWinsOverGP

### <a name="windows10secureassessmentconfigurationallowprinting"></a>Windows10SecureAssessmentConfiguration.AllowPrinting 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SecureAssessment  
**Identyfikator URI przesunięcia**: /RequirePrinting

### <a name="windows10secureassessmentconfigurationallowscreencapture"></a>Windows10SecureAssessmentConfiguration.AllowScreenCapture 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SecureAssessment  
**Identyfikator URI przesunięcia**: /AllowScreenMonitoring

### <a name="windows10secureassessmentconfigurationallowtextsuggestion"></a>Windows10SecureAssessmentConfiguration.AllowTextSuggestion 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SecureAssessment  
**Identyfikator URI przesunięcia**: /AllowTextSuggestions

### <a name="windows10secureassessmentconfigurationconfigurationaccount"></a>Windows10SecureAssessmentConfiguration.ConfigurationAccount 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SecureAssessment  
**Identyfikator URI przesunięcia**: /TesterAccount

### <a name="windows10secureassessmentconfigurationconfigurationaccounttype"></a>Windows10SecureAssessmentConfiguration.ConfigurationAccountType 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SecureAssessment  
**Identyfikator URI przesunięcia**: /TesterAccount

### <a name="windows10secureassessmentconfigurationlaunchuri"></a>Windows10SecureAssessmentConfiguration.LaunchUri 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SecureAssessment  
**Identyfikator URI przesunięcia**: /LaunchURI

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsblocktelemetry"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsBlockTelemetry 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /MOMAgent/WorkspaceID i /MOMAgent/WorkspaceKey

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspaceid"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsWorkspaceId 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /MOMAgent/WorkspaceID

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspacekey"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsWorkspaceKey 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /MOMAgent/WorkspaceKey

### <a name="windows10teamgeneralconfigurationconnectappblockautolaunch"></a>Windows10TeamGeneralConfiguration.ConnectAppBlockAutoLaunch 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/Connect/AutoLaunch

### <a name="windows10teamgeneralconfigurationdeviceaccountblockexchangeservices"></a>Windows10TeamGeneralConfiguration.DeviceAccountBlockExchangeServices 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /DeviceAccount/Email

### <a name="windows10teamgeneralconfigurationdeviceaccountemailaddress"></a>Windows10TeamGeneralConfiguration.DeviceAccountEmailAddress 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /DeviceAccount/Email

### <a name="windows10teamgeneralconfigurationdeviceaccountexchangeserveraddress"></a>Windows10TeamGeneralConfiguration.DeviceAccountExchangeServerAddress 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /DeviceAccount/ExchangeServer

### <a name="windows10teamgeneralconfigurationdeviceaccountrequirepasswordrotation"></a>Windows10TeamGeneralConfiguration.DeviceAccountRequirePasswordRotation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /DeviceAccount/PasswordRotationEnabled

### <a name="windows10teamgeneralconfigurationdeviceaccountsessioninitiationprotocoladdress"></a>Windows10TeamGeneralConfiguration.DeviceAccountSessionInitiationProtocolAddress 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /DeviceAccount/SipAddress

### <a name="windows10teamgeneralconfigurationmaintenancewindowblocked"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /MaintenanceHoursSimple/Hours/Duration i /MaintenanceHoursSimple/Hours/StartTime

### <a name="windows10teamgeneralconfigurationmaintenancewindowdurationinhours"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowDurationInHours 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /MaintenanceHoursSimple/Hours/Duration

### <a name="windows10teamgeneralconfigurationmaintenancewindowstarttime"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowStartTime 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /MaintenanceHoursSimple/Hours/StartTime

### <a name="windows10teamgeneralconfigurationmiracastblocked"></a>Windows10TeamGeneralConfiguration.MiracastBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/WirelessProjection/Enabled

### <a name="windows10teamgeneralconfigurationmiracastchannel"></a>Windows10TeamGeneralConfiguration.MiracastChannel 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/WirelessProjection/Channel

### <a name="windows10teamgeneralconfigurationmiracastrequirepin"></a>Windows10TeamGeneralConfiguration.MiracastRequirePin 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/WirelessProjection/PINRequired

### <a name="windows10teamgeneralconfigurationsettingsblockmymeetingsandfiles"></a>Windows10TeamGeneralConfiguration.SettingsBlockMyMeetingsAndFiles 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/DoNotShowMyMeetingsAndFiles

### <a name="windows10teamgeneralconfigurationsettingsblocksessionresume"></a>Windows10TeamGeneralConfiguration.SettingsBlockSessionResume 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/AllowSessionResume

### <a name="windows10teamgeneralconfigurationsettingsblocksigninsuggestions"></a>Windows10TeamGeneralConfiguration.SettingsBlockSigninSuggestions 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/DisableSigninSuggestions

### <a name="windows10teamgeneralconfigurationsettingsdefaultvolume"></a>Windows10TeamGeneralConfiguration.SettingsDefaultVolume 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/DefaultVolume

### <a name="windows10teamgeneralconfigurationsettingsscreentimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsScreenTimeoutInMinutes 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/ScreenTimeout

### <a name="windows10teamgeneralconfigurationsettingssessiontimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsSessionTimeoutInMinutes 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/SessionTimeout

### <a name="windows10teamgeneralconfigurationsettingssleeptimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsSleepTimeoutInMinutes 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /Properties/SleepTimeout

### <a name="windows10teamgeneralconfigurationwelcomescreenbackgroundimageurl"></a>Windows10TeamGeneralConfiguration.WelcomeScreenBackgroundImageUrl 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/Welcome/CurrentBackgroundPath

### <a name="windows10teamgeneralconfigurationwelcomescreenblockautomaticwakeup"></a>Windows10TeamGeneralConfiguration.WelcomeScreenBlockAutomaticWakeUp 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/Welcome/AutoWakeScreen

### <a name="windows10teamgeneralconfigurationwelcomescreenmeetinginformation"></a>Windows10TeamGeneralConfiguration.WelcomeScreenMeetingInformation 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/SurfaceHub  
**Identyfikator URI przesunięcia**: /InBoxApps/Welcome/MeetingInfoOption

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingblob"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOffboardingBlob 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Identyfikator URI przesunięcia**: /Offboarding 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingfilename"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOffboardingFilename
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Identyfikator URI przesunięcia**: /Offboarding 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingblob"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOnboardingBlob 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Identyfikator URI przesunięcia**: /Onboarding 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingfilename"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AdvancedThreatProtectionOnboardingFilename 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Identyfikator URI przesunięcia**: /Onboarding 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationallowsamplesharing"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.AllowSampleSharing 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Identyfikator URI przesunięcia**: /Configuration/SampleSharing

### <a name="windowsdefenderadvancedthreatprotectionconfigurationenableexpeditedtelemetryreporting"></a>WindowsDefenderAdvancedThreatProtectionConfiguration.EnableExpeditedTelemetryReporting 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection  
**Identyfikator URI przesunięcia**: /Configuration/TelemetryReportingFrequency

### <a name="windowsdeliveryoptimizationconfigurationdeliveryoptimizationmode"></a>WindowsDeliveryOptimizationConfiguration.DeliveryOptimizationMode 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeliveryOptimization/DODownloadMode

### <a name="windowsidentityprotectionconfigurationenhancedantispoofingforfacialfeaturesenabled"></a>WindowsIdentityProtectionConfiguration.EnhancedAntiSpoofingForFacialFeaturesEnabled 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /Biometrics/FacialFeaturesUseEnhancedAntiSpoofing

### <a name="windowsidentityprotectionconfigurationpinexpirationindays"></a>WindowsIdentityProtectionConfiguration.PinExpirationInDays 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/Expiration

### <a name="windowsidentityprotectionconfigurationpinlowercasecharactersusage"></a>WindowsIdentityProtectionConfiguration.PinLowercaseCharactersUsage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/LowercaseLetters

### <a name="windowsidentityprotectionconfigurationpinmaximumlength"></a>WindowsIdentityProtectionConfiguration.PinMaximumLength 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/MaximumPINLength

### <a name="windowsidentityprotectionconfigurationpinminimumlength"></a>WindowsIdentityProtectionConfiguration.PinMinimumLength 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/MinimumPINLength

### <a name="windowsidentityprotectionconfigurationpinpreviousblockcount"></a>WindowsIdentityProtectionConfiguration.PinPreviousBlockCount 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/History

### <a name="windowsidentityprotectionconfigurationpinrecoveryenabled"></a>WindowsIdentityProtectionConfiguration.PinRecoveryEnabled 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/EnablePinRecovery

### <a name="windowsidentityprotectionconfigurationpinspecialcharactersusage"></a>WindowsIdentityProtectionConfiguration.PinSpecialCharactersUsage 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/SpecialCharacters

### <a name="windowsidentityprotectionconfigurationpinuppercasecharactersusage"></a>WindowsIdentityProtectionConfiguration.PinUppercaseCharactersUsage
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/PINComplexity/UppercaseLetters

### <a name="windowsidentityprotectionconfigurationsecuritydevicerequired"></a>WindowsIdentityProtectionConfiguration.SecurityDeviceRequired 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/RequireSecurityDevice

### <a name="windowsidentityprotectionconfigurationunlockwithbiometricsenabled"></a>WindowsIdentityProtectionConfiguration.UnlockWithBiometricsEnabled 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /Biometrics/UseBiometrics

### <a name="windowsidentityprotectionconfigurationusecertificatesforonpremisesauthenabled"></a>WindowsIdentityProtectionConfiguration.UseCertificatesForOnPremisesAuthEnabled 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/UseCertificateForOnPremAuth

### <a name="windowsidentityprotectionconfigurationwindowshelloforbusinessblocked"></a>WindowsIdentityProtectionConfiguration.WindowsHelloForBusinessBlocked 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/PassportForWork  
**Identyfikator URI przesunięcia**: /{AADTenantId}/Policies/UsePassportForWork

### <a name="windowskioskconfigurationedgekioskenablepublicbrowsing"></a>WindowsKioskConfiguration.EdgeKioskEnablePublicBrowsing 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ConfigureKioskMode

### <a name="windowskioskconfigurationedgekioskresetafteridletimeinminutes"></a>WindowsKioskConfiguration.EdgeKioskResetAfterIdleTimeInMinutes 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Browser/ConfigureKioskResetAfterIdleTimeout

### <a name="windowskioskconfigurationkioskbrowserblockedurlexceptions"></a>WindowsKioskConfiguration.KioskBrowserBlockedUrlExceptions 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/BlockedUrlExceptions

### <a name="windowskioskconfigurationkioskbrowserblockedurls"></a>WindowsKioskConfiguration.KioskBrowserBlockedURLs 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/BlockedUrls

### <a name="windowskioskconfigurationkioskbrowserdefaulturl"></a>WindowsKioskConfiguration.KioskBrowserDefaultUrl 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/DefaultUrl

### <a name="windowskioskconfigurationkioskbrowserenableendsessionbutton"></a>WindowsKioskConfiguration.KioskBrowserEnableEndSessionButton 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/EnableEndSessionButton

### <a name="windowskioskconfigurationkioskbrowserenablehomebutton"></a>WindowsKioskConfiguration.KioskBrowserEnableHomeButton 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/EnableHomeButton

### <a name="windowskioskconfigurationkioskbrowserenablenavigationbuttons"></a>WindowsKioskConfiguration.KioskBrowserEnableNavigationButtons 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/EnableNavigationButtons

### <a name="windowskioskconfigurationkioskbrowserrestartonidletimeinminutes"></a>WindowsKioskConfiguration.KioskBrowserRestartOnIdleTimeInMinutes 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/KioskBrowser/KioskBrowserRestartOnIdleTimeInMinutes

### <a name="windowsupdateforbusinessconfigurationautomaticupdatemode"></a>WindowsUpdateForBusinessConfiguration.AutomaticUpdateMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/AllowAutoUpdate

### <a name="windowsupdateforbusinessconfigurationautorestartnotificationdismissal"></a>WindowsUpdateForBusinessConfiguration.AutoRestartNotificationDismissal 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/AutoRestartRequiredNotificationDismissal

### <a name="windowsupdateforbusinessconfigurationbusinessreadyupdatesonly"></a>WindowsUpdateForBusinessConfiguration.BusinessReadyUpdatesOnly 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/BranchReadinessLevel

### <a name="windowsupdateforbusinessconfigurationdeliveryoptimizationmode"></a>WindowsUpdateForBusinessConfiguration.DeliveryOptimizationMode 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/DeliveryOptimization/DODownloadMode

### <a name="windowsupdateforbusinessconfigurationdriversexcluded"></a>WindowsUpdateForBusinessConfiguration.DriversExcluded 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/ExcludeWUDriversInQualityUpdate

### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartDeadlineForFeatureUpdatesInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/EngagedRestartDeadlineForFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartDeadlineInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/EngagedRestartDeadline

### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartSnoozeScheduleForFeatureUpdatesInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/EngagedRestartSnoozeScheduleForFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartSnoozeScheduleInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/EngagedRestartSnoozeSchedule

### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartTransitionScheduleForFeatureUpdatesInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/EngagedRestartTransitionScheduleForFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleindays"></a>WindowsUpdateForBusinessConfiguration.EngagedRestartTransitionScheduleInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/EngagedRestartTransitionSchedule

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesdeferralperiodindays"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesDeferralPeriodInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/DeferFeatureUpdatesPeriodInDays

### <a name="windowsupdateforbusinessconfigurationfeatureupdatespaused"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesPaused 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/PauseFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationfeatureupdatespausestartdatetime"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesPauseStartDateTime 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/PauseFeatureUpdatesStartTime

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesrollbackstartdatetime"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesRollbackStartDateTime
**Dostawca usług konfiguracji**: Nie dotyczy — tylko interfejs Graph API **Identyfikator URI przesunięcia**: Nie dotyczy — tylko interfejs Graph API

### <a name="windowsupdateforbusinessconfigurationfeatureupdateswillberolledback"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesWillBeRolledBack 
**Dostawca usług konfiguracji**: Nie dotyczy — tylko interfejs Graph API **Identyfikator URI przesunięcia**: Nie dotyczy — tylko interfejs Graph API

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesrollbackwindowindays"></a>WindowsUpdateForBusinessConfiguration.FeatureUpdatesRollbackWindowInDays
**Dostawca usług konfiguracji**: Nie dotyczy — tylko interfejs Graph API **Identyfikator URI przesunięcia**: Nie dotyczy — tylko interfejs Graph API

### <a name="windowsupdateforbusinessconfigurationinstallationschedule"></a>WindowsUpdateForBusinessConfiguration.InstallationSchedule
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy **Identyfikator URI przesunięcia**: /Config/Update/ActiveHoursStart, /Config/Update/ActiveHoursEnd, /Config/Update/ScheduledInstallDay,  /Config/Update/ScheduledInstallTime

### <a name="windowsupdateforbusinessconfigurationmicrosoftupdateserviceallowed"></a>WindowsUpdateForBusinessConfiguration.MicrosoftUpdateServiceAllowed 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/AllowMUUpdateService

### <a name="windowsupdateforbusinessconfigurationpreviewbuildsetting"></a>WindowsUpdateForBusinessConfiguration.PreviewBuildSetting 
**Dostawca usług konfiguracji**: ./Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/ManagePreviewBuilds

### <a name="windowsupdateforbusinessconfigurationqualityupdatesdeferralperiodindays"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesDeferralPeriodInDays 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/DeferQualityUpdatesPeriodInDays

### <a name="windowsupdateforbusinessconfigurationqualityupdatespaused"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesPaused 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/PauseQualityUpdates

### <a name="windowsupdateforbusinessconfigurationqualityupdatespausestartdatetime"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesPauseStartDateTime 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/PauseQualityUpdatesStartTime

### <a name="windowsupdateforbusinessconfigurationqualityupdatesrollbackstartdatetime"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesRollbackStartDateTime
**Dostawca usług konfiguracji**: Nie dotyczy — tylko interfejs Graph API **Identyfikator URI przesunięcia**: Nie dotyczy — tylko interfejs Graph API

### <a name="windowsupdateforbusinessconfigurationqualityupdateswillberolledback"></a>WindowsUpdateForBusinessConfiguration.QualityUpdatesWillBeRolledBack 
**Dostawca usług konfiguracji**: Nie dotyczy — tylko interfejs Graph API **Identyfikator URI przesunięcia**: Nie dotyczy — tylko interfejs Graph API

### <a name="windowsupdateforbusinessconfigurationscheduleimminentrestartwarninginminutes"></a>WindowsUpdateForBusinessConfiguration.ScheduleImminentRestartWarningInMinutes 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/ScheduleImminentRestartWarning

### <a name="windowsupdateforbusinessconfigurationschedulerestartwarninginhours"></a>WindowsUpdateForBusinessConfiguration.ScheduleRestartWarningInHours 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/ScheduleRestartWarning

### <a name="windowsupdateforbusinessconfigurationskipchecksbeforerestart"></a>WindowsUpdateForBusinessConfiguration.SkipChecksBeforeRestart 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/SetEDURestart

### <a name="windowsupdateforbusinessconfigurationupdateweeks"></a>WindowsUpdateForBusinessConfiguration.UpdateWeeks 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/ScheduledInstallEveryWeek, /Config/Update/ScheduledInstallFirstWeek, /Config/Update/ScheduledInstallFourthWeek, /Config/Update/ScheduledInstallSecondWeek, /Config/Update/ScheduledInstallThirdWeek

### <a name="windowsupdateforbusinessconfigurationuserpauseaccess"></a>WindowsUpdateForBusinessConfiguration.UserPauseAccess 
**Dostawca usług konfiguracji**: ./Device/Vendor/MSFT/Policy  
**Identyfikator URI przesunięcia**: /Config/Update/SetDisablePauseUXAccess


## <a name="next-steps"></a>Następne kroki

- [Przegląd konfiguracji urządzenia](../configuration/device-profiles.md)
- [Dokumentacja dostawcy usługi konfiguracji](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (otwiera kolejną witrynę docs)
