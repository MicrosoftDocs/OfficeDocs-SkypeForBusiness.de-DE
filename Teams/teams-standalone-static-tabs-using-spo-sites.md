---
title: Erstellen einer Intranet-Portal-App für Teams von einer SharePoint Online-Website oder -Seite aus
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Verwenden Sie eine vorhandene SharePoint Online-Website oder -Seite und erstellen Sie eine eigenständige statische Registerkarte, die als Intranet-Portal für Ihre Organisation verwendet werden kann.
localization_priority: Priority
ms.openlocfilehash: 63527cb3cccc5f882f44ff39911d33270bafb4c8
ms.sourcegitcommit: 9419860f9a1c1dd2c7c444162e1d55d704e19c69
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43207074"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Erstellen einer Intranet-Portal-App für Teams von einer SharePoint Online-Website oder -Seite aus

Führen Sie die in diesem Artikel aufgeführten Schritte aus, um eine eigenständige und statische App innerhalb von Teams zu erstellen, die mit der Intranet-Seite Ihrer Organisation verknüpft ist.

Eine *Persönliche Teams-App* Ihrer SharePoint-Intranet-Website wird erstellt und als Registerkarte innerhalb von Teams angezeigt. Diese Registerkarte enthält Informationen, die für alle Teammitglieder wichtig sind. Es ist eine schnelle und bequeme Möglichkeit für die Benutzer von Teams, auf Updates zuzugreifen, die nur einen Tab-Klick entfernt sind.

Beachten Sie, dass für den gezeigten Vorgang eine *moderne* SharePoint-Website oder -Seite verwendet werden **muss**. Diese Vorgehensweise ist für *klassische* Websites oder Seiten nicht verfügbar.

> [!IMPORTANT]
> Stellen Sie sicher, dass Side-Loading von Teams-Apps für Ihren Mandanten aktiviert ist. Je nachdem, wo Sie sich im Migrationsprozess des Teams-Administratorportals befinden, müssen Sie dies möglicherweise entweder unter Teams > Administrator oder unter Administrator > Einstellungen > Dienste und Add-Ins > Microsoft Teams > Apps > Externe Apps in der vorherigen Version des Portals aktivieren!

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Verwenden von App Studio zum Erstellen einer eigenständigen SharePoint Online-App

Bevor Sie beginnen:

1. Sie müssen die URL einer modernen SharePoint Online-Kommunikations- oder-Team-Website oder-Seite kennen.
    - Diese Websites verfügen immer über */teams/* oder */sites/* in ihren Pfaden.

2. Sie müssen die Unterdomäne Ihres Mandanten kennen, die im Platzhalter **{{subdomain}}** verwendet wird.

3. In diesem Artikel wird der Platzhalter **{{siteUrl}}** für die *URL* der ausgewählten Website oder Seite verwendet.
    - Beispiel-*URLs*:   https://contoso.sharepoint.com/teams/Contoso   *oder* https://contoso.sharepoint.com/sites/Contoso
4. Außerdem wird **{{sitePath}}** dazu verwendet, den *Pfad* der URL (beispielsweise: /teams/contoso) zu kennzeichnen.
    - *Beispielpfade*:   /teams/Contoso   *oder* /sites/Contoso

Beginnen Sie mit den folgenden Schritten:

1. Wechseln Sie zum Teams-Store.

2. Installieren oder öffnen Sie App Studio.

3. Klicken Sie neben der App-Option auf **Öffnen**.

4. Klicken Sie bei geöffnetem App Studio auf **Manifest-Editor**.

5. **Erstellen Sie eine neue App**.

6. Füllen Sie alle **App-Details** aus.

7. Klicken Sie auf **Registerkarten** unter Funktionen.

8. Klicken Sie unter persönliche Registerkarte auf **Hinzufügen**.

9. Füllen Sie den **Namen** aus, und wählen Sie **eine neue eindeutige Entitäts-ID** aus.

10. Füllen Sie die **contentURL und Website-URL** aus.

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**: {{siteUrl}}

    Beispiel-**contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub

11. Navigieren Sie zu **Domänen und Berechtigungen**. Stellen Sie sicher, dass der Abschnitt gültige Domänen Ihren SharePoint Online-Domänennamen enthält.

    Beispiel: contoso.sharepoint.com

12. Fügen Sie die folgenden Web App-Eigenschaften für **Einmaliges Anmelden (Single Sign-on, SSO)** hinzu:

     Beispiel:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com

    ![Web App-Single Sign-On, mit ID und URL.](media/personal-app.png)

13. **Speichern Sie** diese Eigenschaften und navigieren Sie dann zu **Testen und Verteilen**.

14. Installieren Sie die App, um die Anwendung persönlich zu testen.

> [!IMPORTANT]
> Wenn Sie nicht mit Teams App Studio arbeiten, müssen Sie die soeben erstellte manifest.JSON-Datei als .zip komprimieren, zum App Store in Teams navigieren und auf den Link **benutzerdefinierte App hochladen** (unten rechts im App Store) klicken. Dadurch wird die App für Sie verfügbar.

15. Die App ist nun als statische Registerkarte verfügbar, die Sie laden und in Teams anzeigen können.

## <a name="test-and-view-your-new-static-tab"></a>Testen und Betrachten Sie Ihre statische Registerkarte

Um die neue Registerkarte im Team-Desktop anzuzeigen, navigieren Sie auf der linken Seite der App-Leiste zu den Auslassungszeichen (**...**). Suchen Sie Ihre neue App, laden Sie sie herunter und testen Sie Ihre eigenständige Anwendung in Teams.

Wenn Sie die neue App im linken Menü an einer höheren Position verfügbar machen möchten, müssen Sie dafür eine App-Richtlinieneinstellung verwenden. Diese Einstellung finden Sie im Abschnitt Team Administrator > App-Richtlinie > Hinzufügen einer angehefteten Anwendung. Wenn Sie einem Benutzer die Richtlinie zum Test zuweisen, wird die Änderung 24 Stunden später angezeigt. In diesem Sinne sollten Sie frühzeitig entscheiden, wo die App angezeigt werden soll, um Verzögerungen zu vermeiden.

Wenn Sie die neue App auf einem mobilen Gerät anzeigen und testen möchten, öffnen Sie die App-Schublade, indem Sie auf das Chevron (**^**) oberhalb der Registerkartenleiste am unteren Rand des Bildschirms tippen. Suchen Sie Ihre App, und navigieren Sie auf Ihrem mobilen Gerät zu ihr.

> [!CAUTION]
> Die Unterstützung für Mobilgeräte befindet sich derzeit im Developer Preview. Um Developer Preview zu aktivieren, navigieren Sie zu Einstellungen > Info, und aktivieren Sie dann den Developer Preview-Modus.

## <a name="a-sample-manifestjson-file"></a>Eine Manifest.JSON-Beispieldatei

Die von Ihnen generierte JSON-Datei sieht in etwa so wie die nachfolgende aus.

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

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
