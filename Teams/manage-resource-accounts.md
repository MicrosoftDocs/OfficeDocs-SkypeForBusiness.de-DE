---
title: Verwalten von Ressourcenkonten in Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Informationen zum Verwalten von Ressourcenkonten in Microsoft Teams
ms.openlocfilehash: d1963c5c5bfdfe28385756762b86ddcbbbe6f644
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706900"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Verwalten von Ressourcenkonten in Microsoft Teams

Ein Ressourcenkonto wird in Azure AD auch als *deaktiviertes Benutzerobjekt* bezeichnet und kann verwendet werden, um Ressourcen allgemein darzustellen. In Exchange kann es z. B. verwendet werden, um Konferenzräume darzustellen und ermöglicht, dass diese eine Telefonnummer haben. Ein Ressourcenkonto kann in Microsoft 365 oder lokal unter Verwendung von Skype for Business Server 2019 verwaltet werden.

In Microsoft Teams oder Skype for Business Online ist für jede Telefonsystem-Anrufwarteschleife oder automatische Telefonzentrale mindestens ein zugeordnetes Ressourcenkonto erforderlich. Ob ein Ressourcenkonto eine zugewiesene Telefonnummer benötigt, hängt von der vorgesehenen Verwendung der zugehörigen Anrufwarteschleife oder der automatischen Telefonzentrale ab, wie im folgenden Diagramm dargestellt. Sie können auch die Artikel zu Anrufwarteschleifen und automatischen Telefonzentralen, die am Ende dieses Artikels verknüpft sind, zu Rate ziehen, bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen.

![Beispiel für Ressourcenkonten und Benutzerlizenzen](media/resource-account.png)

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online. Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden, finden Sie unter [Konfigurieren von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="overview"></a>Übersicht

Wenn Ihre Organisation bereits mindestens eine Telefonsystemlizenz verwendet, können Sie einer Telefonsystem-Anrufwarteschleife wie folgt eine Telefonnummer zuweisen:

1. Rufen sie eine Dienstnummer ab.
2. Rufen Sie eine kostenlose Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine kostenpflichtige Telefonsystemlizenz ab, die mit dem Ressourcenkonto oder einer Telefonsystemlizenz verwendet werden soll.
3. Erstellen Sie das Ressourcenkonto. Eine automatische Telefonzentrale oder Anrufwarteschleife muss über ein zugeordnetes Ressourcenkonto verfügen.
4. Weisen Sie dem Ressourcenkonto das Telefonsystem oder eine Telefonsystem – virtuelle Benutzerlizenz zu.
5. Weisen Sie dem Ressourcenkonto, dem Sie gerade Lizenzen zugewiesen haben, eine Dienstelefonnummer zu.
6. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem
7. Verknüpfen Sie das Ressourcenkonto mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale.

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

Wenn die automatische Telefonzentrale oder Anrufwarteschleife unter einer automatischen Telefonzentrale der obersten Ebene geschachtelt ist, benötigt das zugeordnete Ressourcenkonto nur eine Telefonnummer, wenn Sie mehrere Einstiegspunkte in die Struktur von automatischen Telefonzentralen und Anrufwarteschleifen benötigen.

Um Anrufe an Personen in Ihrer Organisation umzuleiten, die online sind, müssen diese über eine **Telefonsystemlizenz** verfügen und für Enterprise-VoIP aktiviert sein oder über einen Office 365-Anrufplan verfügen. Nähers hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise den folgenden Befehl aus: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> Um Probleme mit dem Ressourcenkonto zu vermeiden, führen Sie die folgenden Schritte in dieser Reihenfolge aus.

Wenn die von Ihnen erstellte Telefonsystem-Anrufwarteschleife oder Telefonzentrale geschachtelt wird und keine Telefonnummer benötigt, ist die Vorgehensweise:

1. Erstellen des Ressourcenkontos
2. Erstellen einer Warteschlange oder eine automatische Telefonzentrale für das Telefonsystem
3. Verknüpfen des Ressourcenkontos mit einer Anrufwarteschleife oder einer automatischen Telefonzentrale

### <a name="create-a-resource-account-with-a-phone-number"></a>Erstellen eines Ressourcenkontos mit einer Telefonnummer

<a name="phonenumber"> </a>

> [!IMPORTANT]
> Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.

Eine automatische Telefonzentrale oder Anrufwarteschleife der obersten Ebene erfordert, dass eine Telefonnummer mit ihrer automatischen Telefonzentrale verknüpft wird. Wenn Sie ein Ressourcenkonto erstellen möchten, das eine Telefonnummer verwendet, ist die Vorgehensweise:

1. Portieren Sie eine gebührenpflichtige oder gebührenfreie Dienstnummer oder rufen Sie diese ab. Die Nummer kann keiner anderen Voice Services oder Ressourcenkonten zugewiesen werden.

   Bevor Sie einem Ressourcenkonto eine Telefonnummer zuweisen, müssen Sie Ihre bestehenden gebührenpflichtigen oder gebührenfreien Dienstnummern abrufen oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Diensttelefonnummern erhalten haben, werden diese unter **Microsoft Teams Admin Center** > **Voice** > **Telefonnummern** angezeigt, und der **Nummerntyp** wird als **Dienst – gebührenfrei** aufgelistet. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Service-Telefonnummern](getting-service-phone-numbers.md) oder wenn Sie eine vorhandene Service-Nummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

   Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose virtuelle Benutzerlizenz des Telefonsystems verwenden. Auf diese Weise können Telefonsystem-Funktionen für Telefonnummern auf Organisationsebene bereitgestellt werden, und Sie können die Funktionen der automatischen Telefonzentrale und der Anrufwarteschleife erstellen.

