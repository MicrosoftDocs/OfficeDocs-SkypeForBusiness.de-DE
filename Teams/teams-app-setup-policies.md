---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen Sie zu Richtlinien für die app Setup in Microsoft-Teams und Nutzung zum Anpassen von Teams für Benutzer in Ihrer Organisation Pin apps.
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: b38a381e95855380e017050441885474934cbe8f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227246"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

> [!NOTE]
> Wenn Sie die gesamte Org app Berechtigung Richtlinie, **Interaktion mit benutzerdefinierten apps zulassen**aktiviert möglicherweise Richtlinien für die app Setup noch in der Verwaltungskonsole von Microsoft-Teams, nicht angezeigt. Es ist derzeit eingeführt werden und werden bald in Ihrer Organisation zur Verfügung stehen.

Als Administrator können Sie Richtlinien für die app-Setup zum Anpassen von Microsoft-Teams, um apps zu markieren, die am besten für Ihre Benutzer wichtig sind. Sie wählen den apps zum Anheften und Festlegen der Reihenfolge, die sie angezeigt werden. Richtlinien für die App Setup können Sie apps, die Benutzer in Ihrer Organisation auch von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt müssen, präsentieren. Sie können auch Richtlinien für die app-Setup zum Verwalten von Features wie integrierter angezeigt werden.

Apps sind an die app-Leiste angeheftet. Dies ist die Leiste rechts auf dem Desktopclient Teams und am unteren Rand der Teams mobilen Clients (iOS und Android). 

|Desktopclient Teams  |Teams mobiler Clients |
|---------|---------|
|![App-Setup-Policies-Desktop-App-bar.PNG](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-Policies-Mobile-App-bar.PNG](media/app-setup-policies-mobile-app-bar.png)      |

Sie können Richtlinien für die app Setup in der Verwaltungskonsole von Microsoft-Teams verwalten. Verwenden Sie die globale Richtlinie (Org geltende Standard) oder benutzerdefinierte Richtlinien erstellen, und Benutzern zuweisen. Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen, und weisen Sie eine benutzerdefinierte Richtlinie an.

Sie können die Einstellungen zum Einschließen von apps, die Sie möchten in der globalen Richtlinie bearbeiten. Wenn Sie Teams für verschiedene Gruppen von Benutzern in Ihrer Organisation anpassen möchten, erstellen und eine oder mehrere benutzerdefinierte Richtlinien zuweisen. Wenn ein Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer. Wenn ein Benutzer eine benutzerdefinierte Richtlinie zugewiesen wird nicht, gilt die globale Richtlinie für den Benutzer.

