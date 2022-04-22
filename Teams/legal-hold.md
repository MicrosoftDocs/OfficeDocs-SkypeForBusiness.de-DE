---
title: Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
author: v-tophillips
ms.author: v-tophillips
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
description: Erfahren Sie, wie Sie einen Microsoft Teams Benutzer oder ein Team mithilfe des Microsoft Purview Compliance-Portals in die gesetzliche Aufbewahrungspflicht setzen und erfahren, was eine gesetzliche Aufbewahrung basierend auf Datenanforderungen erforderlich ist.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f0ea852b564ac339ac390994384258cc5d68ea1
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031910"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams

Wenn eine angemessene Erwartung von Rechtsstreitigkeiten besteht, müssen Organisationen elektronisch gespeicherte Informationen (ESI) aufbewahren, einschließlich Teams Chatnachrichten, die für den Fall relevant sind. Organisationen müssen möglicherweise alle Nachrichten im Zusammenhang mit einer bestimmten Untersuchung oder für eine bestimmte Person aufbewahren. In diesem Artikel wird die Verwendung eines gesetzlichen Haltebereichs zum Aufbewahren von Inhalten in Microsoft Teams erläutert. Informationen zum Beibehalten von Inhalten in anderen Diensten in Microsoft 365 finden [Sie unter Erstellen eines eDiscovery-Haltebereichs](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> Im Februar 2020 haben wir die gesetzliche Aufbewahrung für private Kanäle aktiviert. Chats in privaten Kanälen werden in Benutzerpostfächern gespeichert, während Standardkanalchats in dem Postfach gespeichert werden, das dem übergeordneten Team zugeordnet ist. Wenn bereits eine gesetzliche Aufbewahrung für ein Benutzerpostfach vorhanden ist, gilt die Aufbewahrungsrichtlinie jetzt automatisch für nachrichten im privaten Kanal, die in diesem Postfach gespeichert sind. Es ist keine weitere Aktion erforderlich, damit ein Administrator dies aktivieren kann. Die gesetzliche Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird ebenfalls unterstützt.

Innerhalb Microsoft Teams kann ein gesamtes Team oder ausgewählte Benutzer gesetzlich gesperrt werden. Dadurch wird sichergestellt, dass alle Nachrichten, die in diesen Teams ausgetauscht wurden (einschließlich privater und freigegebener Kanäle) oder von diesen Personen ausgetauschte Nachrichten von den Compliance-Managern der Organisation oder Teams Administratoren auffindbar sind.

> [!NOTE]
> Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).
> In Aktivitätsfeeds gesendete Benachrichtigungen können nicht in den Haltebereich gesetzt werden.

So setzen Sie einen Benutzer oder ein Team in einem eDiscovery-Fall (Standard) in die gesetzliche Aufbewahrungspflicht ein:

