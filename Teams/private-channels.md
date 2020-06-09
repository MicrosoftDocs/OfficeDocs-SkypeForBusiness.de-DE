---
title: Private Kanäle in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie private Kanäle in Microsoft Teams nutzen und verwalten können.
ms.openlocfilehash: 769fd2b489d65b276823abd7c3ff8f579100617a
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637934"
---
# <a name="private-channels-in-microsoft-teams"></a>Private Kanäle in Microsoft Teams

Private Kanäle in Microsoft Teams schaffen konzentrierte Räume für die Zusammenarbeit innerhalb Ihrer Teams. Nur die Benutzer im Team, die Besitzer oder Mitglieder des privaten Kanals sind, können auf den Kanal zugreifen. Jeder, auch Gäste, kann als Mitglied zu einem privaten Kanals hinzugefügt werden, solange er bereits Mitglied des Teams ist.

Sie können einen privaten Kanal verwenden, wenn Sie die Zusammenarbeit auf diejenigen beschränken möchten, die das entsprechende Wissen benötigen, oder wenn Sie die Kommunikation zwischen einer Gruppe von Personen, die einem bestimmten Projekt zugeordnet sind, erleichtern möchten, ohne ein zusätzliches Team zur Verwaltung bilden zu müssen.

Ein privater Kanal ist zum Beispiel in diesen Szenarien nützlich:

- Eine Gruppe von Personen in einem Team möchten einen konzentrierten Raum für die Zusammenarbeit nutzen, ohne ein separates Team bilden zu müssen.
- Eine Untergruppe von Personen in einem Team möchten einen privaten Kanal nutzen, um vertrauliche Informationen, wie z. B. Budgets, Ressourcen, strategische Positionierung usw. zu besprechen.

Ein Schloss-Symbol zeigt einen privaten Kanal an. Nur Mitglieder privater Kanäle können die privaten Kanäle, zu denen sie hinzugefügt wurden, anzeigen und an ihnen teilnehmen.

