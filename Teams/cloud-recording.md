---
title: Aufzeichnung einer Teams-Cloudbesprechung
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Praktische Anleitungen für die Bereitstellung von Cloud-Sprachfeatures in Teams zum Aufzeichnen von Teams-Besprechungen und Gruppen anrufen, um Audio-, Video-und Bildschirmfreigabe Aktivitäten zu erfassen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e38b7fcfdbe8789604716410beca3c5d76975c29
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905497"
---
# <a name="teams-cloud-meeting-recording"></a>Aufzeichnung einer Teams-Cloudbesprechung

In Microsoft Teams können Benutzer ihre Besprechungen und Gruppenanrufe aufzeichnen, um Aktivitäten der Audio-, Video- und Bildschirmfreigabe festzuhalten. Es gibt auch eine Option für die automatische Transkription von Aufzeichnungen, sodass Benutzer Besprechungsaufzeichnungen mit Untertiteln wiedergeben und nach wichtigen Diskussionsbeiträgen in der Transkription suchen können. Die Aufzeichnung erfolgt in der Cloud und wird im [Microsoft Stream](https://docs.microsoft.com/stream/) gespeichert, sodass Benutzer sie sicher in ihrer Organisation freigeben können.

Verwandt: [Teams-Besprechungsaufzeichnung, Endbenutzer-Dokumentation](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Voraussetzungen für die Aufzeichnung von Teams-Cloudbesprechungen.

Damit Besprechungen eines Teams-Benutzers aufgezeichnet werden, muss Microsoft Stream für den Mandanten aktiviert sein. Darüber hinaus gelten die folgenden Voraussetzungen, die sowohl für den Organisator der Besprechung als auch für die Person, welche die Aufzeichnung initiiert, erforderlich sind:

- Der Benutzer verfügt über Office 365 E1, E3, E5, A1, A3, A5, M365 Business, Business Premium oder Business Essentials.
- Der Benutzer muss für Microsoft Stream lizenziert sein. <sup>1</sup> 
- Der Benutzer hat die Berechtigung zum Hochladen von Videos in Microsoft Stream
- Der Benutzer hat den Unternehmensrichtlinien zugestimmt, falls diese vom Administrator erstellt wurden
- Der Benutzer verfügt über genügend Speicherplatz in Microsoft Stream, um Aufzeichnungen zu speichern
- Der Benutzer hat die TeamsMeetingPolicy-AllowCloudRecording-Einstellung auf „True“ eingestellt
- Der Benutzer ist kein anonymer, Gast- oder Verbundbenutzer in der Besprechung

> [!NOTE]
> Zusätzlich muss, damit die Person, die die Aufzeichnung initiiert, auch die Wahl hat, dass die Aufzeichnung automatisch transkribiert wird, die TeamsMeetingPolicy-AllowTranscription-Einstellung des Benutzers auf „True“ eingestellt sein

<sup>1</sup> Der Benutzer muss dazu lizenziert sein, Besprechungen in/aus Microsoft Stream hoch- oder herunterzuladen, benötigt jedoch keine Lizenz zum Aufzeichnen einer Besprechung. Wenn Sie einen Benutzer daran hindern möchten, eine Besprechung aus Microsoft Teams aufzuzeichnen, müssen Sie eine TeamsMeetingPolicy gewähren, die AllowCloudRecording auf $False festgelegt hat.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Einrichten der Aufzeichnungsfunktion für Teams-Cloudmeetings für Benutzer in Ihrer Organisation

In diesem Abschnitt wird erläutert, wie die Aufzeichnung von Besprechungen in Teams eingerichtet und geplant wird.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Aktivieren von Microsoft Stream für Benutzer in der Organisation

Microsoft Stream ist als Teil der berechtigten Microsoft 365-und Office 365-Abonnements oder als eigenständiger Dienst verfügbar.  Weitere Details finden Sie unter [Übersicht über die Stream-Lizenzierung](https://docs.microsoft.com/stream/license-overview).  Microsoft Stream ist jetzt in Microsoft 365 Business, Microsoft 365 Business Standard und Microsoft 365 Business Basic enthalten.

Hier erfahren Sie, wie Sie [Benutzern in Office 365 Lizenzen zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) können, damit Benutzer auf Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft Stream für die Benutzer nicht blockiert ist, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Sicherstellen, dass Benutzer in Microsoft Stream über Upload-Video Berechtigungen verfügen

Standardmäßig kann jeder Mitarbeiter des Unternehmens in Stream Inhalte erstellen, sobald Stream aktiviert ist und dem Benutzer die Lizenz zugewiesen ist. Ein Microsoft Stream-Administrator kann [Mitarbeiter bei der Erstellung von Inhalten in Stream einschränken](https://docs.microsoft.com/stream/restrict-uploaders). Die Benutzer, die in dieser Liste als „eingeschränkt“ markiert sind, können keine Besprechungen aufzeichnen.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Mitarbeiter in Microsoft Stream dazu auffordern, den Richtlinien des Unternehmens zuzustimmen

Wenn ein Microsoft Stream-Administrator [Unternehmensrichtlinien eingerichtet](https://docs.microsoft.com/stream/company-policy-and-consent) hat und die Mitarbeiter diese Richtlinie vor dem Speichern von Inhalten anerkennen müssen, müssen die Benutzer dies tun, bevor sie in Microsoft Teams aufzeichnen können. Bevor Sie das Aufzeichnungsfeature in der Organisation ausrollen, müssen Sie sicherstellen, dass die Benutzer der Richtlinie zugestimmt haben.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Aktivieren oder Deaktivieren von „Cloud-Aufnahme“

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob Besprechungen zwischen Benutzern aufgezeichnet werden dürfen.

Aktivieren bzw. deaktivieren Sie im Microsoft Teams Admin Center die Einstellung **Zulassen von Cloud-Aufzeichnung** in der Besprechungsrichtlinie. Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Mithilfe von PowerShell konfigurieren Sie die Einstellung „AllowCloudRecording“ in TeamsMeetingPolicy. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Beachten Sie, dass sowohl der Besprechungsorganisator als auch der Initiator der Aufzeichnung über die Berechtigung zum Aufzeichnen der Besprechung verfügen müssen. Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, in der AllowCloudRecording standardmäßig deaktiviert ist.

Wenn ein Benutzer auf die globale Richtlinie zurückgesetzt werden soll, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinienzuweisung für einen Benutzer zu entfernen:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Verwenden Sie das folgende Cmdlet, um den Wert von AllowCloudRecording in der globalen Richtlinie zu ändern:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Szenario                                                                 |                                                                                                                                                                         Schritte                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Ich möchte, dass alle Benutzer in meinem Unternehmen ihre Besprechungen aufzeichnen können                                    |                                                                     <ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = True aufweist<li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = True </ol>                                                                     |
| Ich möchte, dass die Mehrzahl meiner Benutzer in der Lage ist, ihre Besprechungen aufzuzeichnen, aber selektiv bestimmte Benutzer zu deaktivieren, die nicht dazu in der Lage sein sollen |        <ol><li>Stellen Sie sicher, dass GlobalCsTeamsMeetingPolicy den Eintrag AllowCloudRecording = True aufweist<li>Die meisten Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = True<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = False zugewiesen</ol>         |
|                                                   Ich möchte, dass die Aufzeichnung zu 100% deaktiviert ist                                                   |                                                                <ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist<li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False                                                                 |
|      Ich möchte, dass die Aufzeichnung für die Mehrzahl der Benutzer deaktiviert wird, aber bestimmte Benutzer, die Daten aufzeichnen dürfen, selektiv aktivieren       | <ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist<li>Die Mehrzahl aller Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = True zugewiesen <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Wo Ihre Besprechungsaufzeichnungen gespeichert werden

Besprechungsaufzeichnungen werden im Microsoft Stream-Cloudspeicher gespeichert. Nachdem Sie eine Besprechung aufgezeichnet haben, wird Sie von Microsoft Stream für immer aufbewahrt (oder bis der Besitzer der Aufzeichnung Sie löscht). Wenn die Aufzeichnung nicht in den Datenstrom hochgeladen wird, wird Sie im Cloud-Speicher der Teams gespeichert, wo Sie 20 Tage lang heruntergeladen werden kann. Derzeit ist das Feature für die Besprechungsaufzeichnung von Teams für Kunden ausgeschaltet, deren Teams-Daten inländisch gespeichert werden, falls Microsoft Stream im inländischen Datenbereich, in dem die Daten gespeichert werden, nicht verfügbar ist.

Um herauszufinden, in welcher Region Ihre Microsoft Stream-Daten gespeichert werden, klicken Sie in Microsoft Stream auf **?** Klicken Sie in der oberen, rechten Ecke auf **Über Microsoft Stream** und dann auf **Ihre Daten werden gespeichert in**.  Um mehr über die Regionen zu erfahren, in denen Microsoft Stream Daten speichert, lesen Sie [Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Um mehr darüber zu erfahren, wo die Daten der Dienste von Office 365 gespeichert werden, lesen Sie [Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Aufzeichnungstranskription ein- oder ausschalten

Wenn Benutzer ihre Teams-Besprechungen aufzeichnen, können sie bestätigen, dass nach der Aufzeichnung der Besprechung automatisch eine Niederschrift generiert wird. Wenn Sie die Transkriptionsfunktion für den Besprechungsorganisator und den Initiator der Aufzeichnung deaktiviert haben, wird der Initiator der Aufzeichnung nicht die Wahl haben, die Besprechungsaufzeichnung zu transkribieren.

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob der Initiator der Besprechung die Wahl haben soll, die Besprechungsaufzeichnung zu transkribieren.

Schalten Sie im Microsoft Teams Admin-Center die Option **Transkription gestatten** in der Besprechungsrichtlinie ein oder aus. Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md#allow-transcription).

Mithilfe von PowerShell konfigurieren Sie die Einstellung „AllowTranscription“ in TeamsMeetingPolicy. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, in der AllowTranscription standardmäßig deaktiviert ist.

Wenn ein Benutzer auf die globale Richtlinie zurückgesetzt werden soll, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinienzuweisung für einen Benutzer zu entfernen:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Verwenden Sie das folgende Cmdlet, um den Wert von AllowCloudRecording in der globalen Richtlinie zu ändern:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Szenario|Schritte |
|---|---|
|Ich möchte, dass alle Benutzer in meinem Unternehmen beim Initiieren einer Besprechungsaufzeichnung transkribieren können. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = True aufweist <li>Alle Benutzer verfügen über die globale csTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = True. </ol>|
|Ich möchte, dass die Mehrzahl meiner Benutzer in der Lage ist, ihre Besprechungen zu transkribieren, aber selektiv bestimmte Benutzer zu deaktivieren, die nicht dazu in der Lage sein sollen |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = True aufweist <li>Die Mehrheit der Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = True <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowTranscription = False zugewiesen </ol>|
|Ich möchte, dass die Transkription der Aufzeichnung zu 100% deaktiviert ist |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = False aufweist <li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = False </ol>|
|Ich möchte, dass die Transkription für die Mehrzahl der Benutzer deaktiviert wird, aber selektiv bestimmte Benutzer aktivieren, die in der Lage sind, Aufzeichnungen zu transkribieren |<ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist <li>Die Mehrzahl aller Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = True zugewiesen </ol>|
|||

### <a name="planning-for-storage"></a>Planung der Speicheranforderungen

Die Größe einer einstündigen Aufzeichnung beträgt 400 MB. Stellen Sie sicher, dass Sie die für aufgezeichnete Dateien erforderliche Kapazität kennen und über genügend Speicherplatz in Microsoft Stream verfügen.  Lesen [diesen Artikel](https://docs.microsoft.com/stream/license-overview), um mehr über den im Abonnement enthaltenen Basisspeicher und den Erwerb zusätzlichen Speichers zu erfahren.

## <a name="manage-meeting-recordings"></a>Verwalten von Besprechungsaufzeichnungen

Die Besprechungsaufzeichnungen gelten als mandanteneigener Inhalt. Wenn der Besitzer der Aufzeichnung das Unternehmen verlässt, kann der Administrator die Video-URL der Aufzeichnung in Microsoft Stream im Administratormodus öffnen. Der Administrator kann die Aufzeichnung löschen, die Metadaten der Aufzeichnung bearbeiten oder Berechtigungen für das Video der Aufzeichnung ändern. Erfahren Sie mehr über [Administratorfunktionen in Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Weitere Informationen zum Verwalten von Aufzeichnungen und des Benutzerzugriffs finden Sie unter [Verwalten von Benutzerdaten in Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) und [Berechtigungen und Datenschutz in Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Compliance und eDiscovery für Besprechungsaufzeichnungen

Die Besprechungsaufzeichnungen werden in Microsoft Stream (Office 365 Tier-C-konform) gespeichert. Um e-Discovery-Anforderungen für Compliance-Administratoren zu unterstützen, die an Besprechungen oder Anrufaufnahmen für Microsoft-Streams interessiert sind, steht die Meldung „Aufzeichnung abgeschlossen“ in der Funktionalität zur Inhaltssuche für Microsoft Teams zur Verfügung. Compliance-Administratoren können nach dem Stichwort „Aufzeichnung“ in der Betreffzeile des Elements in der Vorschau der Compliance-Inhaltssuche suchen und Besprechungen und Anrufaufnahmen in der Organisation entdecken. Eine Voraussetzung für die Anzeige aller Aufzeichnungen ist, dass sie in Microsoft Stream mit Administratorzugriff ausgestattet werden müssen. Erfahren Sie mehr über das [Zuweisen von Administratorberechtigungen in Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
