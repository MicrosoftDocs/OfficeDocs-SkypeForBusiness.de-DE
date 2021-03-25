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
ms.openlocfilehash: 9f2f269d75a7bf8bd97165329d2ae6b006b940f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112301"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
==================================================

Wenn eine angemessene Erwartung von Rechtsstreitigkeiten besteht, müssen Organisationen elektronisch gespeicherte Informationen (ESI) beibehalten, einschließlich Teams-Chatnachrichten, die für den Fall relevant sind. Organisationen müssen möglicherweise alle Nachrichten im Zusammenhang mit einem bestimmten Thema oder für bestimmte Personen beibehalten. Dieser Artikel behandelt den rechtlichen Haltebereich in Microsoft Teams (Informationen zur Implementierung des Haltebereichs im gesamten M365-Bereich finden Sie unter [Verwalten von eDiscovery-Fällen:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Platzieren von Inhaltsspeicherorten im Haltebereich.).

> [!NOTE]
> Im Februar 2020 haben wir den rechtlichen Halte- oder Fallspeicher für private Kanäle aktiviert (Chats privater Kanäle werden in Benutzerpostfächern gespeichert, normale Kanalchats werden im Gruppenpostfach eines Teams gespeichert). Wenn bereits ein rechtlicher Halteraum für ein Benutzerpostfach vorhanden ist, gilt die Halterichtlinie jetzt automatisch für Nachrichten im privaten Kanal, die in diesem Postfach gespeichert sind. Ein Administrator muss diese Aktion nicht mehr aktivieren. Der rechtliche Halteraum von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

In Microsoft Teams kann ein ganzes Team oder ausgewählte Benutzer in den Halte- oder Rechtsraum bzw. in den Halteraum bzw. in den halte ich ihn ein. Dadurch wird sichergestellt, dass alle Nachrichten, die in diesen Teams ausgetauscht wurden (einschließlich privater Kanäle) oder von diesen Personen ausgetauschte Nachrichten von den Compliancemanagern oder Teamsadministratoren der Organisation ermittelt werden können.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).

So setzen Sie einen Benutzer oder ein Team in einen rechtlichen Halteraum:

1. Navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites im Halteraum zu platzieren.

2. Wechseln Sie zu eDiscovery oder Advanced eDiscovery, und erstellen Sie einen Fall, indem Sie auf "Fall erstellen" klicken. Nachdem der Fall erstellt wurde, öffnen Sie ihn.

   > [!div class="mx-imgBorder"]
   > ![Die Registerkarte Microsoft Teams eDiscovery ist ausgewählt und zeigt die Schaltfläche Fall erstellen an.](media/LegalHold1.png)

3. Wechseln Sie im oberen Menü zum Abschnitt "Haltebereich", und klicken Sie auf "+ Erstellen", um einen Haltebereich zu erstellen. Wenn Sie einen Benutzer oder ein Team in den Halteraum setzen, werden alle von diesen Benutzern ausgetauschten Nachrichten oder Nachrichten speichert. Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites im Halteraum zu platzieren.

   > [!div class="mx-imgBorder"]
   > ![Ein Bild mit der ausgewählten Registerkarte Halte hält und darunter die Schaltfläche Erstellen.](media/LegalHold2.png)

   1. **Benennen Sie Ihren Halteraum**. Wählen Sie einen aussagekräftigen und eindeutigen Namen für den Halteraum aus, den Sie erstellen möchten.

      > [!div class="mx-imgBorder"]
      > ![Dieser Screenshot zeigt die Registerkarte Halteregistername, auf der Sie einen Namen und eine Beschreibung für den halte, den Sie erstellen, eingeben können.](media/LegalHold3.png)

    2. **Wählen Sie Speicherort aus.** Wählen Sie aus, ob der Halteraum auf einen Benutzer oder ein gesamtes Team angewendet werden soll (der Halteraum kann vorerst nicht auf einzelne Kanäle angewendet werden). Hinweis: Wenn ein Benutzer im Halteraum ist, werden alle nachrichten im Halteraum angezeigt, einschließlich der Nachrichten, die er in einem 1:1-Chat, einem 1:n- oder Gruppenchat oder einer Kanalunterhaltung (einschließlich privater Kanäle) gesendet hat.
  
       > [!div class="mx-imgBorder"]
       > ![Hier finden Sie den Abschnitt Speicherorte auswählen unter Erstellen eines neuen Haltebereichs, in dem Sie entscheiden können, für welche M365-Optionen, einschließlich Microsoft Teams, der Haltebereich gelten soll.](media/LegalHold4.png)

    3. **Abfrage erstellen**. Sie können den Halteraum anpassen, wenn Sie mehr Granularität in der Halterichtlinie wünschen. Sie können beispielsweise Schlüsselwörter angeben, nach deren Suchen Sie suchen möchten, oder Sie können weitere Bedingungen hinzufügen, die erfüllt sein müssen, damit der Halteraum wirksam wird.
    
    4. **Überprüfen Sie Ihre Einstellungen,** bevor Sie sie in Ihrer Organisation veröffentlichen.

