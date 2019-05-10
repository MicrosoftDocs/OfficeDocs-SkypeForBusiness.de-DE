---
title: Verwalten von Ressourcenkonten in Microsoft Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Erfahren Sie mehr über das Verwalten von Ressourcenkonten in Microsoft-Teams
ms.openlocfilehash: dea4a154e25c719ddabc572ba26ddb7d25c43d71
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835418"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto wird auch als ein deaktiviertes Benutzerobjekt in Azure Active Directory und kann verwendet werden, um Ressourcen im Allgemeinen darstellen. In Exchange kann verwendet werden, Konferenzräumen, beispielsweise darstellen und ermöglicht es ihnen, Sie haben eine Telefonnummer ein. Ein Ressourcenkonto kann in Microsoft 365 oder lokal mit Skype für Business Server verwaltet werden, und diese Konten werden mithilfe von Powershell-Befehlen erstellt.

In Microsoft-Teams oder Skype für Business Online, jeden Anruf Warteschlange oder automatische wird Attendant erforderlich, um ein Ressourcenkonto zugeordneten verfügen. Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt wird abhängig von der beabsichtigten Verwendung von der zugehörigen Aufruf Warteschlange oder automatische Telefonzentrale. Finden Sie in den Artikeln für Anruf Warteschlangen und automatische um-Telefonzentralen verknüpft unten in diesem Artikel, bevor Sie eine Telefonnummer ein Ressourcenkonto zuweisen.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Erforderliche Komponenten ein Ressourcenkonto eine Telefonnummer zuweisen

Erste Schritte beim es ist wichtig, sollten Sie einige Dinge bedenken:
  
- Eine automatische Telefonzentrale oder ein Anruf Warteschlange ist erforderlich, um ein Ressourcenkonto zugeordneten verfügen. Details auf Ressourcenkonten finden Sie unter [Manage Ressourcenkonten in Teams](manage-resource-accounts.md) .
- Wenn Sie eine direkte Routing Number zuweisen möchten, müssen Sie erwerben und weisen Sie die folgenden Lizenzen der Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on\).
- Wenn Sie stattdessen eine Microsoft-Dienst Zahl zuordnen möchten, müssen Sie erwerben und weisen Sie Ihr Ressourcenkonto folgenden Lizenzen \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on und Aufrufen planen\).
- Sie müssen nur die Ressourcenkonten mit einer Telefonnummer, die ihnen zugewiesenen lizenzieren. In einer geschachtelten automatische Telefonzentrale oder ein Anruf Warteschlange müssen nicht Sie den Rest der automatischen Telefonzentralen lizenzieren, oder rufen Sie Warteschlangen aus, wenn keine ihnen zugeordnete Telefonnummern vorhanden sind

> [!NOTE] 
> Direkte Routing Service Zahlen für die automatische Telefonzentrale und Anruf Warteschlangen werden für Benutzer von Microsoft-Teams und Agents nur unterstützt.

> [!NOTE] 
> Microsoft arbeitet eine entsprechende Lizenzierungsmodell für Anwendungen wie Cloud automatische Telefonzentrale und den Anruf-Warteschlangen für an jetzt Sie das Benutzerlizenzierung Objektmodell verwenden müssen.
    
> [!NOTE]
> Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans. Finden Sie unter [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Sie können eine direkte Routing Hybrid Anzahl Ihrer Ressourcenkonto zuweisen.  Einzelheiten finden Sie unter [Planen der direkten Routing](direct-routing-plan.md) .
- Für Microsoft aufrufende plant können Sie nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder Port aus einer anderen Dienstanbieter ein Ressourcenkonto. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

> [!NOTE]
> Ein Ressourcenkonto können nicht Benutzer (Abonnent) Rufnummern zugewiesen werden. Nur Service gebührenpflichtige oder gebührenfreie Telefonnummern können verwendet werden.

Eine Telefonnummer ein, um ein Ressourcenkonto zuzuweisen, müssen Sie abzurufen oder port Ihrer vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) oder wenn Sie eine vorhandene Servicenummer durchstellen möchten, finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Erstellen Sie ein Ressourcenkonto im Microsoft-Teams, Administrationscenter

Im Microsoft-Teams, Administrationscenter, navigieren Sie zu **Organisation geltende Settings** > **Ressourcenkonten**. 

![ASD](media/r-a-master.png)

![Nummer 1](media/sfbcallout1.png)

So erstellen Sie eine neue Ressource Konto klicken Sie auf **+ Neues Konto**. Im Popup füllen Sie den Anzeigenamen und Benutzernamen für das Ressourcenkonto (der Domänenname sollte automatisch aufgefüllt) klicken Sie dann auf **Speichern**.

![Ressource-Konto](media/res-acct.png)

Im nächsten Schritt müssen Sie das Ressourcenkonto eine Lizenz gilt gemäß [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)

