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
ms.openlocfilehash: ace4098b56539408e8c29e5d16e43c8ae255f372
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013349"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams

Wenn eine angemessene Erwartung von Rechtsstreitigkeiten besteht, müssen Organisationen elektronisch gespeicherte Informationen (ESI) beibehalten, einschließlich Teams-Chatnachrichten, die für den Fall relevant sind. Organisationen müssen möglicherweise alle Nachrichten im Zusammenhang mit einem bestimmten Thema oder für bestimmte Personen beibehalten. Dieser Artikel behandelt die gesetzliche In-Halten-In-Halten-In-Halten in Microsoft Teams. Informationen zum In-Hand-Halten von Inhalten in Microsoft 365 finden Sie unter [Erstellen eines eDiscovery-Halteraums.](/microsoft-365/compliance/create-ediscovery-holds)

> [!NOTE]
> Im Februar 2020 haben wir die gesetzliche Erkung für private Kanäle aktiviert. Chats in privaten Kanälen werden in Benutzerpostfächern gespeichert, während normale Kanalchats im Gruppenpostfach von Teams gespeichert werden. Wenn für ein Benutzerpostfach bereits ein gesetzlicher Halteraum besteht, gilt die Halterichtlinie jetzt automatisch für Nachrichten privater Kanäle, die in diesem Postfach gespeichert sind. Es ist keine weitere Maßnahme erforderlich, damit ein Administrator dies aktivieren kann. Das gesetzliche Speichern von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

In Microsoft Teams kann ein gesamtes Team oder ausgewählte Benutzer gesetzlich in einen Halteraum setzen werden. Dadurch wird sichergestellt, dass alle in diesen Teams ausgetauschten Nachrichten (einschließlich privater Kanäle) oder von diesen Personen ausgetauschten Nachrichten von den Compliance-Managern oder Teams-Administratoren der Organisation ermittelt werden können.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).
> Im Aktivitätsfeed gesendete Benachrichtigungen können nicht im Halteraum platziert werden.

So setzen Sie einen Benutzer oder ein Team in einen Core eDiscovery-Fall in einen gesetzlichen Haltebereich

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com). Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

2. Wechseln Sie zu **eDiscovery**  >  **Core,** und erstellen Sie einen Fall, indem Sie auf **Fall erstellen klicken.** Öffnen Sie den Fall, nachdem er erstellt wurde.
  
   ![Die Registerkarte "Microsoft Teams eDiscovery" ist ausgewählt und zeigt die Schaltfläche "Fall erstellen" an.](media/LegalHold1.png)

   > [!NOTE]
   > Sie können einen Benutzer auch in einen Halteraum setzen, der einem Advanced eDiscovery-Fall zugeordnet ist. Weitere Informationen finden Sie unter [Verwalten von Halte in der erweiterten eDiscovery.](/microsoft-365/compliance/managing-holds)

