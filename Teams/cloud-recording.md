---
title: Aufzeichnung einer Teams-Cloudbesprechung
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9feaffd1677d96c53dee57b03f9061c6fa8184ce
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516941"
---
# <a name="teams-cloud-meeting-recording"></a>Aufzeichnung einer Teams-Cloudbesprechung

In Microsoft Teams können Benutzer ihre Teams-Besprechungen und Gruppenanrufe aufzeichnen, um Audio-, Video-und Bildschirmfreigabe Aktivitäten zu erfassen. Es gibt auch eine Option für die automatische Transkription von Aufzeichnungen, sodass Benutzer Besprechungsaufzeichnungen mit Untertiteln wiedergeben und nach wichtigen Diskussionsbeiträgen in der Transkription suchen können. Die Aufzeichnung erfolgt in der Cloud und wird in [Microsoft Stream](https://docs.microsoft.com/stream/)gespeichert, sodass Benutzer Sie in der gesamten Organisation sicher freigeben können.

Related: [Teams Besprechung Aufzeichnung Endbenutzer-Dokumentation](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Voraussetzungen für die Cloud-Besprechungsaufzeichnung von Teams

Damit Besprechungen eines Teams-Benutzers aufgezeichnet werden, muss Microsoft Stream für den Mandanten aktiviert sein. Darüber hinaus sind die folgenden Voraussetzungen für den Besprechungsorganisator und die Person erforderlich, die die Aufzeichnung initiiert:

- Der Benutzer verfügt über ein Office 365 E1, E3, E5, a1, a3, A5, M365 Business, Business Premium oder Business Essentials
- Der Benutzer muss für Microsoft Stream<sup>1</sup> lizenziert sein. 
- Benutzer hat Microsoft Stream-Upload-Video Berechtigungen
- Der Benutzer hat den Richtlinien des Unternehmens zugestimmt, wenn er vom Administrator eingerichtet wurde.
- Der Benutzer verfügt über genügend Speicherplatz in Microsoft Stream, damit Aufzeichnungen gespeichert werden.
- Der Benutzer hat die TeamsMeetingPolicy-AllowCloudRecording-Einstellung auf "true" festgelegt.
- Der Benutzer ist kein anonymer, Gast-oder Verbundbenutzer in der Besprechung

> [!NOTE]
> Darüber hinaus muss die TeamsMeetingPolicy-AllowTranscription-Einstellung des Benutzers auf "true" festgelegt werden, damit die Person, die die Aufzeichnung initiiert, auswählen kann, ob die Aufzeichnung automatisch transkribiert werden soll.

<sup>1</sup> Der Benutzer muss zum Hochladen/Herunterladen von Besprechungen von/zu Microsoft Stream lizenziert werden, Sie benötigen jedoch keine Lizenz zum Aufzeichnen einer Besprechung. Wenn Sie einen Benutzer daran hindern möchten, eine Microsoft Teams-Besprechung zu speichern, müssen Sie einen TeamsMeetingPolicy gewähren, der AllowCloudRecording auf $false festzulegen hat.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Einrichten der Cloud-Besprechungsaufzeichnung von Teams für Benutzer in Ihrer Organisation

In diesem Abschnitt wird erläutert, wie Sie Besprechungen für Teams aufzeichnen und planen können.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Aktivieren von Microsoft Stream für Benutzer in der Organisation

Microsoft Stream steht als Teil der zulässigen Office 365-Abonnements oder als eigenständiger Dienst zur Verfügung.  Weitere Informationen finden Sie in der [Übersicht zur Datenstrom Lizenzierung](https://docs.microsoft.com/stream/license-overview) .  Microsoft Stream ist jetzt in Microsoft 365 Business, Office 365 Business Premium und Office 365 Business Essentials enthalten.

Erfahren Sie mehr darüber, wie Sie [Benutzern in Office 365 Lizenzen zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) können, damit Benutzer auf Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft Stream nicht für die Benutzer blockiert ist, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Sicherstellen, dass Benutzer Video Berechtigungen in Microsoft Stream hochladen

Standardmäßig können alle Mitarbeiter des Unternehmens Inhalte im Datenstrom erstellen, sobald Datenstrom aktiviert ist und dem Benutzer die Lizenz zugewiesen wurde. Ein Microsoft Stream-Administrator kann [Mitarbeiter für das Erstellen von Inhalten](https://docs.microsoft.com/stream/restrict-uploaders) im Datenstrom einschränken. Die Benutzer, die sich in dieser Liste mit Einschränkungen befinden, können keine Besprechungen aufzeichnen.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Benachrichtigen der Mitarbeiter zur Zustimmung zu Unternehmensrichtlinien in Microsoft Stream

Wenn ein Microsoft Stream-Administrator die Richt [Linie für Unternehmensrichtlinien eingerichtet](https://docs.microsoft.com/stream/company-policy-and-consent) hat und Mitarbeiter dazu auffordert, diese Richtlinie vor dem Speichern von Inhalten zu akzeptieren, müssen die Benutzer dies vor der Aufzeichnung in Microsoft Teams tun. Bevor Sie das Aufzeichnungsfeature in der Organisation ausrollen, stellen Sie sicher, dass die Benutzer der Richtlinie zugestimmt haben.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Aktivieren oder Deaktivieren der Cloud-Aufzeichnung

Verwenden Sie die Einstellung AllowCloudRecording in TeamsMeetingPolicy in Teams PowerShell, um zu steuern, ob die Besprechungen eines Benutzers aufgezeichnet werden dürfen. Weitere Informationen zum Verwalten von TeamsMeetingPolicy mit Office 365 PowerShell finden Sie [hier](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Beachten Sie, dass sowohl der Besprechungsorganisator als auch der Aufnahme Initiator über die Aufzeichnungs Berechtigung zum Aufzeichnen der Besprechung verfügen müssen. Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, für die standardmäßig AllowTranscription deaktiviert ist.

Damit ein Benutzer auf die globale Richtlinie zurückgreifen kann, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinien Aufgabe für einen Benutzer zu entfernen:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Wenn Sie den Wert von AllowCloudRecording in der globalen Richtlinie ändern möchten, verwenden Sie das folgende Cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Szenario                                                                 |                                                                                                                                                                         Schritte                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Ich möchte, dass alle Benutzer in meinem Unternehmen Ihre Besprechungen aufzeichnen können.                                    |                                                                     <ol><li>Confirm Global CsTeamsMeetingPolicy has AllowCloudRecording = true<li>Alle Benutzer haben die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = true </ol>                                                                     |
| Ich möchte, dass die meisten meiner Benutzer Ihre Besprechungen aufzeichnen, aber bestimmte Benutzer, die nicht aufgenommen werden dürfen, selektiv deaktivieren können. |        <ol><li>Confirm GlobalCsTeamsMeetingPolicy hat AllowCloudRecording = true<li>Die Mehrheit der Benutzer verfügt über die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = true.<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = false gewährt.</ol>         |
|                                                   Ich möchte, dass die Aufzeichnung 100% deaktiviert ist                                                   |                                                                <ol><li>Confirm Global CsTeamsMeetingPolicy has AllowCloudRecording = false<li>Allen Benutzern wurde die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = false gewährt.                                                                 |
|      Ich möchte, dass die Aufzeichnung für die Mehrzahl der Benutzer deaktiviert wird, aber bestimmte Benutzer, die Daten aufzeichnen dürfen, selektiv aktivieren       | <ol><li>Confirm Global CsTeamsMeetingPolicy has AllowCloudRecording = false<li>Die Mehrheit der Benutzer erhielt die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = false.<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = true gewährt. <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>Aktivieren oder Deaktivieren der Transkription der Aufzeichnung

Wenn Benutzer ihre Teams-Besprechungen aufzeichnen, können Sie überprüfen, ob nach der Aufzeichnung der Besprechung automatisch eine Aufzeichnung erstellt wird. Wenn Administratoren die Transkriptions Funktion für den Besprechungsorganisator und den Aufzeichnungs Initiator deaktiviert haben, erhält der Aufnahme Initiator keine Auswahl, um die Besprechungsaufzeichnungen zu transkribieren.

Verwenden Sie die Einstellung AllowTranscription in TeamsMeetingPolicy in Teams PowerShell, um zu steuern, ob ein Recording-Initiator eine Auswahl für die Transkription der Besprechungsaufzeichnung erhält. Weitere Informationen zum Verwalten von TeamsMeetingPolicy mit Office 365 PowerShell finden Sie [hier](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten Sie eine globale Richtlinie, für die standardmäßig AllowTranscription deaktiviert ist.

Damit ein Benutzer auf die globale Richtlinie zurückgreifen kann, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinien Aufgabe für einen Benutzer zu entfernen:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Wenn Sie den Wert von AllowCloudRecording in der globalen Richtlinie ändern möchten, verwenden Sie das folgende Cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Szenario|Schritte |
|---|---|
|Ich möchte, dass alle Benutzer in meinem Unternehmen beim Initiieren der Aufzeichnung einer Besprechung transkribieren können |<ol><li>Confirm Global CsTeamsMeetingPolicy has AllowTranscription = true <li>Alle Benutzer haben die globale csTeamsMeetingPolicy oder eine der csTeamsMeetingPolicy-Richtlinien mit AllowTranscription = true. </ol>|
|Ich möchte, dass die meisten meiner Benutzer in der Lage sind, die Besprechungsaufzeichnungen zu transkribieren, aber bestimmte Benutzer, die nicht übertragen werden dürfen, selektiv zu deaktivieren |<ol><li>Confirm Global CsTeamsMeetingPolicy has AllowTranscription = true <li>Die Mehrheit der Benutzer verfügt über die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = true. <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = false gewährt. </ol>|
|Ich möchte, dass die Transkription der Aufzeichnung 100% deaktiviert ist |<ol><li>Confirm Global CsTeamsMeetingPolicy has AllowTranscription = false <li>Allen Benutzern wurde die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = false gewährt. </ol>|
|Ich möchte, dass die Transkription für die Mehrzahl der Benutzer deaktiviert wird, aber bestimmte Benutzer, die transkribieren können, selektiv aktivieren |<ol><li>Confirm Global CsTeamsMeetingPolicy has AllowCloudRecording = false <li>Die Mehrheit der Benutzer erhielt die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = false. <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = true gewährt. </ol>|
|||

### <a name="planning-for-storage"></a>Planen von Speicher

Die Größe einer 1-stündigen Aufzeichnung beträgt 400 MB. Stellen Sie sicher, dass Sie die für aufgezeichnete Dateien erforderliche Kapazität verstehen und über genügend Speicherplatz in Microsoft Stream verfügen.  Lesen Sie [diesen Artikel](https://docs.microsoft.com/stream/license-overview) , um den im Abonnement enthaltenen Basisspeicher zu verstehen und zu erfahren, wie Sie zusätzlichen Speicher erwerben.

## <a name="manage-meeting-recordings"></a>Verwalten von Besprechungsaufzeichnungen
Die Besprechungsaufzeichnungen gelten als im Besitz des Mandanten befindliche Inhalte. Wenn der Besitzer der Aufzeichnung das Unternehmen verlässt, kann der Administrator die Aufnahme Video-URL in Microsoft Stream im Administratormodus öffnen. Der Administrator kann die Aufzeichnung löschen, aufgezeichnete Metadaten aktualisieren oder die Berechtigungen für das Aufnahme Video ändern. Weitere Informationen zu den [Administratorfunktionen in Stream](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Compliance und eDiscovery für Besprechungsaufzeichnungen
Die Besprechungsaufzeichnungen werden in Microsoft Stream gespeichert, der Office 365 Tier-C-kompatibel ist. Zur Unterstützung von e-Discovery-Anforderungen für Compliance-Administratoren, die an Besprechungen oder Anrufaufnahmen für Microsoft-Streams interessiert sind, steht die Meldung "Aufzeichnung abgeschlossen" in der Suchfunktion für Compliance-Inhalte für Microsoft Teams zur Verfügung. Compliance-Administratoren können nach dem Stichwort "Aufzeichnung" in der Betreffzeile des Elements in der Vorschau für die Compliance-Inhaltssuche suchen und Besprechungen und Anrufaufzeichnungen in der Organisation entdecken. Eine Voraussetzung für die Anzeige aller Aufzeichnungen ist, dass Sie in Microsoft Stream mit Administratorzugriff eingerichtet werden müssen. Weitere Informationen finden Sie [unter Zuweisen von Administratorberechtigungen in Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Einrichten Ihres Computers für Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

