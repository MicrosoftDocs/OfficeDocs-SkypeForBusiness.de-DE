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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Informationen zum Verwalten von Ressourcenkonten in Microsoft Teams
ms.openlocfilehash: 58d3df08b871dcdcffd9e5d0f331870bb519d5e7
ms.sourcegitcommit: 35930c6f634623983aefeed104bc6c66a8aab174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "34957549"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto wird auch als deaktiviertes Benutzerobjekt in Azure Active Directory bezeichnet und kann verwendet werden, um Ressourcen im allgemeinen darzustellen. In Exchange kann Sie beispielsweise dazu verwendet werden, Konferenzräume darzustellen und Ihnen die Möglichkeit zu geben, eine Telefonnummer zu haben. Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server verwaltet werden, und diese Konten werden mithilfe von PowerShell-Befehlen erstellt.

In Microsoft Teams oder Skype for Business Online ist für jede Anrufwarteschlange oder automatische Telefonzentrale ein zugeordnetes Ressourcenkonto erforderlich. Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der beabsichtigten Verwendung der zugehörigen Anrufwarteschlange oder der automatischen Telefonzentrale ab. Weitere Informationen finden Sie in den Artikeln zu Anrufwarteschlangen und automatischen Telefonzentralen, die am Ende dieses Artikels verknüpft sind, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online. Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren automatischer Cloud-Telefonzentralen](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant).

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Voraussetzungen, um einem Ressourcenkonto eine Telefonnummer zuzuweisen

Um zu beginnen, sollten Sie sich ein paar Dinge merken:
  
- Eine automatische Telefonzentrale oder eine Anrufwarteschlange ist für ein zugeordnetes Ressourcenkonto erforderlich. 
- Das Ressourcenkonto benötigt eine zugewiesene Telefonnummer, wenn es einer automatischen Telefonzentrale oder einer Anrufwarteschlange zugewiesen wird. 
- Wenn die automatische Telefonzentrale oder Anrufwarteschlange unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen einbeziehen möchten.
- Sie müssen die Ressourcenkonten nur mit einer Telefonnummer lizenzieren, die Ihnen zugewiesen ist. In einer geschachtelten automatischen Telefonzentrale oder Anrufwarteschlange müssen Sie die restlichen automatischen Telefonzentralen oder Anrufwarteschlangen nicht lizenzieren, wenn Ihnen keine Telefonnummern zugeordnet sind.
- Wenn Sie eine Telefonnummer zuweisen, die für die direkte Weiterleitung verwendet wird, und Sie über eine Enterprise E1-oder E3-Lizenz verfügen, müssen Sie eine Telefon System Lizenz erwerben und Ihnen das Ressourcenkonto zuweisen, das Sie verwenden werden. Wenn Sie über eine Enterprise E5-Lizenz verfügen, ist das Telefon System bereits enthalten, daher müssen Sie keine kaufen. 
- Wenn Sie stattdessen eine Microsoft-Dienstnummer zuweisen, müssen Sie dem Ressourcenkonto \(Office 365 Enterprise E1, E3 oder E5 mit dem Telefon System-Add-on und einem Anrufplan die folgenden Lizenzen erwerben und zuweisen\).
- Sie können Ihrem Ressourcenkonto eine direkte Routing-Hybrid Nummer zuweisen.  Weitere Informationen finden Sie unter [Planen des direkten Routings](direct-routing-plan.md) .
- Für Microsoft-Anrufpläne können Sie nur gebührenpflichtige und gebührenfreie Telefonnummern für Dienstleistungen zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten haben oder die von einem anderen Dienstanbieter zu einem Ressourcenkonto portiert wurden. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

> [!NOTE]
> Direct Routing-Dienstnummern, die Ressourcenkonten für die automatische Telefonzentrale und die Anrufwarteschlangen zugewiesen sind, werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.

> [!NOTE]
> Microsoft arbeitet an einem geeigneten Lizenzierungsmodell für Anwendungen wie automatische Cloud-Telefonzentralen und Anrufwarteschlangen, denn jetzt müssen Sie das Benutzer Lizenzierungsmodell verwenden.

Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Telefonnummern von Benutzern (Abonnenten) können einem Ressourcenkonto nicht zugewiesen werden. Es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.

