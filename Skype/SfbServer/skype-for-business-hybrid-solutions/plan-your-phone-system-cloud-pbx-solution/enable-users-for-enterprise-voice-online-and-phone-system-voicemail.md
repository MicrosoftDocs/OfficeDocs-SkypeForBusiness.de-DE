---
title: Aktivieren von Benutzern für Enterprise-VoIP online und für Telefonsystem-Voicemail
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Erfahren Sie, wie Sie Telefonsystem VoIP-Dienste für Ihre Skype for Business Benutzer aktivieren.
ms.openlocfilehash: 9c9123b79a1fd5557d0d31db7b4b150bcda80af3
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563438"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Aktivieren von Benutzern für Enterprise-VoIP online und für Telefonsystem-Voicemail
 
> [!Important]
> Skype for Business Online wurde am 31. Juli 2021 eingestellt, und die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung , ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online, wird nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)mit Teams verbinden.

Erfahren Sie, wie Sie Telefonsystem VoIP-Dienste für Ihre Skype for Business Benutzer aktivieren.
  
Der letzte Schritt bei der Bereitstellung von Telefonsystem mit lokaler PSTN-Konnektivität besteht darin, Ihren Benutzern Telefonsystem und Voicemail zu ermöglichen. Um diese Funktionen zu aktivieren, müssen Sie ein Benutzer mit der Rolle "Globaler Administrator" sein und Remote-PowerShell ausführen können. Sie müssen die Schritte in diesem Thema für alle Benutzerkonten ausführen, die noch nicht Enterprise-VoIP für Skype for Business Online aktiviert haben.
  
## <a name="enable-phone-system-voice-services"></a>Aktivieren Telefonsystem VoIP-Dienste

Um einen Benutzer für Telefonsystem VoIP und Voicemail zu aktivieren, müssen Sie einige erste Schritte ausführen, z. B. überprüfen, ob der Skype for Business Online Connector auf Ihren Servern bereitgestellt ist, und Ihre Benutzer für gehostete Voicemail aktivieren.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>So aktivieren Sie Ihre Benutzer für Telefonsystem Voice- und Voicemail

> [!NOTE]
> Skype for Business Online-Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
> Wenn Sie die neueste [Teams öffentliche PowerShell-Version](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

1. Bevor Sie beginnen, überprüfen Sie, ob das Teams PowerShell-Modul auf Ihren Front-End-Servern installiert ist. Wenn dies nicht der Fall ist, installieren Sie die Installation mithilfe der Anweisungen in [Teams Installation des PowerShell-Moduls.](/microsoftteams/teams-powershell-install)
    
2. Starten Sie Windows PowerShell als Administrator.
    
3. Geben Sie Folgendes ein, und drücken Sie die EINGABETASTE:
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Verwenden Sie das Cmdlet Set-CsUser, um dem Benutzer die eigenschaften $EnterpriseVoiceEnabled und $HostedVoiceMail wie folgt zuzuweisen:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Beispiel:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Sie können einen Benutzer auch anhand seiner SIP-Adresse, des Benutzerprinzipalnamens (UPN), des Domänennamens und Benutzernamens (Domäne\Benutzername) und des Anzeigenamens in Active Directory ("Bob Kelly") angeben. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Aktualisieren des Anschluss-URI und des Wählplans für Benutzer, die für Telefonsystem aktiviert sind

In diesem Abschnitt wird beschrieben, wie Sie den Anschluss-URI und den Wählplan für Benutzer aktualisieren, die für Telefonsystem aktiviert sind. 
  
### <a name="to-update-the-line-uri"></a>So aktualisieren Sie den Anschluss-URI

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Verwenden Sie die Startmenü oder Desktopverknüpfung, um die Skype for Business Server Systemsteuerung zu öffnen.
    
    > [!NOTE]
    > Sie können auch ein Browserfenster öffnen und dann die Administrator-URL eingeben, um die Skype for Business Server Systemsteuerung zu öffnen. 
  
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business Benutzerkonto, das Sie den Zeilen-URI ändern möchten.
    
6. Klicken Sie auf **den Anschluss-URI,** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. tel:+14255550200). Klicken Sie dann auf **"Commit ausführen".**
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren des Wählplans mit lokalen Windows PowerShell Cmdlets