2. Rufen Sie eine virtuelle Benutzerlizenz für das Telefonsystem oder eine herkömmliche Telefonsystemlizenz ab.

   Um die virtuelle Benutzerlizenz zu erhalten, wechseln Sie im Microsoft 365 Admin Center zur Seite **Rechnungsstellung** > **Dienste kaufen** > **Add-On-Abonnements** und scrollen Sie bis zum Ende. Dort sehen Sie die Lizenz „Telefonsystem – virtueller Benutzer“. Wählen Sie **Jetzt kaufen** aus. Es entstehen keine Kosten, Sie müssen jedoch dennoch die diese Schritte befolgen, um die Lizenz zu erwerben.
3. Erstellen Sie ein neues Ressourcenkonto. Informationen hierzu finden Sie unter [Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).
4. Weisen Sie dem Ressourcenkonto eine Telefonsystem – [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md) oder eine Telefonsystemlizenz zu. Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md) und [Zuweisen von Lizenzen zu einem Benutzer](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Weisen Sie dem Ressourcenkonto die Dienstnummer zu. Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).
6. Richten Sie eines der Folgenden ein:
   - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
   - [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)
7. Verknüpfen Sie das Ressourcenkonto mit der automatischen Telefonzentrale oder der Anrufwarteschleife. Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).

Wenn Sie beim Erstellen einer automatischen Telefonzentrale ein Ressourcenkonto erstellen, werden die Lizenzen automatisch zugewiesen.

### <a name="create-a-resource-account-without-a-phone-number"></a>Erstellen eines Ressourcenkontos ohne Telefonnummer

Eine geschachtelte automatische Telefonzentrale oder Anrufwarteschleife erfordert ein Ressourcenkonto, aber in vielen Fällen benötigt das entsprechende Ressourcenkonto keine Telefonnummer und die erforderliche Lizenzierung, um eine Telefonnummer zu unterstützen. Wenn Sie ein Ressourcenkonto erstellen, für das keine Rufnummer erforderlich ist, müssen Sie die folgenden Aufgaben in der folgenden Reihenfolge ausführen:

