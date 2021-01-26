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
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980449"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
==================================================

Wenn eine angemessene Erwartung eines Rechtsstreitigkeitens besteht, müssen Organisationen elektronisch gespeicherte Informationen (ESI) beibehalten, einschließlich Teams-Chatnachrichten, die für den Fall relevant sind. Organisationen müssen möglicherweise alle Nachrichten im Zusammenhang mit einem bestimmten Thema oder für bestimmte Personen beibehalten. Dieser Artikel behandelt die gesetzliche In-Haltebereich-Setzung in Microsoft Teams (Informationen zur Implementierung von Haltebereichs für den gesamten M365-Bereich finden Sie unter "Verwalten von [eDiscovery-Fällen:](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)In-Halten von Inhaltsspeicherorten".)

> [!NOTE]
> Im Februar 2020 haben wir die gesetzliche Bzw. Fallspeicherung für private Kanäle aktiviert (Chats privater Kanäle werden in Benutzerpostfächern gespeichert, normale Kanalchats werden im Gruppenpostfach eines Teams gespeichert). Wenn für ein Benutzerpostfach bereits ein gesetzliches Haltefach aktiviert ist, gilt die Halterichtlinie jetzt automatisch für Nachrichten privater Kanäle, die in diesem Postfach gespeichert sind. Es ist keine weitere Maßnahme erforderlich, damit ein Administrator diese Aktion aktivieren kann. Das gesetzliche Speichern von Dateien, die in privaten Kanälen freigegeben wurden, wird ebenfalls unterstützt.

Innerhalb von Microsoft Teams kann ein gesamtes Team oder ausgewählte Benutzer in einen Halteraum oder eine gesetzliche Schleife setzen. Dadurch wird sichergestellt, dass alle Nachrichten, die in diesen Teams ausgetauscht wurden (einschließlich privater Kanäle), oder von diesen Personen ausgetauschte Nachrichten von den Compliancemanagern oder Teamadministratoren der Organisation ermittelt werden können.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).

So setzen Sie einen Benutzer oder ein Team in einen gesetzlichen Halteraum

