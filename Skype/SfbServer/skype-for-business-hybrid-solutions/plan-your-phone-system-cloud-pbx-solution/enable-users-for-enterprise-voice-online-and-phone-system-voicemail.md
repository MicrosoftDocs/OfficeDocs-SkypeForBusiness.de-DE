---
title: Aktivieren von Benutzern für Enterprise-VoIP online und Telefonsystem in Office 365-Voicemail
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
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
description: Erfahren Sie, wie in Office 365-VoIP-Dienste für Ihre Skype für Unternehmensbenutzer Telefonsystem aktivieren.
ms.openlocfilehash: ef1e7b98ad4a6080d07dc4abca717aef49a725ed
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887904"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Aktivieren von Benutzern für Enterprise-VoIP online und Telefonsystem in Office 365-Voicemail
 
Erfahren Sie, wie in Office 365-VoIP-Dienste für Ihre Skype für Unternehmensbenutzer Telefonsystem aktivieren.
  
Der letzte Schritt bei der Bereitstellung von Telefonsystem in Office 365 mit lokalen PSTN-Anbindung ist Ihre Benutzer für Telefonsystem in Office 365 und Voicemail aktivieren. Um diese Funktionen aktivieren zu können, muss Ihnen als Benutzer in Office 365 die globale Administratorrolle zugewiesen sein, und Sie müssen in der Lage sein, Remote-PowerShell auszuführen. Sie müssen die Schritte in diesem Abschnitt für alle Benutzerkonten ausführen, für die Enterprise-VoIP für Skype for Business Online noch nicht aktiviert ist.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Aktivieren Sie Telefonsystem in Office 365-VoIP-Dienste

Um einen Benutzer für Telefonsystem in Office 365-VoIP und Voicemail aktivieren, müssen Sie erste Schritte, wie das Prüfen von der Skype für Business Online Connector auf Ihren Servern bereitgestellt wird und Sie Ihre Benutzer für gehostete Voicemail aktivieren ausführen.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>So aktivieren Sie Ihre Benutzer für Telefonsystem in Office 365 Sprach- und voicemail