Nachdem der rechtliche Halteraum festgelegt wurde, können Sie nach dem [Artikel Teams eDiscovery](eDiscovery-investigation.md) alle Inhalte entdecken, die von einer Halterichtlinie aufbewahrt werden.

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in den Halteraum gesetzt wird, werden alle Nachrichtenkopien beibehalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal gepostet und die Nachricht dann geändert hat, bleiben in einem Halteszenario beide Kopien der Nachricht erhalten. Ohne den gesetzlichen Halteraum bleibt nur die neueste Nachricht erhalten.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Inhaltsstandorte, die in den gesetzlichen Halteraum zum Beibehalten von Teams-Inhalten einsortieren werden

Als hilfreiche Anleitung können Sie die folgende Tabelle verwenden, um zu verstehen, welchen Inhaltsspeicherort (z. B. ein Postfach oder eine Website) sie in einen rechtlichen Halteraum setzen müssen, um verschiedene Arten von Teams-Inhalten zu erhalten.

|Szenario  |Inhaltsspeicherort  |
|---------|---------|
|Teams-Chats für einen Benutzer (z. B. 1:1-Chats, 1:N-Gruppenchats und Unterhaltungen im privaten Kanal)     |Benutzerpostfach.         |
|Chats im Teams-Kanal (ohne private Kanäle)    |Gruppenpostfach, das für das Team verwendet wird.         |
|Dateiinhalte von Teams (z. B. Wiki-Inhalte und -Dateien)     |SharePoint-Website, die vom Team verwendet wird.         |
|Dateien des privaten Teamskanals     |Dedizierte SharePoint-Website für private Kanäle.     |
|Private Inhalte des Benutzers     |Das OneDrive for #A0 des Benutzers.         |
|Karteninhalte in Chats|Benutzerpostfach für 1:1-Chats, 1:N-Gruppenchats und Unterhaltungen im privaten Kanal oder Gruppenpostfach für Karteninhalte in Kanalnachrichten. Weitere Informationen finden Sie im Abschnitt "Karteninhalt beibehalten" unter [Erstellen eines eDiscovery-Haltebereichs.](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Wenn Sie die Kommunikation in privaten Kanälen beibehalten möchten, müssen Sie die Benutzerpostfächer (Benutzer des privaten Kanals) in den Halteraum setzen, und wenn Sie das eDiscovery-Tool zum Suchen verwenden, sollten Sie im Postfach dieses Benutzers suchen. Wie bereits erwähnt, werden Chats im privaten Kanal in Benutzerpostfächern und nicht in Gruppenpostfächern eines Teams gespeichert.

Wenn Sie dieses Thema für Nicht-Teams-Bereiche in Microsoft 365 weiter lesen möchten, lesen Sie [Verwalten von eDiscovery-Fällen:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Platzieren von Inhaltsstandorten im Haltebereich.