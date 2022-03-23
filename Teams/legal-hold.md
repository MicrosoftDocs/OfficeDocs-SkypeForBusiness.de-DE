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
description: Erfahren Sie, wie Sie Microsoft Teams Benutzer oder Team mithilfe der -Microsoft 365 Compliance Center gesetzlich in den Halteraum setzen und was aufgrund von Datenanforderungen gesetzlich in den Halteraum setzen muss.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711559"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams

Wenn eine angemessene Erwartung eines Rechtsstreitigkeitens besteht, müssen Organisationen elektronisch gespeicherte Informationen (elektronisch gespeicherte Informationen, ESI) beibehalten, einschließlich Teams Chatnachrichten, die für den Fall relevant sind. Organisationen müssen möglicherweise alle Nachrichten im Zusammenhang mit einer bestimmten Untersuchung oder einer bestimmten Person beibehalten. In diesem Artikel wird erläutert, wie Sie Inhalte in einem bestimmten Jahr gesetzlich Microsoft Teams. Informationen zum Beibehalten von Inhalten in Microsoft 365 Diensten finden Sie unter [Erstellen eines eDiscovery-Halteraums](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> Im Februar 2020 haben wir die gesetzliche Erkung für private Kanäle aktiviert. Chats in privaten Kanälen werden in Benutzerpostfächern gespeichert, standardkanalige Chats werden in dem Postfach gespeichert, das dem übergeordneten Team zugeordnet ist. Wenn für ein Benutzerpostfach bereits ein gesetzlicher Halteraum besteht, gilt die Halterichtlinie jetzt automatisch für Nachrichten privater Kanäle, die in diesem Postfach gespeichert sind. Es ist keine weitere Maßnahme erforderlich, damit ein Administrator dies aktivieren kann. Das gesetzliche Speichern von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

Innerhalb Microsoft Teams kann ein gesamtes Team oder ausgewählte Benutzer gesetzlich in einen Halteraum setzen werden. Dadurch wird sichergestellt, dass alle nachrichten, die in diesen Teams ausgetauscht wurden (einschließlich privater und freigegebener Kanäle), oder Nachrichten, die von diesen Personen ausgetauscht wurden, von den Compliance-Managern oder Teams-Administratoren der Organisation ermittelt werden können.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).
> In Aktivitätsfeeds gesendete Benachrichtigungen können nicht im Halteraum platziert werden.

So setzen Sie einen Benutzer oder ein Team in einen Core eDiscovery-Fall in einen gesetzlichen Haltebereich

