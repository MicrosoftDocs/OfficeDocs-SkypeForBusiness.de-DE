---
title: Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams
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
description: Informationen Sie zu Richtlinien für die app-Berechtigung in der Microsoft-Teams und deren Verwendung zum Steuern, welche apps für Benutzer in Ihrer Organisation zur Verfügung stehen.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: e88493e5ecb764f207ee0eebd9a46e68db3671cd
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747686"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Ein Administrator können Berechtigungsrichtlinien app Sie steuern, welche apps Microsoft-Teams, Benutzer in Ihrer Organisation zur Verfügung stehen. Sie können zulassen oder blockieren alle apps oder bestimmte apps, die von Microsoft veröffentlicht dritten und Ihrer Organisation. Wenn Sie eine app blockieren, können Benutzer nicht aus dem Teams app Store zu installieren.

Sie können Richtlinien für die app-Berechtigung in der Verwaltungskonsole von Microsoft-Teams verwalten. Sie können Einstellungen Org geltende anwenden, verwenden Sie die globale Richtlinie (Org geltende Standard) und Richtlinien erstellen und zuweisen benutzerdefinierte für einzelne Benutzer oder Benutzer in einer Gruppe.  

![Screenshot der app Berechtigungsrichtlinie](media/app-permission-policies.png)

> [!NOTE]
> Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen, und weisen Sie eine benutzerdefinierte Richtlinie an. Org geltende app-Einstellungen außer Kraft setzen die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und Benutzern zuweisen.

Angenommen Sie, Sie möchten alle Drittanbieter-apps blockieren und bestimmte apps von Microsoft für die HR-Abteilung in Ihrer Organisation zulassen. Sie würden erstellen Sie eine benutzerdefinierte Richtlinie mit dem Namen HR App Berechtigungsrichtlinie, setzen Sie sie blockieren und Zulassen von apps, die Sie möchten und weisen Sie es Benutzern in der HR-Abteilung.

## <a name="manage-org-wide-app-settings"></a>Org geltende app-Einstellungen verwalten

Verwenden Sie Org geltende app-Einstellungen auf Steuerelement, welche apps in Ihrer Organisation zur Verfügung stehen. Org geltende app-Einstellungen steuern das Verhalten für alle Benutzer und überschreiben Sie alle anderen app Berechtigungsrichtlinien, die Benutzern zugewiesen. Org geltende app-Einstellungen werden sofort wirksam und können sie bösartiger oder problematisch apps zu steuern.

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**App > **Berechtigungsrichtlinien**.
2. Wählen Sie **gesamte Org Einstellungen**aus. Sie können dann die gewünschten Einstellungen konfigurieren, in der Systemsteuerung. 
![Screenshot der gesamte Org app-Einstellungen](media/app-permission-policies-org-wide-settings.png)
3. Deaktivieren Sie unter **Drittanbieter - apps**oder aktivieren Sie diese Einstellungen zur Steuerung des Zugriffs auf Drittanbieter-apps:

    - **Zulassen von Drittanbieter - apps in Teams**: Hiermit legen Sie fest, ob Benutzer Drittanbieter-apps verwenden können.
    - **Neue Drittanbieter - apps, die an den Store standardmäßig veröffentlicht zulassen**: Diese steuert, ob neue Drittanbieter-apps, die an die Teams app veröffentlicht werden gespeichert werden automatisch in Teams verfügbar. Sie können diese Option nur festlegen, wenn Sie zulassen, dass Drittanbieter-apps.

4. Klicken Sie unter **benutzerdefinierte apps**deaktivieren Sie oder aktivieren Sie **Zulassen Interaktion mit benutzerdefinierten apps**. Diese Einstellung steuert, ob Benutzer benutzerdefinierte (Sideloaded) apps interagieren können. Beachten Sie, dass dies ermöglicht Benutzern das *Hochladen* von benutzerdefinierten apps unterscheidet beibehalten.
5. Unter **blockiert apps**suchen und Hinzufügen von apps, die Sie in Ihrer Organisation blockieren möchten. Sie können apps aus dem Mandanten app-Katalog oder Teams app Store auswählen.
6. Klicken Sie auf die für die gesamte Org app-Einstellungen **Speichern** , um wirksam wird.