1. Bevor Sie beginnen, überprüfen Sie, dass die Skype für Business Online Connector (Windows PowerShell-Modul) auf Front-End-Servern bereitgestellt wird. Wenn sie nicht der Fall ist, können Sie es aus [dem Downloadcenter](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen. Sie finden weitere Informationen zur Verwendung in diesem Modul zur [Konfiguration des Computers für Skype für das Business Online Management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Starten von Windows PowerShell als Administrator
    
3. Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:
    
  ```
  Import-Module skypeonlineconnector
  ```

4. Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:
    
  ```
  $cred = Get-Credential
  ```

    Nachdem Sie die EINGABETASTE gedrückt haben, sollte das Windows PowerShell-Dialogfeld für die Eingabe von Anmeldeinformationen angezeigt werden.
    
5. Geben Sie Ihren Mandantenadministrator-Benutzernamen und Ihr Kennwort ein und klicken Sie dann auf **OK**.
    
6. Machen Sie folgende Eingaben im PowerShell-Fenster und drücken Sie anschließend die EINGABETASTE:
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. Importieren Sie die Sitzung, indem Sie das folgende Cmdlet eingeben:
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    Bei der Ausführung von PowerShell auf einen Skype für Business Server, die lokalen Skype für Business Cmdlets bereits geladen sind beim Öffnen von PowerShell. Geben Sie den Parameter AllowClobber - damit können die online-Cmdlets, die lokale-Cmdlets mit demselben Namen zu überschreiben.
    
8. Verwenden Sie das Cmdlet „Set-CsUser“ wie folgt, um Ihrem Benutzer die Eigenschaften „$EnterpriseVoiceEnabled“ und „$HostedVoiceMail“ zuzuweisen:
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    Beispiel:
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > Sie können einen Benutzer genauso über seine SIP-Adresse, den Benutzerprinzipalnamen (UPN), den Domänennamen (Domäne\Benutzername) und den Displaynamen in Active Directory („Bob Kelly“) kenntlich machen. 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Aktualisieren Sie den Anschluss-URI und Wähleinstellungen für Benutzer aktiviert für Telefonsystem in Office 365

In diesem Abschnitt wird beschrieben, wie zum Aktualisieren der Anschluss-URI und Wähleinstellungen für Benutzer in Office 365 Telefonsystem. 
  
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

Pro Benutzer weisen Sie Wähleinstellungen mit Windows PowerShell und dem [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) -Cmdlet. Sie können dieses Cmdlet entweder von der Skype für Business Server 2015 oder aus einer Remotesitzung von Windows PowerShell ausführen.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen benutzerbasierten Wählplan zu

- Verwenden Sie das Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , dem Benutzer Ken Myer den benutzerspezifischen Wählplan RedmondDialPlan zugewiesen:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen benutzerbasierten Wählplan zu

- Mit dem folgenden Befehl wird der benutzerbasierte Wählplan „RedmondDialPlan“ allen Benutzern zugewiesen, die in Redmond arbeiten. Weitere Informationen über die Parameter "LdapFilter" in diesem Befehl verwendet finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Möglicherweise verwenden Sie entweder globale oder Benutzerwähleinstellungen für Onlinebenutzer. Standortwählpläne können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>So heben Sie die Zuweisung eines benutzerbasierten Wählplans auf

- Verwenden Sie das [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) -Cmdlet zum Aufheben der Zuweisung von alle benutzerspezifischen Wählplan zuvor Ken Myer zugewiesen. Nachdem die Zuweisung des benutzerbezogenen Wählplans aufgehoben wurde, wird „Ken Myer“ automatisch mithilfe des globalen Wählplans oder des Wählplans auf Dienstebene für seine erweiterte Registrierungsstelle oder sein PSTN-Gateway verwaltet. Ein Wählplan auf Dienstebene hat Vorrang vor dem globalen Wählplan.
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aktualisieren der Richtlinien für das VoIP-Routing mithilfe von lokalen Windows PowerShell-Cmdlets

In diesem Abschnitt wird beschrieben, wie die VoIP-Routingrichtlinien zurückgegeben Telefonsystem in Office 365-fähigen Benutzer aktualisieren.
  
Telefonsystem in Office 365-Benutzer benötigen eine VoIP-Routing-Richtlinie zugewiesen für Anrufe erfolgreich weitergeleitet. Das ist anders als bei lokalen Unternehmens-VoIP-Benutzern, denen eine VoIP-Richtlinie zugewiesen sein muss, damit Anrufe erfolgreich weitergeleitet werden können. Die VoIP-Routing-Richtlinie sollte PSTN-Verwendungen enthalten, die autorisierten Anrufe und Routen für Telefonsystem in Office 365-Benutzer zu definieren. Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue Richtlinien für das VoIP-Routing kopieren. Weitere Informationen finden Sie unter ["New-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Alle Telefonsystem in Office 365-Benutzer werden die gleichen online VoIP-Richtlinie mit dem Namen BusinessVoice definiert die zulässige Anruffunktion zugewiesen. Beispielsweise können Sie Gleichzeitiges Klingeln. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für das VoIP-Routing auf Benutzerebene zu

- Verwenden Sie das Cmdlet ["Grant-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) , die pro Benutzer bei der VoIP-Routingrichtlinie "redmondvoiceroutingpolicy" dem Benutzer Ken Myer zugewiesen:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für das VoIP-Routing auf Benutzerebene zu

- Mit dem nächsten Befehl wird die benutzerbasierte Richtlinie „RedmondVoiceRoutingPolicy“ allen Benutzern in der Stadt Redmond zugewiesen. Weitere Informationen über die Parameter "LdapFilter" in diesem Befehl verwendet finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Möglicherweise verwenden Sie entweder globale Einstellungen oder Einstellungen für das VoIP-Routing für Onlinebenutzer. Standortrichtlinien für das VoIP-Routing können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>So heben Sie die Zuweisung einer Richtlinie für das VoIP-Routing auf Benutzerebene auf

- Verwenden Sie das Grant-CsVoiceRoutingPolicy zum Aufheben der Zuweisung von alle VoIP-Routingrichtlinie pro Benutzer zuvor Ken Myer zugewiesen. Nachdem die Zuweisung der benutzerbezogenen VoIP-Routingrichtlinie aufgehoben ist, wird „Ken Myer“ automatisch über die globale VoIP-Routingrichtlinie verwaltet.
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Weitere Informationen finden Sie unter ["Grant-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