![Zahlenformatvorlage 3](media/sfbcallout3.png) , nachdem Sie das Ressourcenkonto erstellt haben und die Lizenz zugewiesen, klicken Sie auf **Zuweisen/Zuweisung entfernen** , um das Ressourcenkonto eine aufrufen planen Servicenummer zuzuweisen, oder weisen Sie dem Ressourcenkonto an eine automatische Telefonzentrale oder ein Anruf-Warteschlange, die bereits vorhanden ist. Zuweisen einer direkten Bankleitzahl ist möglich, nur mithilfe von Cmdlets. Wenn die Warteschlange Anruf oder automatische Telefonzentrale weiterhin erstellt werden soll, können Sie das Ressourcenkonto verknüpfen, während Sie es erstellen. Klicken Sie auf **Speichern** , wenn Sie fertig sind.

![Ressourcenkonto zuweisen](media/r-a-assign.png)

![Zahlenformatvorlage 2](media/sfbcallout2.png) können Sie den Anzeigenamen der Ressource-Konto mit der Option **Bearbeiten** bearbeiten.  Klicken Sie auf **Speichern** , wenn Sie fertig sind.
![Ressourcenkonto bearbeiten](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>Erstellen Sie ein Ressourcenkonto in Powershell

Für Microsoft aufrufende plant können Sie nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder Port aus einer anderen Dienstanbieter ein Ressourcenkonto. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

Je nachdem, ob Ihr Ressourcenkonto online oder lokal befindet müssen Sie in der entsprechenden Aufforderung Powershell mit Administratorberechtigungen eine Verbindung herstellen. 
- Die folgenden Powershell, Cmdlet-Beispiele nehmen an, dass das Ressourcenkonto online verwaltet wird, mithilfe von [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ein Ressourcenkonto erstellen, die online verwaltet wird.

- Ressource Konten lokal in Skype für Business Server 2019, die mit Cloud aufrufen, Warteschlangen und Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Konfigurieren von Cloud Aufrufen von Warteschlangen](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) oder [Cloud-Telefonzentralen konfigurieren](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md). Hybrid-Implementierungen (Zahlen verwaltet auf direktes Routing) werden [Neu CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)verwenden.

Die Anwendung IDs, dass Sie beim Erstellen der Anwendung Listeninstanzen werden verwenden müssen:
- **Automatische um-Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07
- **Warteschlange aufrufen:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie die Warteschlange Anruf möchten oder automatische Telefonzentrale von lokalen Benutzern durchsucht werden können, sollten Sie Ihre Ressource Konten am Standort, erstellen, da online-Ressourcenkonten nicht nach unten zu Active Directory synchronisiert werden.

1. So erstellen Sie das Benutzerkonto eine Ressource für verwenden mit eine automatische Telefonzentrale, mit den folgenden Befehl ein.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Sie werden nicht das Ressourcenkonto verwenden, bis Sie eine Lizenz darauf anwenden können. Informationen zum Anwenden einer Lizenzvertrags auf ein Konto im Office 365 Administrationscenter finden Sie unter [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) sowie [Skype für Business Lizenzen zuweisen](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. (Optional) Nachdem die richtige Lizenz auf das Ressourcenkonto angewendet wird können Sie eine Telefonnummer ein, das Ressourcenkonto festlegen, wie unten dargestellt. Nicht alle Resource Konten erfordern eine Telefonnummer ein. Die Telefon Zuweisung schlägt fehl, wenn Sie eine Lizenz nicht auf das Ressourcenkonto angewendet haben.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

> [!NOTE]
> Es ist am einfachsten, die mit dem Microsoft-Teams, Administrationscenter online Telefonnummer festgelegt, wie oben beschrieben.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Verwalten von Einstellungen für Ressource-Konto im Microsoft-Teams, Administrationscenter

Navigieren Sie zum Verwalten von Einstellungen der Ressource-Konto im Microsoft-Teams, Administrationscenter zu **Org geltende Settings**  > **Ressource Firmen**, auswählen das Ressourcenkonto Sie Einstellungen für ändern müssen und dann auf die Schaltfläche **Bearbeiten** . Klicken Sie im Bildschirm **Ressourcenkonto bearbeiten** können Sie diese Einstellungen zu ändern:

- **Anzeigename** für das Konto
- Rufen Sie die Warteschlange oder automatische um-Telefonzentrale, die das Konto verwendet
- Das Konto zugewiesene Telefonnummer

Klicken Sie abschließend auf **Speichern**.

## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer von der Ressourcenkonto vor dem Löschen, um zu vermeiden, die Servicenummer Ihres hängen ausstehenden Modus Zuordnung aufzuheben. Sie können mit dem folgenden Cmdlet ausführen: 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```
                
Nachdem Sie dies tun, können Sie das Ressourcenkonto über das O365-Admin-Portal unter Registerkarte Benutzer löschen.


## <a name="related-information"></a>Verwandte Informationen

Für Implementierungen sind, Hybrid mit Skype für Business Server:

[Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Konfigurieren automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Für Implementierungen in Teams oder Skype für Business Online:

[Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

[Einrichten einer automatischen Cloudtelefonzentrale](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Erstellen einer Cloudanrufwarteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Neue CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Neue CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