### <a name="phone-numbers"></a>Telefonnummern

Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Übertragen oder besorgen Sie sich eine gebührenpflichtige oder gebührenfreie Servicenummer. Die Nummer kann keinen anderen VoIP-Diensten oder Ressourcenkonten zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **sprach** > **Telefonnummern**angezeigt, und der angegebene **Nummerntyp** wird als " **Dienst gebührenfrei**" aufgeführt. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](getting-service-phone-numbers.md) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).

2. Kaufen Sie eine Telefon System Lizenz und einen Anrufplan. Sieh:  
   - [Office 365 Enterprise E1- und E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Enterprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)- -[Anrufpläne für Office 365](calling-plans-for-office-365.md)

3. Erstellen Sie ein neues Ressourcenkonto. Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell)
4. Weisen Sie dem Ressourcenkonto die Lizenz für das Telefon System und den Anrufplan zu. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md) und [Zuweisen von Lizenzen zu einem Benutzer](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Weisen Sie dem Ressourcenkonto die Dienstnummer zu. Weitere Informationen finden Sie unter Zuweisen/Aufheben der [Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).

Ein Ressourcenkonto, für das keine Telefonnummer erforderlich ist, kann die Schritte 1, 2 und 5 auslassen.

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center

Nachdem Sie eine Telefon System Lizenz und einen Anrufplan mit dem Microsoft Teams Admin Center gekauft haben, navigieren Sie zu den **organisationsweiten Einstellungen** > für**Ressourcenkonten**. 

![Screenshot der Seite "Ressourcenkonten"](media/r-a-master.png)

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

Klicken Sie zum Erstellen eines neuen Ressourcenkontos auf **+ Neues Konto**. Füllen Sie im Popup den Anzeigenamen und den Benutzernamen für das Ressourcenkonto aus (der Domänenname sollte automatisch aufgefüllt werden), und klicken Sie auf **Speichern**.

![Screenshot der Optionen für das neue Ressourcenkonto](media/res-acct.png)

Wenden Sie als nächstes eine Lizenz auf das Ressourcenkonto im Office 365 Admin Center an, wie unter [Zuweisen von Lizenzen für Benutzer in Office 365 for Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) beschrieben wird.

### <a name="edite-resource-account-name"></a>Ressourcenkontoname bearbeiten
![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png) verweist Sie können den Anzeigenamen des Ressourcenkontos mit der Option " **Bearbeiten** " bearbeiten.  Klicken Sie auf **Speichern** , wenn Sie fertig sind.
![Screenshot der Option "Ressourcenkonto bearbeiten"](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>Zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten

![Symbol der Zahl 3, auf eine Beschriftung im vorherigen Screenshot](media/sfbcallout3.png) verweisen nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen/Aufheben der Zuweisung klicken, um dem Ressourcenkonto eine Anruf Plan **-** Servicenummer zuzuweisen, oder zuweisen Das Ressourcenkonto für eine automatische Telefonzentrale oder eine Anrufwarteschlange, die bereits vorhanden ist. Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen. Wenn Ihre Anrufwarteschlange oder automatische Telefonzentrale noch erstellt werden muss, können Sie das Ressourcenkonto während der Erstellung verknüpfen. Klicken Sie auf **Speichern** , wenn Sie fertig sind.

Verwenden Sie das folgende Cmdlet, um eine direkte Routingnummer zuzuweisen: 

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

> [!IMPORTANT]
> Wenn Ihr Mandant keine Telefon System Lizenz und einen Anrufplan gekauft hat, führt eine interne Überprüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen. Sie können die Nummer nicht zuweisen oder das Ressourcenkonto einem Dienst zuordnen.

![Screenshot der Optionen zum Zuweisen/Aufheben der Zuweisung](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a>Erstellen eines Ressourcenkontos in PowerShell

Für Microsoft-Anrufpläne können Sie nur gebührenpflichtige und gebührenfreie Telefonnummern für Dienstleistungen zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten haben oder die von einem anderen Dienstanbieter zu einem Ressourcenkonto portiert wurden. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

Je nachdem, ob sich Ihr Ressourcenkonto Online oder lokal befindet, müssen Sie mit der entsprechenden PowerShell-Aufforderung mit Administratorrechten eine Verbindung herstellen. 
- In den folgenden PowerShell-Cmdlet-Beispielen wird davon ausgegangen, dass das Ressourcenkonto mithilfe von [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) online verwaltet wird, um ein Online verwaltetes Ressourcenkonto zu erstellen.

- Informationen zu Ressourcenkonten, die lokal in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, verwaltet werden, finden Sie unter [Konfigurieren von Cloud-Anrufwarteschlangen](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) oder [Konfigurieren von automatischen Cloud-Telefonzentralen](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md). Bei Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) wird [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)verwendet.

Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen verwenden müssen, sind:
- **Automatische Telefonzentrale:** ce933385-9390-45D1-9512-c8d228074e07
- **Anrufwarteschlange:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie möchten, dass die Anrufwarteschlange oder die automatische Telefonzentrale von lokalen Benutzern durchsucht werden kann, sollten Sie Ihre Ressourcenkonten lokal erstellen, da Online Ressourcenkonten nicht mit Active Directory synchronisiert werden.

1. Verwenden Sie den folgenden Befehl, um ein Ressourcenkonto für die Verwendung mit einer automatischen Telefonzentrale online zu erstellen.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Sie können das Ressourcenkonto erst dann verwenden, wenn Sie ihm eine Lizenz zuweisen. Informationen zum Anwenden einer Lizenz auf ein Konto im Office 365 Admin Center finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 für Unternehmen](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) und [Zuweisen von Lizenzen für Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Optional Nachdem die richtige Lizenz auf das Ressourcenkonto angewendet wurde, können Sie eine Telefonnummer für das Ressourcenkonto einrichten, wie unten dargestellt. Nicht für alle Ressourcenkonten ist eine Telefonnummer erforderlich. Wenn Sie keine Lizenz auf das Ressourcenkonto angewendet haben, schlägt die Zuweisung der Telefonnummer fehl.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

> [!NOTE]
> Am einfachsten ist es, die Online-Telefonnummer mit dem Microsoft Teams Admin Center festzulegen, wie es zuvor beschrieben wurde.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Verwalten von Ressourcenkonto Einstellungen im Microsoft Teams Admin Center

Navigieren Sie zum Verwalten von Ressourcenkonto Einstellungen im Microsoft Teams Admin Center zu **organisationsweiten Einstellungen**  > -**Ressourcenkonten**, wählen Sie das Ressourcenkonto aus, für das Sie die Einstellungen ändern möchten, und klicken Sie dann auf die Schaltfläche **Bearbeiten** . auf dem Bildschirm " **Ressourcenkonto bearbeiten** " können Sie die folgenden Einstellungen ändern:

- **Anzeigenamen** für das Konto
- Anrufwarteschlange oder automatische Telefonzentrale, die das Konto verwendet
- Telefonnummer, die dem Konto zugewiesen ist

Klicken Sie abschließend auf **Speichern**.

## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer aus dem Ressourcenkonto distanzieren, bevor Sie Sie löschen, um zu verhindern, dass Ihre Servicenummer im ausstehenden Modus hängen bleibt. Dazu können Sie die folgenden Unifiedgroup verwenden: 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

Anschließend können Sie das Ressourcenkonto über das Office 365-Verwaltungsportal auf der Registerkarte Benutzer löschen.

## <a name="troubleshooting"></a>Problembehandlung

Wenn die Telefonnummer, die dem Ressourcenkonto im Team Admin Center zugewiesen ist, nicht angezeigt wird und Sie die Nummer nicht von dort aus zuweisen können, überprüfen Sie bitte Folgendes:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Wenn das Department-Attribut den Skype for Business-Anwendungsendpunkt anzeigt, führen Sie das folgende Cmdlet aus:

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> Aktualisieren Sie die Webseite des Teams admin Centers, nachdem Sie das cmldet ausgeführt haben, und Sie sollten in der Lage sein, die Nummer richtig zuzuweisen.

## <a name="related-information"></a>Verwandte Informationen

Für Implementierungen, die mit Skype for Business Server Hybrid sind:

[Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Konfigurieren automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Für Implementierungen in Teams oder Skype for Business Online:

[Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

[Einrichten einer automatischen Cloudtelefonzentrale](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)

[Erstellen einer Cloudanrufwarteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Neu – CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Neu – CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
