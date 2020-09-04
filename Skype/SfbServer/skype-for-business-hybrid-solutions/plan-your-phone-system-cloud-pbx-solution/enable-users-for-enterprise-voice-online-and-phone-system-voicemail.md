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
description: Erfahren Sie, wie Sie VoIP-Dienste für Telefonsysteme für Ihre Skype for Business-Benutzer aktivieren.
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359181"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Aktivieren von Benutzern für Enterprise-VoIP online und für Telefonsystem-Voicemail
 
> [!Important]
> Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

Erfahren Sie, wie Sie VoIP-Dienste für Telefonsysteme für Ihre Skype for Business-Benutzer aktivieren.
  
Der letzte Schritt bei der Bereitstellung von Telefonsystem mit lokaler PSTN-Konnektivität besteht darin, Ihre Benutzer für Telefonsystem und Voicemail zu aktivieren. Um diese Funktionen zu aktivieren, müssen Sie ein Benutzer mit der Rolle "globaler Administrator" sein und Remote-PowerShell ausführen können. Sie müssen die Schritte in diesem Thema für alle Benutzerkonten ausführen, für die Enterprise-VoIP für Skype for Business Online noch nicht aktiviert ist.
  
## <a name="enable-phone-system-voice-services"></a>VoIP-Dienste für Telefonsysteme aktivieren

Wenn Sie einen Benutzer für Telefon System-VoIP und Voicemail aktivieren möchten, müssen Sie einige anfängliche Schritte ausführen, um zu überprüfen, ob der Skype for Business Online-Connector auf Ihren Servern bereitgestellt wurde, und Ihre Benutzer für gehostete Voicemail zu aktivieren.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>So aktivieren Sie Ihre Benutzer für Telefon System Sprache und Voicemail

1. Bevor Sie beginnen, sollten Sie sicherstellen, dass der Skype for Business Online Connector (Windows PowerShell-Modul) auf Ihren Front-End-Servern bereitgestellt wird. Wenn dies nicht der Fall ist, können Sie es aus [dem Download Center](https://www.microsoft.com/download/details.aspx?id=39366)herunterladen. Weitere Informationen zur Verwendung dieses Moduls finden Sie unter [Konfigurieren Ihres Computers für Skype for Business Online Verwaltung](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).
    
2. Starten Sie Windows PowerShell als Administrator.
    
3. Geben Sie Folgendes ein, und drücken Sie die EINGABETASTE:
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Geben Sie Folgendes ein, und drücken Sie die EINGABETASTE:
    
   ```powershell
   $cred = Get-Credential
   ```

    Nachdem Sie die EINGABETASTE gedrückt haben, sollte das Dialogfeld Windows PowerShell Anmeldeinformationen angezeigt werden.
    
5. Geben Sie den Benutzernamen und das Kennwort Ihres Mandanten Administrators ein, und klicken Sie auf **OK**.
    
6. Geben Sie im PowerShell-Fenster Folgendes ein, und drücken Sie die EINGABETASTE:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importieren Sie die Sitzung, indem Sie das folgende Cmdlet eingeben:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Beim Ausführen von PowerShell auf einem Skype for Business Server werden die lokalen Skype for Business-Cmdlets bereits geladen, wenn Sie PowerShell öffnen. Sie müssen den Parameter-AllowClobber angeben, damit die Online-Cmdlets die lokalen Cmdlets mit dem gleichen Namen überschreiben können.
    
8. Verwenden Sie das Cmdlet "CsUser", um dem Benutzer die Eigenschaften $EnterpriseVoiceEnabled und $HostedVoiceMail wie folgt zuzuweisen:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Zum Beispiel:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Sie können einen Benutzer auch über seine SIP-Adresse, den Benutzerprinzipalnamen (User Principal Name, UPN), den Domänennamen und den Benutzernamen (Domäne \ Benutzername) und den Anzeigenamen in Active Directory ("Bob Kelly") angeben. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Aktualisieren der Leitungs-URI und des Wählplans für Benutzer, die für das Telefon System aktiviert sind

In diesem Abschnitt wird beschrieben, wie Sie den Anschluss-URI und die Wähleinstellungen für für Telefonsysteme aktivierte Benutzer aktualisieren. 
  
### <a name="to-update-the-line-uri"></a>So aktualisieren Sie den Anschluss-URI

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Verwenden Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Skype for Business Server-Systemsteuerung zu öffnen.
    
    > [!NOTE]
    > Sie können auch ein Browserfenster öffnen und die Administrator-URL eingeben, um die Skype for Business Server-Systemsteuerung zu öffnen. 
  
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business Benutzerkonto, für das Sie den Anschluss-URI ändern möchten.
    
6. Klicken Sie auf **Leitungs-URI**, und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise Tel: + 14255550200). Klicken Sie dann auf **Commit**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren der Wähleinstellungen mithilfe von lokalen Windows PowerShell-Cmdlets

