---
title: Aktivieren von Benutzern für Enterprise-VoIP und für Telefonsystem in Office 365 Voicemail
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Erfahren Sie, wie Sie das Telefon System in Office 365 Voice Services für Ihre Skype for Business-Benutzer aktivieren.
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003465"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Aktivieren von Benutzern für Enterprise-VoIP und für Telefonsystem in Office 365 Voicemail
 
Erfahren Sie, wie Sie das Telefon System in Office 365 Voice Services für Ihre Skype for Business-Benutzer aktivieren.
  
Der letzte Schritt beim Bereitstellen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität besteht darin, Ihre Benutzer für das Telefonsystem in Office 365 und Voicemail zu aktivieren. Um diese Funktionen aktivieren zu können, muss Ihnen als Benutzer in Office 365 die globale Administratorrolle zugewiesen sein, und Sie müssen in der Lage sein, Remote-PowerShell auszuführen. Sie müssen die Schritte in diesem Abschnitt für alle Benutzerkonten ausführen, für die Enterprise-VoIP für Skype for Business Online noch nicht aktiviert ist.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Aktivieren des Telefonsystems in Office 365 Voice Services

Wenn Sie einen Benutzer für das Telefon System in Office 365 Voice und Voicemail aktivieren möchten, müssen Sie einige erste Schritte ausführen, beispielsweise überprüfen, ob der Skype for Business Online-Connector auf Ihren Servern bereitgestellt wird, und Ihre Benutzer für die gehostete Voicemail aktivieren.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>So aktivieren Sie Ihre Benutzer für das Telefon System in Office 365 Voice und Voicemail

1. Bevor Sie beginnen, überprüfen Sie, ob der Skype for Business Online Connector (Windows PowerShell-Modul) auf Ihren Front-End-Servern bereitgestellt wird. Wenn dies nicht der Fall ist, können Sie Sie aus [dem Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen. Weitere Informationen zur Verwendung dieses Moduls finden Sie unter [Konfigurieren Ihres Computers für die Skype for Business Online-Verwaltung](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Starten von Windows PowerShell als Administrator
    
3. Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:
    
   ```powershell
   $cred = Get-Credential
   ```

    Nachdem Sie die EINGABETASTE gedrückt haben, sollte das Windows PowerShell-Dialogfeld für die Eingabe von Anmeldeinformationen angezeigt werden.
    
5. Geben Sie Ihren Mandantenadministrator-Benutzernamen und Ihr Kennwort ein und klicken Sie dann auf **OK**.
    
6. Machen Sie folgende Eingaben im PowerShell-Fenster und drücken Sie anschließend die EINGABETASTE:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importieren Sie die Sitzung, indem Sie das folgende Cmdlet eingeben:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Wenn PowerShell auf einem Skype for Business-Server ausgeführt wird, sind die lokalen Cmdlets für Skype for Business bereits geladen, wenn Sie PowerShell öffnen. Sie müssen den-AllowClobber-Parameter angeben, damit die Online-Cmdlets die lokalen Cmdlets mit demselben Namen überschreiben können.
    
8. Verwenden Sie das Cmdlet „Set-CsUser“ wie folgt, um Ihrem Benutzer die Eigenschaften „$EnterpriseVoiceEnabled“ und „$HostedVoiceMail“ zuzuweisen:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Beispiel:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Sie können einen Benutzer genauso über seine SIP-Adresse, den Benutzerprinzipalnamen (UPN), den Domänennamen (Domäne\Benutzername) und den Displaynamen in Active Directory („Bob Kelly“) kenntlich machen. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Aktualisieren des Leitungs-URIs und des Wählplans für Benutzer, die für das Telefon System in Office 365 aktiviert sind

In diesem Abschnitt wird beschrieben, wie Sie den Zeilen-URI und den Wählplan für für Telefonsysteme aktivierte Benutzer in Office 365 aktualisieren. 
  
### <a name="to-update-the-line-uri"></a>So aktualisieren Sie die Anschluss-URI

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Benutzen Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Systemsteuerung von Skype for Business Server zu öffnen.
    
    > [!NOTE]
    > Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen. 
  
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business-Benutzerkonto, dessen Anschluss-URI Sie ändern möchten.
    
6. Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. Tel:+14255550200). Klicken Sie dann auf **Commit ausführen**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren des Wählplans mithilfe lokaler Windows PowerShell-Cmdlets

Sie können Wählpläne für einzelne Benutzer mit Windows PowerShell und dem Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) zuweisen. Sie können dieses Cmdlet entweder über den Skype for Business Server 2015 oder über eine Remotesitzung von Windows PowerShell ausführen.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen benutzerbasierten Wählplan zu