1. Erstellen Sie ein neues Ressourcenkonto. Informationen hierzu finden Sie unter [Erstellen eines Ressourcenkontos im Microsoft Teams Admin Center](#create-a-resource-account-in-microsoft-teams-admin-center) oder [Erstellen eines Ressourcenkontos in PowerShell](#create-a-resource-account-in-powershell).
2. Richten Sie eines der Folgenden ein:
   - [Automatische Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md)
   - [Cloud-Anrufwarteschleife](create-a-phone-system-call-queue.md)
3. Weisen Sie das Ressourcenkonto der Anrufwarteschleife oder der automatischen Telefonzentrale zu. Informationen finden Sie unter [Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten](#assignunassign-phone-numbers-and-services).


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Erstellen eines Ressourcenkontos in Microsoft Teams Admin Center

Nachdem Sie eine Telefon System Lizenz erworben haben, navigieren Sie mithilfe des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Ressourcenkonten**.

![Screenshot der Seite „Ressourcenkonten“](media/r-a-master.png)

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/teamscallout1.png)

Klicken Sie zum Erstellen eines neuen Ressourcenkontos auf **+ Hinzufügen**. Füllen Sie im Popup-Fenster den **Anzeigenamen**, den **Benutzernamen** (der Domänenname sollte automatisch aufgefüllt werden) und den Typ des Ressourcen **Kontos** für das Ressourcenkonto aus. Der Ressourcen Kontotyp kann abhängig von der APP, die Sie dem Ressourcenkonto zuordnen möchten, entweder eine **automatische Telefonzentrale** oder eine **Anrufwarteschlange** sein. Wenn Sie fertig sind, klicken Sie auf **Speichern**.

![Screenshot der Optionen für „Neues Ressourcenkonto“](media/res-acct.png)

Wenden Sie als nächstes im O365 Admin Center eine Lizenz auf das Ressourcenkonto an, wie unter Zuweisen von [Lizenzen zu Benutzern in Office 365 Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) beschrieben.

### <a name="edit-resource-account"></a>Ressourcenkonto bearbeiten 

![Symbol der](media/teamscallout2.png) Zahl 2, die auf eine Legende im vorherigen Screenshot verweist Sie können den **Anzeigenamen** des Ressourcenkontos und den **Ressourcen Kontotyp** mithilfe der Option " **Bearbeiten** " bearbeiten. Klicken Sie abschließend auf **Speichern**.

![Screenshot der Option „Ressourcenkonto bearbeiten“](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>Zuweisen oder aufheben der Zuweisung von Telefonnummern und Diensten

![Symbol der Zahl 3, auf eine Beschriftung im vorherigen Screenshot](media/teamscallout3.png) verweisen nachdem Sie das Ressourcenkonto erstellt und die Lizenz zugewiesen haben, können Sie auf zuweisen/Aufheben der **Zuweisung** klicken, um dem Ressourcenkonto eine Dienstnummer zuzuweisen, den Typ der Telefonnummer festzulegen oder das Ressourcenkonto einer bestimmten automatischen Telefonzentrale oder Anrufwarteschlange zuzuweisen, die bereits vorhanden ist. Das Zuweisen einer direkten Routingnummer kann nur über Cmdlets erfolgen. Wenn Sie die Anrufwarteschlange oder die automatische Telefonzentrale, die Sie dem Ressourcenkonto zuordnen, noch nicht erstellt haben, lassen Sie das Feld leer. Sie können das Ressourcenkonto während der Erstellung verknüpfen. Klicken Sie abschließend auf **Speichern**.

Die Optionen für den **Typ "Telefonnummer** " lauten wie folgt:

- Keine
- Online
- Gebührenfrei
- Lokal

![Screenshot der Optionen „Zuweisen/Aufheben der Zuweisung“](media/r-a-assign.png)

Wenn Sie einem Ressourcenkonto eine direkte Routing-oder Hybrid-Nummer zuweisen möchten, müssen Sie PowerShell verwenden, siehe hierzu den folgenden Abschnitt.

> [!IMPORTANT]
> Wenn Ihr Ressourcenkonto nicht über eine gültige Lizenz verfügt, führt eine interne Prüfung zu einem Fehler, wenn Sie versuchen, die Telefonnummer dem Ressourcenkonto zuzuweisen. Sie sind dann nicht in der Lage, die Nummer zuzuweisen oder das Ressourcenkonto einer Anrufwarteschleife oder automatischen Telefonzentrale zuzuordnen.

> [!IMPORTANT]
> Eine Telefonnummer wird nicht direkt der automatischen Telefonzentrale oder Anrufwarteschlange, sondern dem Ressourcenkonto zugewiesen, das der automatischen Telefonzentrale oder Anrufwarteschlange zugeordnet ist.



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Ändern eines vorhandenen Ressourcenkontos, um eine virtuelle Benutzerlizenz zu verwenden

Wenn Sie sich entscheiden, die Lizenzen für Ihr vorhandenes Ressourcenkonto von einer Telefonsystemlizenz auf eine virtuelle Benutzerlizenz zu übertragen, müssen Sie die ﻿kostenlose virtuelle Benutzerlizenz erwerben. Führen Sie dann die verknüpften Schritte im Microsoft 365 Admin Center aus, um [Benutzer zu einem anderen Abonnement zu verschieben](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Entfernen Sie immer die vollständige Telefonsystemlizenz und weisen Sie die virtuelle Benutzerlizenz der gleichen Lizenzaktivität zu. Wenn Sie die alte Lizenz entfernen, die Kontoänderungen speichern, die neue Lizenz hinzufügen und dann die Kontoeinstellungen erneut speichern, funktioniert das Ressourcenkonto möglicherweise nicht mehr wie erwartet. In diesem Fall empfiehlt es sich, ein neues Ressourcenkonto für die virtuelle Benutzerlizenz zu erstellen und das beschädigte Ressourcenkonto zu entfernen. 

## <a name="create-a-resource-account-in-powershell"></a>Erstellen eines Ressourcenkontos in PowerShell

Je nachdem, ob Ihr Ressourcenkonto online oder in Skype for Business 2019 vorliegt, müssen Sie eine Verbindung mit der entsprechenden PowerShell-Eingabeaufforderung mit Administratorrechten herstellen.

- In den folgenden Beispielen für PowerShell-Cmdlets wird gezeigt, wie Sie mit [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ein online verwaltetes Ressourcenkonto erstellen. 

- Informationen zu Ressourcenkonten, die in Skype for Business Server 2019 verwaltet werden und mit Cloud-Anrufwarteschleifen und automatischen Cloud-Telefonzentralen verwendet werden können, finden Sie unter [Konfigurieren von Cloud-Anrufwarteschlangen](/skypeforbusiness/hybrid/configure-call-queue.md) oder [Konfigurieren von automatischen Cloud-Telefonzentralen](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md). Hybrid Implementierungen (Zahlen, die im direkten Routing verwaltet werden) werden mithilfe des Cmdlets [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) auf einem lokalen Skype for Business Server 2019-Server konfiguriert.

Die Anwendungs-IDs, die Sie beim Erstellen der Anwendungsinstanzen benötigen, sind Folgende:

- **Automatische Telefonzentrale:** ce933385-9390-45d1-9512-c8d228074e07
- **Anrufwarteschleife:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Wenn Sie möchten, dass die Anrufwarteschleife oder automatische Telefonzentrale von Benutzern von Skype For Business Server 2019 durchsucht werden kann, sollten Sie Ihre Ressourcenkonten in Skype For Business Server 2019 erstellen, da Online-Ressourcenkonten nicht mit Active Directory synchronisiert werden. Wenn DNS-SRV-Einträge für sipfederationtls in Skype for Business Server 2019 aufgelöst werden, dann **müssen** die Ressourcenkonten mithilfe der SfB-Management-Shell in Skype for Business Server 2019 erstellt und mit Azure AD online synchronisiert werden.

 

1. Verwenden Sie den folgenden Befehl, um ein Ressourcenkonto für die Verwendung mit einer automatischen Telefonzentrale online zu erstellen:

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Sie können das Ressourcenkonto erst dann verwenden, wenn Sie ihm eine Lizenz zuweisen. Informationen zum Zuweisen einer Lizenz zu einem Konto im O365 Admin Center finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) sowie unter [Zuweisen von Skype for Business-Lizenzen](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. (Optional) Nachdem Sie die richtige Lizenz auf das Ressourcenkonto angewendet haben, können Sie eine Telefonnummer für das Ressourcenkonto zuweisen, wie unten dargestellt. Nicht alle Ressourcenkonten benötigen eine Telefonnummer. Wenn Sie keine Lizenz auf das Ressourcenkonto angewendet haben, schlägt die Telefonnummernzuordnung fehl.

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   Weitere Details hierzu finden Sie unter [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps).

   > [!NOTE]
   > Die Online-Telefonnummer lässt sich am einfachsten mithilfe des Microsoft Teams Admin Centers festlegen, wie zuvor beschrieben.

   Wenn Sie einem (in Microsoft Teams oder Skype for Business Server 2019 verwalteten) Ressourcenkonto eine direkte Routingtelefonnummer zuweisen möchten, verwenden Sie das folgende Cmdlet für Skype for Business Online PowerShell:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Verwalten der Einstellungen für das Ressourcenkonto in Microsoft Teams Admin Center

Wenn Sie die Einstellungen für das Ressourcenkonto im Microsoft Teams Admin Center verwalten möchten, navigieren Sie zu **Organisationsweite Einstellungen** > **Ressourcenkonten** und wählen Sie das Ressourcenkonto aus, für das Sie die Einstellungen ändern möchten. Klicken Sie dann auf die Schaltfläche **Bearbeiten**. Auf dem Bildschirm **Ressourcenkonto bearbeiten** können Sie diese Einstellungen ändern:

- **Anzeigename** für das Konto
- Anrufwarteschleife oder automatische Telefonzentrale, die das Konto verwendet
- Dem Konto zugewiesene Telefonnummer

Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="delete-a-resource-account"></a>Löschen eines Ressourcenkontos

Stellen Sie sicher, dass Sie die Telefonnummer vom Ressourcenkonto trennen, bevor Sie sie löschen, um zu verhindern, dass Ihre Dienstnummer im Modus „Ausstehend“ verbleibt. Zu diesem Zweck können Sie die folgenden Befehle verwenden:

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

Sobald Sie dies getan haben, können Sie das Ressourcenkonto über das O365-Administratorportal unter der Registerkarte „Benutzer“ löschen.

Verwenden Sie den folgenden Cmdlet, um eine direkte Routing-Telefonnummer vom Ressourcenkonto zu trennen:

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>Problembehandlung

Wenn die Telefonnummer, die dem Ressourcenkonto im Admin Center des Teams zugeordnet ist, nicht angezeigt wird und Sie die Nummer dort nicht zuweisen können, überprüfen Sie Folgendes:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Wenn das Department-Attribut den Skype for Business-Anwendungsendpunkt anzeigt, führen Sie den folgenden Cmdlet aus:

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Aktualisieren Sie nach dem Ausführen des cmldet die Website des Teams Admin Centers. Sie sollten dann in der Lage sein, die Nummer ordnungsgemäß zuzuweisen.

## <a name="related-information"></a>Verwandte Informationen

Bei hybride Implementierungen mit Skype for Business Server:

   [Planen automatischer Cloudtelefonzentralen](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planen von Cloud-Anrufwarteschleifen](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Konfigurieren lokalen von Ressourcenkonten](/SkypeForBusiness/hybrid/configure-onprem-ra)


Bei Implementierungen in Teams oder Skype for Business Online:

   [Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

   [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant)

   [Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)

   [Erstellen einer Cloudanrufwarteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Telefonsystem – virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)
