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
description: Hier erfahren Sie, wie Sie private Kanäle in Microsoft Teams verwenden und verwalten.
ms.openlocfilehash: 45d05f2dd726b340ac79ac11810d23d00c8b3e9d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837315"
---
# <a name="private-channels-in-microsoft-teams"></a>Private Kanäle in Microsoft Teams

Private Kanäle in Microsoft Teams erstellen fokussierte Bereiche für die Zusammenarbeit in ihren Teams. Nur die Benutzer im Team, die Besitzer oder Mitglieder des privaten Kanals sind, können auf den Kanal zugreifen. Alle Personen, einschließlich Gäste, können als Mitglied eines privaten Kanals hinzugefügt werden, sofern Sie bereits Mitglieder des Teams sind.

Möglicherweise möchten Sie einen privaten Kanal verwenden, wenn Sie die Zusammenarbeit auf diejenigen beschränken möchten, die wissen müssen, oder wenn Sie die Kommunikation zwischen einer Gruppe von Personen, die einem bestimmten Projekt zugeordnet sind, erleichtern möchten, ohne ein zusätzliches Team für die Verwaltung erstellen zu müssen.

Beispielsweise ist ein privater Kanal in diesen Szenarien hilfreich:

- Eine Gruppe von Personen in einem Team möchte einen fokussierten Bereich für die Zusammenarbeit, ohne ein separates Team erstellen zu müssen.
- Eine Teilmenge der Personen in einem Team möchte, dass ein privater Kanal vertrauliche Informationen wie Budgets, Resourcing, strategische Positionierung usw. behandelt.

Ein Sperrsymbol zeigt einen privaten Kanal an. Nur Mitglieder privater Kanäle können private Kanäle sehen und daran teilnehmen, denen Sie hinzugefügt werden.