![App-Setup-policies.png](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie Teams für Bildungseinrichtungen verfügen, ist es wichtig zu wissen, dass die app Zuordnungen standardmäßig in der globalen Richtlinie fixiert ist, auch wenn derzeit nicht angezeigt, dass es in der globalen Richtlinie aufgeführt. Es wird die vierte app in der Liste der angeheftete apps auf Teams Clients sein.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen Sie eine benutzerdefinierte Anwendung Setup-Richtlinie

Das Microsoft-Teams, Administrationscenter können Sie eine benutzerdefinierte Richtlinie erstellen.

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**Apps > **Richtlinien einrichten**.
2. Wählen Sie **neue Richtlinie**aus.
3. Geben Sie einen beschreibenden Namen für die Richtlinie ein, und klicken Sie dann auf **apps hinzufügen**.
4. Aktivieren oder Deaktivieren von **benutzerdefinierten apps Hochladen zulassen**, je nachdem, ob Sie benutzerdefinierte apps in Teams hoch Benutzern ermöglichen möchten.
5. Suchen Sie im Bereich **Hinzufügen fixiert apps** für die apps, den, die Sie hinzufügen, und klicken Sie dann auf **Hinzufügen**möchten. Sie können auch apps durch app Berechtigungsrichtlinie filtern. Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **Hinzufügen**.

     ![App-Setup-Richtlinien-add-apps.png](media/app-setup-policies-add-apps.png)

6. Ordnen Sie die apps in der Reihenfolge, in der Sie sollen in Teams angezeigt, und klicken Sie dann auf **Speichern**.

    ![App-Setup-Policies-New-Policy-Setup.PNG](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer Richtlinie für den app-setup

Das Microsoft-Teams, Administrationscenter können Sie eine Richtlinie, einschließlich der globalen (Org geltende) Standardrichtlinie und benutzerdefinierte Richtlinien, die Sie erstellen, bearbeiten.

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**Apps > **Richtlinien einrichten**.
2. Wählen Sie die Richtlinie, den, die Sie bearbeiten möchten. 
3. Stellen Sie dort die gewünschten Änderungen. Sie können hinzufügen oder entfernen und Ändern der Reihenfolge von apps.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer Richtlinie auf benutzerdefinierte Anwendung Setup für Benutzer

Das Microsoft-Teams, Administrationscenter können Sie weisen Sie eine benutzerdefinierte Richtlinie für einzelne Benutzer oder die Skype für Business PowerShell-Modul für Gruppen von Benutzern, beispielsweise eine Sicherheitsgruppe oder Verteilergruppe eine benutzerdefinierte Richtlinie zuweisen.

> [!IMPORTANT]
> Es wird empfohlen, mithilfe von PowerShell nur für Richtlinien Benutzern zuweisen. Verwenden Sie das Microsoft-Teams, Administrationscenter zu erstellen, bearbeiten und Verwalten von Richtlinien.

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>Zuweisen einer Richtlinie auf benutzerdefinierte Anwendung Setup für einzelne Benutzer

1. Im linken Navigationsbereich von Microsoft-Teams, Administrationscenter wechseln Sie zu dem **Benutzer**, und klicken Sie dann auf Benutzer.
2. Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus.
3. Wählen Sie unter **Teams App Setup Richtlinie**die app-Setup-Richtlinie, die Sie zuweisen möchten, und wählen Sie dann auf **Speichern**.

    ![App-Setup-Richtlinien-zuweisen-policy.png](media/app-setup-policies-assign-policy.png)

Sie können einen oder mehrere Benutzer auch wie folgt eine app-Setup-Richtlinie zuweisen:

1. Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **Teams apps** > **Richtlinien einrichten**.
2. Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.
3. Wählen Sie **Benutzer verwalten**.
4. Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.
5. Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Zuweisen einer Richtlinie auf benutzerdefinierte Anwendung Setup für Benutzer in einer Gruppe

Sie möchten eine benutzerdefinierte Anwendung Setup-Richtlinie zu mehreren Benutzern zuweisen, die Sie bereits ermittelt haben. Beispiel: Sie möchten eine Richtlinie für alle Benutzer in einer Sicherheitsgruppe zuweisen. Hierzu können Sie eine Verbindung mit Azure Active Directory PowerShell Graph-Modul und die Skype für Business PowerShell-Modul. Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).

In diesem Beispiel weisen wir eine benutzerdefinierte Anwendung Setup Richtlinie HR App Setup Policy aufgerufen, um alle Benutzer in der Gruppe Contoso Pharmaceuticals HR-Projekt.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zuerst die Azure Active Directory-PowerShell-Modul Diagramm und Skype für Business PowerShell-Modul anschließen, durch die Schritte in [Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Rufen Sie die GroupObjectId bestimmten Gruppe.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Rufen Sie die Mitglieder der angegebenen Gruppe.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie alle Benutzer in der Gruppe zu einer bestimmten app-Setup-Richtlinie. In diesem Beispiel ist es HR App Setup Policy.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
Abhängig von der Anzahl der Elemente in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit Richtlinien für die app-setup

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten app-Setup-Richtlinien sind in der Microsoft-Teams-Verwaltungskonsole enthalten?

- **Global (Org geltende Standard)**: Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie eine andere Richtlinie zuweisen. Bearbeiten Sie die globale Richtlinie für die Pin-apps, die für Ihre Benutzer am wichtigsten sind.
- **FirstLineWorker**: Diese Richtlinie für Firstline Mitarbeiter ist. Sie können es Firstline Mitarbeiter in Ihrer Organisation zuweisen. Es ist wichtig, zu wissen, dass Sie wie benutzerdefinierte Richtlinien, die Sie erstellen, weisen Sie die Richtlinie, die Benutzern für die Einstellungen aktiv sein müssen. Weitere Informationen finden Sie in den Abschnitt [weisen Sie eine benutzerdefinierte Anwendung Setup-Richtlinie für Benutzer](#assign-a-custom-app-setup-policy-to-users) dieses Artikels.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich eine app nicht im Bereich angeheftete apps hinzufügen finden?

Nicht alle apps können Teams über eine app Setup zu fixiert werden. Einige apps können diese Funktion nicht unterstützt. Um apps zu suchen, die fixiert werden können, suchen Sie für die app im Bereich **Hinzufügen fixiert apps** . Registerkarten, die einem persönlichen Bereich (statische Registerkarten) und von Programmen haben auf dem Desktopclient Teams fixiert werden können, und diese apps im Bereich **Hinzufügen fixiert apps** verfügbar sind.

Behalten Sie im Hinterkopf Teams app Store alle Teams apps aufgeführt, während der **Hinzufügen fixiert apps** Bereich nur apps umfasst die Teams über eine Richtlinie fixiert werden können. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Teams für Bildungseinrichtungen Admin. Was muss ich über Richtlinien für die app Setup in Teams für Bildungseinrichtungen wissen?

Die Aufruf von app nicht in Teams für Bildungseinrichtungen zur Verfügung. Wenn Sie eine neue benutzerdefinierte Anwendung Setup Richtlinie erstellen, wird die Aufruf von app in der Liste der apps angezeigt. Jedoch die app wird nicht fixiert Teams Clients und Teams für Bildungseinrichtungen Benutzer werden die Anrufe-app in Teams nicht angezeigt. 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>Wie viele apps können auf eine Richtlinie hinzugefügt werden?

Zu den Teams mobilen Clients (iOS und Android) muss mindestens zwei apps fixiert werden. Weist eine Richtlinie auf weniger als zwei apps, die mobilen Clients die Benutzerrichtlinien werden nicht aktualisiert und stattdessen werden weiterhin die vorhandene Konfiguration zu verwenden.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es Richtlinie, damit Änderungen wirksam werden, bis?

Nachdem Sie die globale Richtlinie bearbeiten oder einer Richtlinie zuweisen, dauert es bis zu 24 Stunden, damit die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können die Benutzer ihre angeheftete apps in Teams anzeigen?

Um alle apps anzuzeigen, die für einen Benutzer fixiert sind, möglicherweise Benutzer je nach der Anzahl der installierten apps und die Größe der ihrer Client-Fenster Teams folgende Aktionen ausführen.

|Desktopclient Teams |Teams mobiler Clients |
|---------|---------|
|Klicken Sie in der app-Leiste an der Seite Teams auf **... Weitere apps**.| In der app-Leiste am unteren Rand Teams zu führen.|
|![App-Setup-Policies-Desktop-More-Apps.PNG](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-Policies-Mobile-More-Apps.PNG](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über des mobilen Zugriffs Teams wissen?

Die Teams mobilen Clients (iOS und Android) derzeit nicht persönliche apps mit statischen Registerkarten unterstützen. Je nach der apps in der Richtlinie festgelegt sind apps, die auf dem Desktopclient Teams fixiert in Teams mobilen Clients möglicherweise nicht angezeigt. Persönliche Bots werden weiterhin im Chat auf mobilen Clients angezeigt.

Mit den mobilen Clients Teams die Benutzer sehen Core Teams apps wie Aktivität, Chat und Teams und können Sie einige apps erste Teilnehmern von Microsoft, wie etwa Schichten anheften.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge von apps, die über eine Richtlinie fixiert ändern?

Derzeit können Benutzer die Reihenfolge der ihre angeheftete apps auf mobilen Clients Teams jedoch nicht auf die Teams Desktop oder Web Clients ändern. 

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation eine benutzerdefinierte Teams-Anwendung erstellt und veröffentlicht, auf Elemente verwenden oder den Mandanten app-Katalog, aber das app-Symbol wird nicht angezeigt, wie erwartet, wenn die app auf der app-Leiste in Teams fixiert ist. Wie behebe ich es? 

Stellen Sie sicher, dass die Logorichtlinien befolgen, bevor Sie die app zu übermitteln. Finden Sie weitere Informationen finden Sie unter [Prüfliste für die Übermittlung Seller Dashboard](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist). 

 ## <a name="related-topics"></a>Verwandte Themen
- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Veröffentlichen einer app mit dem Mandanten Apps Katalog vom Client Teams](tenant-apps-catalog-teams.md)
