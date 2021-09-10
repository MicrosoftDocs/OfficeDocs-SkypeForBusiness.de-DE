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
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Praktische Anleitung für die Bereitstellung von Cloud-Voice-Funktionen in Teams zur Aufzeichnung von Teams-Besprechungen und Gruppengesprächen, um Audio und Video sowie Bildschirmfreigabe-Aktivitäten aufzuzeichnen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1e8bc4836cab206389fcc011e4d7a41d2b54f74
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973063"
---
# <a name="teams-cloud-meeting-recording"></a>Aufzeichnung einer Teams-Cloudbesprechung

In Microsoft Teams können Benutzer ihre Besprechungen und Gruppenanrufe aufzeichnen, um Aktivitäten der Audio-, Video- und Bildschirmfreigabe festzuhalten. Es gibt auch eine Option für die automatische Transkription von Aufzeichnungen, sodass Benutzer Besprechungsaufzeichnungen mit Untertiteln wiedergeben und nach wichtigen Diskussionsbeiträgen in der Transkription suchen können. Die Aufzeichnung erfolgt in der Cloud und wird im Microsoft OneDrive for Business und Microsoft Office SharePoint Online gespeichert, sodass Benutzer sie sicher in ihrer Organisation freigeben können.

Wenn eine Besprechung aufgezeichnet wird, erfolgt damit Folgendes automatisch:

- In OneDrive for Business oder SharePoint Online hochgeladen
- Berechtigung für die zur Besprechung eingeladenen Personen
- Im Chat für die Besprechung verknüpft
- Wird auf der Registerkarte "Aufzeichnungen und Transkripte" für die Besprechung im Teams-Kalender angezeigt
- Zu verschiedenen Dateilisten in Microsoft 365 hinzugefügt: Für mich freigegeben, office.com, Empfohlen, Zuletzt verwendet usw.
- Indiziert für Microsoft 365 Suche