1. Navigieren Sie zum [Security & Compliance Center.](https://go.microsoft.com/fwlink/?linkid=854628) Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

2. Wechseln Sie zu eDiscovery oder Advanced eDiscovery, und erstellen Sie einen Fall, indem Sie auf "Fall erstellen" klicken. Sobald der Fall erstellt wurde, öffnen Sie ihn.

   > [!div class="mx-imgBorder"]
   > ![Die Registerkarte "Microsoft Teams eDiscovery" ist ausgewählt und zeigt die Schaltfläche "Fall erstellen" an.](media/LegalHold1.png)

3. Wechseln Sie im oberen Menü zum Abschnitt "Haltebereich", und klicken Sie auf "+ Erstellen", um einen Haltebereich zu erstellen. Wenn Sie einen Benutzer oder ein Team in den Halteraum setzen, werden alle von diesen Benutzern ausgetauschten Nachrichten oder Nachrichten erspart. Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

   > [!div class="mx-imgBorder"]
   > ![Abbildung der ausgewählten Registerkarte "Halte halte", darunter die Schaltfläche "Erstellen".](media/LegalHold2.png)

   1. **Geben Sie Dem in-Halten einen Namen.** Wählen Sie einen aussagekräftigen und eindeutigen Namen für den Halteraum aus, den Sie erstellen möchten.

      > [!div class="mx-imgBorder"]
      > ![Dieser Screenshot zeigt die Registerkarte "Halten benennen", auf der Sie einen Namen und eine Beschreibung für den halteraum eingeben können, den Sie erstellen.](media/LegalHold3.png)

    2. **Wählen Sie den Speicherort aus.** Wählen Sie aus, ob der Halteraum auf einen Benutzer oder ein gesamtes Team angewendet werden soll (der Halteraum kann vorerst nicht für einzelne Kanäle angewendet werden). Hinweis: Wenn ein Benutzer im Halteschleifenfenster ist, werden alle nachrichten im Halteraum angezeigt, einschließlich der Nachrichten, die er in einem 1:1-Chat, einem 1:n- oder Gruppenchat oder einer Kanalunterhaltung (einschließlich privater Kanäle) gesendet hat.
  
       > [!div class="mx-imgBorder"]
       > ![Hier haben wir den Abschnitt "Speicherorte auswählen" von "Neuen Haltebereich erstellen", in dem Sie entscheiden können, für welche M365-Optionen, einschließlich Microsoft Teams, der Haltebereich gelten soll.](media/LegalHold4.png)

    3. **"Abfrage erstellen" aus.** Sie können den Halteraum anpassen, wenn Sie mehr Granularität in der Halterichtlinie wünschen. Sie können z. B. Schlüsselwörter angeben, nach der sie suchen sollen, oder sie können weitere Bedingungen hinzufügen, die erfüllt sein müssen, damit der Halte hold wirksam wird.
    
    4. **Überprüfen Sie Ihre Einstellungen,** bevor Sie sie in Ihrer Organisation veröffentlichen.

Nachdem die gesetzliche Stellrichtlinie festgelegt wurde, können Sie alle Inhalte, die von einer Halterichtlinie aufbewahrt werden, im Anschluss an [den Teams eDiscovery-Artikel](eDiscovery-investigation.md) ermitteln.

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in den Halteraum gesetzt wird, werden alle Nachrichtenkopien beibehalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal gepostet und dann geändert hat, bleiben in einem Halteszenario beide Kopien der Nachricht erhalten. Ohne gesetzliche In-Place-Benachrichtigung wird nur die neueste Nachricht aufbewahrt.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Inhaltsorte, die für die Erhaltung von Inhalten in Teams gesetzlich in einen Halteraum zu setzen sind

Als hilfreiches Handbuch können Sie die folgende Tabelle verwenden, um zu verstehen, welcher Inhaltsspeicherort (z. B. ein Postfach oder eine Website) in einen gesetzlichen Halteraum verschoben werden soll, um verschiedene Arten von Teaminhalten zu erhalten.

|Szenario  |Inhaltsspeicherort  |
|---------|---------|
|Teamchats für einen Benutzer (z. B. 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen)     |Benutzerpostfach.         |
|Chats in Teams-Kanälen (mit Ausnahme privater Kanäle)    |Gruppenpostfach, das für das Team verwendet wird.         |
|Inhalt von Dateien in Teams (z. B. Wiki-Inhalt und -Dateien)     |Die vom Team verwendete SharePoint-Website.         |
|Dateien privater Kanäle in Teams     |Dedizierte SharePoint-Website für private Kanäle.     |
|Private Inhalte des Benutzers     |Das OneDrive for #A0 des Benutzers.         |
|Karteninhalte in Chats|Benutzerpostfach für 1:1-Chats, 1:N-Gruppenchats und Unterhaltungen in privaten Kanälen oder Gruppenpostfach für Karteninhalte in Kanalnachrichten. Weitere Informationen finden Sie im Abschnitt "Beibehalten des Karteninhalts" in ["Erstellen eines eDiscovery-Haltebereichs".](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Um die Kommunikation in privaten Kanälen zu erhalten, müssen Sie die Benutzerpostfächer (Benutzer privater Kanäle) in den Halteraum setzen, und wenn Sie das eDiscovery-Tool für die Suche verwenden, sollten Sie im Postfach dieses Benutzers suchen. Wie bereits erwähnt, werden Chats privater Kanäle in Benutzerpostfächern und nicht in Gruppenpostfächern eines Teams gespeichert.

Weitere Informationen zu diesem Thema für Nicht-Teams-Bereiche in Microsoft 365 finden Sie unter "Verwalten von [eDiscovery-Fällen:](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)In-Haltebereich für Inhaltspositionen".