Sie können benutzerspezifische Wählpläne mit Windows PowerShell und dem Cmdlet [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) zuweisen. Sie können dieses Cmdlet entweder im Skype for Business Server 2015 oder in einer Remotesitzung von Windows PowerShell ausführen.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen Benutzerwählplan zu

- Verwenden Sie das Cmdlet [Grant-CsDialPlan,](/powershell/module/skype/grant-csdialplan?view=skype-ps) um dem Benutzer Ken Myer den Benutzerwählplan "RedmondDialPlan" zuzuweisen:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen Benutzerwählplan zu

- Der folgende Befehl weist den Benutzerwählplan "RedmondDialPlan" allen Benutzern zu, die in der Stadt Redmond arbeiten. Weitere Informationen zum in diesem Befehl verwendeten Parameter "LdapFilter" finden Sie in der Dokumentation zum Cmdlet ["Get-CsUser":](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Sie können entweder globale oder Benutzerwählpläne für Onlinebenutzer verwenden. Standortwählpläne können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>So heben Sie die Zuweisung eines Benutzerwählplans auf

- Verwenden Sie das Cmdlet [Grant-CsDialPlan,](/powershell/module/skype/grant-csdialplan?view=skype-ps) um die Zuweisung eines benutzerbasierten Wählplans aufzuheben, der zuvor Ken Myer zugewiesen wurde. Nachdem der Wählplan pro Benutzer nicht zugewiesen wurde, wird Ken Myer automatisch mithilfe des globalen Wählplans oder des Wählplans auf Dienstebene verwaltet, der seiner Registrierungsstelle oder seinem PSTN-Gateway zugewiesen ist. Ein Wählplan für den Dienstbereich hat Vorrang vor dem globalen Wählplan:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren der VoIP-Routingrichtlinien mithilfe lokaler Windows PowerShell Cmdlets

In diesem Abschnitt wird beschrieben, wie Sie die VoIP-Routingrichtlinien für Benutzer aktualisieren, die für Telefonsystem aktiviert sind.
  
Telefonsystem Benutzern muss eine VoIP-Routingrichtlinie zugewiesen sein, damit Anrufe erfolgreich weitergeleitet werden können. Dies unterscheidet sich von lokalen Business Voice-Benutzern, denen eine VoIP-Richtlinie zugewiesen werden muss, damit Anrufe erfolgreich weitergeleitet werden können. Die VoIP-Routingrichtlinie sollte PSTN-Verwendungen enthalten, die autorisierte Anrufe und Routen für Telefonsystem Benutzer definieren. Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue VoIP-Routingrichtlinien kopieren. Weitere Informationen finden Sie unter [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Allen Telefonsystem Benutzern wird dieselbe Online-VoIP-Richtlinie mit dem Namen "BusinessVoice" zugewiesen, die die zulässigen Anruffunktionen definiert, z. B. "Gleichzeitiges Klingeln zulassen". 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerbasierte VoIP-Routingrichtlinie zu

- Verwenden Sie das Cmdlet [Grant-CsVoiceRoutingPolicy,](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) um dem Benutzer Ken Myer die Benutzer-VoIP-Routingrichtlinie "RedmondVoiceRoutingPolicy" zuzuweisen:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Benutzerspezifische VoIP-Routingrichtlinie zu

- Der nächste Befehl weist die benutzerbasierte VoIP-Routingrichtlinie "RedmondVoiceRoutingPolicy" allen Benutzern zu, die in der Stadt Redmond arbeiten. Weitere Informationen zum in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Sie können entweder globale oder Benutzer-VoIP-Routingrichtlinien für Onlinebenutzer verwenden. Standort-VoIP-Routingrichtlinien können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>So heben Sie die Zuweisung einer benutzerbasierten VoIP-Routingrichtlinie auf

- Verwenden Sie die Grant-CsVoiceRoutingPolicy, um die Zuweisung einer benutzerbasierten VoIP-Routingrichtlinie aufzuheben, die zuvor Ken Myer zugewiesen wurde. Nachdem die Zuweisung der VoIP-Routingrichtlinie pro Benutzer aufgehoben wurde, wird Ken Myer automatisch mithilfe der globalen VoIP-Routingrichtlinie verwaltet.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Weitere Informationen finden Sie unter [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
