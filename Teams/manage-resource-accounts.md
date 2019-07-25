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
ms.openlocfilehash: f1028e35bff7a2801a82e50e032c1b181200e00e
ms.sourcegitcommit: 384e123f3b5cf1600ebd5ddd69bd022f9b8ba0f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "35861895"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto wird auch als deaktiviertes *Benutzerobjekt* in Azure Active Directory bezeichnet und kann verwendet werden, um Ressourcen im allgemeinen darzustellen. In Exchange kann Sie beispielsweise dazu verwendet werden, Konferenzräume darzustellen und Ihnen die Möglichkeit zu geben, eine Telefonnummer zu haben. Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.

In Microsoft Teams oder Skype for Business Online ist für jede Telefon System-Anrufwarteschlange oder automatische Telefonzentrale ein zugeordnetes Ressourcenkonto erforderlich. Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der beabsichtigten Verwendung der zugehörigen Anrufwarteschlange oder der automatischen Telefonzentrale ab, wie in der nachstehenden Abbildung zu sehen ist. Sie können sich auch auf die Artikel über Anrufwarteschlangen und automatische Telefonzentralen beziehen, die am Ende dieses Artikels verknüpft sind, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.

![Beispiel für Ressourcenkonten und Benutzerlizenzen](media/resource-account.png)

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online. Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra).


## <a name="overview"></a>Übersicht

Vorausgesetzt, dass Ihre Organisation bereits mindestens eine Telefonsystem Lizenz verwendet, müssen Sie die verschiedenen Abhängigkeiten in der folgenden Reihenfolge berücksichtigen, um eine Telefonsystem-Anrufwarteschlange oder eine automatische Telefonzentrale einer Telefonnummer zuzuweisen:

1. Rufen Sie eine Dienstnummer ab.
2. Besorgen Sie sich ein kostenloses Telefonsystem – eine [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine gebührenpflichtige Telefonsystem Lizenz, die Sie mit dem Ressourcenkonto verwenden können.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder eine Anrufwarteschlange ist für ein zugeordnetes Ressourcenkonto erforderlich.
4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem-virtuelle Benutzerlizenz zu.
5. Weisen Sie dem Ressourcenkonto, dem Sie soeben Lizenzen zugewiesen haben, eine Dienst Telefonnummer zu. 
6. Erstellen einer Telefon System-Anrufwarteschlange oder einer automatischen Telefonzentrale
7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschlange oder einer automatischen Telefonzentrale.



Wenn die automatische Telefonzentrale oder Anrufwarteschlange unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschlangen einbeziehen möchten.

Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online verwaltet werden, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> Führen Sie die folgenden Schritte in dieser Reihenfolge aus, um Probleme mit dem Ressourcenkonto zu vermeiden.

Wenn die Telefon System-Anrufwarteschlange oder die automatische Telefonzentrale, die Sie erstellen, geschachtelt sind und keine Telefonnummer benötigen, lautet der Vorgang wie folgt:

1. Erstellen des Ressourcenkontos  
2. Erstellen einer Telefon System-Anrufwarteschlange oder einer automatischen Telefonzentrale
3. Zuordnen des Ressourcenkontos zu einer Telefon System-Anrufwarteschlange oder einer automatischen Telefonzentrale

### <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

Für eine automatische Telefonzentrale oder eine Anrufwarteschlange einer obersten Ebene muss eine Telefonnummer mit der automatischen Telefonzentrale verknüpft sein. Zum Erstellen eines Ressourcenkontos, das eine Telefonnummer verwendet, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Portieren oder eine gebührenpflichtige oder gebührenfreie Servicenummer erhalten. Die Nummer kann keinen anderen VoIP-Diensten oder Ressourcenkonten zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **sprach** > **Telefonnummern**angezeigt, und der angegebene **Nummerntyp** wird als " **Dienst gebührenfrei**" aufgeführt. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](getting-service-phone-numbers.md) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose virtuelle Benutzerlizenz für das Telefon System verwenden. Dies bietet Telefon System Funktionen für Telefonnummern auf Organisationsebene und ermöglicht Ihnen das Erstellen von automatischen Telefonzentralen-und Anruf Warteschlangenfunktionen.

2. Besorgen Sie sich eine virtuelle Telefonsystem-Benutzerlizenz oder eine reguläre Telefonsystem Lizenz. 

   Um die Lizenz für den virtuellen Benutzer zu erhalten, starten Sie vom Microsoft 365 Admin Center aus, gehen Sie zu den Abonnements für **Billing** > **Purchase Services** > -**Add-on** und Scrollen Sie bis zum Ende – es wird die Lizenz "Telefon System-virtueller Benutzer" angezeigt. Wählen Sie **Jetzt kaufen**aus. Es fallen zwar keine Kosten an, doch müssen Sie die folgenden Schritte ausführen, um die Lizenz zu erwerben.
3. Erstellen Sie ein neues Ressourcenkonto. Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell)
4. Weisen Sie dem Ressourcenkonto eine Telefonsystem-Lizenz für einen [virtuellen Benutzer](teams-add-on-licensing/virtual-user.md) oder eine Telefonsystem Lizenz zu. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md) und [Zuweisen von Lizenzen zu einem Benutzer](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Weisen Sie dem Ressourcenkonto die Dienstnummer zu. Weitere Informationen finden Sie unter Zuweisen/Aufheben der [Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).
6. Richten Sie eine der folgenden Optionen ein:
   - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
   - [Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md)
7. Verknüpfen Sie das Ressourcenkonto mit der automatischen Telefonzentrale oder der Anrufwarteschlange. Siehe [zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services)

### <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

Eine geschachtelte automatische Telefonzentrale oder Anrufwarteschlange erfordert ein Ressourcenkonto, doch in vielen Fällen benötigt das entsprechende Ressourcenkonto keine Telefonnummer und die Lizenzierung, die zur Unterstützung einer Telefonnummer erforderlich ist.  Zum Erstellen eines Ressourcenkontos, das keine Telefonnummer benötigt, müssen die folgenden Aufgaben in der folgenden Reihenfolge ausgeführt werden:

1. Erstellen Sie ein neues Ressourcenkonto. Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell)
2. Richten Sie eine der folgenden Optionen ein:
   - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
   - [Cloud-Anrufwarteschlange](create-a-phone-system-call-queue.md)
