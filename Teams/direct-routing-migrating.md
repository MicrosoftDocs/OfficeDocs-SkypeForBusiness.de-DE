---
title: Migrieren zu direkten Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Hier erfahren Sie, was für die Migration zu direkten Routing von einer Skype für Business Online und Teams Konfiguration Perspektive erforderlich ist.
ms.openlocfilehash: 859ab19162f8cf16cc419f7f871fc0059e4566d6
ms.sourcegitcommit: 1cfbf3d7cdd8b40db47aa92625aa73b63d6e86e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "22546597"
---
# <a name="migrating-to-direct-routing"></a>Migrieren zu direkten Routing

In diesem Artikel wird beschrieben, was für die Migration zu direkten Routing von einer Skype für Business Online und Microsoft-Teams Konfiguration Perspektive erforderlich ist. Dieser Artikel behandelt die Migration aus den folgenden: 
 
- Telefonsystem mit Aufruf von Office 365-Pläne (für Teams und Skype für Unternehmen Online) 
- Office 365 Telefonsystem mit lokalen PSTN-Konnektivität in Skype für Business Server (für Skype für Unternehmen Online)  
- Office 365 Telefonsystem mit lokalen PSTN-Konnektivität mit der Cloud Connector Edition (für Skype für Business Online)

  
Zusätzlich zu diese Konfigurationsschritte ist Konfiguration auch auf Session Border Controller (SBC) erforderlich, die Anrufe für die neue Route weitergeleitet. Das liegt außerhalb des Bereichs des in diesem Dokument. Weitere Informationen finden Sie unter Ihrer SBC-Herstellers.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Benutzer, die Bereitstellung Endstatus für verschiedene Optionen der PSTN-Konnektivität 

Die folgende Tabelle zeigt Endstatus für einen Benutzer für den ausgewählten Optionen der PSTN-Konnektivität in Office 365-Telefonsystem bereitgestellt. Nur für VoIP relevanten Attribute werden angezeigt.

|Benutzerattribute-Objekt |Telefonsystem mit Anrufplänen|Phone System mit lokalen PSTN-Anbindung über Skype für Business Server|Telefon-System mit lokalen PSTN-Anbindung über Cloud-Connector|Telefon-System mit lokalen PSTN-Anbindung über direkte Routing|
|---|---|---|---|---|
|Client|Skype für Geschäftskunden und Teams |Skype for Business |Skype for Business |Microsoft Teams|
|Lizenzen|Skype-Business Online</br>Planen von 2</br></br>MCOProfessional oder MCOSTANDARD)</br></br></br>Telefonsystem (MCOEV)</br></br></br>Anrufpläne</br>Microsoft Teams|Skype Business Online-Plan 2 (MCOProfessional oder MCOSTANDARD)</br></br></br>Telefonsystem (MCOEV)|Skype Business Online-Plan 2 (MCOProfessional oder MCOSTANDARD)</br></br></br>Telefonsystem (MCOEV)|Skype Business Online-Plan 2 (MCOProfessional oder MCOSTANDARD</br></br></br>Telefonsystem (MCOEV)</br></br>Microsoft Teams|
OnPremLineURI |-|Die Telefonnummer synchronisiert werden muss, aus der lokalen AD. |Die Telefonnummer kann entweder im lokalen Active Directory oder im Azure Active Directory verwaltet werden.|Die Telefonnummer kann entweder im lokalen Active Directory oder im Azure Active Directory verwaltet werden. Wenn die Organisation der lokale Skype für Unternehmen verfügt, muss die Nummer aus der lokalen Active Directory synchronisiert werden.|
|"Lineuri"|Aufrufen von PSTN-Telefonnummer|Legen Sie automatisch aus dem OnPremLineURI-parameter|Legen Sie automatisch aus dem OnPremLineURI-parameter|Legen Sie automatisch aus dem OnPremLineURI-parameter|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|"Voicepolicy" sein|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|"Hostedvoicemailpolicy" |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Hat den Wert|Hat den Wert|Hat den Wert|-|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Hat den Wert|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly oder Inseln|$Null|$Null|Inseln oder TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient – lesen Sie bitte den Hinweis unten.|Teams oder SfB |SfB|SfB|Microsoft Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|-|-|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|-|-|True|
||||||

<sup>1</sup> Auswählen des richtigen Modus von der TeamsUpgradePolicy, hängt vom Szenario ab. Bitte informieren Sie sich über die VoIP-Erfahrung in unterschiedlichen Modi [Migration und Interoperabilität Anleitungen für Organisationen](migration-interop-guidance-for-teams-with-skype.md)mit Teams zusammen mit Skype für Unternehmen.

<sup>2</sup> Als zuvor bekannt gegebenen TeamsInteropPolicy (für das Ende des Q3 gezielte) zurückgezogen und seine Funktionalität ist in TeamsUpgradePolicy konsolidiert werden. Interoperabilität und Migration werden mit "Koexistenzmodus", wie durch TeamsUpgradePolicy, bestimmt das jetzt verfügbar ist verwaltet werden. Auswahl des Benutzers Modus wird gesteuert, beide routing von eingehenden Anrufen und Chats und der Benutzer kann in der Clientcomputer Chats und Anrufe initiieren oder Besprechungen planen. Während der TeamsInteropPolicy gültig ist, muss sie während der Phaseout parallel mit TeamsUpgradePolicy festgelegt werden.  

Im Rahmen der Maßnahme hat Microsoft kürzlich der "Microsoft-Teams & Skype für Business-Verwaltungskonsole" (auch bekannt als modernen Portal) entsprechend den neuen Model im Projektmanagement basierend auf Koexistenz Modi aktualisiert. In modernen Portal festgelegt konfigurieren TeamsUpgradePolicy wird nun automatisch auch TeamsInteropPolicy auf konsistente Wert, damit TeamsInteropPolicy nicht mehr in der Benutzeroberfläche verfügbar gemacht wird. Administratoren über PowerShell müssen jedoch weiterhin sowohl TeamsUpgradePolicy und TeamsInteropPolicy zusammen ordnungsgemäßes routing sicherzustellen festgelegt. Nach Abschluss der Übergang zur TeamsUpgradePolicy werden nicht mehr erforderlich, auch TeamsInteropPolicy festgelegt.

Weitere Informationen finden Sie auf [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrieren von Aufrufen Pläne

Weitere Informationen zum Migrieren von Aufrufen plant finden Sie unter:

- [Einrichten von Anrufplänen](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice-Benutzer](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/en-us/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Es wird empfohlen, Previouslycconfigured Lizenzinformationen Plan wie folgt zu entfernen:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrieren von Office 365-Telefonsystem mit lokalen PSTN-Konnektivität in Skype for Business Server

Weitere Informationen zum Migrieren von Telefonsystem mit lokalen PSTN-Konnektivität in Skype für Business Server finden Sie unter den folgenden:

- [Planung](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Bereitstellen von](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Es wird empfohlen, dass Sie zuvor konfigurierten VoIP-routing-Informationen wie folgt entfernen:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrieren von Office 365-Telefonsystem mit lokalen PSTN-Anbindung über Cloud Connector Edition 

Weitere Informationen zum Migrieren von Telefonsystem mit lokalen PSTN-Anbindung über Cloud-Connector finden Sie unter den folgenden:

- [Planung](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Bereitstellen von](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Benutzerkonfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Es wird empfohlen, dass Sie zuvor konfigurierten VoIP-routing-Informationen wie folgt entfernen:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>VERWANDTE LINKS

[Hinweise zur Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen](migration-interop-guidance-for-teams-with-skype.md)

[GRANT-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Neue CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

