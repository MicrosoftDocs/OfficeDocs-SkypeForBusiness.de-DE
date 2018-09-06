---
title: Teams Cloud besprechungsaufzeichnung
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
description: Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64a0dd2cccfe92fe1385b40caa45551bfe91bba9
ms.sourcegitcommit: 39516662ee3eefe2fb86735c5bae97b3fb32b7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "23835023"
---
# <a name="teams-cloud-meeting-recording"></a>Teams Cloud besprechungsaufzeichnung

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

In Microsoft-Teams können Benutzer ihre Teams Besprechungen und Gruppe Aufrufe von Audio-, Video- und Bildschirmfreigabe Aktivität erfassen aufzeichnen. Es ist auch eine Option für Aufzeichnungen automatische Lautschrift haben, damit Benutzer wieder besprechungsaufzeichnungen mit Untertitel und suchen Sie nach wichtige Diskussionselemente in der Schulungsunterlagen ausgeführt werden können. Die Aufzeichnung geschieht in der Cloud und wird in [Microsoft Stream](https://docs.microsoft.com/en-us/stream/)gespeichert, sodass Benutzer sicher in ihrer Organisation gemeinsam verwendet werden können.

Verwandte: [Teams Besprechung aufzeichnen Endbenutzerdokumentation](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Erforderliche Komponenten für Teams cloud besprechungsaufzeichnung

Für ein Teams Benutzer Besprechungen aufgezeichnet werden sollen muss Microsoft-Stream für den Mandanten aktiviert sein. Darüber hinaus sind die folgenden erforderlichen Komponenten für den Organisator der Besprechung und die Person, die die Aufzeichnung initiiert erforderlich:

- Benutzer verfügt über eine Lizenz für Office 365 Enterprise E1, E3 oder E5
- Benutzer muss für Microsoft Stream lizenziert werden
- Benutzer hat Microsoft Stream video Berechtigungen hochladen
- Benutzer, das den Richtlinien Unternehmen zugestimmt hat, wenn durch den Administrator einrichten
- Benutzer verfügt über ausreichend Speicherplatz im Microsoft-Stream für Aufzeichnungen gespeichert werden soll
- Benutzer hat TeamsMeetingPolicy AllowCloudRecording Einstellung auf True festgelegt
- Benutzer hat TeamsMeetingPolicy.AllowTranscription Einstellung Festlegung auf "true", kann Benutzer auswählen, ob auf die Aufzeichnungen automatisch aufzuzeichnen
- Benutzer ist keiner anonymen, Gast oder Verbundbenutzer in der Besprechung

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Einrichten von Teams Cloud besprechungsaufzeichnung für Benutzer in Ihrer Organisation

In diesem Abschnitt wird erläutert, wie Sie eingerichtet und zum Aufzeichnen von Teams Besprechungen planen können.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Aktivieren von Microsoft-Stream für Benutzer in der Organisation

Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst.  Finden Sie unter der [Stream Übersicht über die Lizenzierung](https://docs.microsoft.com/en-us/stream/license-overview) für weitere Details.  Beachten Sie, dass Microsoft Stream ist nicht enthalten in Business Essentials Business Premium plans.

Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft-Stream für die Benutzer nicht gesperrt ist, wie in [diesem Artikel](https://docs.microsoft.com/en-us/stream/disable-user-organization)definiert.

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Stellen Sie sicher, dass Benutzer haben video Berechtigungen in Microsoft Stream hochladen

In der Standardeinstellung kann Person im Unternehmen Inhalte in Stream-Objekt erstellen, sobald Stream aktiviert ist und der Benutzer die Lizenz zugewiesen ist. Ein Microsoft-Stream-Administrator können im Datenstrom [Mitarbeiter zum Erstellen von Inhalt zu beschränken](https://docs.microsoft.com/en-us/stream/restrict-uploaders) . Der Benutzer, die in dieser Liste beschränkt sind möglich zum Aufzeichnen von Besprechungen nicht.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Benachrichtigen Sie Mitarbeiter, Unternehmen Richtlinien in Microsoft Stream zuzustimmen

Wenn ein Administrator Microsoft Stream [Unternehmensrichtlinie Richtlinie eingerichtet](https://docs.microsoft.com/en-us/stream/company-policy-and-consent) wurde und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, müssen Benutzer vor der Aufzeichnung in Microsoft-Teams, dafür. Bevor Sie die Aufzeichnungsfunktion in der Organisation bereitstellen, stellen Sie sicher, dass Benutzer die Richtlinie zugestimmt haben.

### <a name="enabledisable-cloud-recording-for-users"></a>Deaktivieren Sie Cloud für Benutzer Aufzeichnung aktivieren /

Verwenden Sie die Einstellung AllowCloudRecording in TeamsMeetingPolicy in Teams PowerShell Kontrolle, ob ein Benutzer Besprechungen zulässig sind oder nicht aufgezeichnet werden sollen. Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingPolicy mit Office 365 PowerShell [hier](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Beachten Sie, dass der Organisator der Besprechung und der Initiator Aufzeichnung die Aufzeichnung Berechtigungen für das Aufzeichnen der Besprechung müssen. Wenn der Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die Aufzeichnung, die in der Standardeinstellung aktiviert hat.

Verwenden Sie das folgende Cmdlet für einen Benutzer auf globale Richtlinie zurückgreifen um eine bestimmte Richtlinie-Zuordnung für einen Benutzer zu entfernen:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Um Wert der AllowCloudRecording in der globalen Richtlinie zu ändern, verwenden Sie das folgende Cmdlet aus:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|Szenario|Schritte |
|---|---|
|Ich möchte alle Benutzer in meinem Unternehmen können ihre Besprechungen aufzeichnen |<ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowCloudRecording = True<li>Alle Benutzer haben die globalen CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording = True </ol>|
|Ich möchte, dass die meisten Benutzer können ihre Besprechungen aufzeichnen, aber bestimmte Benutzer, die nicht zulässig sind, so zeichnen Sie einzeln zu deaktivieren |<ol><li>Bestätigen GlobalCsTeamsMeetingPolicy hat AllowCloudRecording = True<li>Die Mehrheit der Benutzer haben die globalen CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording = True<li>Alle anderen Benutzer gewährt wurden eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording = False</ol>|
|Ich möchte Aufzeichnung um 100 % deaktiviert werden.| <ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowCloudRecording = False<li>Alle Benutzer der globalen CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording gewährt wurden = False|
|Ich möchte aufzeichnen, wenn Sie für die meisten Benutzer deaktiviert werden jedoch bestimmte Benutzer, die berechtigt sind, so zeichnen Sie selektiv zu aktivieren|<ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowCloudRecording = False<li>Die Mehrheit der Benutzer die globale CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording gewährt wurden = False<li>Alle anderen Benutzer gewährt wurden eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording = True <ol>|
|||

### <a name="enabledisable-recording-transcription-for-users"></a>Aktivieren/Deaktivieren der Aufzeichnung Lautschrift für Benutzer

Wenn Benutzer ihren Teams Besprechungen aufzeichnen, können sie überprüfen, ob um eine Kopie automatisch generiert werden soll, nachdem die Besprechung aufgezeichnet wird. Wenn Administratoren Lautschrift-Funktion für den Organisator der Besprechung und der Initiator Aufzeichnung deaktiviert haben, erhalten der Initiator Aufzeichnung keine Entscheidung für die besprechungsaufzeichnungen aufzuzeichnen.

Verwenden Sie die Einstellung AllowTranscription in TeamsMeetingPolicy in Teams PowerShell Kontrolle, ob ein Aufzeichnung Initiator eine Entscheidung für die besprechungsaufzeichnung aufzuzeichnen ruft. Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingPolicy mit Office 365 PowerShell [hier](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Wenn der Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten sie die globale Richtlinie, die nicht deaktiviert hat in der Standardeinstellung aktiviert.

Verwenden Sie das folgende Cmdlet für einen Benutzer auf globale Richtlinie zurückgreifen um eine bestimmte Richtlinie-Zuordnung für einen Benutzer zu entfernen:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Um Wert der AllowCloudRecording in der globalen Richtlinie zu ändern, verwenden Sie das folgende Cmdlet aus:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Szenario|Schritte |
|---|---|
|Ich möchte alle Benutzer in meinem Unternehmen aufzuzeichnen beim Aufzeichnen einer Besprechung initiieren können |<ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowTranscription = True <li>Alle Benutzer haben die globalen CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowTranscription = True. </ol>|
|Ich möchte die Mehrzahl der meine Benutzer möglicherweise die besprechungsaufzeichnungen aufzuzeichnen, jedoch bestimmte Benutzer, die nicht aufzuzeichnen dürfen selektiv zu deaktivieren |<ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowTranscription = True <li>Die Mehrheit der Benutzer haben die globalen CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowTranscription = True <li>Alle anderen Benutzer gewährt wurden eine der Richtlinien CsTeamsMeetingPolicy mit AllowTranscription = False </ol>|
|Ich möchte Umsetzung der Aufzeichnung auf 100 % deaktiviert werden. |<ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowTranscription = False <li>Alle Benutzer der globalen CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowTranscription gewährt wurden = False </ol>|
|Ich möchte Lautschrift für die Mehrheit der Benutzer deaktiviert, aber bestimmte Benutzer, die berechtigt sind, aufzuzeichnen selektiv aktivieren |<ol><li>Bestätigen Sie globale CsTeamsMeetingPolicy hat AllowCloudRecording = False <li>Die Mehrheit der Benutzer die globale CsTeamsMeetingPolicy oder eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording gewährt wurden = False <li>Alle anderen Benutzer gewährt wurden eine der Richtlinien CsTeamsMeetingPolicy mit AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Planung der Speicherung

Die Größe einer Aufzeichnung 1 Stunde beträgt 400 MB. Stellen Sie sicher, dass Sie verstehen, die für die Dateien der Aufzeichnungen erforderliche Kapazität und verfügen über genügend Speicherplatz verfügbar in Microsoft-Stream.  [In diesem Artikel](https://docs.microsoft.com/en-us/stream/license-overview) zu verstehen, die base-Speicherung in das Abonnement und Informationen zum Kauf von zusätzlichen Speichers enthalten lesen.

## <a name="manage-meeting-recordings"></a>Verwalten von besprechungsaufzeichnungen
Die besprechungsaufzeichnungen gelten Inhalt im Besitz des Mandanten. Wenn der Besitzer der Aufzeichnung das Unternehmen verlässt, kann der Administrator Aufzeichnung-video-URL in Stream Microsoft im Administratormodus geöffnet. Der Administrator kann die Aufzeichnung zu löschen, Metadaten, die Aufzeichnung aktualisieren oder Ändern der Berechtigungen für das Aufzeichnen von video. Weitere Informationen zu [Admin-Funktionen in Stream-Objekt](https://docs.microsoft.com/en-us/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Compliance und eDiscovery zur Erfüllung von Aufzeichnungen
Die besprechungsaufzeichnungen werden im Microsoft-Stream gespeichert, die Office 365 Tier-C kompatibel ist. Zur Unterstützung der e-Discovery-Anfragen für Compliance-Admins, die Besprechungen oder Aufzeichnungen für Microsoft-Streams interessiert sind, ist die Aufzeichnung abgeschlossenen Nachricht in der Compliance Inhaltssuche-Funktionen für Microsoft-Teams, verfügbar. Compliance-Admins kann Aufzeichnungen in der Organisation für das Stichwort "Aufzeichnung" in die Betreffzeile des Elements in Content Suchvorschau Konformität suchen und entdecken die Besprechung und aufrufen. Voraussetzung für die Anzeige des alle Aufzeichnungen ist, dass sie im Microsoft-Stream mit Administratorzugriff eingerichtet werden müssen. Weitere Informationen zur [Zuweisung von Administratorberechtigungen in Stream-Objekt](https://docs.microsoft.com/en-us/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Einrichten Ihres Computers für Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