![Screenshot privater Kanäle in einem Team](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Was Sie über private Kanäle wissen müssen

Derzeit unterstützen private Kanäle Connectors und Tabs (mit Ausnahme von Stream, Planner und Formularen). Wir arbeiten an der vollständigen apps-Unterstützung für private Kanäle, einschließlich Messaging-Erweiterungen und Bots.

Jedes Team kann maximal 30 private Kanäle haben, und jeder private Kanal kann maximal 250-Mitglieder haben. Der Grenzwert für das Limit von 30 privaten Kanälen beläuft sich zusätzlich auf den 200-Standardkanal pro Team.

> [!NOTE]
> Wir fügen den privaten Kanälen kontinuierlich Funktionen hinzu, damit Sie die neuesten Informationen zu apps, Kanal Besprechungen und zur Skalierung privater Kanäle für große Teams abrufen können.

## <a name="when-to-create-a-private-channel"></a>Wann wird ein privater Kanal erstellt?

Wenn Sie feststellen möchten, ob ein privater Kanal geeignet ist, sollten Sie die folgenden Fragen zu den Personen, die zusammenarbeiten müssen, und zur Zusammenarbeit in der Zusammenarbeit Bedenken.

|Gibt es bereits ein Team, das diese Personen als Teammitglieder hat?  |Muss diese Arbeit von anderen Personen Privat aufbewahrt werden?  |Sind mehrere unterschiedliche Themen zu besprechen?  |Empfehlung  |
|---------|---------|---------|---------|
|Ja       |Ja          |Ja          |Erstellen Sie einen privaten Kanal im vorhandenen Team, oder erstellen Sie für jedes Thema dedizierte private Kanäle.         |
|Ja      |Ja         |Nein         |Erstellen Sie einen privaten Kanal im vorhandenen Team.         |
|Ja     |Nein         |Nein         |Erstellen eines Kanals im vorhandenen Team         |
|Nein     |Nein         |Nein         |In diesem Fall sollten Sie ein neues Team erstellen.         |
|Nein     |Nein         |Ja         |Wenn Sie ein neues Team erstellen, sollten Sie in Abhängigkeit von der Vertraulichkeit der einzelnen Themen für jedes Thema separate Standard-oder private Kanäle erstellen.         |
|Nein     |Ja         |Nein         |Erstellen Sie ein neues Team, oder erstellen Sie einen neuen privaten Kanal in einem vorhandenen Team.         |

Wenn ein privater Kanal erstellt wird, ist er mit dem übergeordneten Team verknüpft und kann nicht in ein anderes Team verschoben werden. Darüber hinaus können private Kanäle nicht in Standardkanäle konvertiert werden und umgekehrt.

## <a name="private-channel-creation-and-membership"></a>Erstellen und Mitgliedschaft im privaten Kanal

### <a name="who-can-create-private-channels"></a>Wer kann private Kanäle erstellen?

Standardmäßig können alle Teambesitzer oder Teammitglieder einen privaten Kanal erstellen. Gäste können Sie nicht erstellen. Die Möglichkeit zum Erstellen privater Kanäle kann auf Teamebene und auf Organisationsebene verwaltet werden:

- Auf der Registerkarte **Einstellungen** für ein Team können Teambesitzer die Möglichkeit für Mitglieder zum Erstellen privater Kanäle deaktivieren oder aktivieren.
- Als Administrator können Sie mithilfe von [Richtlinien](teams-policies.md) steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.

Die Person, die einen privaten Kanal erstellt, ist der private Kanalbesitzer und nur der private Kanalbesitzer kann Personen direkt hinzufügen oder daraus entfernen. Ein privater Kanalbesitzer kann jedes Teammitglied zu einem von ihm erstellten privaten Kanal hinzufügen, einschließlich Gästen. Mitglieder eines privaten Kanals verfügen über einen sicheren Konversations Raum, und wenn neue Mitglieder hinzugefügt werden, können Sie alle Unterhaltungen (sogar alte Konversationen) in diesem privaten Kanal sehen.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>Was passiert, wenn ein Teammitglied aus einem Team verlässt oder entfernt wird?

Wenn ein Teammitglied ein Team verlässt oder entfernt, wird dieser Benutzer auch aus allen privaten Kanälen des Teams entfernt oder entfernt. Wenn der Benutzer dem Team wieder hinzugefügt wird, muss er wieder zu den privaten Kanälen im Team hinzugefügt werden.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>Was passiert, wenn ein privater Kanalbesitzer aus einem privaten Kanal entfernt wird?

Ein privater Kanalbesitzer kann nicht über den Teams-Client entfernt werden, wenn er der letzte Besitzer eines oder mehrerer privater Kanäle ist.

Wenn ein privater Kanalbesitzer Ihre Organisation verlässt oder wenn er aus der Office 365-Gruppe entfernt wird, die dem Team zugeordnet ist, wird ein Mitglied des privaten Kanals automatisch als privater Kanalbesitzer heraufgestuft.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>Was können Teambesitzer und Teammitglieder in einem privaten Kanal sehen?

Teambesitzer können die Namen aller privaten Kanäle in Ihrem Team sehen und können auch jeden privaten Kanal im Team löschen. (Ein gelöschter privater Kanal kann innerhalb von 30 Tagen nach dem Löschen wiederhergestellt werden). Team Besitzer können die Dateien in einem privaten Kanal oder in den Unterhaltungen und in der Mitgliederliste eines privaten Kanals nicht sehen, es sei denn, Sie sind Mitglieder dieses privaten Kanals.

In der folgenden Tabelle wird angezeigt, wer was in einem privaten Kanal sehen kann.

|Element  |Der Team Besitzer kann sehen |Team Mitglieder können sehen |
|---------|---------|---------|
|Name und Beschreibung    |Alle privaten Kanäle im Team         |Nur die privaten Kanäle, denen Sie hinzugefügt werden         |
|Unterhaltungen und Registerkarten     |Nur beim Hinzufügen zum privaten Kanal         |Nur beim Hinzufügen zum privaten Kanal         |
|Dateien und Inhalte    |Nur beim Hinzufügen zum privaten Kanal        |Nur beim Hinzufügen zum privaten Kanal         |
|Privater Kanalbesitzer    |Alle privaten Kanäle im Team        |Nur beim Hinzufügen zum privaten Kanal         |
|Zeitstempel der letzten Aktivität  |Alle privaten Kanäle im Team       |Nur beim Hinzufügen zum privaten Kanal         |

## <a name="manage-private-channels"></a>Verwalten privater Kanäle

In der folgenden Tabelle wird erläutert, welche Aktionen Besitzer, Mitglieder und Gäste in privaten Kanälen ausführen können.

|Aktion  |Team Besitzer|Team Mitglied|Team Gast|Privater Kanalbesitzer|Mitglied des privaten Kanals|Privater Kanal Gast|
|---------|---------|---------|---------|---------|---------|---------|
|Privaten Kanal erstellen|Ja<sup>1</sup>|Ja<sup>1, 2</sup>|Nein|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|
|Privaten Kanal löschen|Ja|Nein|Nein|Ja|Nein|Nein|
|Privaten Kanal beurlauben|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Ja<sup>3</sup>|Ja |Ja |
|Privaten Kanal bearbeiten|Nein|Nicht zutreffend|Nicht zutreffend|Ja|Nein|Nein|
|Wiederherstellen eines gelöschten privaten Kanals|Ja|Nein|Nein|Ja|Nein|Nein|
|Hinzufügen von Mitgliedern|Nein|Nicht zutreffend|Nicht zutreffend|Ja|Nein|Nein|
|Bearbeiten von Einstellungen|Nein|Nicht zutreffend|Nicht zutreffend|Ja|Nein|Nein|
|Verwalten von Registerkarten und Apps|Nein|Nicht zutreffend|Nicht zutreffend|Ja<sup>4</sup>|Ja<sup>5</sup>|Nein|

<sup>1</sup> vorausgesetzt, die von Ihnen, dem Administrator, konfigurierte Richtlinie ermöglicht es dem Benutzer, private Kanäle zu erstellen.<br>
<sup>2</sup> jedes Team hat eine Einstellung, die Teambesitzer aktivieren oder deaktivieren können, damit Teammitglieder private Kanäle erstellen können. Team Besitzer können immer private Kanäle erstellen.<br>
<sup>3</sup> vorausgesetzt, der Besitzer des privaten Kanals ist nicht der letzte Besitzer des Kanals. <br>
<sup>4</sup> erfordert, dass das Team eine APP für einen privaten Kanal installiert hat, um Sie zu verwenden.<br>
<sup>5</sup> private Kanalbesitzer können dies konfigurieren.

### <a name="manage-private-channel-membership-and-settings"></a>Verwalten der Mitgliedschaft und Einstellungen für den privaten Kanal

Jeder private Kanal verfügt über eigene Einstellungen, einschließlich der Möglichkeit zum Hinzufügen und Entfernen von Mitgliedern, Hinzufügen von Registerkarten und @mentioning für den gesamten Kanal. Diese Einstellungen sind unabhängig von den Einstellungen des übergeordneten Teams. Wenn ein privater Kanal erstellt wird, erbt er die Einstellungen des übergeordneten Teams, wodurch dessen Einstellungen unabhängig von den Einstellungen des übergeordneten Teams geändert werden können.

Der private Kanalbesitzer kann auf **Kanal verwalten**klicken und dann die Registerkarten **Mitglieder** und **Einstellungen** verwenden, um Mitglieder hinzuzufügen oder zu entfernen und Einstellungen zu bearbeiten.  

![Screenshot der Einstellungen für den privaten Kanal](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Verwalten des Lebenszyklus von privaten Kanälen

Anleitungen zum Verwalten des Lebenszyklus privater Kanäle in Ihrer Organisation finden Sie unter [Verwalten des Lebenszyklus privater Kanäle in Teams](private-channels-life-cycle-management.md) . Hier erfahren Sie, wie Sie steuern können, ob Benutzer in Ihrer Organisation private Kanäle erstellen können, wie Sie im Auftrag eines Team Besitzers einen privaten Kanal erstellen, wie Sie eine Liste aller privaten Kanal Nachrichten zu Archivierungs-und Überwachungszwecken sowie zu anderen Verwaltungsaufgaben erhalten.  

## <a name="private-channel-sharepoint-sites"></a>Private Kanal-SharePoint-Websites

Jeder private Kanal verfügt über eine eigene SharePoint-Websitesammlung, die für die Dateifreigabe und schnelle Bereitstellung optimiert wurde. Die separate Websitesammlung dient dazu, sicherzustellen, dass der Zugriff auf private Kanaldateien nur auf Mitglieder des privaten Kanals beschränkt ist, die mit der Teamwebsite verglichen werden, auf der Teambesitzer auf alle Ressourcen in der Websitesammlung zugreifen können. Diese Websitesammlungen werden standardmäßig mit einer Dokumentbibliothek erstellt und können mithilfe der [Website Verwaltungsoberfläche](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04)problemlos auf eine vollständige Websitesammlung erweitert werden. Jede Websitesammlung wird in derselben geografischen Region wie die Websitesammlung des übergeordneten Teams erstellt. Diese Lightweight-Websites verfügen über eine benutzerdefinierte Vorlagen-ID, "TEAMCHANNEL # 0", um die Verwaltung über PowerShell und die Diagramm-API zu vereinfachen.  Sie werden im SharePoint Admin Center nicht angezeigt.

Um eine größere Anzahl von Websitesammlungen pro Mandanten aufnehmen zu können, ist der Grenzwert von 500.000 auf 2 Millionen gestiegen. Eine private Kanal-Websitesammlung synchronisiert die Datenklassifizierung und erbt die Gastzugriffs Berechtigungen aus der Websitesammlung des übergeordneten Teams.  Die Mitgliedschaft beim Besitzer der Websitesammlung und in den Mitgliedsgruppen wird mit der Mitgliedschaft des privaten Kanals in Microsoft Teams synchronisiert. Alle Änderungen an der Mitgliedschaft von Besitzer-oder Mitgliedsgruppen in SharePoint Online werden innerhalb von vier Stunden automatisch auf eine private Kanal Mitgliedschaft zurückgesetzt. In Szenarien, in denen bestimmte Benutzer auf Dokumente zugreifen müssen, ohne auf private Kanal Nachrichten zugreifen zu müssen, fügen Sie Sie der Gruppe Besucher auf der Website oder einer neuen Gruppe hinzu, die von Besitzern und Mitgliedern getrennt ist.

Teams verwaltet den Lebenszyklus der SharePoint-Websitesammlung für private Kanäle. Wenn die Websitesammlung außerhalb von Teams gelöscht wird, stellt ein Hintergrund Auftrag die Website innerhalb von vier Stunden wieder her, solange der private Kanal weiterhin aktiv ist. Wenn die Website gelöscht und schwer gelöscht wird, wird eine neue Websitesammlung für den privaten Kanal bereitgestellt.

Wenn ein privater Kanal oder ein Team, das einen privaten Kanal enthält, wiederhergestellt wird, werden die Websitesammlungen damit wiederhergestellt. Wenn eine private Kanal-Websitesammlung wiederhergestellt wird und es jenseits des 30-tägigen Soft-Delete-Fensters für den privaten Kanal liegt, fungiert die Websitesammlung als eigenständige Websitesammlung.

## <a name="private-channel-message-compliance-records"></a>Konformitätsdatensätze für private Kanal Nachrichten

Datensätze für Nachrichten, die in einem privaten Kanal gesendet wurden, werden an das Postfach aller privaten Kanalmitglieder und nicht an ein Gruppenpostfach übermittelt. Die Titel der Datensätze werden so formatiert, dass Sie angeben, von welchem privaten Kanal Sie gesendet wurden.

Weitere Informationen zum Durchführen einer eDiscovery-Suche für private Kanal Nachrichten finden Sie unter [eDiscovery privater Kanäle](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Überlegungen rund um den Zugriff in privaten Kanälen

Wenn ein neues OneNote-Notizbuch in einem privaten Kanal erstellt wird, können weitere Benutzer weiterhin auf das Notizbuch zugreifen, da das Verhalten dem Freigeben des Zugriffs auf ein beliebiges anderes Element auf einer SharePoint-Website auf einem privaten Kanal mit einem Benutzer entspricht.

Wenn einem Benutzer der Zugriff auf ein Notizbuch in einem privaten Kanal über SharePoint gewährt wird, wird durch Entfernen des Benutzers aus dem Team oder privaten Kanal der Zugriff des Benutzers auf das Notizbuch nicht entfernt.

Wenn ein vorhandenes Notizbuch einem privaten Kanal als Registerkarte hinzugefügt wird, wird der Zugriff auf den privaten Kanal nicht geändert. Dies bedeutet Folgendes:

- Nicht jeder im privaten Kanal kann standardmäßig auf das Notizbuch zugreifen. Dies liegt daran, dass Sie möglicherweise nicht auf die Stelle zugreifen können, an der das Notizbuch gehostet wird, beispielsweise die SharePoint-Website eines anderen Teams.
- Benutzer, die keine Mitglieder des privaten Kanals sind, können das Notizbuch anzeigen.  

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Teams und Kanäle in Teams](teams-channels-overview.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Verwenden der Microsoft Graph-API zum Arbeiten mit Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