- Verwenden Sie das Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , um dem Benutzer Ken Myers den benutzerseitigen Wähl Plan redmonddialplan "zuzuweisen:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen benutzerbasierten Wählplan zu

- Mit dem folgenden Befehl wird der benutzerbasierte Wählplan „RedmondDialPlan“ allen Benutzern zugewiesen, die in Redmond arbeiten. Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Möglicherweise verwenden Sie entweder globale oder Benutzerwähleinstellungen für Onlinebenutzer. Standortwählpläne können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>So heben Sie die Zuweisung eines benutzerbasierten Wählplans auf

- Verwenden Sie das Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , um die Zuweisung von benutzerseitigen Wählplänen aufzuheben, die Ken Myers zuvor zugewiesen wurden. Nachdem die Zuweisung des benutzerbezogenen Wählplans aufgehoben wurde, wird „Ken Myer“ automatisch mithilfe des globalen Wählplans oder des Wählplans auf Dienstebene für seine erweiterte Registrierungsstelle oder sein PSTN-Gateway verwaltet. Ein Wählplan auf Dienstebene hat Vorrang vor dem globalen Wählplan.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren der Richtlinien für das VoIP-Routing mithilfe von lokalen Windows PowerShell-Cmdlets

In diesem Abschnitt wird beschrieben, wie Sie die VoIP-Routing Richtlinien für Benutzer, die für das Telefon System aktiviert sind, in Office 365 aktualisieren.
  
Telefon System in Office 365 Benutzern muss eine VoIP-Routing Richtlinie zugewiesen sein, damit Anrufe erfolgreich weitergeleitet werden können. Das ist anders als bei lokalen Unternehmens-VoIP-Benutzern, denen eine VoIP-Richtlinie zugewiesen sein muss, damit Anrufe erfolgreich weitergeleitet werden können. Die VoIP-Routing Richtlinie sollte PSTN-Nutzungen enthalten, die autorisierte Anrufe und Routen für Telefonsysteme in Office 365-Benutzern definieren. Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue Richtlinien für das VoIP-Routing kopieren. Weitere Informationen finden Sie unter [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Alle Telefonsysteme in Office 365 Benutzern wird dieselbe Online-VoIP-Richtlinie mit dem Namen BusinessVoice zugewiesen, in der die zulässigen Anruffunktionen definiert sind. So können Sie beispielsweise Gleichzeitiges Klingeln zulassen. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für das VoIP-Routing auf Benutzerebene zu

- Verwenden Sie das Cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) , um dem Benutzer Ken Myers die benutzerspezifische VoIP-Routing Richtlinien-RedmondVoiceRoutingPolicy zuzuweisen:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für das VoIP-Routing auf Benutzerebene zu

- Mit dem nächsten Befehl wird die benutzerbasierte Richtlinie „RedmondVoiceRoutingPolicy“ allen Benutzern in der Stadt Redmond zugewiesen. Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Möglicherweise verwenden Sie entweder globale Einstellungen oder Einstellungen für das VoIP-Routing für Onlinebenutzer. Standortrichtlinien für das VoIP-Routing können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>So heben Sie die Zuweisung einer Richtlinie für das VoIP-Routing auf Benutzerebene auf

- Verwenden Sie die Grant-CsVoiceRoutingPolicy, um die Zuweisung einer benutzerseitigen VoIP-Routing Richtlinie aufzuheben, die Ken Myers zuvor zugewiesen wurde. Nachdem die Zuweisung der benutzerbezogenen VoIP-Routingrichtlinie aufgehoben ist, wird „Ken Myer“ automatisch über die globale VoIP-Routingrichtlinie verwaltet.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Weitere Informationen finden Sie unter [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