![Screenshot privater Kanäle in einem Team](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Wissenswertes über private Kanäle

Derzeit unterstützen private Kanäle Connectors und Registerkarten (außer Stream, Planner und Forms). Wir arbeiten an der vollständigen Unterstützung von Apps für private Kanäle, einschließlich Messagingerweiterungen und Bots.

Jedes Team kann maximal 30 private Kanäle nutzen, und jeder private Kanal kann maximal 250 Mitglieder haben. Der Grenzwert der 30 private Kanälen gilt zusätzlich zu den 200 Standardkanälen pro Team.

> [!NOTE]
> Wir fügen den privaten Kanälen ständig neue Funktionen hinzu, also schauen Sie bald wieder vorbei, um die neuesten Informationen über Apps, Kanalbesprechungen und die Skalierung privater Kanäle für große Teams zu erhalten.

## <a name="when-to-create-a-private-channel"></a>Wann sollten Sie einen privaten Kanal erstellen?

Um zu bestimmen, ob ein privater Kanal geeignet ist, sollten Sie sich die folgenden Fragen dazu stellen, wer zusammenarbeiten muss und worum es bei der Zusammenarbeit geht.

|Gibt es bereits ein Team, in dem diese Personen Teammitglieder sind?  |Muss diese Arbeit vor anderen vertraulich gehalten werden?  |Gibt es viele unterschiedliche Themen zu diskutieren?  |Empfehlung  |
|---------|---------|---------|---------|
|Ja      |Ja         |Ja         |Erstellen Sie einen privaten Kanal im bestehenden Team, oder erwägen Sie die Erstellung dedizierter privater Kanäle für jedes Thema.         |
|Ja     |Ja         |Nein         |Erstellen Sie einen privaten Kanal im bestehenden Team.         |
|Ja     |Nein         |Nein         |Erstellen Sie einen Kanal im bestehenden Team.         |
|Nein     |Nein         |Nein         |Ziehen Sie die Erstellung eines neuen Teams in Betracht.         |
|Nein     |Nein         |Ja         |Ziehen Sie die Erstellung eines neuen Teams in Betracht, und erwägen Sie dann, je nach der Vertraulichkeit der einzelnen Themen, die Erstellung separater Standard- oder Privatkanäle für jedes Thema.         |
|Nein     |Ja         |Nein         |Erstellen Sie ein neues Team, und erwägen Sie die Erstellung eines privaten Kanals.         |

Wenn ein privater Kanal erstellt wird, ist er mit dem übergeordneten Team verbunden und kann nicht in ein anderes Team verschoben werden. Außerdem können private Kanäle nicht in Standardkanäle umgewandelt werden und umgekehrt.

## <a name="private-channel-creation-and-membership"></a>Erstellung von und Mitgliedschaft in privaten Kanälen

### <a name="who-can-create-private-channels"></a>Wer kann private Kanäle erstellen?

Standardmäßig kann jeder Teambesitzer oder jedes Teammitglied einen privaten Kanal erstellen. Gäste können keinen privaten Kanal erstellen. Die Möglichkeit zum Erstellen privater Kanäle kann auf Teamebene und auf Organisationsebene verwaltet werden.

> 1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

> 2. Verwenden Sie [Richtlinien](teams-policies.md) , um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.
    Nachdem Sie die Richtlinien eingerichtet haben, können Teambesitzer die Möglichkeit für Mitglieder, private Kanäle auf der Registerkarte **Einstellungen** für ein Team zu erstellen, deaktivieren oder aktivieren.

Die Person, die einen privaten Kanal erstellt, ist der Besitzer des privaten Kanals, und nur der Besitzer des privaten Kanals kann Personen direkt zum Kanal hinzufügen oder daraus entfernen. Der Besitzer eines privaten Kanals kann ein beliebiges Teammitglied zu diesem privaten Kanal hinzufügen, einschließlich Gäste. Mitglieder eines privaten Kanals verfügen über einen sicheren Bereich für Unterhaltungen, und wenn neue Mitglieder hinzugefügt werden, können diese alle Unterhaltungen (auch alte Unterhaltungen) in diesem privaten Kanal sehen.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>Was geschieht, wenn ein Teammitglied ein Team verlässt oder daraus entfernt wird?

Verlässt ein Teammitglied ein Team, oder wird es daraus entfernt, wird dieser Benutzer auch aus allen privaten Kanälen des Teams gelöscht. Wenn der Benutzer wieder zum Team hinzugefügt wird, muss er wieder zu den privaten Kanälen im Team hinzugefügt werden.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>Was geschieht, wenn ein Besitzer eines privaten Kanals aus einem privaten Kanal entfernt wird?

Der Besitzer eines privaten Kanals kann nicht über den Teams-Client entfernt werden, wenn er der letzte Besitzer eines oder mehrerer privater Kanäle ist.

Wenn ein privater Kanalbesitzer Ihre Organisation verlässt oder wenn er aus der Microsoft 365-Gruppe entfernt wird, die dem Team zugeordnet ist, wird ein Mitglied des privaten Kanals automatisch als privater Kanalbesitzer heraufgestuft.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>Was können Teambesitzer und Teammitglieder in einem privaten Kanal sehen?

Teambesitzer können die Namen aller privaten Kanäle in ihrem Team sehen und jeden privaten Kanal im Team löschen. (Ein gelöschter privater Kanal kann innerhalb von 30 Tagen nach dem Löschen wiederhergestellt werden). Teambesitzer können die Dateien in einem privaten Kanal oder die Unterhaltungen und die Mitgliederliste eines privaten Kanals nicht sehen, sofern sie nicht Mitglieder dieses privaten Kanals sind.

Die folgende Tabelle zeigt, wer was in einem privaten Kanal sehen kann.

|Element  |Was Teambesitzer sehen |Was Teammitglieder sehen |
|---------|---------|---------|
|Name und Beschreibung    |Alle privaten Kanäle in einem Team         |Nur die privaten Kanäle, denen Sie hinzugefügt wurden         |
|Unterhaltungen und Registerkarten     |Nur wenn sie zum privaten Kanal hinzugefügt wurden         |Nur wenn sie zum privaten Kanal hinzugefügt wurden         |
|Dateien und Inhalte    |Nur wenn sie zum privaten Kanal hinzugefügt wurden        |Nur wenn sie zum privaten Kanal hinzugefügt wurden         |
|Besitzer eines privaten Kanals    |Alle privaten Kanäle in einem Team        |Nur wenn sie zum privaten Kanal hinzugefügt wurden         |
|Zeitstempel der letzten Aktivität  |Alle privaten Kanäle in einem Team       |Nur wenn sie zum privaten Kanal hinzugefügt wurden         |

## <a name="manage-private-channels"></a>Verwalten privater Kanäle

In der folgenden Tabelle wird beschrieben, welche Aktionen Besitzer, Mitglieder und Gäste in privaten Kanälen ausführen können.

|Aktion  |Teambesitzer|Teammitglied|Teamgast|Besitzer eines privaten Kanals|Mitglied eines privaten Kanals|Gast eines privaten Kanals|
|---------|---------|---------|---------|---------|---------|---------|
|Erstellen eines privaten Kanals|Ja<sup>1</sup>|Ja<sup>1,2</sup>|Nein|–|N/V|N/V|
|Löschen eines privaten Kanals|Ja|Nein|Nein|Ja|Nein|Nein|
|Verlassen eines privaten Kanals|N/V|N/V|N/V|Ja<sup>3</sup>|Ja |Ja|
|Bearbeiten eines privaten Kanals|Nein|–|N/V|Ja|Nein|Nein|
|Gelöschte private Kanäle wiederherstellen|Ja|Nein|Nein|Ja|Nein|Nein|
|Mitglieder hinzufügen|Nein|–|N/V|Ja|Nein|Nein|
|Bearbeiten von Einstellungen|Nein|–|N/V|Ja|Nein|Nein|
|Verwalten von Registerkarten und Apps|Nein|–|Nicht zutreffend|Ja<sup>4</sup>|Ja<sup>5</sup>|Nein|

<sup>1</sup> Vorausgesetzt, dass die von Ihnen als Administrator konfigurierte Richtlinie dem Benutzer gestattet, private Kanäle zu erstellen.<br>
<sup>2</sup> Jedes Team verfügt über eine Einstellung, die Teambesitzer aktivieren oder deaktivieren können, um Teammitgliedern das Erstellen privater Kanäle zu gestatten bzw. nicht zu erlauben. Teambesitzer können jederzeit private Kanäle erstellen.<br>
<sup>3</sup> Vorausgesetzt, dass der Besitzer des privaten Kanals nicht der letzte Besitzer des Kanals ist. <br>
<sup>4</sup> Setzt voraus, dass das Team eine entsprechende App für einen privaten Kanal installiert hat.<br>
<sup>5</sup> Besitzer privater Kanäle können dies konfigurieren.

### <a name="manage-private-channel-membership-and-settings"></a>Verwalten von Mitgliedschaften und Einstellungen des privaten Kanals

Jeder private Kanal verfügt über eigene Einstellungen, beispielsweise zum Hinzufügen und Entfernen von Mitgliedern, zum Hinzufügen von Registerkarten sowie für @Erwähnungen für den gesamten Kanal. Diese Einstellungen sind unabhängig von den Einstellungen des übergeordneten Teams. Wenn ein privater Kanal erstellt wird, erbt er zunächst die Einstellungen des übergeordneten Teams. Anschließend können die Einstellungen unabhängig von den Einstellungen des übergeordneten Teams geändert werden.

Der Besitzer des privaten Kanals kann auf **Kanal verwalten** klicken und dann die Registerkarten **Mitglieder** und **Einstellungen** verwenden, um Mitglieder hinzuzufügen oder zu entfernen und Einstellungen zu bearbeiten.  

![Screenshot der Einstellungen eines privaten Kanals](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Verwalten des Lebenszyklus von privaten Kanälen

Eine Anleitung zum Verwalten des Lebenszyklus von privaten Kanälen in Ihrer Organisation finden Sie unter [Verwalten des Lebenszyklus von privaten Kanälen](private-channels-life-cycle-management.md). Hier erfahren Sie, wie Sie steuern können, ob Benutzer in Ihrer Organisation private Kanäle erstellen können, wie ein privater Kanal im Auftrag eines Teambesitzers erstellt wird, wie Sie eine Liste aller Nachrichten im privaten Kanal zu Archivierungs- und Überwachungszwecken abrufen und wie Sie andere Verwaltungsaufgaben ausführen.  

## <a name="private-channel-sharepoint-sites"></a>SharePoint-Websites im privaten Kanal

Jeder private Kanal verfügt über eine eigene SharePoint-Websitesammlung, die für die Dateifreigabe und die schnelle Bereitstellung optimiert wurde. Die separate Websitesammlung dient dazu, sicherzustellen, dass der Zugriff auf Dateien in privaten Kanälen auf Mitglieder des privaten Kanals beschränkt ist, im Gegensatz zur Teamwebsite, auf der Teambesitzer auf alle Objekte in der Websitesammlung zugreifen können. Diese Websitesammlungen werden standardmäßig mit einer Dokumentbibliothek erstellt und können über die [Benutzeroberfläche für die Websiteverwaltung](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04) auf einfache Weise in eine Websitesammlung mit vollem Funktionsumfang erweitert werden. Jede Websitesammlung wird in derselben geografischen Region wie die Websitesammlung des übergeordneten Teams erstellt. Diese Lightweight-Websites verfügen über eine benutzerdefinierte Vorlagen-ID, "TEAMCHANNEL # 0", um die Verwaltung über PowerShell und die Graph-API zu vereinfachen.  Sie werden standardmäßig im SharePoint Admin Center nicht angezeigt.

Um einer größeren Anzahl von Websitesammlungen pro Mandant unterzubringen, wurde der Grenzwert von 500.000 auf 2 Millionen erhöht. Eine Websitesammlung eines privaten Kanals synchronisiert die Datenklassifizierung und erbt Gastzugriffsberechtigungen von der Websitesammlung des übergeordneten Teams.  Die Mitgliedschaft bei den Gruppen "Besitzer" oder "Mitglied" der Websitesammlung wird mit der Mitgliedschaft des privaten Kanals innerhalb von Teams synchronisiert. Alle Änderungen an der Mitgliedschaft in den Gruppen "Besitzer" oder "Mitglied" in SharePoint Online werden innerhalb von vier Stunden automatisch auf die Mitgliedschaft im privaten Kanal zurückgesetzt. In Szenarien, in denen bestimmte Benutzer auf Dokumente aber nicht auf private Kanalnachrichten zugreifen müssen, fügen Sie die Benutzer zur Gruppe "Besucher" der Website oder einer neuen Gruppe hinzu, die von Besitzern und Mitgliedern getrennt ist.

Teams verwalten den Lebenszyklus der SharePoint-Websitesammlung für private Kanäle. Wenn die Websitesammlung außerhalb von Teams gelöscht wird, kann die Website in einem Hintergrundauftrag innerhalb von vier Stunden wiederhergestellt werden, sofern der private Kanal noch aktiv ist. Wenn die Website als gelöscht gekennzeichnet und dauerhaft gelöscht wird, erfolgt die Bereitstellung einer neuen Websitesammlung für den privaten Kanal.

Wird ein privater Kanal oder ein Team, das einen privaten Kanal enthält, wiederhergestellt, werden die Websitesammlungen darin wiederhergestellt. Wenn eine Websitesammlung eines privaten Kanals wiederhergestellt wird und das 30-Tage-Fenster für "vorläufiges Löschen" für den privaten Kanal überschritten ist, wird die Websitesammlung als eigenständige Websitesammlung ausgeführt.

## <a name="private-channel-message-compliance-records"></a>Complianceeinträge für Nachrichten in einem privaten Kanal

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Weitere Informationen zum Durchführen einer eDiscovery-Suche nach Nachrichten eines privaten Kanals finden Sie unter [eDiscovery privater Kanäle](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Überlegungen zum Zugriff in privaten Kanälen

Wird ein neues OneNote-Notizbuch in einem privaten Kanal erstellt, können zusätzliche Benutzer weiterhin Zugriff auf das Notizbuch erhalten, denn das Verhalten ist dasselbe, wie beim Teilen des Zugriff auf ein beliebiges anderes Element in einer SharePoint-Website des privaten Kanals mit einem Benutzer.

Wird einem Benutzer über SharePoint der Zugriff auf ein Notizbuch in einem privaten Kanal gewährt und der Zugriff des Benutzer aus dem Team oder privaten Kanal entfernt, kann der Benutzer weiterhin auf das Notizbuch zugreifen.

Wird ein vorhandenes Notizbuch als Registerkarte zu einem privaten Kanal hinzugefügt, wird der Zugriff auf den privaten Kanal nicht geändert. Das bedeutet:

- Nicht jeder im privaten Kanal hat standardmäßig Zugriff auf das Notizbuch. Der Grund dafür ist, dass der Benutzer möglicherweise keinen Zugriff auf den Ort hat, an dem das Notizbuch gespeichert ist, z. B. die SharePoint-Website eines anderen Teams.
- Benutzer, die keine Mitglieder des privaten Kanals sind, können das Notizbuch anzeigen.  

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Teams und Kanäle in Teams](teams-channels-overview.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Verwenden der Microsoft Graph-API zum Arbeiten mit Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
