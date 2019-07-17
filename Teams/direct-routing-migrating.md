---
title: Migration zu direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Erfahren Sie, was erforderlich ist, um aus einer Skype for Business Online-und Teams-Konfigurations Perspektive zur direkten Weiterleitung zu migrieren.
ms.openlocfilehash: 49980a0364e729fc41e6fe716de336a8a28f85bb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759008"
---
# <a name="migrate-to-direct-routing"></a>Migration zu direktem Routing

In diesem Artikel wird beschrieben, was für die Migration zur direkten Weiterleitung aus einer Skype for Business Online-und Microsoft Teams-Konfigurations Perspektive erforderlich ist. In diesem Artikel wird die Migration von folgenden Themen behandelt: 
 
- Office 365-Telefon System mit Anrufplänen (für Teams und Skype for Business Online) 
- Office 365-Telefon System mit lokalem PSTN-Konnektivität in Skype for Business Server (für Skype for Business Online)  
- Office 365-Telefon System mit lokalem PSTN-Konnektivität mithilfe der Cloud Connector Edition (für Skype for Business Online)

  
Zusätzlich zu diesen Konfigurationsschritten ist auch die Konfiguration für den Session Border Controller (SBC) erforderlich, um die Anrufe an die neue Route weiterzuleiten. Dies liegt außerhalb des Bereichs dieses Dokuments. Weitere Informationen finden Sie in der Dokumentation Ihres SBC-Herstellers.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Endzustand der Benutzerbereitstellung für verschiedene PSTN-Verbindungsoptionen 

Die folgende Tabelle zeigt den Endstatus für einen Benutzer, der für die ausgewählten PSTN-Verbindungsoptionen mit dem Office 365 Phone-System bereitgestellt wurde. Nur Attribute, die für die Sprachausgabe relevant sind, werden angezeigt.

|Benutzerobjekt Attribute |Telefon System mit Anrufplänen|Telefon System mit lokales PSTN-Konnektivität über Skype for Business Server|Telefon System mit lokales PSTN-Konnektivität über Cloud Connector|Telefon System mit lokales PSTN-Konnektivität über direktes Routing|
|---|---|---|---|---|
|Client|Skype for Business oder Teams |Skype for Business |Skype for Business |Microsoft Teams|
|Lizenzen|Skype Business Online</br>Plan 2</br></br>MCOProfessional oder MCOSTANDARD)</br></br></br>Telefon System (MCOEV)</br></br></br>Anrufpläne</br>Teams|Skype Business Online Plan 2 (MCOProfessional oder MCOSTANDARD)</br></br></br>Telefon System (MCOEV)|Skype Business Online Plan 2 (MCOProfessional oder MCOSTANDARD)</br></br></br>Telefon System (MCOEV)|Skype Business Online Plan 2 (MCOProfessional oder MCOSTANDARD</br></br></br>Telefon System (MCOEV)</br></br>Teams|
OnPremLineURI |Nicht zutreffend|Die Telefonnummer muss von der lokalen Anzeige synchronisiert werden. |Die Telefonnummer kann entweder in einem lokalen Active Directory oder in Azure Active Directory verwaltet werden.|Die Telefonnummer kann entweder in einem lokalen Active Directory oder in Azure Active Directory verwaltet werden. Wenn die Organisation jedoch lokal über Skype for Business verfügt, muss die Nummer aus dem lokalen Active Directory synchronisiert werden.|
|LineURI|Telefonnummer für PSTN-Anrufe|Automatisches Einstellen des OnPremLineURI-Parameters|Automatisches Einstellen des OnPremLineURI-Parameters|Automatisches Einstellen des OnPremLineURI-Parameters|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Hat einen Wert|Hat einen Wert|Hat einen Wert|Nicht zutreffend|
|OnlineVoiceRoutingPolicy|$NULL|$NULL|$NULL|Hat einen Wert|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly oder Inseln|$NULL|$NULL|Inseln oder TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient – Bitte lesen Sie die nachstehenden Hinweise.|Teams oder SFB |SFB|SFB|Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|n/v|n/v|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|n/v|n/v|True|
||||||

<sup>1</sup> Die Auswahl des richtigen TeamsUpgradePolicy-Modus hängt vom jeweiligen Szenario ab. Bitte lesen Sie die Sprachkenntnisse in verschiedenen Modi in [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Wie bereits angekündigt, wird TeamsInteropPolicy eingestellt (für das Ende des dritten Quartals vorgesehen), und seine Funktionalität wird in TeamsUpgradePolicy konsolidiert. Die Interoperabilität und Migration wird mithilfe des "Koexistenzmodus" verwaltet, wie von TeamsUpgradePolicy festgelegt, das jetzt verfügbar ist. Die Auswahl des Benutzermodus steuert sowohl das Routing von eingehenden Anrufen als auch von Chats und in welchem Client der Benutzer Chats und Anrufe initiieren oder Besprechungen planen kann. Während TeamsInteropPolicy eingestellt wird, muss es immer noch parallel zu TeamsUpgradePolicy während des Ausstiegs gesetzt werden.  

Im Rahmen dieser Bemühungen hat Microsoft vor kurzem das "Microsoft Teams Admin Center" (auch bekannt als modernes Portal) aktualisiert, um das neue Verwaltungsmodell auf der Grundlage von Koexistenzmodus wiederzugeben. Im modernen Portal wird durch die Konfiguration von TeamsUpgradePolicy nun automatisch auch TeamsInteropPolicy auf konsistenten Wert gesetzt, damit TeamsInteropPolicy nicht mehr auf der Benutzeroberfläche verfügbar gemacht wird. Administratoren, die PowerShell verwenden, müssen jedoch weiterhin sowohl TeamsUpgradePolicy als auch TeamsInteropPolicy so einrichten, dass die ordnungsgemäße Weiterleitung gewährleistet ist. Nach Abschluss des Übergangs zu TeamsUpgradePolicy ist es nicht mehr notwendig, auch TeamsInteropPolicy zu definieren.

Weitere Informationen finden Sie unter [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrieren von Anrufplänen

Weitere Informationen zum Migrieren von Anrufplänen finden Sie unter:

- [Einrichten von Anrufplänen](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Satz-CsOnlineVoice-Benutzer](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Es wird empfohlen, zuvor konfigurierte Lizenzierungs Planinformationen wie folgt zu entfernen:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrieren von Office 365 Phone System mit lokalen PSTN-Konnektivität in Skype for Business Server

Weitere Informationen zum Migrieren von einem Telefon System mit einer lokalen PSTN-Konnektivität in Skype for Business Server finden Sie unter den folgenden Themen:

- [Planung](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Einsatz](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Es wird empfohlen, zuvor konfigurierte VoIP-Weiterleitungsinformationen wie folgt zu entfernen:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrieren von Office 365 Phone System mit lokalen PSTN-Konnektivität über Cloud Connector Edition 

Weitere Informationen zum Migrieren von einem Telefon System mit einer lokalen PSTN-Konnektivität über Cloud Connector finden Sie unter den folgenden Themen:

- [Planung](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Einsatz](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Benutzerkonfiguration](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Es wird empfohlen, zuvor konfigurierte VoIP-Weiterleitungsinformationen wie folgt zu entfernen:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Neu – CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Satz-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Satz-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