## <a name="create-a-custom-app-permission-policy"></a>Erstellen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie

Wenn Sie möchten die apps zu steuern, die für verschiedene Gruppen von Benutzern in Ihrer Organisation zur Verfügung stehen, erstellen Sie, und weisen Sie Berechtigungsrichtlinien für eine oder mehrere benutzerdefinierte Anwendung. Sie erstellen und Zuweisen von separaten basierend auf gibt an, ob apps von Microsoft veröffentlicht werden benutzerdefinierte Richtlinien können Drittanbieter oder Ihre Organisation. Es ist wichtig, zu wissen, dass nach der Erstellung einer benutzerdefinierten Richtlinie nicht mehr ändern können, wenn Drittanbieter-apps in Org geltende Einstellungen deaktiviert sind. 

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**App > **Berechtigungsrichtlinien**.
2. Wählen Sie **neue Richtlinie**aus.
    ![Screenshot des neuen app-Berechtigungsrichtlinie](media/app-permission-policies-new-policy.png)
3. Geben Sie einen beschreibenden Namen für die Richtlinie ein.
4. Wählen Sie unter **Microsoft-apps**, **Drittanbieter - apps**und **Mandanten apps**eine der folgenden:

    - **Alle apps zulassen**
    - **Zulassen Sie bestimmte apps oder blockieren Sie alle anderen**
    - **Blockieren Sie bestimmte apps, und zulassen alle anderen**
    - **Blockieren Sie alle apps**

5. Wenn Sie **bestimmte apps zulassen und verhindern, dass Benutzer**ausgewählt haben, fügen Sie die apps, die Sie zulassen möchten:

    1. Wählen Sie **apps zulassen**.
    1. Suchen Sie nach der apps, die Sie zulassen, und klicken Sie dann auf **Hinzufügen**möchten. Die Suchergebnisse werden mit dem app-Verleger (**Microsoft-apps**, **Drittanbieter - apps**oder **apps Mandanten**) gefiltert.
    1. Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **Zulassen**.

6. Wenn Sie **bestimmte apps blockieren und alle anderen Benutzern gestatten**ausgewählt haben, suchen Sie nach und Hinzufügen von apps, die Sie blockieren möchten.
7. Klicken Sie auf **Speichern**.

## <a name="edit-an-app-permission-policy"></a>Bearbeiten einer Berechtigungsrichtlinie für eine app

Das Microsoft-Teams, Administrationscenter können Sie eine Richtlinie, einschließlich der globalen (Org geltende) Standardrichtlinie und benutzerdefinierte Richtlinien, die Sie erstellen, bearbeiten. 

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**App > **Berechtigungsrichtlinien**.
2. Wählen Sie die Richtlinie, den, die Sie bearbeiten möchten.
3. Stellen Sie dort die gewünschten Änderungen. Sie können basierte auf den Herausgeber der app-Einstellungen verwalten und hinzufügen und Entfernen von apps basierend auf der Einstellung zulassen/blockieren.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Weisen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie für Benutzer

Das Microsoft-Teams, Administrationscenter können Sie weisen Sie eine benutzerdefinierte Richtlinie für einzelne Benutzer oder die Skype für Business PowerShell-Modul mehrere Benutzer, wie alle Benutzer in einer Sicherheitsgruppe oder Verteilergruppe eine benutzerdefinierte Richtlinie zugewiesen.

> [!IMPORTANT]
> Es wird empfohlen, mithilfe von PowerShell nur für Richtlinien Benutzern zuweisen. Verwenden Sie das Microsoft-Teams, Administrationscenter zu erstellen, bearbeiten und Verwalten von Richtlinien.

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>Weisen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie für einzelne Benutzer

1. Im linken Navigationsbereich von Microsoft-Teams, Administrationscenter wechseln Sie zu dem **Benutzer**, und klicken Sie dann auf Benutzer.
2. Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus.
3. Wählen Sie unter **App Berechtigungsrichtlinie**die app-Berechtigung-Richtlinie, den, die Sie zuweisen möchten, und wählen Sie dann auf **Speichern**.

    ![App-Setup-Berechtigung-zuweisen-policy.png](media/app-permission-policies-assign-policy.png)

