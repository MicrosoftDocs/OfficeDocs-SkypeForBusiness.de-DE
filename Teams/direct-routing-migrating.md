---
title: Migration zu Direct Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informationen dazu, wie Sie aus der Ansicht einer Skype for Business Online- und Teams-Konfiguration zu Direct Routing migrieren können.
ms.openlocfilehash: 71776c18dc6ec802c19f9dfc94c51b2b714bc210
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599750"
---
# <a name="migrate-to-direct-routing"></a>Migration zu Direct Routing

In diesem Artikel wird beschrieben, wie Sie aus der Ansicht einer Skype for Business Online- und einer Microsoft Teams-Konfiguration zu Direct Routing migrieren können. Dieser Artikel behandelt die Migration zu Direct Routing ausgehend von den folgenden Konfigurationen: 
 
- Telefonsystem mit Anrufplänen (für Teams und Skype for Business Online) 
- Telefonsystem mit lokalem PSTN-Konnektivität in Skype for Business Server (für Skype for Business Online)  
- Telefonsystem der lokalen PSTN-Anbindung mithilfe der Cloud Connector Edition (für Skype for Business Online)


Zusätzlich zu diesen Konfigurationsschritten ist auch die Konfiguration im Session Border Controller (SBC) erforderlich, um Anrufe auf die neue Verbindung umzuleiten. Dies ist nicht Inhalt dieses Dokuments. Weitere Informationen hierzu finden Sie in der Dokumentation Ihres SBC-Herstellers.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Endstatus der Benutzer-Bereitstellung für verschiedene Optionen von Festnetzanbindungen (PSTN-Konnektivität) 

Die folgende Tabelle zeigt den Endstatus für einen Benutzer, der für die ausgewählten PSTN-Konnektivitätsoptionen bereitgestellt wurde, mit Telefonsystem. Es werden ausschließlich die für die Sprachausgabe relevanten Attribute angezeigt.

|Benutzerspezifische Objektattribute |Telefonsystem mit Anrufplänen|Telefonsystem mit lokaler Festnetzanbindung über den Skype for Business Server|Telefonsystem mit lokaler Festnetzanbindung über den Cloud Connector|Telefonsystem mit lokaler Festnetzanbindung über Direct Routing|
|---|---|---|---|---|
|Client|Skype for Business oder Teams |Skype for Business |Skype for Business |Teams|
|Lizenzen|Skype Business Online</br>Plan 2</br></br>MCOProfessional oder MCOSTANDARD)</br></br></br>Telefonsystem (MCOEV)</br></br></br>Anrufpläne</br>Teams|Skype Business Online Plan 2 (MCOProfessional oder MCOSTANDARD)</br></br></br>Telefonsystem (MCOEV)|Skype Business Online Plan 2 (MCOProfessional oder MCOSTANDARD)</br></br></br>Telefonsystem (MCOEV)|Skype Business Online Plan 2 (MCOProfessional oder MCOSTANDARD</br></br></br>Telefonsystem (MCOEV)</br></br>Teams|
OnPremLineURI |Nicht zutreffend|Die Telefonnummer muss aus dem lokalen AD synchronisiert werden. |Die Telefonnummer kann entweder im lokalen Active Directory oder im Azure Active Directory verwaltet werden.|Die Telefonnummer kann entweder im lokalen Active Directory oder im Azure Active Directory verwaltet werden. Wenn das Unternehmen bzw. die Organisation allerdings über eine lokale Skype for Business-Anwendung verfügt, muss die Nummer vom lokalen Active Directory ausgehend synchronisiert werden.|
|LineURI|Telefonnummer des Festnetzanschlusses|Automatische Festlegung ausgehend vom Parameter „OnPremLineURI“|Automatische Festlegung ausgehend vom Parameter „OnPremLineURI“|Automatische Festlegung ausgehend vom Parameter „OnPremLineURI“|
|EnterpriseVoiceEnabled|Wahr|Wahr|Wahr|Wahr|
|HostedVoiceMail |Wahr|Wahr|Wahr|Wahr|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Weist einen Wert auf|Weist einen Wert auf|Weist einen Wert auf|Nicht zutreffend|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Weist einen Wert auf|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|Wahr|Nicht zutreffend|Nicht zutreffend|Wahr|
|TeamsCallingPolicy</br>AllowGroupCalling|Wahr|Nicht zutreffend|Nicht zutreffend|Wahr|
||||||

<sup>1</sup> Die Auswahl des richtigen Modus der TeamsUpgradePolicy hängt vom Szenario ab. Weitere Informationen zur Sprachqualität in verschiedenen Modi finden Sie unter [Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md).

Als Teil dieser Bemühungen hat Microsoft kürzlich das „Microsoft Teams Admin Center“ (auch als „Modern Portal“ bezeichnet) aktualisiert, um das neue Verwaltungsmodell basierend auf koexistierenden Modi darzustellen. Im Modern Portal wird durch das Konfigurieren der TeamsUpgradePolicy jetzt automatisch auch die TeamsInteropPolicy auf den konstanten Wert gesetzt, so dass die TeamsInteropPolicy nicht mehr auf der Benutzeroberfläche angezeigt wird. Allerdings müssen Administratoren, die PowerShell verwenden, sowohl die TeamsUpgradePolicy als auch die TeamsInteropPolicy gemeinsam festlegen, um eine ordnungsgemäße Weiterleitung zu gewährleisten. Nach Abschluss des Übergangs zur TeamsUpgradePolicy ist es nicht mehr erforderlich, auch die TeamsInteropPolicy festzulegen.

Weitere Informationen finden Sie unter [Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migration ausgehend von Anrufplänen

Weitere Informationen zur Migration ausgehend von Anrufplänen finden Sie unter:

- [Einrichten von Anrufplänen](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice User](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Es wird empfohlen, zuvor konfigurierte Lizenzierungsplan-Informationen wie folgt zu entfernen:
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migration ausgehend vom Office 365 Telefonsystem mit lokaler Festnetzanbindung über den Skype for Business Server

Weitere Informationen zur Migration ausgehend von einem Telefonsystem mit lokaler Festnetzanbindung über den Skype for Business Server finden Sie unter:

- [Planung](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Bereitstellung](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Es wird empfohlen, zuvor konfigurierte Sprachanruf-Weiterleitungsinformationen wie folgt zu entfernen:

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> Wenn eine globale CsVoiceRoutingPolicy konfiguriert ist, empfiehlt es sich, alle PSTN-Verwendungen zu entfernen, die dieser globalen Richtlinie zugeordnet sind. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migration ausgehend vom Office 365 Telefonsystem mit lokaler Festnetzanbindung über die Cloud Connector Edition 

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 sowie Skype for Business Online abziehen. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie hier, wie Sie Ihr lokales Telefonienetzwerk mithilfe von [Direct-Routing](direct-routing-landing-page.md)mit Teams verbinden.

Weitere Informationen zur Migration ausgehend von einem Telefonsystem mit lokaler Festnetzanbindung über den Cloud Connector finden Sie unter:

- [Planung](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Bereitstellung](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Benutzerkonfiguration](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Es wird empfohlen, zuvor konfigurierte Sprachanruf-Weiterleitungsinformationen wie folgt zu entfernen:
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)