1. Wechseln Sie zum [Microsoft Purview Compliance-Portal](https://compliance.microsoft.com). Wenn Sie einen neuen Fall erstellen, wird Ihnen die Möglichkeit angezeigt, Postfächer oder Websites in den Haltebereich zu setzen.

2. Wechseln Sie zu **eDiscoveryCore** > , und erstellen Sie einen Fall, indem Sie auf "**Fall erstellen"** klicken. Nachdem der Fall erstellt wurde, öffnen Sie ihn.
  
   ![Microsoft Teams Registerkarte "eDiscovery" mit der Schaltfläche "Fall erstellen" ausgewählt ist.](media/LegalHold1.png)

   > [!NOTE]
   > Sie können einen Benutzer auch in einen Haltebereich setzen, der einem eDiscovery-Fall (Premium) zugeordnet ist. Weitere Informationen finden Sie unter [Verwalten von Haltebereichen in eDiscovery (Premium).For more information, see Manage holds in eDiscovery (Premium)](/microsoft-365/compliance/managing-holds).

3. Wechseln Sie im oberen Menü zur Registerkarte **"Haltebereiche** ", und klicken Sie auf **"Erstellen** ", um einen Haltebereich zu erstellen. Wenn Sie einen Benutzer oder ein Team in den Haltebereich setzen, bleiben alle von diesen Benutzern ausgetauschten Nachrichten erhalten. Wenn Sie einen neuen Fall erstellen, wird Ihnen die Möglichkeit angezeigt, Postfächer oder Websites in den Haltebereich zu setzen.

   ![Abbildung der ausgewählten Registerkarte "Haltebereiche" und der darunter liegenden Schaltfläche "Erstellen".](media/LegalHold2.png)

   1. **Benennen Sie Ihren Haltebereich**. Wählen Sie einen aussagekräftigen und eindeutigen Namen für den Haltebereich aus, den Sie erstellen möchten.
  
       ![Dieser Screenshot zeigt den Namen der Registerkarte "Haltebereich", auf der Sie einen Namen und eine Beschreibung für den Haltebereich eingeben können, den Sie erstellen.](media/LegalHold3.png)

   2. **Wählen Sie den Speicherort** aus. Wählen Sie aus, ob der Haltebereich auf einen Benutzer oder ein gesamtes Team angewendet werden soll (ein Haltebereich kann vorerst nicht auf einzelne Kanäle angewendet werden). Wenn sich ein Benutzer im Haltebereich befindet, werden alle seine Nachrichten beibehalten, einschließlich Nachrichten in 1:1-Chats, Gruppenchats und privaten Kanälen. Nachrichten in Standard- und freigegebenen Kanälen bleiben erhalten, wenn das übergeordnete Team in den Haltebereich versetzt wird.

      ![Wählen Sie die Datenspeicherorte aus, die Sie im Haltebereich platzieren möchten.](media/LegalHold4.png)

   3. **Abfrage erstellen**. Sie können den Haltebereich anpassen, wenn Sie mehr Granularität in der Aufbewahrungsrichtlinie wünschen. Beispielsweise können Sie Schlüsselwörter angeben, nach denen gesucht werden soll, oder Sie können weitere Bedingungen hinzufügen, die erfüllt sein müssten, damit der Haltebereich wirksam wird.

   4. **Überprüfen Sie Ihre Einstellungen** , bevor Sie den Haltebereich erstellen.

Nachdem der Haltebereich erstellt wurde, können Sie die Inhalte durchsuchen, die von der Aufbewahrungsrichtlinie aufbewahrt werden. Weitere Informationen finden [Sie unter Durchführen einer eDiscovery-Untersuchung in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Wenn ein Benutzer oder eine Gruppe in den Haltebereich versetzt wird, bleiben alle Compliancekopien von Nachrichten erhalten. Wenn ein Benutzer beispielsweise eine Nachricht in einem Kanal sendet und dann die Nachricht ändert, bleiben beide Kopien der Nachricht erhalten. Ohne den Haltebereich wird nur die neueste Nachricht beibehalten.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Inhaltsspeicherorte, die in den Haltebereich platziert werden sollen, um Teams Inhalte beizubehalten

Verwenden Sie als hilfreiche Anleitung die folgende Tabelle, um zu verstehen, welche Inhaltsspeicherorte (z. B. ein Postfach oder eine Website) in den Haltebereich platziert werden sollen, um unterschiedliche Arten von Teams Inhalten beizubehalten.

|Szenario  |Inhaltsspeicherort  |
|---------|---------|
|Chatnachrichten für einen Benutzer (z. B. 1:1-Chats, 1:N-Gruppenchats und Private Channel-Unterhaltungen)     |Benutzerpostfächer         |
|Chatnachrichten in Standard- und freigegebenen Kanälen    |Postfach, das dem übergeordneten Team zugeordnet ist         |
|Dateien in Standardkanälen (z. B. Wiki-Inhalte und Dateien)     |SharePoint Website, die dem übergeordneten Team zugeordnet ist        |
|Dateien in privaten und freigegebenen Kanälen     |Dedizierte SharePoint Website, die dem Kanal zugeordnet ist
|Private Inhalte des Benutzers     |Das OneDrive for Business Konto des Benutzers       |
|Karteninhalte in Chats|Benutzerpostfach für 1:1-Chats, 1:N-Gruppenchats und private Kanalunterhaltungen; das übergeordnete Teampostfach für Karteninhalte in Standard- und freigegebenen Kanalnachrichten. Weitere Informationen finden Sie im Abschnitt "Beibehalten von Karteninhalten" im [Abschnitt "Erstellen eines eDiscovery-Haltebereichs](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)".|
|||

> [!NOTE]
> Um Nachrichteninhalte in privaten Kanälen aufzubewahren, müssen Sie die Benutzerpostfächer (der Mitglieder eines privaten Kanals) in den Haltebereich setzen. und wenn Sie das eDiscovery-Tool zum Durchsuchen von Nachrichten in privaten Kanälen verwenden, müssen Sie das Postfach des Benutzers durchsuchen. Wie bereits erwähnt, werden Chats im privaten Kanal in Benutzerpostfächern und nicht in dem Gruppenpostfach gespeichert, das dem übergeordneten Team zugeordnet ist.