3. Wechseln Sie im oberen **Menü** zur Registerkarte Halte halte, und klicken Sie **auf Erstellen,** um einen Haltepunkt zu erstellen. Wenn Sie einen Benutzer oder ein Team in den Halteraum setzen, bleiben alle von diesen Benutzern oder Nachrichten ausgetauschten Nachrichten erhalten. Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

   ![Abbildung der ausgewählten Registerkarte "Halte halte", darunter die Schaltfläche "Erstellen".](media/LegalHold2.png)
    
    1. **Nennen Sie den Halte hold**. Wählen Sie einen aussagekräftigen und eindeutigen Namen für den Halteraum aus, den Sie erstellen möchten.
  
       ![Dieser Screenshot zeigt die Registerkarte "Halten benennen", auf der Sie einen Namen und eine Beschreibung für den von Ihnen erstellten Halteraum eingeben können.](media/LegalHold3.png)

    1. **Wählen Sie den Speicherort aus.** Wählen Sie aus, ob der Halte hold auf einen Benutzer oder ein gesamtes Team angewendet werden soll (der Halte hold kann vorerst nicht auf einzelne Kanäle angewendet werden). Hinweis: Wenn ein Benutzer in der Warteschleife ist, werden alle seine Nachrichten im Halteraum bleiben, einschließlich aller Nachrichten, die er in einem 1:1-Chat, in einem 1:n-Chat oder in einer Gruppenunterhaltung oder in einer Kanalunterhaltung (einschließlich privater Kanäle) gesendet hat.
    ![Hier haben wir den Abschnitt Speicherorte auswählen unter Neuen Haltebereich erstellen, in dem Sie entscheiden können, für welche M365-Optionen (einschließlich Microsoft Teams) der Haltebereich gelten soll.](media/LegalHold4.png)

    2. **Abfrage erstellen**. Sie können den Halteraum anpassen, wenn Sie eine präzisere Darstellung der Halterichtlinie wünschen. Sie können z. B. Schlüsselwörter angeben, nach der suchen soll, oder sie können weitere Bedingungen hinzufügen, die erfüllt sein müssten, damit der Halte in Kraft tritt.
    
    3. **Überprüfen Sie ihre Einstellungen,** bevor Sie den halte in-/halten.

Nachdem die gesetzliche Schutzrichtlinie erstellt wurde, können Sie die durch eine Halterichtlinie aufbewahrten Inhalte durchsuchen. Weitere Informationen finden Sie unter [Durchführen einer eDiscovery-Untersuchung in Teams.](eDiscovery-investigation.md)

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in den Halteraum gesetzt wird, bleiben alle Nachrichtenkopien erhalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal gepostet und dann geändert hat, bleiben in einem Haltefallszenario beide Kopien der Nachricht erhalten. Ohne gesetzliche In-Place-Sitzung bleibt nur die neueste Nachricht erhalten.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Inhaltsorte, die gesetzlich in eine Halteschleife setzen müssen, um Teams-Inhalte zu erhalten

Als hilfreiches Handbuch können Sie die folgende Tabelle verwenden, um zu verstehen, welcher Inhaltsspeicherort (z. B. ein Postfach oder eine Website) in einen gesetzlichen Halteraum verschoben werden muss, um verschiedene Arten von Teams-Inhalten zu erhalten.

|Szenario  |Inhaltsspeicherort  |
|---------|---------|
|Teams-Chats für einen Benutzer (z. B. 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen)     |Benutzerpostfach.         |
|Teams-Kanalchats (ausgenommen private Kanäle)    |Gruppenpostfach, das für das Team verwendet wird.         |
|Teams-Dateiinhalte (z. B. Wiki-Inhalte und -Dateien)     |SharePoint-Website, die vom Team verwendet wird.         |
|Dateien in privaten Teams-Kanälen     |Dedizierte SharePoint-Website für private Kanäle.     |
|Private Inhalte des Benutzers     |Das OneDrive for Business-Konto des Benutzers.         |
|Karteninhalte in Chats|Benutzerpostfach für 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen oder Gruppenpostfach für Karteninhalte in Kanalnachrichten. Weitere Informationen finden Sie unter Erstellen eines eDiscovery-Haltebereichs im Abschnitt "Beibehalten von [Karteninhalten".](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)|


> [!NOTE]
> Um die Kommunikation in privaten Kanälen zu bewahren, müssen Sie die Benutzerpostfächer (Benutzer privater Kanäle) in den Halteraum setzen, und wenn Sie das eDiscovery-Tool für die Suche verwenden, sollten Sie das Postfach dieses Benutzers durchsuchen. Wie bereits erwähnt, werden Chats in privaten Kanälen in Benutzerpostfächern und nicht in Gruppenpostfächern eines Teams gespeichert.

Wenn Sie weitere Informationen zu diesem Thema für Nicht-Teams-Bereiche in Microsoft 365 lesen möchten, sollten Sie Verwalten von [eDiscovery-Fällen lesen:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Inhaltsorte in den Haltebereich setzen.