1. Wechseln Sie zur [Microsoft 365 Compliance Center](https://compliance.microsoft.com). Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

2. Wechseln Sie zu **eDiscoveryCore** > , und erstellen Sie einen Fall, indem Sie auf **Fall erstellen klicken**. Öffnen Sie den Fall, nachdem er erstellt wurde.
  
   ![Microsoft Teams Registerkarte eDiscovery mit der Schaltfläche Fall erstellen ausgewählt.](media/LegalHold1.png)

   > [!NOTE]
   > Sie können einen Benutzer auch in einen Halteraum setzen, der einem Fall zugeordnet Advanced eDiscovery ist. Weitere Informationen finden Sie unter [Verwalten von Halte Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Wechseln Sie im oberen **Menü** zur Registerkarte Halte halte, und klicken Sie **auf Erstellen** , um einen Haltepunkt zu erstellen. Wenn sie einen Benutzer oder ein Team in den Halteraum setzen, bleiben alle von diesen Benutzern ausgetauschten Nachrichten erhalten. Wenn Sie einen neuen Fall erstellen, wird die Option angezeigt, Postfächer oder Websites in den Halteraum zu setzen.

   ![Abbildung der ausgewählten Registerkarte "Halte halte", darunter die Schaltfläche "Erstellen".](media/LegalHold2.png)

   1. **Geben Sie dem in-Mail-Konto einen Namen**. Wählen Sie einen aussagekräftigen und eindeutigen Namen für den Halteraum aus, den Sie erstellen möchten.
  
       ![Dieser Screenshot zeigt die Registerkarte "Halten benennen", auf der Sie einen Namen und eine Beschreibung für den von Ihnen erstellten Halteraum eingeben können.](media/LegalHold3.png)

   2. **Wählen Sie den Speicherort aus**. Wählen Sie aus, ob der Halte hold auf einen Benutzer oder ein gesamtes Team angewendet werden soll (ein Halte hold kann vorerst nicht auf einzelne Kanäle angewendet werden). Wenn ein Benutzer im Halteraum ist, bleiben alle seine Nachrichten erhalten, einschließlich Nachrichten in Einzelchats, Gruppenchats und privaten Kanälen. Nachrichten in Standard- und freigegebenen Kanälen werden beibehalten, wenn das übergeordnete Team in einen Halteraum gesetzt wird.

      ![Wählen Sie die Datenspeicherorte aus, die Sie im Halteraum platzieren möchten.](media/LegalHold4.png)

   3. **Erstellen sie eine Abfrage**. Sie können den Halteraum anpassen, wenn Sie eine präzisere Darstellung der Halterichtlinie wünschen. Sie können z. B. Schlüsselwörter angeben, nach der suchen soll, oder sie können weitere Bedingungen hinzufügen, die erfüllt sein müssten, damit der Halte in Kraft tritt.

   4. **Überprüfen Sie Ihre Einstellungen,** bevor Sie den halte in-/halten.

Nachdem der Halteraum erstellt wurde, können Sie die durch die Halterichtlinie aufbewahrten Inhalte durchsuchen. Weitere Informationen finden Sie unter [Durchführen einer eDiscovery-Untersuchung in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in einen Halteraum gesetzt wird, werden alle Compliancekopien von Nachrichten beibehalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal postet und die Nachricht dann ändert, bleiben beide Kopien der Nachricht erhalten. Ohne den Halteraum wird nur die neueste Nachricht beibehalten.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Inhaltspositionen, die in einen Halteraum setzen werden, um ihre Teams zu erhalten

Verwenden Sie die folgende Tabelle als hilfreiche Anleitung, um zu verstehen, welche Inhaltsspeicherorte (z. B. ein Postfach oder eine Website) in einem Haltespeicher platzieren werden müssen, um unterschiedliche Arten von Inhaltstypen Teams erhalten.

|Szenario  |Inhaltsspeicherort  |
|---------|---------|
|Chatnachrichten für einen Benutzer (z. B. 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen)     |Benutzerpostfächer         |
|Chatnachrichten in Standard- und freigegebenen Kanälen    |Postfach, das dem übergeordneten Team zugeordnet ist         |
|Dateien in Standardkanälen (z. B. Wiki-Inhalt und -Dateien)     |SharePoint, die dem übergeordneten Team zugeordnet ist        |
|Dateien in privaten und freigegebenen Kanälen     |Dedizierte SharePoint, die dem Kanal zugeordnet ist
|Private Inhalte des Benutzers     |Das Konto des OneDrive for Business Benutzers       |
|Karteninhalte in Chats|Benutzerpostfach für 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen; das übergeordnete Teampostfach für Karteninhalte in Standard- und freigegebenen Kanalnachrichten. Weitere Informationen finden Sie unter Erstellen eines eDiscovery-Haltebereichs im Abschnitt "Beibehalten von [Karteninhalten"](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Um Nachrichteninhalte in privaten Kanälen zu archivieren, müssen Sie die Benutzerpostfächer (der Mitglieder eines privaten Kanals) in den Halteraum setzen. und wenn Sie das eDiscovery-Tool zum Durchsuchen von Nachrichten in privaten Kanälen verwenden, müssen Sie das Postfach des Benutzers durchsuchen. Wie bereits erwähnt, werden Chats in privaten Kanälen in Benutzerpostfächern und nicht in dem Gruppenpostfach gespeichert, das dem übergeordneten Team zugeordnet ist.
