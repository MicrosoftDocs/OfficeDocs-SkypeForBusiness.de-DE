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
ms.openlocfilehash: 3e52b10f0a7a8dd3ac67f7a2c15b9d1e082186ab
ms.sourcegitcommit: dba7984f899f8921b462a56d158fa0a1cc2c2a8b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929291"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
==================================================

Wenn eine angemessene Erwartung von Rechtsstreitigkeiten vorliegt, müssen Organisationen elektronisch gespeicherte Informationen (elektronisch gespeicherte Informationen, ESI) beibehalten, einschließlich Teams Chatnachrichten, die für den Fall relevant sind. Organisationen müssen möglicherweise alle Nachrichten im Zusammenhang mit einem bestimmten Thema oder für bestimmte Personen beibehalten. Dieser Artikel behandelt den gesetzlichen Haltebereich in Microsoft Teams (Informationen zum Adressieren der Implementierung von Haltebereichs im gesamten M365-Raum finden Sie unter Verwalten von [eDiscovery-Fällen:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Platzieren von Inhaltsspeicherorten im Haltebereich.).

> [!NOTE]
> Im Februar 2020 haben wir einen gesetzlichen Halte- oder Fallspeicher für private Kanäle aktiviert (Chats privater Kanäle werden in Benutzerpostfächern gespeichert, normale Kanalchats werden im Gruppenpostfach eines Teams gespeichert). Wenn für ein Benutzerpostfach bereits ein gesetzlicher Halteraum besteht, gilt die Halterichtlinie jetzt automatisch für Nachrichten privater Kanäle, die in diesem Postfach gespeichert sind. Es ist keine weitere Maßnahme erforderlich, damit ein Administrator dies aktivieren kann. Das gesetzliche Speichern von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

Innerhalb Microsoft Teams kann ein gesamtes Team oder ausgewählte Benutzer in einen Halteraum oder gesetzlichen Halteraum setzen. Dadurch wird sichergestellt, dass alle Nachrichten, die in diesen Teams ausgetauscht wurden (einschließlich privater Kanäle), oder nachrichten, die von diesen Personen ausgetauscht wurden, von den Compliance-Managern der Organisation oder von den Teams können.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).
> Benachrichtigungen, die in einem Aktivitätsfeed gesendet werden, können nicht gesetzlich in den Halteraum setzen werden.

So setzen Sie einen Benutzer oder ein Team in einen gesetzlichen Halteraum

1. Navigieren Sie zum [Security & Compliance Center.](https://go.microsoft.com/fwlink/?linkid=854628) Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

2. Wechseln Sie zu eDiscovery oder Advanced eDiscovery erstellen Sie einen Fall, indem Sie auf "Fall erstellen" klicken. Sobald der Fall erstellt wurde, öffnen Sie ihn.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Teams Registerkarte "eDiscovery" mit der Schaltfläche "Fall erstellen" ausgewählt.](media/LegalHold1.png)

