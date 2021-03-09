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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Erfahren Sie, wie Sie Telefonsystem-Voicedienste für Ihre Skype for Business-Benutzer aktivieren.
ms.openlocfilehash: bbcf8b35d91015067943eec2cbe43525e952a7f7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569357"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Aktivieren von Benutzern für Enterprise-VoIP online und für Telefonsystem-Voicemail
 
> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Erfahren Sie, wie Sie Telefonsystem-Voicedienste für Ihre Skype for Business-Benutzer aktivieren.
  
Der letzte Schritt bei der Bereitstellung von Telefonsystem mit lokalen PSTN-Verbindungen besteht in der Aktivierung Ihrer Benutzer für Telefonsystem und Voicemail. Um diese Funktionen zu aktivieren, müssen Sie ein Benutzer mit der Rolle "Globaler Administrator" sein und remote PowerShell ausführen können. Sie müssen die Schritte in diesem Thema für alle Benutzerkonten ausführen, die noch nicht Enterprise-VoIP skype for Business Online aktiviert sind.
  
## <a name="enable-phone-system-voice-services"></a>Aktivieren von Sprachdiensten des Telefonsystems

Um einen Benutzer für Voice- und Voicemail im Telefonsystem zu aktivieren, müssen Sie einige erste Schritte ausführen, z. B. um zu überprüfen, ob der Skype for Business Online Connector auf Ihren Servern bereitgestellt ist, und ihre Benutzer für gehostete Voicemail zu aktivieren.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>So aktivieren Sie Ihre Benutzer für Voice- und Voicemail im Telefonsystem

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

1. Bevor Sie beginnen, überprüfen Sie, ob das Teams PowerShell-Modul auf Ihren Front-End-Servern installiert ist. Falls nicht, installieren Sie die Installation mithilfe der Anweisungen in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Starten Windows PowerShell als Administrator.
    
3. Geben Sie Folgendes ein, und drücken Sie die EINGABETASTE:
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Verwenden Sie Set-CsUser cmdlet, um die Eigenschaften $EnterpriseVoiceEnabled und $HostedVoiceMail Benutzer wie folgt zuzuordnen:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Zum Beispiel:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Sie können einen Benutzer auch nach seiner SIP-Adresse, dem Benutzerprinzipalnamen (UPN), dem Domänennamen und Benutzernamen (Domäne\Benutzername) und dem Anzeigenamen in Active Directory ("Bob Kelly") angeben. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Aktualisieren des Leitungs-URI und des Wählplans für Benutzer, die für das Telefonsystem aktiviert sind

In diesem Abschnitt wird beschrieben, wie Sie den Leitungs-URI und den Wählplan für Benutzer aktualisieren, die für das Telefonsystem aktiviert sind. 
  
### <a name="to-update-the-line-uri"></a>So aktualisieren Sie den Zeilen-URI

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Verwenden Sie das Startmenü oder die Desktopverknüpfung, um die Skype for Business Server-Systemsteuerung zu öffnen.
    
    > [!NOTE]
    > Sie können auch ein Browserfenster öffnen und dann die Administrator-URL eingeben, um die Skype for Business Server-Systemsteuerung zu öffnen. 
  
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business-Benutzerkonto, das Sie den Zeilen-URI ändern möchten.
    
6. Klicken **Sie auf Zeilen-URI,** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. tel:+14255550200). Klicken Sie dann auf **Commit**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren des Wählplans mithilfe von lokalen Windows PowerShell Cmdlets

Sie können benutzerspezifischen Wählplänen Windows PowerShell und dem [Grant-CsDialPlan-Cmdlet](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) zuweisen. Sie können dieses Cmdlet entweder über Skype for Business Server 2015 oder über eine Remotesitzung von Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen Benutzerwählplan zu

- Verwenden Sie das [Grant-CsDialPlan-Cmdlet,](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) um den benutzerspezifischen Wählplan RedmondDialPlan dem Benutzer Ken Myer zuzuordnen:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen Benutzerwählplan zu

- Der folgende Befehl weist den Benutzerwählplan RedmondDialPlan allen Benutzern zu, die in der Stadt Redmond arbeiten. Weitere Informationen zum in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation zum [Cmdlet Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Sie können entweder globale oder Benutzerwählpläne für Onlinebenutzer verwenden. Standortwählpläne können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>So designiert sie einen benutzerfreundlichen Wählplan

- Verwenden Sie [das Cmdlet Grant-CsDialPlan,](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) um die Zuteilung eines benutzerspezifischen Wählplans auf, der zuvor Ken Myer zugewiesen war. Nachdem der Benutzerwählplan nicht mehr zugewiesen wurde, wird Ken Myer automatisch mithilfe des globalen Wählplans oder des Dienstwählplans verwaltet, der seinem Registrar- oder PSTN-Gateway zugewiesen ist. Ein Dienstbereichswählplan hat Vorrang vor dem globalen Wählplan:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren der Voiceroutingrichtlinien mithilfe von lokalen Windows PowerShell Cmdlets

In diesem Abschnitt wird beschrieben, wie Sie die Voiceroutingrichtlinien für Benutzer aktualisieren, die für Das Telefonsystem aktiviert sind.
  
Telefonsystembenutzern muss eine Voiceroutingrichtlinie zugewiesen sein, damit Anrufe erfolgreich geroutet werden können. Dies unterscheidet sich von lokalen Business Voice-Benutzern, denen eine Voicerichtlinie zugewiesen werden muss, damit Anrufe erfolgreich geroutet werden können. Die Voiceroutingrichtlinie sollte PSTN-Verwendungen enthalten, die autorisierte Anrufe und Routen für Benutzer des Telefonsystems definieren. Sie können diese PSTN-Verwendungen aus vorhandenen Voicerichtlinien in neue Voiceroutingrichtlinien kopieren. Weitere Informationen finden Sie unter [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Allen Telefonsystembenutzern wird dieselbe #A0 namens BusinessVoice zugewiesen, die die zulässigen Anruffunktionen definiert. Beispiel: Gleichzeitiges Klingeln zulassen. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Benutzer-Voiceroutingrichtlinie zu

- Verwenden Sie das [Grant-CsVoiceRoutingPolicy-Cmdlet,](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) um dem Benutzer Ken Myer die Benutzer-Voiceroutingrichtlinie RedmondVoiceRoutingPolicy zuzuordnen:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Benutzer-Voiceroutingrichtlinie zu

- Mit dem nächsten Befehl wird die Benutzerrichtlinie "RedmondVoiceRoutingPolicy" allen Benutzern zugewiesen, die in der Stadt Redmond arbeiten. Weitere Informationen zum in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Sie können entweder globale oder Benutzer-Voiceroutingrichtlinien für Onlinebenutzer verwenden. Standort voice routing policies cannot be used as these apply only to users who are hosted on premises and are assigned to an on-premises site. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>So designiert sie eine Benutzer-Voiceroutingrichtlinie

- Verwenden Sie Grant-CsVoiceRoutingPolicy, um die Zuzuweisen von Benutzer-Voiceroutingrichtlinien auf, die Zuvor Ken Myer zugewiesen waren. Nachdem die Benutzerrichtlinie für das Voicerouting nicht mehr zugewiesen wurde, wird Ken Myer automatisch mithilfe der globalen Voiceroutingrichtlinie verwaltet.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Weitere Informationen finden Sie unter [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

