---
title: Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die gesetzliche Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams unter Verwendung des Security & Compliance Center festlegen können und welche Datenanforderungen für eine gesetzliche Aufbewahrung notwendig sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d11ae740f051d4da2a5e930193797c08451cbe7c
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121355"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
==================================================

Wenn eine angemessene Erwartung eines Rechtsstreits vorliegt, müssen Organisationen elektronisch gespeicherte Informationen (ESI) beibehalten, einschließlich der für den Fall relevanten Team-Chatnachrichten. Organisationen müssen möglicherweise alle Nachrichten, die sich auf ein bestimmtes Thema beziehen, oder für bestimmte Personen beibehalten. In diesem Artikel wird die rechtliche Aufbewahrungszeit in Microsoft Teams behandelt (um die Implementierung über den M365-Speicherplatz zu adressieren, lesen Sie [Verwalten von eDiscovery-Fällen: Platzieren von Inhaltsspeicherorten in Wartestellung](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).

> [!NOTE]
> In Feb 2020 haben wir rechtliche Aufbewahrungs-oder Aufbewahrungs Fälle auf privaten Kanälen aktiviert (private Kanal-Chats werden in Benutzerpostfächern gespeichert, normale Kanal-Chats werden in den Gruppen Postfächern dieser Teams gespeichert). Wenn für ein Benutzerpostfach bereits eine rechtliche Aufbewahrungszeit vorhanden ist, gilt die Richtlinie für den Haltebereich jetzt automatisch für private Kanal Nachrichten, die in diesem Postfach gespeichert sind. Es ist keine weitere Aktion erforderlich, damit ein Administrator diese Option aktivieren kann. Der rechtliche Halt von Dateien, die in privaten Kanälen freigegeben werden, wird ebenfalls unterstützt.

In Microsoft Teams kann ein gesamtes Team oder ausgewählte Benutzer in die Wartestellung oder in den Wartebereich gesetzt werden. Dadurch wird sichergestellt, dass alle Nachrichten, die in diesen Teams (einschließlich privater Kanäle) ausgetauscht wurden, oder Nachrichten, die von diesen Personen ausgetauscht wurden, von den Compliance-Managern oder Team Administratoren der Organisation erkannt werden.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).

So stellen Sie einen Benutzer oder ein Team in rechtlicher Wartestellung:

1. Navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). Wenn Sie einen neuen Fall erstellen, haben Sie die Möglichkeit, Postfächer oder Websites in Wartestellung zu platzieren.
1. Wechseln Sie zu eDiscovery oder Advanced eDiscovery, und erstellen Sie einen Fall, indem Sie auf "+ Fall erstellen" klicken. Nachdem der Fall erstellt wurde, öffnen Sie ihn.
![Microsoft Teams-eDiscovery-Registerkarte mit der Schaltfläche "Groß-/Kleinschreibung erstellen" ausgewählt.](media/LegalHold1.png)
1. Wechseln Sie im oberen Menü zum Abschnitt "haltebereiche", und klicken Sie auf "+ erstellen", um einen Haltebereich zu erstellen. Wenn ein Benutzer oder ein Team angehalten wird, speichert alle Nachrichten, die von diesen Benutzern oder Nachrichten ausgetauscht werden, wenn Sie einen neuen Fall erstellen, wird Ihnen die Möglichkeit angezeigt, Postfächer oder Websites in Wartestellung zu platzieren.
![Ein Bild, in dem die Registerkarte "haltebereiche" ausgewählt ist, und die Schaltfläche "erstellen" darunter](media/LegalHold2.png)
    1. **Nennen Sie Ihren halte**Bereich. Wählen Sie einen beschreibenden und eindeutigen Namen für den Haltebereich aus, den Sie erstellen möchten.
![Dieser Screenshot zeigt die Registerkarte Name Ihres haltebereichs, in der Sie einen Namen und eine Beschreibung für den zu erstellden Haltebereich eingeben können.](media/LegalHold3.png)
    1. **Wählen Sie Standort aus**. Wählen Sie aus, ob der Haltebereich auf einen Benutzer oder ein gesamtes Team angewendet werden soll (der Haltebereich kann jetzt nicht auf einzelne Kanäle angewendet werden). Hinweis: Wenn ein Benutzer angehalten wird, werden alle Nachrichten in Wartestellung gehalten, einschließlich der von Ihnen in einem 1:1-Chat gesendeten, 1: viele oder Gruppen-Chats oder einer Kanal Unterhaltung (einschließlich privater Kanäle).
    ![Hier befindet sich der Abschnitt "Speicherorte auswählen", in dem Sie einen neuen Haltebereich erstellen können, in dem Sie entscheiden können, welche M365-Optionen, einschließlich Microsoft Teams, auf die Sie den Haltebereich anwenden möchten.](media/LegalHold4.png)
    1. **Erstellen einer Abfrage** Sie können den Haltebereich anpassen, wenn Sie mehr Granularität in der Richtlinie halten möchten. So können Sie beispielsweise Stichwörter angeben, nach denen Sie suchen, oder Sie können weitere Bedingungen hinzufügen, die erfüllt sein müssen, damit der Haltebereich wirksam wird.
    1. **Überprüfen Sie Ihre Einstellungen** , bevor Sie Sie in Ihrer Organisation veröffentlichen.

Nachdem der rechtliche Aufbewahrungs Rahmen festgesetzt wurde, können Sie nach dem eDiscovery-Artikel von [Teams](eDiscovery-investigation.md) alle Inhalte ermitteln, die von einer Aufbewahrungsrichtlinie aufbewahrt werden.

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in Wartestellung gesetzt wird, bleiben alle Nachrichten-Kopien erhalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal gepostet und dann die Nachricht geändert hat, werden beide Kopien der Nachricht in einem Warteschleife-Szenario beibehalten. Ohne den rechtlichen Aufbewahrungs Status wird nur die neueste Nachricht beibehalten.

Als hilfreiche Anleitung können Sie anhand der nachstehenden Tabelle verstehen, was auf der Grundlage der Datenanforderungen in den rechtlichen Aufbewahrungsbereich gesetzt werden muss:

|Szenario  |Was muss aufbewahrt werden  |
|---------|---------|
|**Microsoft Teams Chat-Inhalte von einem Benutzer (in 1:1-Chats, 1: viele oder Gruppen-Chats, private Kanal Unterhaltungen usw.)**     |Benutzerpostfächer         |
|**Microsoft Teams-Kanal-Chats (ohne private Kanäle)**    |Für das Team verwendete Gruppenpostfach         |
|**Microsoft Teams-Inhalte (z. b. wiki, Dateien)**     |Vom Team verwendete SharePoint-Site         |
|**Microsoft Teams-private Kanaldateien**     |Dedizierte private Kanal-SharePoint-Website     |
|**Privater Inhalt des Benutzers**     |OneDrive for Business-Site des Benutzers         |

> [!NOTE]
> Wenn Sie die Kommunikation in privaten Kanälen beibehalten möchten, müssen Sie die Benutzerpostfächer (Private Channel-Benutzer) in Wartestellung setzen, und wenn Sie das eDiscovery-Tool zum Suchen verwenden, sollten Sie im Postfach dieses Benutzers suchen. Wie bereits erwähnt, werden private Kanal-Chats in Benutzerpostfächern gespeichert, nicht im Gruppenpostfach eines Teams.

Wenn Sie weitere Informationen zu diesem Thema für nicht-Teams-Bereiche in M365 lesen möchten, sollten Sie [eDiscovery-Fälle verwalten überprüfen: Platzieren von Inhaltsspeicherorten in Wartestellung](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).