3. Wechseln Sie im oberen Menü zum Abschnitt "Haltebereich", und klicken Sie auf "+ Erstellen", um einen Haltebereich zu erstellen. Wenn Sie einen Benutzer oder ein Team in den Halteraum setzen, werden alle von diesen Benutzern ausgetauschten Nachrichten oder Nachrichten erspart. Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

   > [!div class="mx-imgBorder"]
   > ![Abbildung der ausgewählten Registerkarte "Halte halte", darunter die Schaltfläche "Erstellen".](media/LegalHold2.png)

   1. **Nennen Sie den Halte hold**. Wählen Sie einen aussagekräftigen und eindeutigen Namen für den Halteraum aus, den Sie erstellen möchten.

      > [!div class="mx-imgBorder"]
      > ![Dieser Screenshot zeigt die Registerkarte "Halten benennen", auf der Sie einen Namen und eine Beschreibung für den von Ihnen erstellten Halteraum eingeben können.](media/LegalHold3.png)

    2. **Wählen Sie den Speicherort aus.** Wählen Sie aus, ob der Halte hold auf einen Benutzer oder ein gesamtes Team angewendet werden soll (der Halte hold kann vorerst nicht auf einzelne Kanäle angewendet werden). Hinweis: Wenn ein Benutzer im Halteraum ist, werden alle seine Nachrichten im Halteraum bleiben, einschließlich der Nachrichten, die er in einem 1:1-Chat, in einem 1:n-Chat oder in einer Gruppenunterhaltung oder in einer Kanalunterhaltung (einschließlich privater Kanäle) gesendet hat.
  
       > [!div class="mx-imgBorder"]
       > ![Hier haben wir den Abschnitt Speicherorte auswählen unter Neuen Haltebereich erstellen, in dem Sie entscheiden können, für welche M365-Optionen , einschließlich Microsoft Teams, der Haltebereich gelten soll.](media/LegalHold4.png)

    3. **Abfrage erstellen**. Sie können den Halteraum anpassen, wenn Sie eine präzisere Darstellung der Halterichtlinie wünschen. Sie können z. B. Schlüsselwörter angeben, nach der suchen soll, oder sie können weitere Bedingungen hinzufügen, die erfüllt sein müssten, damit der Halte in Kraft tritt.
    
    4. **Überprüfen Sie Ihre Einstellungen,** bevor Sie sie in Ihrer Organisation veröffentlichen.

Nachdem die gesetzliche Stellrichtlinie festgelegt wurde, können Sie alle Inhalte ermitteln, die durch eine Halterichtlinie aufbewahrt werden, indem Sie Teams [eDiscovery-Artikel](eDiscovery-investigation.md) folgen.

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in den Halteraum gesetzt wird, bleiben alle Nachrichtenkopien erhalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal gepostet und dann geändert hat, bleiben in einem Haltefallszenario beide Kopien der Nachricht erhalten. Ohne gesetzliche In-Place-Sitzung bleibt nur die neueste Nachricht erhalten.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Inhaltsorte, die für die Erhaltung ihrer Inhalte gesetzlich Teams werden müssen

Als hilfreiches Handbuch können Sie die folgende Tabelle verwenden, um zu verstehen, welcher Inhaltsspeicherort (z. B. ein Postfach oder eine Website) in einen gesetzlichen Halteraum verschoben werden muss, um unterschiedliche Arten von Inhalten Teams erhalten.

|Szenario  |Inhaltsspeicherort  |
|---------|---------|
|Teams Chats für einen Benutzer (z. B. 1:1-Chats, 1:N-Gruppenchats und Unterhaltungen in privaten Kanälen)     |Benutzerpostfach.         |
|Teams von Kanalchats (ausgenommen private Kanäle)    |Gruppenpostfach, das für das Team verwendet wird.         |
|Teams von Dateiinhalten (z. B. Wiki-Inhalt und -Dateien)     |SharePoint, die vom Team verwendet wird.         |
|Teams privater Kanaldateien     |Dedizierte SharePoint für private Kanäle.     |
|Private Inhalte des Benutzers     |Das Konto des OneDrive for Business Kontos.         |
|Karteninhalte in Chats|Benutzerpostfach für 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen oder Gruppenpostfach für Karteninhalte in Kanalnachrichten. Weitere Informationen finden Sie unter Erstellen eines eDiscovery-Haltebereichs im Abschnitt "Beibehalten von [Karteninhalten".](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Um die Kommunikation in privaten Kanälen zu bewahren, müssen Sie die Benutzerpostfächer (Benutzer privater Kanäle) in den Halteraum setzen, und wenn Sie das eDiscovery-Tool für die Suche verwenden, sollten Sie das Postfach dieses Benutzers durchsuchen. Wie bereits erwähnt, werden Chats in privaten Kanälen in Benutzerpostfächern und nicht in Gruppenpostfächern eines Teams gespeichert.

Weitere Informationen zu diesem Thema für nicht Teams-Bereiche in Microsoft 365 finden Sie unter Verwalten von [eDiscovery-Fällen:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Platzieren von Inhaltspositionen im Haltebereich.
