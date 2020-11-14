---
title: Aufzeichnung einer Teams-Cloudbesprechung
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Praktische Anleitung für die Bereitstellung von Cloud-Voice-Funktionen in Teams zur Aufzeichnung von Teams-Besprechungen und Gruppengesprächen, um Audio und Video sowie Bildschirmfreigabe-Aktivitäten aufzuzeichnen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2942de5e824d0553ba9d92f445d3635d73f0fe83
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031031"
---
# <a name="teams-cloud-meeting-recording"></a>Aufzeichnung einer Teams-Cloudbesprechung

In Microsoft Teams können Benutzer ihre Besprechungen und Gruppenanrufe aufzeichnen, um Aktivitäten der Audio-, Video- und Bildschirmfreigabe festzuhalten. Es gibt auch eine Option für die automatische Transkription von Aufzeichnungen, sodass Benutzer Besprechungsaufzeichnungen mit Untertiteln wiedergeben und nach wichtigen Diskussionsbeiträgen in der Transkription suchen können. Die Aufzeichnung erfolgt in der Cloud und wird im [Microsoft Stream](https://docs.microsoft.com/stream/) gespeichert, sodass Benutzer sie sicher in ihrer Organisation freigeben können.

Verwandt: [Teams-Besprechungsaufzeichnung, Endbenutzer-Dokumentation](https://aka.ms/recordmeeting)

>[!Note]
> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](tmr-meeting-recording-change.md) erfolgt schrittweise. Bei der Markteinführung können Sie sich optional für diese Erfahrung anmelden. Im November müssen Sie sich abmelden, wenn Sie Stream weiterhin nutzen möchten. Ab Anfang 2021 verlangen wir von allen Kunden die Verwendung von OneDrive for Business und Microsoft Office SharePoint Online für Besprechungsaufzeichnungen.

> [!NOTE]
> Informationen zum Verwenden von Rollen in Teams-Besprechungen und zum Ändern der Rollen von Benutzern finden Sie unter [Rollen in einer Teambesprechung](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Voraussetzungen für die Aufzeichnung von Teams-Cloudbesprechungen.

Damit die Besprechungen eines Team-Benutzers aufgezeichnet werden können, muss Microsoft Stream für den Mandanten aktiviert sein. Darüber hinaus gelten die folgenden Voraussetzungen, die sowohl für den Organisator der Besprechung als auch für die Person, welche die Aufzeichnung initiiert, erforderlich sind:

- Benutzer hat Office 365 E1, E3, E5, a1, a3, A5, Microsoft 365 Business Premium, Business Standard oder Business Basic<sup>1</sup>
- Der Benutzer muss für Microsoft Stream<sup>2</sup> lizenziert sein 
- Der Benutzer hat die Berechtigung zum Hochladen von Videos in Microsoft Stream
- Der Benutzer hat den Unternehmensrichtlinien zugestimmt, falls diese vom Administrator erstellt wurden
- Der Benutzer verfügt über genügend Speicherplatz in Microsoft Stream, um Aufzeichnungen zu speichern
- Der Benutzer hat die TeamsMeetingPolicy-AllowCloudRecording-Einstellung auf „True“ eingestellt
- Der Benutzer ist kein anonymer, Gast- oder Verbundbenutzer in der Besprechung
- Um die Transkription für eine Benutzer Besprechung zu aktivieren, muss die für die Team-Besprechungsrichtlinie, der Sie zugewiesen ist, die-AllowTranscription-Einstellung auf true festgelegt sein.

<sup>1</sup> ab August 20, 2020, wird der Zugriff auf die Besprechungs Aufnahmedatei nach 21 Tagen für Benutzer mit a1 ablaufen. Weitere Informationen finden Sie unter [Hochladen einer Microsoft Teams-Besprechungsaufzeichnung in den Datenstrom](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording).

<sup>2</sup> Benutzer müssen lizenziert werden, um Besprechungen von/zu Microsoft Stream hoch-oder herunterzuladen, Sie benötigen jedoch keine Lizenz zum Aufzeichnen einer Besprechung. Wenn Sie einen Benutzer daran hindern möchten, eine Besprechung aus Microsoft Teams aufzuzeichnen, müssen Sie eine TeamsMeetingPolicy gewähren, die AllowCloudRecording auf $False festgelegt hat.

> [!IMPORTANT] 
> Benutzer benötigen keine Microsoft Stream-Lizenz, wenn sie nur die Möglichkeit haben sollen, Aufzeichnungen mitzuschneiden und herunterzuladen. Dies bedeutet, dass die Aufzeichnungen nicht in Microsoft Stream gespeichert werden, sondern stattdessen in Azure Media Services (AMS) mit einer Höchstgrenze von 21 Tagen gespeichert werden, bevor Sie gelöscht werden. Derzeit kann ein Administrator dies weder steuern noch verwalten, einschließlich der Möglichkeit zum Löschen.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Einrichten der Aufzeichnungsfunktion für Teams-Cloudmeetings für Benutzer in Ihrer Organisation

In diesem Abschnitt wird erläutert, wie die Aufzeichnung von Besprechungen in Teams eingerichtet und geplant wird.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Aktivieren Sie Microsoft Stream für Benutzer in der Organisation

Microsoft Stream ist als Teil der berechtigten Microsoft 365- und Office 365-Abonnements oder als eigenständiger Dienst verfügbar.  Weitere Details finden Sie unter [Übersicht über die Stream-Lizenzierung](https://docs.microsoft.com/stream/license-overview).  Microsoft Stream ist jetzt in Microsoft 365 Business, Microsoft 365 Business Standard und Microsoft 365 Business Basic enthalten.

Erfahren Sie mehr darüber, wie Sie [Benutzern in Microsoft 365 oder Office 365 Lizenzen zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) können, damit Benutzer auf Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft Stream nicht für die Benutzer blockiert ist, wie in [Block Sign-ups für Microsoft Stream](https://docs.microsoft.com/stream/disable-user-organization)definiert.

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Stellen Sie sicher, dass Benutzer die Berechtigung zum Hochladen von Videos in Microsoft Stream haben

Standardmäßig kann jeder Mitarbeiter des Unternehmens in Stream Inhalte erstellen, sobald Stream aktiviert ist und dem Benutzer die Lizenz zugewiesen ist. Ein Microsoft Stream-Administrator kann [Mitarbeiter bei der Erstellung von Inhalten in Stream einschränken](https://docs.microsoft.com/stream/restrict-uploaders). Die Benutzer, die in dieser Liste als „eingeschränkt“ markiert sind, können keine Besprechungen aufzeichnen.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Mitarbeiter in Microsoft Stream dazu auffordern, den Richtlinien des Unternehmens zuzustimmen

Wenn ein Microsoft Stream-Administrator [Unternehmensrichtlinien eingerichtet](https://docs.microsoft.com/stream/company-policy-and-consent) hat und die Mitarbeiter diese Richtlinie vor dem Speichern von Inhalten anerkennen müssen, müssen die Benutzer dies tun, bevor sie in Microsoft Teams aufzeichnen können. Bevor Sie das Aufzeichnungsfeature in der Organisation ausrollen, müssen Sie sicherstellen, dass die Benutzer der Richtlinie zugestimmt haben.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Aktivieren oder Deaktivieren von „Cloud-Aufnahme“

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob Besprechungen zwischen Benutzern aufgezeichnet werden dürfen.

Aktivieren bzw. deaktivieren Sie im Microsoft Teams Admin Center die Einstellung **Zulassen von Cloud-Aufzeichnung** in der Besprechungsrichtlinie. Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Mithilfe von PowerShell konfigurieren Sie die Einstellung „AllowCloudRecording“ in TeamsMeetingPolicy. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Beachten Sie, dass sowohl der Besprechungsorganisator als auch der Initiator der Aufzeichnung über die Berechtigung zum Aufzeichnen der Besprechung verfügen müssen. Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, für die standardmäßig AllowCloudRecording aktiviert ist.

> [!NOTE]
> Weitere Informationen zum Verwenden von Teamrollen zum Konfigurieren der Personen, die über die Berechtigung zum Aufzeichnen einer Besprechung verfügen, finden Sie unter [Rollen in einer Teambesprechung](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Wenn ein Benutzer auf die globale Richtlinie zurückgesetzt werden soll, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinienzuweisung für einen Benutzer zu entfernen:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Verwenden Sie das folgende Cmdlet, um den Wert von AllowCloudRecording in der globalen Richtlinie zu ändern:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
</br>
</br>


|                                                                 Szenario                                                                 |                                                                                                                                                                         Schritte                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Ich möchte, dass alle Benutzer in meinem Unternehmen ihre Besprechungen aufzeichnen können                                    |                                                                     <ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = True aufweist<li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = True </ol>                                                                     |
| Ich möchte, dass die Mehrzahl meiner Benutzer in der Lage ist, ihre Besprechungen aufzuzeichnen, aber selektiv bestimmte Benutzer zu deaktivieren, die nicht dazu in der Lage sein sollen |        <ol><li>Stellen Sie sicher, dass GlobalCsTeamsMeetingPolicy den Eintrag AllowCloudRecording = True aufweist<li>Die meisten Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = True<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = False zugewiesen</ol>         |
|                                                   Ich möchte, dass die Aufzeichnung zu 100% deaktiviert ist                                                   |                                                                <ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist<li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False                                                                 |
|      Ich möchte, dass die Aufzeichnung für die Mehrheit der Benutzer deaktiviert wird und bestimmte Benutzer, denen die Aufzeichnung erlaubt ist, selektiv aktiviert werden       | <ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist<li>Die Mehrzahl aller Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = True zugewiesen <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Wo Ihre Besprechungsaufzeichnungen gespeichert werden

Besprechungsaufzeichnungen werden im Microsoft Stream-Cloudspeicher gespeichert. Aufzeichnungen werden aufbewahrt und können 21 Tage lang angezeigt und heruntergeladen werden. Derzeit ist das Feature für die Besprechungsaufzeichnung von Teams für Kunden ausgeschaltet, deren Teams-Daten inländisch gespeichert werden, falls Microsoft Stream im inländischen Datenbereich, in dem die Daten gespeichert werden, nicht verfügbar ist. In Zukunft wird das Feature für die Besprechungsaufzeichnung von Teams für Kunden eingeschaltet, deren Daten inländisch gespeichert werden, auch wenn Microsoft Stream im inländischen Datenbereich nicht verfügbar ist.

Wenn diese Änderung wirksam wird, werden Besprechungsaufzeichnungen standardmäßig in der nächstgelegenen geografischen Region für Microsoft Stream gespeichert. Wenn Ihre Teams-Daten inländisch gespeichert werden und Sie Besprechungsaufzeichnungen lieber im Inland speichern möchten, empfehlen wir, dass Sie dieses Feature deaktivieren und es erst dann wieder aktivieren, nachdem Microsoft Stream für Ihren Datenaufbewahrungsbereich in Ihrem Land bereitgestellt wurde. Wenn Sie das Feature für alle Benutzer in Ihrer Organisation deaktivieren möchten, deaktivieren Sie in der globalen Teams-Besprechungsrichtlinie, die sich im Microsoft Teams Admin Center befindet, die Einstellung " **Cloud-Aufzeichnung zulassen** ". Wenn Sie jedoch weiterhin möchten, dass Aufzeichnungen in der nächstgelegenen geografischen Region für Microsoft Stream gespeichert werden, müssen Sie die Option **Cloud-Aufzeichnung zulassen** und **Aufzeichnungs Speicher außerhalb der Region zulassen** aktivieren, bevor diese Änderung durchgeführt wird.

Verwenden Sie das folgende Cmdlet, um Aufzeichnungen in der globalen Richtlinie für den Bereich zu aktivieren:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global – AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```


Nachfolgend finden Sie eine Zusammenfassung dessen, was passiert, wenn Sie die Besprechungsaufzeichnung aktivieren, wenn diese Änderung wirksam wird:

|Wenn Sie Besprechungsaufzeichnungen aktivieren|Besprechungsaufzeichnungen werden gespeichert... |
|---|---|
|Bevor Microsoft Stream in Ihrer Region für den nationalen Daten Wohnsitz verfügbar ist |Im nächsten Microsoft-Datenstrom Bereich|
|Nach der Verfügbarkeit von Microsoft Stream in Ihrer Region für den nationalen Daten Wohnsitz |In der Region für den nationalen Daten Wohnsitz|

Bei neuen und vorhandenen Mandanten, die die Besprechungsaufzeichnung noch nicht aktiviert haben, werden neue Aufzeichnungen lokal gespeichert, nachdem Microsoft Stream im lokalen Datenaufbewahrungsbereich zur Verfügung steht. Allerdings wird jeder Mandant, der die Aufzeichnung von Besprechungen ermöglicht, bevor Microsoft Stream in der Region "in-Country-Daten" zur Verfügung steht, weiterhin den Microsoft-Datenstrom Speicher für vorhandene und neue Aufzeichnungen verwenden, auch wenn Microsoft Stream in der Region für den nationalen Daten Wohnsitz verfügbar ist.

Um herauszufinden, in welcher Region Ihre Microsoft Stream-Daten gespeichert werden, klicken Sie in Microsoft Stream auf **?** Klicken Sie in der oberen, rechten Ecke auf **Über Microsoft Stream** und dann auf **Ihre Daten werden gespeichert in**.  Um mehr über die Regionen zu erfahren, in denen Microsoft Stream Daten speichert, lesen Sie [Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Weitere Informationen dazu, wo Daten in Microsoft 365 oder Office 365 in verschiedenen Diensten gespeichert werden, finden Sie unter [wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Aufzeichnungstranskription ein- oder ausschalten

Mit dieser Einstellung wird gesteuert, ob Beschriftungen und Transkriptions Features bei der Wiedergabe von Besprechungsaufzeichnungen zur Verfügung stehen. Wenn Sie diese Option deaktivieren, stehen die Optionen " **Suchen** " und " **CC** " während der Wiedergabe einer Besprechungsaufzeichnung nicht zur Verfügung. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktiviert haben, damit die Aufzeichnung auch Transkription umfasst.

> [!NOTE]
> Diese Transkription für aufgezeichnete Besprechungen wird derzeit nur für Benutzer unterstützt, bei denen die Sprache in Teams auf Englisch festgesetzt ist und wenn Englisch in der Besprechung gesprochen wird. Sie werden zusammen mit den Besprechungsaufzeichnungen im Microsoft Stream-cloudspeicher gespeichert.

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob der Initiator der Besprechung die Wahl haben soll, die Besprechungsaufzeichnung zu transkribieren.

Schalten Sie im Microsoft Teams Admin-Center die Option **Transkription gestatten** in der Besprechungsrichtlinie ein oder aus. Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md#allow-transcription).

Mithilfe von PowerShell konfigurieren Sie die Einstellung „AllowTranscription“ in TeamsMeetingPolicy. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, in der AllowTranscription standardmäßig deaktiviert ist.

Wenn ein Benutzer auf die globale Richtlinie zurückgesetzt werden soll, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinienzuweisung für einen Benutzer zu entfernen:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Verwenden Sie das folgende Cmdlet, um den Wert von AllowCloudRecording in der globalen Richtlinie zu ändern:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```
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

Die Größe einer einstündigen Aufzeichnung beträgt 400 MB. Stellen Sie sicher, dass Sie die für aufgezeichnete Dateien erforderliche Kapazität kennen und über genügend Speicherplatz in Microsoft Stream verfügen.  Lesen Sie die [Übersicht über die Microsoft Stream-Lizenzierung](https://docs.microsoft.com/stream/license-overview) , um den im Abonnement enthaltenen Basisspeicher zu verstehen und zu erfahren, wie Sie zusätzlichen Speicher erwerben.

## <a name="manage-meeting-recordings"></a>Verwalten von Besprechungsaufzeichnungen

Die Besprechungsaufzeichnungen gelten als mandanteneigener Inhalt. Wenn der Besitzer der Aufzeichnung das Unternehmen verlässt, kann der Administrator die Video-URL der Aufzeichnung in Microsoft Stream im Administratormodus öffnen. Der Administrator kann die Aufzeichnung löschen, die Metadaten der Aufzeichnung bearbeiten oder Berechtigungen für das Video der Aufzeichnung ändern. Erfahren Sie mehr über [Administratorfunktionen in Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Weitere Informationen zum Verwalten von Aufzeichnungen und des Benutzerzugriffs finden Sie unter [Verwalten von Benutzerdaten in Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) und [Berechtigungen und Datenschutz in Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Compliance und eDiscovery für Besprechungsaufzeichnungen

Die Besprechungsaufzeichnungen werden in Microsoft Stream gespeichert, der Microsoft 365 und Office 365 Tier-C-kompatibel ist. Um e-Discovery-Anforderungen für Compliance-Administratoren zu unterstützen, die an Besprechungen oder Anrufaufnahmen für Microsoft-Streams interessiert sind, steht die Meldung „Aufzeichnung abgeschlossen“ in der Funktionalität zur Inhaltssuche für Microsoft Teams zur Verfügung. Compliance-Administratoren können nach dem Stichwort „Aufzeichnung“ in der Betreffzeile des Elements in der Vorschau der Compliance-Inhaltssuche suchen und Besprechungen und Anrufaufnahmen in der Organisation entdecken. Eine Voraussetzung für die Anzeige aller Aufzeichnungen ist, dass sie in Microsoft Stream mit Administratorzugriff ausgestattet werden müssen. Erfahren Sie mehr über das [Zuweisen von Administratorberechtigungen in Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
