---
title: Freigegebene Kanäle in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie, wie Sie freigegebene Kanäle in Microsoft Teams verwenden und verwalten können.
ms.openlocfilehash: 323d20c152af9595b6a738f917103a59ab4142ef
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647549"
---
# <a name="shared-channels-in-microsoft-teams"></a>Freigegebene Kanäle in Microsoft Teams

Freigegebene Kanäle in Microsoft Teams erstellen Räume für die Zusammenarbeit, in die Sie Personen einladen können, die nicht zum Team gehören. Nur die Benutzer, die Besitzer oder Mitglieder des freigegebenen Kanals sind, können auf den Kanal zugreifen. Während Gäste (Personen mit Azure Active Directory-Gastkonten in Ihrer Organisation) nicht zu einem freigegebenen Kanal hinzugefügt werden können, können Sie Personen außerhalb Ihrer Organisation zur Teilnahme an einem freigegebenen Kanal einladen, indem Sie Azure AD B2B Direct Connect verwenden.

Möglicherweise möchten Sie einen freigegebenen Kanal verwenden, wenn Sie mit einer Gruppe von Personen zusammenarbeiten möchten, die alle Mitglieder verschiedener Teams sind. Beispielsweise könnten Mitarbeiter aus den Bereichen Ingenieurwesen, Vertrieb und Support, die alle an verschiedenen Aspekten desselben Projekts oder Produkts arbeiten, einen gemeinsamen Kanal für die Zusammenarbeit verwenden.

Nur Mitglieder von freigegebenen Kanälen können freigegebene Kanäle, zu denen sie hinzugefügt werden, anzeigen und daran teilnehmen. Andere Mitglieder des Teams, mit denen der freigegebene Kanal verbunden ist, können den Kanal nicht anzeigen.

Wenn ein freigegebener Kanal erstellt wird, ist er mit dem übergeordneten Team verknüpft und kann nicht in ein anderes Team verschoben werden. Außerdem können freigegebene Kanäle nicht in Standardkanäle umgewandelt werden und umgekehrt.

