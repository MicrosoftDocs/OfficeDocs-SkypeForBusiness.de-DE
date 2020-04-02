---
title: Erstellen einer Intranet-Portal-App für Teams über eine SharePoint Online-Website oder-Seite
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Führen Sie eine vorhandene SharePoint Online-Website oder-Seite aus, und erstellen Sie eine eigenständige statische Registerkarte, die als Intranet-Portal für Ihre Organisation verwendet werden kann.
localization_priority: Normal
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100358"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Erstellen einer Intranet-Portal-App für Teams über eine SharePoint Online-Website oder-Seite

Führen Sie die in diesem Artikel beschriebenen Schritte aus, um eine eigenständige und statische APP innerhalb von Teams zu erstellen, die mit der Intranetsite für Ihre Organisation verknüpft sind.

Eine *persönliche Team-App* Ihrer SharePoint-Intranet-Website wird erstellt und als Registerkarte innerhalb von Teams angezeigt. Diese Registerkarte kann Informationen enthalten, die für alle Benutzer von Teams wichtig sind. Es ist eine schnelle und bequeme Möglichkeit für die Benutzer von Teams, auf Updates zuzugreifen, nur einen Klick entfernt.

Beachten Sie, dass der angezeigte Prozess eine *moderne* SharePoint-Website oder-Seite **verwenden muss** , um zu funktionieren. Dieser Prozess steht für *klassische* Websites oder Seiten nicht zur Verfügung.

> [!IMPORTANT]
> Stellen Sie sicher, dass das Seiten Laden von Teams-Apps für Ihren Mandanten aktiviert ist. Je nachdem, wo Sie sich im Migrationsprozess des Teams-Administrator Portals befinden, müssen Sie möglicherweise entweder unter Teams > Administrator oder unter Administrator > Einstellungen > Dienste und Add-ins > Microsoft Teams > apps > externen apps in der vorherigen Version des Portals aktivieren! 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Verwenden von App Studio zum Erstellen ihrer eigenständigen SharePoint Online-App

Bevor Sie beginnen:
1. Sie müssen die URL einer modernen SharePoint Online-Kommunikation oder einer Team Website oder einer Seite kennen.
    - Auf diesen Websites gibt es immer entweder */Teams/* oder */Sites/* in ihren Pfaden.

2. Sie müssen die Unterdomäne Ihres Mandanten kennen, die im Platzhalter **{{Subdomain}}** verwendet wird.

3. In diesem Artikel wird **{{SiteUrl}}** -Platzhalter für die *URL* der Website oder Seite verwendet, die Sie ausgewählt haben.
    - Beispiel- *URLs*: https://contoso.sharepoint.com/teams/Contoso *oder*   https://contoso.sharepoint.com/sites/Contoso 
4. Darüber hinaus wird **{{sitePath}}** verwendet, um den *Pfad* der URL zu kennzeichnen (z. b.:/Teams/Contoso).
    - Beispiel *Pfade*:/Teams/Contoso *oder* /Sites/contoso 

Führen Sie zunächst die folgenden Schritte aus:

1. Wechseln Sie zum Store für Teams.

2. Installieren oder öffnen Sie App Studio.

3. Klicken Sie neben der app-Option auf **Öffnen**.

4. Klicken Sie bei geöffnetem App Studio auf **Manifest-Editor**.

5. **Erstellen Sie eine neue APP**.

6. Füllen Sie alle **App-Details**aus.

7. Klicken Sie auf **Registerkarten** unter Funktionen.

8. Klicken Sie unter persönliche Registerkarte auf **Hinzufügen** .

9. Geben Sie den **Namen** ein, und wählen Sie **eine neue eindeutige Entitäts-ID**aus.

10. Füllen Sie die **URL für contentURL und Website**aus. 

- **contentUrl**: {{siteurl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}  
- **websiteUrl**: {{siteurl}} 

    Beispiel **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. Navigieren Sie zu **Domänen und Berechtigungen**. Stellen Sie sicher, dass der Abschnitt gültige Domänen Ihren SharePoint Online-Domänennamen enthält.

    Beispiel: contoso.SharePoint.com

12. Fügen Sie die folgenden Web App-Eigenschaften **für einmaliges Anmelden** hinzu: 
     
     Beispiel: **Aad-Anwendungs-ID**: 00000003-0000-0ff1-ce00-000000000000- **Ressourcen-URL**: {{Subdomain}}. SharePoint. com

    ![Einmaliges Anmelden für Web-App mit ID und URL.](media/personal-app.png)

13. **Speichern** Sie diese Eigenschaften, und navigieren Sie dann zu **Testen und verteilen**. 

14. Installieren Sie die APP, um die Anwendung persönlich zu testen.

> [!IMPORTANT]
> Wenn Sie Teams App Studio nicht verwenden, müssen Sie das Manifest komprimieren. JSON-Datei, die Sie soeben erstellt haben, navigieren Sie in Microsoft Teams zum App Store, und klicken Sie auf **benutzerdefinierten App** -Link Hochladen (unten rechts im App Store). Damit steht Ihnen die APP zur Verfügung.

15. Nun steht die APP als statische Registerkarte zum Laden und anzeigen in Teams zur Verfügung.

## <a name="test-and-view-your-new-static-tab"></a>Testen und Anzeigen der neuen statischen Registerkarte

Navigieren Sie auf der linken Seite der APP-Leiste zu den Auslassungszeichen (**...**), um die neue Registerkarte auf dem Desktop der Teams anzuzeigen. Suchen Sie Ihre neue APP, laden Sie Sie, und testen Sie Ihre eigenständige Anwendung in Teams.

Wenn Sie die neue APP im linken Menü an einer höheren Position verfügbar machen möchten, müssen Sie hierfür eine APP-Richtlinieneinstellung verwenden. Diese Einstellung finden Sie im Abschnitt Team Administrator > App-Richtlinie > hinzufügen einer angehefteten Anwendung. Wenn Sie die Richtlinie einem Benutzer zum Testen zuweisen, wird die Änderung 24 Stunden später angezeigt. In diesem Sinn sollten Sie entscheiden, wo die APP möglichst früh angezeigt werden soll, um Verzögerungen zu vermeiden.

Wenn Sie die neue APP auf einem mobilen Gerät anzeigen und testen möchten, öffnen Sie die APP-Schublade, indem Sie auf**^** den Chevron () oberhalb der Tab-Leiste am unteren Rand des Bildschirms tippen. Suchen Sie Ihre APP, und navigieren Sie auf Ihrem mobilen Gerät zu ihr.

> [!CAUTION]
> Der Mobile Support befindet sich derzeit in der Entwicklervorschau. Navigieren Sie zum Aktivieren der Entwicklervorschau zu Einstellungen > Info, und aktivieren Sie dann den Entwicklervorschau Modus.

## <a name="a-sample-manifestjson-file"></a>Eine Beispieldatei für Manifest. JSON

Die von Ihnen generierte JSON-Datei sieht ungefähr wie die folgende aus.

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", 

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", 

        "full": "Intranet Portal for Contoso" 

    }, 

    "description": { 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 

    "staticTabs": [ 

        { 

            "entityId": "communicationSiteTab", 

            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```