Verwandt: [Teams-Besprechungsaufzeichnung, Endbenutzer-Dokumentation](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> Der Wechsel von Microsoft Stream (klassisch) zu OneDrive for Business und SharePoint Online für Besprechungsaufzeichnungen erfolgt automatisch im August 2021. Detaillierte Informationen finden Sie unter [Verwenden von OneDrive for Business und SharePoint Online oder Stream für Besprechungsaufzeichnungen](tmr-meeting-recording-change.md).

> [!NOTE]
> Informationen zur Verwendung von Rollen in Microsoft Teams-Besprechungen und zum Ändern von Benutzerrollen finden Sie unter [Rollen in einer Microsoft Teams-Besprechung](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Informationen zu Aufzeichnungsoptionen für Liveereignisse finden Sie unter [Richtlinien für die Aufzeichnung von Liveereignissen in Microsoft Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Voraussetzungen für die Aufzeichnung von Teams-Cloudbesprechungen.

Damit Besprechungen eines Teams-Benutzers aufgezeichnet werden können, müssen OneDrive for Business und SharePoint Online für den Mandanten aktiviert sein. Darüber hinaus gelten die folgenden Voraussetzungen, die sowohl für den Organisator der Besprechung als auch für die Person, welche die Aufzeichnung initiiert, erforderlich sind:

- Der Benutzer verfügt über ausreichend Speicherplatz in OneDrive for Business, damit Besprechungsaufzeichnungen außerhalb des Kanals gespeichert werden können.

- Der Teams-Kanal verfügt über ausreichend Speicherplatz in SharePoint Online, damit Kanalbesprechungsaufzeichnungen gespeichert werden können.

- Der Benutzer hat die Einstellung `CsTeamsMeetingPolicy -AllowCloudRecording` auf TRUE festgelegt, um Besprechungen und Gruppenanrufe zu erfassen.

- Der Benutzer hat die Einstellung `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` auf TRUE festgelegt, um 1:1-Aufrufe aufzuzeichnen.

- Der Benutzer ist kein anonymer Benutzer, Gast oder Verbundbenutzer in der Besprechung.

- Um die Transkription für die Besprechung eines Benutzers zu aktivieren, muss die Einstellung `-AllowTranscription` in der dem Benutzer zugewiesenen Teams-Besprechungsrichtlinie auf TRUE festgelegt sein.

- Damit die Aufzeichnungen von Kanalbesprechungen so gespeichert werden, dass Kanalmitglieder die Aufzeichnungen nicht bearbeiten oder herunterladen können, muss die Einstellung `CSTeamsMeetingPolicy -ChannelRecordingDownload` auf "Blockieren" gesetzt werden.

> [!IMPORTANT]
>
> OneDrive for Business oder SharePoint Online müssen nicht aktiviert sein, wenn Sie möchten, dass die Benutzer nur aufzeichnen und die Aufzeichnungen herunterladen können. Dies bedeutet, dass die Aufnahmen nicht in OneDrive for Business oder SharePoint Online gespeichert werden, sondern im temporären Teams-Speicher mit einem Limit von 21 Tagen gespeichert werden, bevor sie gelöscht werden. Es handelt sich nicht um etwas, das ein Administrator derzeit steuern, verwalten oder löschen kann.
>
> Weitere [Informationen zur Funktionsweise des temporären Speichers für Besprechungsaufzeichnungen](#temp-storage) finden Sie weiter unten.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Einrichten der Aufzeichnungsfunktion für Teams-Cloudmeetings für Benutzer in Ihrer Organisation

In diesem Abschnitt wird erläutert, wie die Aufzeichnung von Besprechungen in Teams über [Teams-Besprechungsrichtlinien](policy-assignment-overview.md) eingerichtet und geplant wird.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Aktivieren oder Deaktivieren von „Cloud-Aufnahme“

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob Besprechungen zwischen Benutzern aufgezeichnet werden dürfen.

Aktivieren bzw. deaktivieren Sie im Microsoft Teams Admin Center die Einstellung **Zulassen von Cloud-Aufzeichnung** in der Besprechungsrichtlinie. Weitere Informationen finden Sie unter [Einstellungen für Besprechungsrichtlinien für Audio und Video](meetings-policies-recording-and-transcription.md#allow-cloud-recording).

Mithilfe von PowerShell konfigurieren Sie die Einstellung „AllowCloudRecording“ in TeamsMeetingPolicy. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Sowohl der Besprechungsorganisator als auch der Initiator der Aufzeichnung müssen über die Berechtigung zum Aufzeichnen der Besprechung verfügen. Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, in der AllowCloudRecording standardmäßig aktiviert ist.

> [!NOTE]
> Weitere Informationen zur Verwendung von Teams-Rollen zum Konfigurieren der Berechtigung, eine Besprechung aufzuzeichnen, finden Sie unter [Rollen in einer Teams-Besprechung](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Wenn ein Benutzer auf die globale Richtlinie zurückgesetzt werden soll, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinienzuweisung für einen Benutzer zu entfernen:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Verwenden Sie das folgende Cmdlet, um den Wert von AllowCloudRecording in der globalen Richtlinie zu ändern:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|Szenario|Schritte|
|--|--|
| Ich möchte, dass alle Benutzer in meinem Unternehmen ihre Besprechungen aufzeichnen können. | <ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = True aufweist.<li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = True.</ol> |
| Ich möchte, dass die meisten meiner Benutzer in der Lage ist, ihre Besprechungen aufzuzeichnen, aber selektiv bestimmte Benutzer deaktivieren, die nicht dazu in der Lage sein sollen. | <ol><li>Stellen Sie sicher, dass die GlobalCsTeamsMeetingPolicy den Eintrag AllowCloudRecording = True aufweist.<li>Den meisten Benutzer wurde die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = True zugewiesen.<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = False zugewiesen.</ol> |
| Ich möchte, dass die Aufzeichnung zu 100% deaktiviert ist. | <ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist.<li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False. |
| Ich möchte, dass die Aufzeichnung für die Mehrheit der Benutzer deaktiviert wird und bestimmte Benutzer, denen die Aufzeichnung erlaubt ist, selektiv aktiviert werden. | <ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist.<li>Den meisten Benutzern wurde die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False zugewiesen.<li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = True zugewiesen. <ol> |


<a name="bd-channel"></a>
### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>Blockieren oder Zulassen des Downloads von Aufzeichnungen von Kanalbesprechungen

Diese Einstellung steuert, ob Kanalbesprechungen in einem Ordner "Aufzeichnungen" oder in einem Ordner "Aufzeichnungen\Nur anzeigen" im Kanal gespeichert werden. Die Einstellung gilt für die Richtlinie des Benutzers, der die Aufzeichnung für die Kanalbesprechung auswählt.

Die beiden Werte für diese Einstellung sind:

- **Zulassen** (Standard): Speichert Kanalbesprechungsaufzeichnungen in einem Ordner "Aufzeichnungen" im Kanal. Die Berechtigungen für die Aufzeichnungsdateien basieren auf den SharePoint Online-Berechtigungen des Kanals. Dies ist identisch mit jeder anderen Datei, die für den Kanal hochgeladen wird.

- **Blockieren**: Speichert Kanalbesprechungsaufzeichnungen in einem Ordner "Aufzeichnungen\Nur anzeigen" im Kanal. Kanalbesitzer verfügen über vollständige Rechte für die Aufzeichnungen in diesem Ordner, aber Kanalmitglieder haben Lesezugriff, ohne herunterladen zu können.

Konfigurieren Sie die Einstellung ChannelRecordingDownload in TeamsMeetingPolicy mithilfe von PowerShell. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Wenn Sie den Benutzern keine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer die globale Richtlinie, in der ChannelRecordingDownload standardmäßig aktiviert ist.

Wenn ein Benutzer auf die globale Richtlinie zurückgesetzt werden soll, verwenden Sie das folgende Cmdlet, um eine bestimmte Richtlinienzuweisung für einen Benutzer zu entfernen:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Verwenden Sie das folgende Cmdlet, um den Wert von ChannelRecordingDownload in der globalen Richtlinie zu ändern:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> Die ChannelRecordingDownload-Einstellung ist nur in der Teams PowerShell-Modulversion 2.4.1 (Vorschau) oder höher verfügbar. Verwenden Sie den folgenden Befehl, um die neueste Vorschauversion des Moduls herunterzuladen:
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>Aufzeichnungstranskription ein- oder ausschalten

Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Wenn Sie diese Option deaktivieren, stehen die Optionen **Suche** und **CC** während der Wiedergabe einer Besprechungsaufzeichnung nicht zur Verfügung. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktivieren, damit die Aufzeichnung auch eine Transkription enthält.

> [!NOTE]
> Diese Transkription aufgezeichneter Besprechungen wird derzeit nur für Benutzer unterstützt, die die Sprache in Microsoft Teams auf Englisch festgelegt haben, und funktioniert nur, wenn in der Besprechung Englisch gesprochen wird. Sie werden zusammen mit den Besprechungsaufzeichnungen in OneDrive for Business und SharePoint Online-Cloudspeicher gespeichert.

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob der Initiator der Besprechung die Wahl haben soll, die Besprechungsaufzeichnung zu transkribieren.

Schalten Sie im Microsoft Teams Admin-Center die Option **Transkription gestatten** in der Besprechungsrichtlinie ein oder aus. Weitere Informationen finden Sie unter [Einstellungen für Besprechungsrichtlinien für Audio und Video](meetings-policies-recording-and-transcription.md#allow-transcription).

Mithilfe von PowerShell konfigurieren Sie die Einstellung „AllowTranscription“ in TeamsMeetingPolicy. Weitere Informationen hierzu finden Sie unter [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) und [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

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
|Ich möchte, dass alle Benutzer in meinem Unternehmen beim Initiieren einer Besprechungsaufzeichnung transkribieren können. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = True aufweist. <li>Alle Benutzer verfügen über die globale csTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = True. </ol>|
|Ich möchte, dass die meisten meiner Benutzer in der Lage sind, Besprechungsaufzeichnungen zu transkribieren, aber selektiv bestimmte Benutzer deaktivieren, die nicht dazu in der Lage sein sollen. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = True aufweist. <li>Die Mehrheit der Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = True. <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowTranscription = False zugewiesen. </ol>|
|Ich möchte, dass die Transkription der Aufzeichnung zu 100% deaktiviert ist. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = False aufweist. <li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = False. </ol>|
|Ich möchte, dass die Transkription für die Mehrzahl der Benutzer deaktiviert wird, aber selektiv bestimmte Benutzer aktivieren, die in der Lage sind, Aufzeichnungen zu transkribieren. |<ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist. <li>Die Mehrzahl aller Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False. <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = True zugewiesen. </ol>|

### <a name="terms-of-use-acceptance"></a>Zustimmung zu den Nutzungsbedingungen
Wenn Ihre Organisation über eine Besprechungsaufzeichnungsrichtlinie verfügt, die Ihre Benutzer vor der Aufzeichnung einer Besprechung akzeptieren sollen, verwenden Sie das Feature [Azure Active Directory-Nutzungsbedingungen](/azure/active-directory/conditional-access/terms-of-use). Mit diesem Feature können Ihre Benutzer die Nutzungsbedingungen Ihrer Organisation akzeptieren, bevor sie Zugriff auf Microsoft Teams erhalten. Dieses Feature bezieht sich nicht spezifisch auf das Klicken auf die Aufzeichnungsschaltfläche, sondern auf die Verwendung von Teams oder anderen Microsoft 365 Apps insgesamt. Unser Vorschlag ist, die Informationen über Ihre Besprechungsaufzeichnungen zu Ihren allgemeinen Nutzungsbedingungen für die Verwendung von Teams oder Microsoft 365 hinzuzufügen. 

## <a name="permissions-and-storage"></a>Berechtigungen und Speicher

Besprechungsaufzeichnungen werden in OneDrive for Business und SharePoint Online-Cloudspeicher gespeichert. Der Speicherort und die Berechtigungen hängen vom Besprechungstyp und der Rolle des Benutzers in der Besprechung ab. Die auf die Aufzeichnung angewendeten Standardberechtigungen sind unten aufgeführt. Benutzer, die über vollständige Bearbeitungsrechte für die Videoaufzeichnungsdatei verfügen, können die Berechtigungen ändern und später bei Bedarf für andere freigeben.

### <a name="non-channel-meetings"></a>Nicht-Kanalbesprechungen

- Die Aufzeichnung wird in einem Ordner namens **Aufzeichnungen** im OneDrive for Business des Benutzers gespeichert, der auf „Aufzeichnen“ geklickt hat. 

  Beispiel: **Aufzeichnungen**/<i>im OneDrive for Business des Aufzeichners</i>

- Personen, die zur Besprechung eingeladen sind, mit Ausnahme externer Benutzer, erhalten automatisch die Berechtigung für die Aufzeichnungsdatei mit Anzeigezugriff, ohne diese herunterladen zu können.

- Der Besprechungsbesitzer und die Person, die auf „Aufzeichnen“ geklickt hat, erhalten vollständigen Bearbeitungszugriff mit der Möglichkeit, Berechtigungen zu ändern und für andere Personen freizugeben.

### <a name="channel-meetings"></a>Kanalbesprechungen

Wenn `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` auf „Zulassen“ festgelegt ist (Standard):

- Die Aufzeichnung in der Teamwebsite-Dokumentationsbibliothek wird in einem Ordner namens **Aufzeichnungen** gespeichert.

  Beispiel: <i>Name des Teams – Kanalname</i>/**Dokumente**/**Aufzeichnungen**

- Das Mitglied, das auf Aufzeichnung geklickt hat, verfügt über Bearbeitungsrechte auf die Aufzeichnung.

- Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint Online-Berechtigungen des Kanals.

Wenn `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` auf "Blockieren" festgelegt ist:

- Bei Kanalbesprechungen wird die Aufzeichnung in der Teamwebsite-Dokumentationsbibliothek in einem Ordner namens **Aufzeichnungen/Nur anzeigen** gespeichert. 

  Beispiel: <i>Name des Teams – Kanalname</i>/**Nur Dokumente/Aufzeichnungen/Nur Anzeigen**

- Kanalbesitzer verfügen über vollständige Bearbeitungs- und Downloadrechte für die Aufzeichnungen in diesem Ordner.

- Kanalmitglieder haben nur Zugriff auf die Ansicht, ohne herunterladen zu können.

Weitere Informationen zu bestimmten Besprechungstypen finden Sie in der folgenden Tabelle:

| Besprechungstyp  | Wer hat auf "Aufzeichnen" geklickt?| Wo landet die Aufzeichnung? | Wer hat Zugriff? Lese/Schreibzugriff, Lesezugriff oder Freigabe  |
|-------------|-----------------------|------------------------|------------------------|
|1:1-Anruf mit internen Parteien             |Anrufer                 |Das OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist der Besitzer und hat vollständige Rechte. <br /><br />Der Angerufene (wenn im selben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br /> Der Angerufene (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss es für den Angerufenen freigeben.|
|1:1-Anruf mit internen Parteien             |Angerufener                 |Das OneDrive for Business-Konto des Angerufenen                        |Der Angerufene ist der Besitzer und hat vollständige Rechte. <br /><br />Der Anrufer (wenn im selben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br />Der Anrufer (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Angerufene muss es für den Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Anrufer                 |Das OneDrive for Business-Konto des Anrufers                        |Der Anrufer ist der Besitzer und hat vollständige Rechte.<br /> <br />Der Angerufene hat keinen Zugriff. Der Anrufer muss es für den Angerufenen freigeben.|
|1:1-Anruf mit einem externen Anruf             |Angerufener                 |Das OneDrive for Business-Konto des Angerufenen                        |Der Angerufene ist der Besitzer und hat vollständige Rechte.<br /><br />Der Anrufer hat keinen Zugriff. Der Angerufene muss es für den Anrufer freigeben.|
|Gruppenanruf                                 |Jedes Mitglied des Anrufs |Gruppenmitglied, das auf das OneDrive for Business-Konto der Aufzeichnung geklickt hat  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte. <br /><br /> Andere Mitglieder von demselben Mandanten verfügen über Leserechte. <br /><br /> Andere Gruppenmitglieder aus unterschiedlichen Mandanten verfügen über keine Rechte darauf.|
|Spontane/Geplante Besprechung                    |Organisator              |Das OneDrive for Business-Konto des Organisators                     |Der Organisator verfügt über die vollständigen Rechte für die Aufzeichnung. <br /><br /> Alle anderen Mitglieder verfügen über Lesezugriff, ohne herunterladen zu können.|
|Spontane/Geplante Besprechung                    |Anderes Besprechungsmitglied   |Besprechungsmitglied, das auf Aufzeichnung geklickt hat                                  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte auf die Aufzeichnung. <br /><br />Der Organisator verfügt über Bearbeitungsrechte und kann freigeben.<br /><br /> Alle anderen Besprechungsmitglieder verfügen über Lesezugriff, ohne herunterladen zu können.|
|Spontane/Geplante Besprechung mit externen Benutzern|Organisator              |Das OneDrive for Business-Konto des Organisators                     |Der Organisator verfügt über die vollständigen Rechte für die Aufzeichnung.<br /> <br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator verfügen über Lesezugriff, ohne herunterladen zu können. <br /><br /> Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Spontane/Geplante Besprechung mit externen Benutzern|Anderes Besprechungsmitglied   |Mitglied, das auf Aufzeichnung geklickt hat                                  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte auf die Aufzeichnung. Der Organisator verfügt über Bearbeitungsrechte und kann freigeben. <br /><br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator verfügen über Lesezugriff, ohne herunterladen zu können. <br /><br />Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Kanalbesprechung                            |Kanalmitglied         |SharePoint Online-Speicherort von Teams für diesen Kanal                   |Wenn "Set-CsTeamsMeetingPolicy -ChannelRecordingDownload" auf "Zulassen" (Standard) festgelegt ist, verfügt das Mitglied, das auf "Aufzeichnen" geklickt hat, über Bearbeitungsrechte für die Aufzeichnung. Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint Online-Berechtigungen des Kanals.<Br><Br>Wenn "Set-CsTeamsMeetingPolicy -ChannelRecordingDownload" auf "Blockieren" festgelegt ist, haben Kanalbesitzer Vollzugriff auf die Aufzeichnung, aber Kanalmitglieder haben Lesezugriff, ohne herunterladen zu können.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-for-business-and-sharepoint-online"></a>Temporärer Speicher, der nicht in OneDrive for Business und SharePoint Online hochgeladen werden kann

Wenn eine Besprechungsaufzeichnung nicht in OneDrive for Business und SharePoint Online hochgeladen werden kann, steht sie vorübergehend 21 Tage lang über Microsoft Teams zum Download zur Verfügung, bevor sie gelöscht wird. Derzeit kann ein Administrator dies weder steuern noch verwalten, einschließlich der Möglichkeit zum Löschen.

Besprechungsaufzeichnungen können aus den folgenden Gründen in diesem temporären Speicher abgelegt werden:

- Für Besprechungen ohne Kanal, wenn der aufzeichnende Benutzer kein OneDrive for Business eingerichtet hat oder das OneDrive for Business sein Speicherkontingent erreicht hat
- Für eine Kanalbesprechung, wenn die SharePoint Online-Website ihr Speicherkontingent erreicht hat oder die Website noch nicht bereitgestellt wurde
- Wenn bestimmte OneDrive for Business und SharePoint Online-Richtlinien aktiviert sind, schränken Sie Benutzer daran ein, Dateien hochzuladen, wenn sie sich nicht in bestimmten IP-Bereichen befinden usw.

Die Aufzeichnung wird in diesem Fall im temporären Speicher aufbewahrt und sie wird von der Chat-Nachricht selbst beeinflusst. Daher führt das Löschen der Chatnachricht für die Aufzeichnung dazu, dass Benutzer nicht auf die Aufzeichnung zugreifen können. Es gibt zwei Szenarien, die sich hierauf auswirken können:

- **Ein Benutzer löscht die Chatnachricht manuell** – In diesem Szenario können Benutzer, da die ursprüngliche Nachricht nicht mehr vorhanden ist, nicht mehr auf die Aufzeichnung zugreifen, und es sind keine weiteren Downloads mehr möglich. Die Aufzeichnung selbst wird jedoch u. U. noch für eine gewisse Zeit in den internen Systemen von Microsoft aufbewahrt (dabei wird der ursprüngliche Zeitraum von 21 Tagen nicht überschritten).

- **Die Chatnachricht der Aufzeichnung wird über eine Aufbewahrungsrichtlinie für Chats gelöscht** – Aufzeichnungen zur temporären Speicherung sind direkt an die Chataufbewahrungsrichtlinie gebunden. Daher werden Aufzeichnungen im temporären Speicher von Teams standardmäßig 21 Tage aufbewahrt, bevor sie gelöscht werden. Wenn die Chatnachricht aufgrund von Aufbewahrungsrichtlinien für Chatnachrichten vor Ablauf der 21-Tage-Frist gelöscht wird, wird die Aufzeichnung ebenfalls gelöscht. Danach gibt es keine Möglichkeit, die Aufzeichnung wiederherzustellen.

### <a name="planning-for-storage"></a>Planung der Speicheranforderungen

Die Größe einer einstündigen Aufzeichnung beträgt 400 MB. Stellen Sie sicher, dass Sie die für aufgezeichnete Dateien erforderliche Kapazität kennen und über genügend Speicherplatz in Microsoft OneDrive for Business und SharePoint Online verfügen.  Lesen Sie [Festlegen des Standardspeicherplatzes für OneDrive for Business](/onedrive/set-default-storage-space) und [Verwalten von Speicherlimiten für SharePoint Online-Websites](/sharepoint/manage-site-collection-storage-limits), um den im Abonnement enthaltenen Basisspeicher zu verstehen und zu erfahren, wie Sie zusätzlichen Speicher erwerben können.

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Automatisches Ablaufen von Microsoft Teams-Besprechungsaufzeichnungen: 

> [!IMPORTANT]
>
> Das in diesem Artikel beschriebene Feature für das automatische Ablaufen wurde noch nicht veröffentlicht. Nähere Informationen zum Veröffentlichungstermin finden Sie in der [Roadmap (Feature-ID: 84580)](https://www.microsoft.com/microsoft-365/roadmap?searchterms=82057&filters=&searchterms=84580).
> 
> Hier finden Sie Informationen zur Funktionsweise dieses Features in der ZUKUNFT, damit Sie sich auf diese Änderung vorbereiten und die Microsoft Teams-Richtlinieneinstellungen im Voraus entsprechend ändern können.
>
> Der BEFEHL zum präventiven Ändern der Standardablaufeinstellung in Microsoft Teams kann noch nicht festgelegt werden.  Wir veröffentlichen einen aktualisierten Beitrag im Nachrichtencenter, sobald die Einstellung zur Änderung verfügbar ist.
>
>

Lesen Sie Antworten auf häufig gestellte Fragen für Administratoren und Endbenutzer, um Erkenntnisse darüber zu erhalten, wie das automatische Ablaufen von Microsoft Teams-Besprechungsaufzeichnungen funktionieren wird, welche Maßnahmen Sie jetzt ergreifen können und welche nach Veröffentlichung des Features.
  
## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Worin besteht die Änderung?**
  
Wir führen eine Standard-Ablauffrist von 60 Tagen für alle neu erstellten Microsoft Teams-Besprechungsaufzeichnungen ein. Dies bedeutet, dass standardmäßig alle nach dem Aktivieren dieses Features erstellten Microsoft Teams-Besprechungsaufzeichnungen 60 Tage nach dem Erstellungsdatum gelöscht werden. Wenn Administratoren möchten, dass Besprechungsaufzeichnungen früher oder später als die Standardeinstellung ablaufen, können sie die Ablaufeinstellung ändern. Die OneDrive- und SharePoint-Systeme überwachen das Ablaufdatum, das für alle Besprechungsaufzeichnungen festgelegt ist, und verschieben Letztere zum Ablaufdatum automatisch in den Papierkorb.

**Wer ist betroffen?**
  
Alle, die eine Microsoft Teams-Besprechungsaufzeichnung (kanalexterne, Kanal- oder Ad-hoc-Besprechung) in OneDrive oder SharePoint speichern.

**Warum sollte ich dieses Feature verwenden?**
  
Sie sollten dieses Feature verwenden, um den von Microsoft Teams-Besprechungsaufzeichnungen belegten OneDrive- oder SharePoint-Speicherplatz zu beschränken (Hinweis: In der Regel werden etwa 400 MB pro Stunde Aufzeichnung belegt).
  
**Warum wird diese Änderung eingeführt?**
  
Kunden haben auffallend häufig bekundet, dass sie mehr Kontrollmöglichkeiten wünschen, um die Speicherbelegung durch Microsoft Teams-Besprechungsaufzeichnungen zu reduzieren. 99 % davon werden durchschnittlich nach 60 Tagen nie wieder angesehen.
  
**Warum wird dies standardmäßig aktiviert sein?**
  
Wir glauben, dass fast alle Kunden von der verringerten Speicherbelegung in den Mandanten profitieren werden, wenn Aufzeichnungen entfernt werden, die wahrscheinlich nach 60 Tagen nicht mehr angesehen werden. Unser Ziel ist es, allen Kunden standardmäßig ein möglichst optimiertes Benutzererlebnis zu bieten.
  
**Wird sie automatisch gelöscht, auch wenn auf die Daten zugegriffen wird oder sie heruntergeladen werden?**
  
Durch den Zugriff auf die Datei wird das Ablaufdatum nicht geändert.
  
**Ist das Ablaufdatum als Spalte in der Liste sichtbar?**

Benutzer mit Ansichtrechten für die Aufzeichnung werden 14 Tage lang vor Ablauf der Datei neben dieser ein rotes Symbol im OneDrive- oder SharePoint-Ordner sehen. Es gibt derzeit keine Möglichkeit, einer Liste eine Spalte mit den Ablaufdaten hinzuzufügen.
  
**Wie wird das Ablaufdatum berechnet?**
  
Das Ablaufdatum wird als der Tag berechnet, an dem die Besprechungsaufzeichnung erstellt wurde, plus der Standardanzahl von Tagen, die der Administrator in den Microsoft Teams-Einstellungen festgelegt hat.
  
**Kann das Ablaufdatum für jede einzelne Microsoft Teams-Besprechungsaufzeichnung geändert werden, z. B. Ablaufdatum für Daten „A“ 30 Tage und für Daten „B“ 60 Tage?**

Ja, das Ablaufdatum wird pro Datei festgelegt. Benutzer können das Ablaufdatum im Detailbereich einer ausgewählten Datei in OneDrive oder SharePoint ändern.

**Wie kann ein Administrator das Ablaufdatum ändern?**
  
Administratoren können die standardmäßige Ablaufeinstellung in PowerShell oder Teams Admin Center ändern, bevor das Feature freigegeben wird. Die Einstellung kann noch nicht geändert werden. Wir veröffentlichen einen aktualisierten Beitrag im Nachrichtencenter, sobald die Einstellung zur Änderung verfügbar ist. Wenn das Feature veröffentlicht wird, können Administratoren diese Einstellung im Microsoft Teams Admin Center ändern. Das Ändern der Ablaufeinstellungen wirkt sich ab diesem Zeitpunkt nur auf neu erstellte Microsoft Teams-Besprechungsaufzeichnungen aus. Vor diesem Datum erstellte Aufzeichnungen sind nicht betroffen.

Die Werte für die ablaufenden Tage können wie folgt festgelegt werden:
  
- Der Wert kann zwischen 1 und 99.999 (maximal 273 Jahre) liegen.
- Der Wert kann auch -1 sein, damit TMR nie abläuft.

Administratoren können das Ablaufdatum für bestehende Microsoft Teams-Besprechungsaufzeichnungen, die bereits vor der Veröffentlichung dieses Features auf OneDrive oder SharePoint hochgeladen wurden, nicht ändern. Dadurch wird der Absicht des Benutzers Rechnung getragen, der Besitzer der betreffenden Microsoft Teams-Besprechungsaufzeichnung ist.
  
**Kann ein Administrator festlegen, dass TMR nie abläuft?**
  
 Ja, Administratoren können festlegen, dass TMRs nie ablaufen.
  
**Ändert sich durch die Wiedergabe der Aufzeichnung das Ablaufdatum?**

Nein, die Wiedergabe wirkt sich nicht auf das Ablaufdatum aus.
  
**Was geschieht mit dem Ablaufdatum, wenn die Aufzeichnung heruntergeladen und erneut hochgeladen wird?**

Das Ablaufdatum wird nach dem erneuten Hochladen unabhängig von der SKU des Benutzers gelöscht.
  
**Was geschieht, wenn ich die Aufzeichnung an einen anderen Ort oder eine andere Website kopiere oder verschiebe?**

Das Datum wird nur für eine verschobene Aufzeichnungsdatei beibehalten. Für eine kopierte Datei gilt das Ablaufdatum nicht, genau wie für eine erneut hochgeladene Aufzeichnung.
  
**Wie können Endbenutzer das Ablaufdatum für eine bestimmte Microsoft Teams-Besprechungsaufzeichnung ändern?**
  
Jeder Benutzer, der über Bearbeitungs- und Löschberechtigungen für eine bestimmte Microsoft Teams-Besprechungsaufzeichnung verfügt, kann deren Ablaufdatum im Detailbereich der Datei in OneDrive oder SharePoint ändern.

Der Benutzer kann den Ablauf um 14, 30 oder 60 Tage verschieben, ein bestimmtes Datum in der Zukunft auswählen oder festlegen, dass die Datei nie abläuft.
  
**Sollten Administratoren diese Funktion für strikte Sicherheit und Complianceeinhaltung nutzen?**
  
Nein, Administratoren sollten sich nicht auf dieses Feature für den rechtlichen Schutz verlassen, da Endbenutzer das Ablaufdatum aller Aufzeichnungen ändern können, über die sie die Kontrolle haben.
  
**Wird durch dieses Feature die Dateiaufbewahrung erzwungen?**
  
Nein, es werden keine Dateien aufgrund dieses Features oder seiner Einstellungen aufbewahrt. Wenn ein Benutzer mit Löschberechtigungen versucht, eine Microsoft Teams-Besprechungsaufzeichnung mit aktiver Ablaufeinstellung zu löschen, wird die Aufzeichnung gelöscht.

**Hat eine Aufbewahrungs- und/oder Löschrichtlinie, die ich im Security & Compliance Center (S+C) festgelegt habe, Vorrang vor der Ablaufeinstellung für Microsoft Teams-Besprechungsaufzeichnungen?**
  
Ja, alle Richtlinien, die Sie im S+C Center festgelegt haben, haben Vorrang. Hier ein Beispiel:
  
- Wenn eine Ihrer Richtlinie vorsieht, dass alle Dateien auf einer Site 100 Tage lang aufbewahrt werden müssen, und die Ablaufeinstellung für eine Microsoft Teams-Besprechungsaufzeichnung 30 Tage beträgt, wird die Aufzeichnungsdatei für die gesamten 100 Tage aufbewahrt.  
- Wenn eine Löschrichtlinie vorsieht, dass alle Microsoft Teams-Besprechungsaufzeichnungen nach fünf Tagen gelöscht werden und Sie für eine Aufzeichnungsdatei eine Ablauffrist von 30 Tagen festgelegt haben, wird diese Datei nach fünf Tagen gelöscht.

**Was geschieht, wenn eine Microsoft Teams-Besprechungsaufzeichnung "abläuft"?**
  
Am Ablaufdatum wird die Microsoft Teams-Besprechungsaufzeichnung in den OneDrive- oder SharePoint-Papierkorb verschoben, und das Ablaufdatumsfeld wird geleert. Dieser Systemvorgang entspricht dem Löschen der Datei durch einen Benutzer. Der Lebenszyklus im Papierkorb folgt anschließend dem herkömmlichen Ablauf. Wenn der Benutzer die Microsoft Teams-Besprechungsaufzeichnung aus dem Papierkorb wiederherstellt, wird sie von diesem Feature nicht erneut gelöscht, da das Ablaufdatum gelöscht wurde, es sei denn, der Endbenutzer legt ein neues Ablaufdatum für sie fest.
  
**Wie werde ich über das Ablaufen einer Datei in Kenntnis gesetzt?**
  
Allen Benutzern mit Ansichtrechten wird ein Hinweis zum Ablaufdatum in der Aufzeichnungsbenachrichtigung im Microsoft Teams-Chatfenster angezeigt.
  
Alle Benutzer mit Ansichtrechten werden 14 Tage lang vor Ablauf der Datei neben dieser ein rotes Symbol in ihrem OneDrive- oder SharePoint-Ordner sehen.
  
Der Dateibesitzer erhält eine E-Mail-Benachrichtigung, wenn die Microsoft Teams-Besprechungsaufzeichnung abläuft, und wird zum Papierkorb weitergeleitet, um die Microsoft Teams-Besprechungsaufzeichnung eventuell wiederherzustellen.
  
**Welche SKUs sind für dieses Feature erforderlich?**
  
Alle SKUs verfügen standardmäßig über dieses Feature. Bei A1-Benutzern wird die Ablauffrist standardmäßig 30 Tage betragen; diese kann nicht von ihnen geändert werden.
  
**Handelt es sich bei dem Dateiablauf um ein überwachtes Ereignis, und wird es in meinen Überwachungsprotokollen aufscheinen?**
  
Ja, Dateiabläufe werden als Systemlöschereignisse im Überwachungsprotokoll festgehalten.
  
**Was muss ich tun, wenn ich möchte, dass der Administrator die vollständige Kontrolle über den Lebenszyklus von Microsoft Teams-Besprechungsaufzeichnungen hat, und dass Endbenutzer das Ablaufdatum nicht ändern können?**
  
Es wird empfohlen, die S+C-Aufbewahrungs- und/oder Löschrichtlinien zu verwenden, die als Teil der E5-Compliance-SKU verfügbar sind. Dieses Angebot ist auf die Vereinfachung im Zusammenhang mit komplexen Richtlinien und SLA-abhängigen, administrativ-rechtlichen Aspekten ausgerichtet.

Dieses Feature ist nur als einfache Lösung zur Reduzierung der Speicherbelegung durch nicht mehr benötigte Microsoft Teams-Besprechungsaufzeichnungen gedacht.
  
**Wann wird die Datei gelöscht?**
  
Die Datei wird innerhalb von 5 Tagen nach dem Ablaufdatum gelöscht, die genaue Einhaltung wird jedoch nicht gewährleistet.
  
**Werden zukünftige Microsoft Teams-Besprechungsaufzeichnungen, die nach der Veröffentlichung dieses Features aus dem klassischen Stream migriert werden, ebenfalls automatisch ablaufen?**
  
Nein, für migrierte Microsoft Teams-Besprechungsaufzeichnungen wird kein Ablauf festgelegt. Wir empfehlen jedoch Administratoren, nur Microsoft Teams-Besprechungsaufzeichnungen zu migrieren, die sie beibehalten möchten. Weitere Informationen werden in der Migrationsdokumentation enthalten sein.
  
## <a name="manage-meeting-recordings"></a>Verwalten von Besprechungsaufzeichnungen

Besprechungsaufzeichnungen werden als Videodateien in OneDrive for Business und SharePoint Online gespeichert und folgen den Verwaltungs- und Governanceoptionen, die auf diesen Plattformen verfügbar sind. Lesen Sie [SharePoint Online-Governance (Übersicht)](/sharepoint/governance-overview), [OneDrive for Business Leitfaden für Unternehmen](/onedrive/plan-onedrive-enterprise) oder [OneDrive for Business Leitfaden für kleine Unternehmen](/onedrive/one-drive-quickstart-small-business), um weitere Informationen zu erhalten.

Bei Besprechungen, die nicht über einen Kanal abgehalten werden, werden die Aufnahmen im OneDrive for Business des Aufzeichners gespeichert, so dass die Handhabung des Eigentums und der Aufbewahrung nach dem Ausscheiden eines Mitarbeiters dem normalen [OneDrive for Business- und SharePoint Online-Prozess](/onedrive/retention-and-deletion#the-onedrive-deletion-process) folgt.

## <a name="closed-captions-for-recordings"></a>Untertitel für Aufzeichnungen

Untertitel für Teams-Besprechungsaufzeichnungen sind während der Wiedergabe nur verfügbar, wenn der Benutzer die Transkription zum Zeitpunkt der Aufzeichnung aktiviert hatte. Administratoren müssen die [Aufzeichnungstranskription über Richtlinien aktivieren](#turn-on-or-turn-off-recording-transcription) um sicherzustellen, dass ihre Benutzer die Möglichkeit haben, Besprechungen mit Transkription aufzeichnen zu können.

Untertitel helfen dabei, inklusive Inhalte für Zuschauer aller Fähigkeiten zu erstellen. Als Besitzer können Sie Untertitel in der Besprechungsaufzeichnung ausblenden, obwohl das Besprechungsprotokoll weiterhin in Teams verfügbar ist, es sei denn, Sie löschen es dort.

Heute sind Untertitel für die Videoaufzeichnungsdatei mit dem Teams-Besprechungstranskript verknüpft. Dieser Link bleibt in den meisten Fällen für die Lebensdauer der Datei erhalten, kann jedoch unterbrochen werden, wenn die Videodatei innerhalb derselben OneDrive for Business- oder SharePoint Online-Website kopiert wird, was dazu führen würde, dass Untertitel in der kopierten Videodatei nicht verfügbar sind.

Zukünftige Änderungen an dem Link zwischen dem Transkript in Teams und der Aufzeichnung werden hier und in den Benachrichtigungen im Nachrichtencenter klargestellt. Wenn wir in Zukunft Änderungen vornehmen, stellen wir sicher, dass Aufzeichnungsdateien, die älter als 60 Tage sind, das Transkript aus der Besprechung als Beschriftungen anzeigen.

> [!NOTE]
> Es gibt nur englische Untertitel (Besprechungstranskription ist in GCC noch nicht verfügbar).

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>eDiscovery und Compliance für Besprechungsaufzeichnungen

### <a name="ediscovery"></a>eDiscovery

Die Besprechungsaufzeichnungen werden in OneDrive for Business und SharePoint Online gespeichert, was mit Microsoft 365 und Office 365 Tier-D-kompatibel ist. Um e-Discovery-Anforderungen für Compliance-Administratoren zu unterstützen, die an Besprechungen oder Anrufaufnahmen interessiert sind, steht die Meldung „Aufzeichnung abgeschlossen“ in der Funktionalität zur Inhaltssuche für Microsoft Teams zur Verfügung. Compliance-Administratoren können nach dem Stichwort „Aufzeichnung“ in der Betreffzeile des Elements in der Vorschau der Compliance-Inhaltssuche suchen und Besprechungen und Anrufaufnahmen in der Organisation entdecken.

Darüber hinaus kann die Videodatei der Besprechungsaufzeichnung über eDiscovery-Suchen nach Dateien auf SharePoint Online und OneDrive for Business gefunden werden.

Weitere Informationen zu eDiscovery finden Sie im Artikel [eDiscovery-Lösungen für Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Mithilfe der ProgID-Eigenschaft können Sie automatische Aufbewahrungsbezeichnungen nur auf Videodateien von Aufzeichnungen von Teams-Besprechungen anwenden. Weitere Informationen finden Sie unter [Automatisches Anwenden einer Aufbewahrungsbezeichnung für Teams-Besprechungsaufzeichnungen](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

### <a name="data-loss-prevention-dlp-policies"></a>Richtlinien zur Verhinderung von Datenverlust (DLP)

Sie können DLP-Richtlinien auch über die ProgID-Eigenschaft auf Besprechungsaufzeichnungsdateien anwenden. Legen Sie in der DLP-Regel für Dateien in SharePoint Online und OneDrive for Business folgende Bedingungen fest:

- Document-Eigenschaft = *ProgID*
- Value = *Media.Meeting*

Weitere Informationen zu DLP finden Sie im Artikel [Informationen zur Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