[Vergleichen Sie freigegebene Kanäle mit anderen Arten von Kanälen](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="getting-started-with-shared-channels"></a>Erste Schritte mit freigegebenen Kanälen

Freigegebene Kanäle sind in Teams standardmäßig aktiviert. Sie können auswählen, ob Personen freigegebene Kanäle erstellen können, ob sie sie für Personen außerhalb Ihrer Organisation freigeben können und ob sie an externen freigegebenen Kanälen teilnehmen können, indem Sie eine [Kanalrichtlinie erstellen](/MicrosoftTeams/teams-policies).

Wenn Sie Kanäle für Personen außerhalb Ihrer Organisation freigeben möchten, lesen Sie [Planen der externen Zusammenarbeit](/microsoft-365/solutions/plan-external-collaboration) für wichtige Planungsüberlegungen.

Das Freigeben von Kanälen für Personen außerhalb Ihrer Organisation setzt auch voraus, dass Sie mandantenübergreifende Zugriffseinstellungen in Azure AD konfigurieren. Jede Organisation, für die Sie Kanäle freigeben möchten, muss diese Konfiguration ebenfalls abschließen. Weitere Informationen finden Sie unter[Zusammenarbeit mit externen Teilnehmern in einem Kanal](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="shared-channel-creation"></a>Erstellung freigegebener Kanäle

Nur Teambesitzer können einen freigegebenen Kanal erstellen. Teammitglieder und Gäste können sie nicht erstellen. Die Möglichkeit zum Erstellen von freigegebene Kanälen kann auf Organisationsebene verwaltet werden. Verwenden Sie [Richtlinien](teams-policies.md), um zu steuern, welche Benutzer in Ihrer Organisation freigegebene Kanäle erstellen dürfen.

Die Person, die einen freigegebenen Kanal erstellt, ist der Besitzer des freigegebenen Kanals, und nur der Besitzer des freigegebenen Kanals kann Personen direkt zum Kanal hinzufügen oder daraus entfernen. (Wenn Sie möchten, können Sie mehrere Besitzer hinzufügen.) Ein Besitzer eines freigegebenen Kanals kann jeden aus der Organisation zu einem freigegebenen Kanal hinzufügen, den er erstellt hat. Mitglieder eines freigegebenen Kanals verfügen über einen sicheren Bereich für Unterhaltungen, und wenn neue Mitglieder hinzugefügt werden, können diese alle Unterhaltungen (auch alte Unterhaltungen) in diesem freigegebenen Kanal sehen.

Teambesitzer können die Namen aller freigegebenen Kanäle in ihrem Team anzeigen und jeden freigegebenen Kanal im Team löschen. Teambesitzer können weder die Dateien, noch die Unterhaltungen oder die Mitgliederliste eines freigegebenen Kanals anzeigen, es sei denn, sie sind Mitglieder dieses freigegebenen Kanals.

Teammitglieder können nur freigegebene Kanäle sehen, zu denen sie hinzugefügt wurden.

Durch das Klonen eines Teams werden die zugehörigen freigegebenen Kanäle nicht geklont.

## <a name="shared-channel-deletion"></a>Löschen eines freigegebenen Kanals

Ein gelöschter freigegebener Kanal kann innerhalb von 30 Tagen nach dem Löschen wiederhergestellt werden. Beim Wiederherstellen eines gelöschten freigegebenen Kanals werden alle vorherigen Mitgliedschaften (Einzel- und Teamfreigabe) wiederhergestellt.

Gelöschte Teams können innerhalb von 30 Tagen nach dem Löschen wiederhergestellt werden. Wenn ein Team gelöscht wird, werden auch alle freigegebenen Kanäle gelöscht. Wenn ein gelöschtes Team wiederhergestellt wird, werden alle freigegebenen Kanäle mit allen Freigabebeziehungen wiederhergestellt.

Wenn ein Team archiviert wird, bleibt die individuelle Freigabe intakt, aber die Freigabe für andere Teams als das übergeordnete Team wird entfernt. Wenn die Archivierung eines archivierte Team aufgehoben wird, werden alle freigegebenen Kanäle mit einer individuellen Freigabe wiederhergestellt.

## <a name="adding-and-removing-owners-and-members"></a>Hinzufügen und Entfernen von Besitzern und Mitgliedern

Der Besitzer eines freigegebenen Kanals kann nicht über den Teams-Client entfernt werden, wenn er der letzte Besitzer eines oder mehrerer freigegebener Kanäle ist.

Wenn der Besitzer des letzten freigegebenen Kanals Ihre Organisation verlässt oder aus der Microsoft 365-Gruppe entfernt wird, die dem Team zugeordnet ist, wird ein Mitglied des freigegebenen Kanals aus Ihrer Organisation automatisch zum Besitzer des freigegebenen Kanals heraufgestuft. Wenn es keine Mitglieder aus Ihrer Organisation gibt, die heraufgestuft werden sollen, bleibt der freigegebene Kanal besitzerlos. Ein Teams-Administrator muss manuell einen Kanalbesitzer zuweisen. Erwägen Sie, mehr als einen Besitzer hinzuzufügen, um diese Situation zu vermeiden.

> [!NOTE]
> Externe Teilnehmer müssen über ihren UPN anstelle ihrer E-Mail-Adresse hinzugefügt werden, wenn die beiden in Azure Active Directory nicht übereinstimmen.

## <a name="channel-owner-settings"></a>Einstellungen des Kanalbesitzers

Jeder freigegebene Kanal verfügt über eigene Einstellungen, die der Kanalbesitzer verwalten kann, einschließlich der Möglichkeit, Mitglieder hinzuzufügen und zu entfernen, Registerkarten hinzuzufügen und @Erwähnung für den gesamten Kanal. Diese Einstellungen sind unabhängig von den Einstellungen des übergeordneten Teams. Wenn ein freigegebener Kanal erstellt wird, erbt er zunächst die Einstellungen des übergeordneten Teams. Anschließend können die Einstellungen unabhängig von den Einstellungen des übergeordneten Teams geändert werden.

Der Besitzer des freigegebenen Kanals kann auf **Kanal verwalten** klicken und dann die Registerkarten **Mitglieder** und **Einstellungen** verwenden, um Mitglieder hinzuzufügen oder zu entfernen und Einstellungen zu bearbeiten.

## <a name="shared-channel-owner-and-member-actions"></a>Aktionen für Besitzern und Mitgliedern eines freigegebenen Kanals

In der folgenden Tabelle wird beschrieben, welche Aktionen Besitzer, Mitglieder und Gäste in freigegebenen Kanälen ausführen können.

|Aktion  |Teambesitzer|Teammitglied|Teamgast|Besitzer des freigegebenen Kanals|Mitglied des freigegebenen Kanals|Externer Teilnehmer des freigegebenen Kanals|
|---------|---------|---------|---------|---------|---------|---------|
|Freigegebenen Kanal erstellen|Vom Administrator gesteuert|Von Administrator und Teambesitzer gesteuert|Nein|Nicht zutreffend|Nein|Nein|
|Freigegebenen Kanal löschen|Ja|Nein|Nein|Ja|Nein|Nein|
|Freigegebenen Kanal verlassen|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Ja, es sei denn, es handelt sich um die letzten Besitzer|Ja|Ja|
|Freigegebenen Kanal bearbeiten|Nein|Nicht zutreffend|Nicht zutreffend|Ja|Nein|Nein|
|Gelöschten freigegebenen Kanal wiederherstellen|Ja|Nein|Nein|Ja|Nein|Nein|
|Mitglieder hinzufügen|Nein|Nicht zutreffend|Nicht zutreffend|Ja|Nein|Nein|
|Bearbeiten von Einstellungen|Nein|Nicht zutreffend|Nicht zutreffend|Ja|Nein|Nein|
|Verwalten von Registerkarten und Apps|Nein|Nicht zutreffend|Nicht zutreffend|Ja, Apps müssen für das Team installiert werden|Vom Kanalbesitzer gesteuert|Nein|

## <a name="shared-channel-sharepoint-sites"></a>SharePoint-Websites des freigegebenen Kanals

Jeder freigegebene Kanal hat [seine eigene SharePoint-Website](/SharePoint/teams-connected-sites). Die separate Website soll sicherstellen, dass der Zugriff auf die Dateien des freigegebenen Kanals nur für Mitglieder des freigegebenen Kanals möglich ist. Diese Websites werden standardmäßig mit einer Dokumentbibliothek erstellt und können über die [Benutzeroberfläche für die Websiteverwaltung](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04) auf einfache Weise in eine Website mit vollem Funktionsumfang erweitert werden. Jede Website wird in derselben geografischen Region wie die Website für das übergeordnete Team erstellt. Diese Lightweight-Websites verfügen über eine benutzerdefinierte Vorlagen-ID, „TEAMCHANNEL#1“, um die Verwaltung über PowerShell und die Graph-API zu vereinfachen. 

Eine freigegebene Kanalwebsite erbt die Vertraulichkeitsbezeichnung des übergeordneten Teams. Dies gilt auch dann, wenn der Kanal direkt mit einem anderen Team geteilt wird.

> [!NOTE]
> Nur Personen mit Besitzer- oder Mitgliedsberechtigungen im Kanal haben Zugriff auf Inhalte auf der freigegebenen Kanalwebsite. Personen im übergeordneten Team und Administratoren haben keinen Zugriff, es sei denn, sie sind auch Kanalmitglieder.

Die Mitgliedschaft in den Websitebesitzer- und Mitgliedergruppen wird mit der Mitgliedschaft des freigegebenen Kanals synchron gehalten. Websiteberechtigungen für die Website eines freigegebenen Kanals können nicht unabhängig über SharePoint verwaltet werden. 

Teams verwaltet den Lebenszyklus der Website des freigegebenen Kanals. Wenn die Website außerhalb von Teams gelöscht wird, wird sie automatisch innerhalb von vier Stunden wiederhergestellt, solange der freigegebene Kanal noch aktiv ist. Wenn die Website dauerhaft gelöscht wird, erfolgt die Bereitstellung einer neuen Website für den freigegebenen Kanal.

Wird ein freigegebener Kanal oder ein Team, das einen freigegebenen Kanal enthält, wiederhergestellt, werden die Websites mit ihm wiederhergestellt. Wenn eine Website eines freigegebenen Kanals wiederhergestellt wird und das 30-Tage-Fenster für das „vorläufige Löschen“ des freigegebenen Kanal überschritten ist, wird die Website als eigenständige Website ausgeführt.

## <a name="shared-channel-messages"></a>Freigegebene Kanalnachrichten

Freigegebene Kanalnachrichten werden in einem dedizierten Systempostfach gespeichert, das dem freigegebenen Kanal und nicht dem Gruppenpostfach zugeordnet ist.

Weitere Informationen zum Ausführen einer eDiscovery-Suche für freigegebene Kanalnachrichten finden Sie unter [Durchführen einer eDiscovery-Untersuchung von Inhalten in Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Überlegungen im Zusammenhang mit dem Zugriff auf Dateien in freigegebenen Kanälen

Dateien, Ordner und OneNote-Notizbücher in einem freigegebenen Kanal können mithilfe der [standardmäßigen SharePoint-Dateifreigabe](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c) für Personen außerhalb des Kanals (aber nicht außerhalb der Organisation) freigegeben werden.

Wenn einem Benutzer über SharePoint Zugriff auf eine Datei, einen Ordner oder ein Notebook in einem freigegebenen Kanal gewährt wird, wird der Zugriff des Benutzers auf die Datei, den Ordner oder das Notebook nicht durch das Entfernen des Benutzers aus dem Team oder dem freigegebenen Kanal entfernt.

Wird ein vorhandenes Notizbuch als Registerkarte zu einem freigegebenen Kanal hinzugefügt, wird der Zugriff auf den freigegebenen Kanal nicht geändert, und das Notizbuch behält die bestehenden Berechtigungen bei.

## <a name="resources-for-your-users"></a>Ressourcen für Ihre Benutzer

Die folgenden Artikel können für die Benutzer in Ihrer Organisation hilfreich sein, wenn sie freigegebene Kanäle verwenden.

[Erstellen eines freigegebenen Kanals in Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Freigeben eines Kanals für Personen in Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Freigeben eines Kanals für ein Team](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Gründe für die Verwendung eines freigegebenen Kanals im Vergleich zu anderen Kanaltypen in Teams?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Gäste und freigegebene Kanäle in Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Besitzer- und Mitgliedsrollen eines freigegebenen Kanals in Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>Grenzwerte für freigegebene Kanäle

Die folgende Tabelle beschreibt die maximale Anzahl von Kanälen und Mitgliedern.

|Maximale Anzahl für|Wert|Hinweise|
|:---------|:----|:----|
|Mitglieder in einem Team|25.000|Umfasst alle Benutzer im Team und direkte Mitglieder in freigegebenen Kanälen.|
|Freigegebene Kanäle pro Team|200|Gehostet und für das Team freigegeben. (Schließt gelöschte Kanäle während des 30-tägigen Wiederherstellungsfensters ein.)|
|Teams, für die ein Kanal freigegeben werden kann|50|Ausschließen des übergeordneten Teams|
|Mitglieder in einem freigegebenen Kanal|5.000 direkte Mitglieder, einschließlich bis zu 50 Teams. (Im Sinne dieses Grenzwerts wird jedes Team, für das der Kanal freigegeben ist, als ein Mitglied gezählt.)|Echtzeit-Updates sind jeweils nur für 25 000 Benutzer verfügbar und nur 25 000 Benutzer werden in der Kanalliste angezeigt.|

Es gelten die folgenden Einschränkungen:

- Für externe Teilnehmer werden nur Arbeits-, Schul- oder Unikonten von Azure AD unterstützt.

- Freigegebene Kanäle unterstützen Registerkarten mit Ausnahme von Stream, Planner und Forms.

- Bots, Connectors und Nachrichtenerweiterungen werden nicht unterstützt.

- Wenn Sie ein Team aus einem bestehenden Team erstellen, werden freigegebene Kanäle des bestehenden Teams nicht übernommen.

- Benachrichtigungen aus freigegebenen Kanälen sind derzeit in E-Mails zu verpassten Aktivitäten nicht enthalten.

- Geteilte Channels werden in Kursteams nicht unterstützt.

## <a name="supported-apps-in-shared-channels"></a>Unterstützte Apps in freigegebenen Kanälen

Informationen dazu, wie Sie Ihre App für freigegebene Kanäle vorbereiten, finden Sie unter [Öffnen Ihrer App für die organisationsübergreifende Zusammenarbeit mit Microsoft Teams Connect](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1).

Die folgenden Apps werden für die Verwendung in freigegebenen Kanälen unterstützt. 

- Aktivität
- Adobe Acrobat Sign
- Asana
- Anrufe
- Chat
- Code by Vivani
- Conceptboard
- Excel
- FileBrowser
- Dateien
- Flipgrid
- Freehand by InVision
- HeyTaco
- Jira Cloud
- Kahoot!
- Listen
- Lucidchart
- Lumio
- MeisterTask
- MindMeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- PDF
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Saved
- Scrum-Poker
- Suche
- SharePoint
- SharePoint-Seiten
- Slido
- Smartsheet
- SurveyMonkey
- Tasks in a Box
- Teams-Manager
- TeamViewer
- Teamarbeit
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Web
- Wooclap
- Word
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>Verwandte Themen

[B2B Direct Connect-Übersicht](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Konfigurieren von mandantenübergreifenden Zugriffseinstellungen für B2B Direct Connect](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Übersicht über Teams und Kanäle in Teams](teams-channels-overview.md)

[Private Kanäle in Microsoft Teams](/microsoftteams/private-channels)