Sie können benutzerspezifische Wählpläne mit Windows PowerShell und dem Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) zuweisen. Sie können dieses Cmdlet entweder im Skype for Business Server 2015 oder in einer Remotesitzung von Windows PowerShell ausführen.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen Wählplan pro Benutzer zu

- Verwenden Sie das [Grant-CsDialPlan-](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet, um den benutzerseitigen Wählplan "redmonddialplan" dem Benutzer Ken Myers zuzuweisen:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen Wählplan pro Benutzer zu

- Mit dem folgenden Befehl wird der benutzerspezifische Wählplan "redmonddialplan" allen Benutzern zugewiesen, die in der Stadt Redmond arbeiten. Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Sie können entweder globale oder Benutzer-Wählpläne für Online-Benutzer verwenden. Website Wähl Pläne können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>So heben Sie die Zuweisung von benutzerbezogenen Wähleinstellungen auf

- Verwenden Sie das [Grant-CsDialPlan-](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet, um die Zuweisung aller benutzerbezogenen Wähleinstellungen aufzuheben, die Ken Myers zuvor zugewiesen wurden. Nachdem der benutzerbezogene Wählplan nicht zugewiesen wurde, wird Ken Myers automatisch mithilfe der globalen Wähleinstellungen oder des Dienstbereichs Wähl Plans verwaltet, der seiner Registrierungsstelle oder dem PSTN-Gateway zugewiesen ist. Ein Dienstbereich Wähleinstellungen hat Vorrang vor den globalen Wähleinstellungen:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren der VoIP-Routing Richtlinien mithilfe von lokalen Windows PowerShell-Cmdlets

In diesem Abschnitt wird beschrieben, wie Sie die VoIP-Routing Richtlinien für für Telefonsysteme aktivierte Benutzer aktualisieren.
  
Telefon System Benutzern muss eine VoIP-Routing Richtlinie zugewiesen sein, damit Anrufe erfolgreich weitergeleitet werden können. Dies unterscheidet sich von lokalen Business Voice-Benutzern, denen eine VoIP-Richtlinie zugewiesen werden muss, damit Anrufe erfolgreich weitergeleitet werden können. Die VoIP-Routing Richtlinie sollte PSTN-Verwendungen enthalten, die autorisierte Anrufe und Routen für Telefon System Benutzer definieren. Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue VoIP-Routing Richtlinien kopieren. Weitere Informationen finden Sie unter [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Allen Telefon System Benutzern wird dieselbe Online Sprachrichtlinie namens "BusinessVoice" zugewiesen, die die zulässigen Anruffunktionen definiert. lassen Sie beispielsweise gleichzeitigen Ring zu. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine VoIP-Routing Richtlinie pro Benutzer zu

- Verwenden Sie das [Grant-csvoiceroutingpolicy "-](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) Cmdlet, um die benutzerbasierte VoIP-Routing Richtlinie" redmondvoiceroutingpolicy "dem Benutzer Ken Myers zuzuweisen:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerspezifische VoIP-Routing Richtlinie zu

- Mit dem folgenden Befehl wird die benutzerspezifische VoIP-Routing Richtlinie "redmondvoiceroutingpolicy" allen Benutzern zugewiesen, die in der Stadt Redmond arbeiten. Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Sie können entweder globale oder Benutzer-VoIP-Routing Richtlinien für Online-Benutzer verwenden. Website VoIP-Routing Richtlinien können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>So heben Sie die Zuweisung einer VoIP-Routing Richtlinie pro Benutzer auf

- Verwenden Sie das Grant-csvoiceroutingpolicy ", um die Zuweisung einer benutzerbasierten VoIP-Routing Richtlinie aufzuheben, die Ken Myers zuvor zugewiesen wurde. Nachdem die Zuweisung der VoIP-Routing Richtlinie pro Benutzer aufgehoben wurde, wird Ken Myers automatisch mithilfe der globalen VoIP-Routing Richtlinie verwaltet.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Weitere Informationen finden Sie unter [Grant-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