3. Weisen Sie das Ressourcenkonto der Anrufwarteschlange oder der automatischen Telefonzentrale zu. Siehe [zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services)


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center

Nachdem Sie eine Telefon System Lizenz erworben haben, navigieren Sie mithilfe des Microsoft Teams admin Centers zu **organisationsweiten Einstellungen** > -**Ressourcenkonten**.

![Screenshot der Seite "Ressourcenkonten"](media/r-a-master.png)

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

Klicken Sie zum Erstellen eines neuen Ressourcenkontos auf **+ Neues Konto**. Füllen Sie im Popup den Anzeigenamen und den Benutzernamen für das Ressourcenkonto aus (der Domänenname sollte automatisch aufgefüllt werden), und klicken Sie auf **Speichern**.

![Screenshot der Optionen für das neue Ressourcenkonto](media/res-acct.png)

Wenden Sie als nächstes eine Lizenz auf das Ressourcenkonto im Office 365 Admin Center an, wie unter [Zuweisen von Lizenzen für Benutzer in Office 365 for Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) beschrieben wird.

### <a name="edit-resource-account-name"></a>Ressourcenkontoname bearbeiten

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot](media/sfbcallout2.png) verweist Sie können den Anzeigenamen des Ressourcenkontos mit der Option " **Bearbeiten** " bearbeiten.  Klicken Sie auf **Speichern** , wenn Sie fertig sind.
![Screenshot der Option "Ressourcenkonto bearbeiten"](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>Zuweisen/Aufheben der Zuweisung von Telefonnummern und Diensten

![Symbol der Zahl 3, auf eine Beschriftung im vorherigen Screenshot](media/sfbcallout3.png) verweisen nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen/Aufheben der **Zuweisung** klicken, um dem Ressourcenkonto eine Dienstnummer zuzuweisen oder die Ressource zuzuweisen. Konto an eine automatische Telefonzentrale oder eine Anrufwarteschlange, die bereits vorhanden ist. Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen. Wenn Ihre Anrufwarteschlange oder automatische Telefonzentrale noch erstellt werden muss, können Sie das Ressourcenkonto während der Erstellung verknüpfen. Klicken Sie auf **Speichern** , wenn Sie fertig sind.

Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuweisen möchten, müssen Sie PowerShell verwenden, und lesen Sie den folgenden Abschnitt.

> [!IMPORTANT]
> Wenn Ihr Ressourcenkonto nicht über eine gültige Lizenz verfügt, führt eine interne Überprüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen. Sie können die Nummer nicht zuweisen oder das Ressourcenkonto einer Anrufwarteschlange oder einer automatischen Telefonzentrale zuordnen.

![Screenshot der Optionen zum Zuweisen/Aufheben der Zuweisung](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos zur Verwendung einer virtuellen Benutzerlizenz

Wenn Sie sich entschließen, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer Telefonsystem Lizenz zu einer virtuellen Benutzerlizenz zu wechseln, müssen Sie die ﻿kostenlose Virtual User-Lizenz erwerben und dann die verknüpften Schritte im Microsoft 365 Admin Center befolgen, um [Benutzer zu einer anderes Abonnement](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Entfernen Sie immer eine vollständige Telefon System Lizenz, und weisen Sie die Lizenz für den virtuellen Benutzer der gleichen Lizenz Aktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfehlen wir, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das fehlerhafte Ressourcenkonto zu entfernen. 

## <a name="create-a-resource-account-in-powershell"></a>Erstellen eines Ressourcenkontos in PowerShell

Je nachdem, ob sich Ihr Ressourcenkonto Online oder lokal befindet, müssen Sie mit der entsprechenden PowerShell-Aufforderung mit Administratorrechten eine Verbindung herstellen.

- In den folgenden PowerShell-Cmdlet-Beispielen wird davon ausgegangen, dass das Ressourcenkonto mithilfe von [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) online verwaltet wird, um ein Online verwaltetes Ressourcenkonto zu erstellen.

- Informationen zu Ressourcenkonten, die lokal in Skype for Business Server 2019, die mit Cloud-Anrufwarteschlangen und automatischen Cloud-Telefonzentralen verwendet werden können, verwaltet werden, finden Sie unter [Konfigurieren von Cloud-Anrufwarteschlangen](/skypeforbusiness/hybrid/configure-call-queue.md) oder [Konfigurieren von automatischen Cloud-Telefonzentralen](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md). Bei Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) wird [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)verwendet.

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
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

> [!NOTE]
> Am einfachsten ist es, die Online-Telefonnummer mit dem Microsoft Teams Admin Center festzulegen, wie es zuvor beschrieben wurde.

Verwenden Sie das folgende Cmdlet, um einem Ressourcenkonto eine direkte Routing-oder Hybrid Nummer zuzuweisen:

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

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
  
   [Planen von Cloud-Anrufwarteschlangen](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Konfigurieren von onprem-Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra)


Für Implementierungen in Teams oder Skype for Business Online:

   [Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

   [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

   [Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)

   [Erstellen einer Cloudanrufwarteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Neu – CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Neu – CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Telefon System – virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)