Sie können einen oder mehrere Benutzer auch wie folgt eine Berechtigungsrichtlinie app zuweisen:

1. Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **Teams apps** > **Berechtigungsrichtlinien**.
2. Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.
3. Wählen Sie **Benutzer verwalten**.
4. Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.
5. Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Weisen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie für Benutzer in einer Gruppe

Sie möchten eine benutzerdefinierte Anwendung Berechtigungsrichtlinie zu mehreren Benutzern zuweisen, die Sie bereits ermittelt haben. Beispiel: Sie möchten eine Richtlinie für alle Benutzer in einer Sicherheitsgruppe zuweisen. Hierzu können Sie eine Verbindung mit Azure Active Directory PowerShell Graph-Modul und die Skype für Business PowerShell-Modul. Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).

In diesem Beispiel weisen wir eine benutzerdefinierte Anwendung Berechtigungsrichtlinie HR App Berechtigungsrichtlinie aufgerufen, um alle Benutzer in der Gruppe Contoso Pharmaceuticals HR-Projekt.  

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
Weisen Sie alle Benutzer in der Gruppe zu einer Berechtigungsrichtlinie für einen bestimmten app. In diesem Beispiel ist es HR App Berechtigungsrichtlinie.
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
Abhängig von der Anzahl der Elemente in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-permission-policies"></a>Arbeiten mit Richtlinien für die app-Berechtigung

#### <a name="can-i-control-line-of-business-lob-apps"></a>Kann ich die Codezeile Business (LOB) apps steuern?

Ja, können Sie Berechtigungsrichtlinien app verwenden, um die Einführung und Verteilung von benutzerdefinierten (LOB) apps zu steuern.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Wie beziehen sich app Berechtigungsrichtlinien angeheftete apps und Richtlinien für die app Setup?

Sie können Richtlinien für die app Setup zusammen mit Berechtigungsrichtlinien app verwenden. Vor dem angeheftete apps sind aus dem Satz von aktivierte apps für einen Benutzer ausgewählt. Verfügt ein Benutzer einer Berechtigungsrichtlinie für eine app, die eine app in ihrer app-Richtlinie Setup blockiert, werden nicht darüber hinaus app in Teams angezeigt.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>Kann ich app Berechtigungsrichtlinien einschränken Hochladen von benutzerdefinierten apps (auch bekannt als Sideloading) verwenden?

Weitere Informationen zum Einschränken des benutzerdefinierten apps hochladen finden Sie unter [Manage benutzerdefinierte app-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es Richtlinie, damit Änderungen wirksam werden, bis?

Nachdem Sie die globale Richtlinie bearbeiten oder einer Richtlinie für Benutzer zuweisen, kann es bis zu 24 Stunden, damit die Änderungen wirksam werden. Org geltende app-Einstellungen werden sofort wirksam.

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Bezieht blockieren einer app Teams mobilen Clients sich auf?

Ja, wenn Sie eine app blockieren, wird diese app über alle Teams Clients blockiert.  

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Was fest ein Benutzer, wenn eine app ausgeschlossen wird?

Benutzer können nicht mit einer blockierten app oder seine Funktionen, solche Bots, Registerkarten und messaging Extensions interagieren. In einem freigegebenen Kontext, beispielsweise einen Chat Team- oder Gruppenmitglieder können Bots weiterhin Nachrichten an alle Teilnehmer dieses Kontexts senden. Teams informiert den Benutzer bei eine app ausgeschlossen wird. 

Beispielsweise, wenn eine app gesperrt wird, können nicht Benutzer der folgenden Aufgaben ausführen:

- Fügen Sie die app persönlich oder einen Chat oder Teams
- Senden von Nachrichten an die app bot
- Ausführen von Aktionen, die Informationen zurück an die app, beispielsweise bearbeitungsfähige Nachrichten senden  
- Anzeigen der app-Registerkarte
- Einrichten von Connectors zum Empfangen von Benachrichtigungen
- Verwenden Sie die app-messaging-Erweiterung

 ## <a name="related-topics"></a>Verwandte Themen
- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Verwalten von Richtlinien für die app Setup in Teams](teams-app-setup-policies.md)
- [Verwalten von benutzerdefinierten app-Richtlinien und Einstellungen im Team](teams-custom-app-policies-and-settings.md)
