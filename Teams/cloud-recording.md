---
title: Aufzeichnung einer Teams-Cloudbesprechung
ms.author: mabond
author: mkbond007
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
ms.openlocfilehash: 1360847f187d98118d0b5468638cf1d6eb215fb8
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706862"
---
# <a name="teams-cloud-meeting-recording"></a>Aufzeichnung einer Teams-Cloudbesprechung

In Microsoft Teams können Benutzer ihre Besprechungen und Gruppenanrufe aufzeichnen, um Aktivitäten der Audio-, Video- und Bildschirmfreigabe festzuhalten. Es gibt auch eine Option für die automatische Transkription von Aufzeichnungen, sodass Benutzer Besprechungsaufzeichnungen mit Untertiteln wiedergeben und nach wichtigen Diskussionsbeiträgen in der Transkription suchen können. Die Aufzeichnung erfolgt in der Cloud und wird in OneDrive und SharePoint gespeichert, sodass Benutzer sie sicher in ihrer Organisation freigeben können.

Wenn eine Besprechung aufgezeichnet wird, erfolgt damit Folgendes automatisch:

- Hochgeladen zu OneDrive oder SharePoint
- Berechtigung für die zur Besprechung eingeladenen Personen
- Im Chat für die Besprechung verknüpft
- Wird auf der Registerkarte "Aufzeichnungen und Transkripte" für die Besprechung im Teams-Kalender angezeigt
- Zu verschiedenen Dateilisten in Microsoft 365 hinzugefügt: Für mich freigegeben, office.com, Empfohlen, Zuletzt verwendet usw.
- Indiziert für Microsoft 365 Suche

Verwandt: [Teams-Besprechungsaufzeichnung, Endbenutzer-Dokumentation](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> Der Wechsel von Microsoft Stream (klassisch) zu OneDrive und SharePoint für Besprechungsaufzeichnungen wird im August 2021 automatisch erfolgen. Detaillierte Informationen finden Sie unter [Verwenden von OneDrive und SharePoint oder Stream für Besprechungsaufzeichnungen](tmr-meeting-recording-change.md).

> [!NOTE]
> Informationen zur Verwendung von Rollen in Microsoft Teams-Besprechungen und zum Ändern von Benutzerrollen finden Sie unter [Rollen in einer Microsoft Teams-Besprechung](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Informationen zu Aufzeichnungsoptionen für Liveereignisse finden Sie unter [Richtlinien für die Aufzeichnung von Liveereignissen in Microsoft Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Voraussetzungen für die Aufzeichnung von Teams-Cloudbesprechungen.

Damit Besprechungen eines Teams-Benutzers aufgezeichnet werden können, müssen OneDrive und SharePoint für den Mandanten aktiviert sein. Darüber hinaus gelten die folgenden Voraussetzungen, die sowohl für den Organisator der Besprechung als auch für die Person, welche die Aufzeichnung initiiert, erforderlich sind:

- Der Benutzer verfügt über ausreichend Speicherplatz in OneDrive, damit Besprechungsaufzeichnungen außerhalb des Kanals gespeichert werden können.

- Der Teams-Kanal verfügt über ausreichend Speicherplatz in SharePoint, damit Kanalbesprechungsaufzeichnungen gespeichert werden können.

- Der Benutzer hat die Einstellung `CsTeamsMeetingPolicy -AllowCloudRecording` auf TRUE festgelegt, um Besprechungen und Gruppenanrufe zu erfassen.

- Der Benutzer hat die Einstellung `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` auf TRUE festgelegt, um 1:1-Aufrufe aufzuzeichnen.

- Der Benutzer ist kein anonymer Benutzer, Gast oder Verbundbenutzer in der Besprechung.

- Um die Transkription für die Besprechung eines Benutzers zu aktivieren, muss die Einstellung `-AllowTranscription` in der dem Benutzer zugewiesenen Teams-Besprechungsrichtlinie auf TRUE festgelegt sein.

- Damit die Aufzeichnungen von Kanalbesprechungen so gespeichert werden, dass Kanalmitglieder die Aufzeichnungen nicht bearbeiten oder herunterladen können, muss die Einstellung `CSTeamsMeetingPolicy -ChannelRecordingDownload` auf "Blockieren" gesetzt werden.

> [!IMPORTANT]
>
> Benutzer müssen OneDrive oder SharePoint nicht aktiviert haben, wenn Sie wollen, dass Benutzer nur Aufzeichnungen erstellen und sie herunterladen können. Dies bedeutet, dass die Aufzeichnungen nicht in OneDrive oder SharePoint gespeichert werden, sondern im temporären Teams-Speicher mit einem Limit von 21 Tagen, bevor sie gelöscht werden. Es handelt sich nicht um etwas, das ein Administrator derzeit steuern, verwalten oder löschen kann.
>
> Weitere [Informationen zur Funktionsweise des temporären Speichers für Besprechungsaufzeichnungen](#temp-storage) finden Sie weiter unten.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Einrichten der Aufzeichnungsfunktion für Teams-Cloudmeetings für Benutzer in Ihrer Organisation

In diesem Abschnitt wird erläutert, wie die Aufzeichnung von Besprechungen in Teams über [Teams-Besprechungsrichtlinien](policy-assignment-overview.md) eingerichtet und geplant wird.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Aktivieren oder Deaktivieren von „Cloud-Aufnahme“

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob Besprechungen zwischen Benutzern aufgezeichnet werden dürfen.

Aktivieren oder deaktivieren Sie im Microsoft Teams-Admin Center die Einstellung **Zulassen von Cloud-Aufnahmen** in der Besprechungsrichtlinie. Weitere Informationen finden Sie unter [Einstellungen für Besprechungsrichtlinien für Audio und Video](meetings-policies-recording-and-transcription.md#cloud-recording).

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

- **Zulassen** (Standard): Speichert Kanalbesprechungsaufzeichnungen in einem Ordner "Aufzeichnungen" im Kanal. Die Berechtigungen für die Aufzeichnungsdateien basieren auf den SharePoint-Berechtigungen des Kanals. Dies ist identisch mit jeder anderen Datei, die für den Kanal hochgeladen wird.

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

Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktiviert haben, damit diese Features mit der Aufzeichnung funktionieren können.
  
Wenn Sie diese Einstellung aktivieren, wird eine Kopie des Transkripts erstellt, das mit der Besprechungsaufzeichnung gespeichert wird. Dadurch werden für die Besprechungsaufzeichnung **"Suchen"**, **"Cc"** und **"Transkripte"** aktiviert.

> [!NOTE]
> Diese Transkription für aufgezeichnete Besprechungen wird derzeit nur unterstützt für: Englisch (USA), Englisch (Kanada), Englisch (Indien), Englisch (Vereinigtes Königreich), Englisch (Australien), Englisch (Neuseeland), Arabisch (Vereinigte Arabische Emirate), Arabisch (Saudi-Arabien), Chinesisch (vereinfacht, China), Chinesisch (traditionell, Hongkong SAR), Chinesisch (traditionell, Taiwan), Tschechisch (Tschechien), Dänisch (Dänemark), Niederländisch (Belgien), Niederländisch (Niederlande), Französisch (Kanada), Französisch (Frankreich), Finnisch (Finnland) , Deutsch (Deutschland), Griechisch (Griechenland), Hebräisch (Israel), Hindi (Indien), Ungarisch (Ungarn), Italienisch (Italien), Japanisch (Japan), Koreanisch (Südkorea), Norwegisch (Norwegen), Polnisch (Polen), Portugiesisch (Brasilien), Portugiesisch (Portugal), Rumänisch (Rumänien), Russisch (Russland), Slowakisch (Slowakei), Spanisch (Mexiko), Spanisch (Spanien), Schwedisch (Schweden), Thailändisch (Thailand), Türkisch (Türkei), Ukrainisch (Ukraine), Vietnamesisch (Vietnam). Sie werden zusammen mit den Besprechungsaufzeichnungen im OneDrive- und SharePoint-Cloudspeicher gespeichert.

Sie können das Microsoft Teams-Admin Center oder PowerShell dazu verwenden, um eine Teams-Besprechungsrichtlinie festzulegen, um zu steuern, ob der Initiator der Besprechung die Wahl haben soll, die Besprechungsaufzeichnung zu transkribieren.

Schalten Sie im Microsoft Teams Admin-Center die Option **Transkription gestatten** in der Besprechungsrichtlinie ein oder aus. Weitere Informationen finden Sie unter [Einstellungen für Besprechungsrichtlinien für Audio und Video](meetings-policies-recording-and-transcription.md#transcription).

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

|Szenario|Schritte |
|---|---|
|Ich möchte, dass alle Benutzer in meinem Unternehmen beim Initiieren einer Besprechungsaufzeichnung transkribieren können. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = True aufweist. <li>Alle Benutzer verfügen über die globale csTeamsMeetingPolicy oder eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = True. </ol>|
|Ich möchte, dass die meisten meiner Benutzer in der Lage sind, Besprechungsaufzeichnungen zu transkribieren, aber selektiv bestimmte Benutzer deaktivieren, die nicht dazu in der Lage sein sollen. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = True aufweist. <li>Die Mehrheit der Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = True. <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowTranscription = False zugewiesen. </ol>|
|Ich möchte, dass die Transkription der Aufzeichnung zu 100% deaktiviert ist. |<ol><li>Stellen Sie sicher, dass die globale CsTeamsMeetingPolicy den Eintrag AllowTranscription = False aufweist. <li>Alle Benutzer verfügen über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowTranscription = False. </ol>|
|Ich möchte, dass die Transkription für die Mehrzahl der Benutzer deaktiviert wird, aber selektiv bestimmte Benutzer aktivieren, die in der Lage sind, Aufzeichnungen zu transkribieren. |<ol><li>Stellen Sie sicher, dass Global CsTeamsMeetingPolicy den Eintrag AllowCloudRecording = False aufweist. <li>Die Mehrzahl aller Benutzer verfügt über die globale CsTeamsMeetingPolicy ODER eine der CsTeamsMeetingPolicy-Richtlinien mit AllowCloudRecording = False. <li>Allen anderen Benutzern wurde eine der CsTeamsMeetingPolicy-Richtlinien mit dem Eintrag AllowCloudRecording = True zugewiesen. </ol>|

### <a name="terms-of-use-acceptance"></a>Zustimmung zu den Nutzungsbedingungen

Wenn Ihre Organisation über eine Besprechungsaufzeichnungsrichtlinie verfügt, die Ihre Benutzer vor der Aufzeichnung einer Besprechung akzeptieren sollen, verwenden Sie das Feature [Azure Active Directory-Nutzungsbedingungen](/azure/active-directory/conditional-access/terms-of-use). Mit diesem Feature können Ihre Benutzer die Nutzungsbedingungen Ihrer Organisation akzeptieren, bevor sie Zugriff auf Microsoft Teams erhalten. Dieses Feature bezieht sich nicht spezifisch auf das Klicken auf die Aufzeichnungsschaltfläche, sondern auf die Verwendung von Teams oder anderen Microsoft 365 Apps insgesamt. Unser Vorschlag ist, die Informationen über Ihre Besprechungsaufzeichnungen zu Ihren allgemeinen Nutzungsbedingungen für die Verwendung von Teams oder Microsoft 365 hinzuzufügen.

### <a name="set-a-custom-privacy-policy-url"></a>Festlegen einer benutzerdefinierten Datenschutzrichtlinien-URL

Als Administrator können Sie die Teams-Aufzeichnung und die Datenschutzrichtlinien-URL für Transkriptionen mit einem benutzerdefinierten Link für Ihre Organisation aktualisieren. Sie können dies im [Azure AD Admin Center](https://aad.portal.azure.com) mit den folgenden Schritten tun:

1. Melden Sie sich beim Azure AD Admin Center an.
1. Wechseln Sie zu **Azure Active Directory** > **-Eigenschaften**.
1. Aktualisieren Sie **das URL-Feld der Datenschutzbestimmungen** mit dem Link zu Ihrer Datenschutzrichtlinie.

> [!NOTE]
> Wenn Sie dieses Feld für Ihre Organisation bereits aktualisiert haben, müssen Sie keine Änderungen vornehmen.

Nach dem Hinzufügen Ihrer Datenschutzrichtlinien-URL wird die standardmäßige Datenschutzerklärung für die Aufzeichnung und Transkription von Teams-Besprechungen durch die neue URL ersetzt, die von Ihrer Organisation bereitgestellt wird.

> [!NOTE]
> Anonyme, Gast- und Verbundbenutzer, die an Teams-Besprechungen teilnehmen, die von Ihrer Organisation gehostet werden, verfügen weiterhin über die Standarddatenschutzrichtlinie für die Aufzeichnung und Transkription von Teams-Besprechungen.

## <a name="permissions-and-storage"></a>Berechtigungen und Speicher

Besprechungsaufzeichnungen werden im OneDrive- und SharePoint-Cloudspeicher gespeichert. Der Speicherort und die Berechtigungen hängen vom Besprechungstyp und der Rolle des Benutzers in der Besprechung ab. Die auf die Aufzeichnung angewendeten Standardberechtigungen sind unten aufgeführt. Benutzer, die über vollständige Bearbeitungsrechte für die Videoaufzeichnungsdatei verfügen, können die Berechtigungen ändern und später bei Bedarf für andere freigeben.

### <a name="non-channel-meetings"></a>Nicht-Kanalbesprechungen

- Die Aufzeichnung wird in einem Ordner namens **Aufzeichnungen** im OneDrive des Benutzers gespeichert, der auf „Aufzeichnen“ geklickt hat. 

  Beispiel: *OneDrive-Aufzeichnungen*/ des **Recorders**

- Personen, die zur Besprechung eingeladen sind, mit Ausnahme externer Teilnehmer, erhalten automatisch die Berechtigung für die Aufzeichnungsdatei mit Anzeigezugriff, ohne die Möglichkeit zum Herunterladen.

- Der Besprechungsbesitzer und die Person, die auf „Aufzeichnen“ geklickt hat, erhalten vollständigen Bearbeitungszugriff mit der Möglichkeit, Berechtigungen zu ändern und für andere Personen freizugeben.

### <a name="channel-meetings"></a>Kanalbesprechungen

Wenn `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` auf „Zulassen“ festgelegt ist (Standard):

- Die Aufzeichnung in der Teamwebsite-Dokumentationsbibliothek wird in einem Ordner namens **Aufzeichnungen** gespeichert.

  Beispiel: *Teams-Name – Kanalname*/**Dokumente**/**Aufzeichnungen**

- Das Mitglied, das auf Aufzeichnung geklickt hat, verfügt über Bearbeitungsrechte auf die Aufzeichnung.

- Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint-Berechtigungen des Kanals.

Wenn `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` auf "Blockieren" festgelegt ist:

- Bei Kanalbesprechungen wird die Aufzeichnung in der Teamwebsite-Dokumentationsbibliothek in einem Ordner namens **Aufzeichnungen/Nur anzeigen** gespeichert. 

  Beispiel: *Teams-Name – Nur Kanalname*/**Dokumente/Aufzeichnungen/Ansicht**

- Kanalbesitzer verfügen über vollständige Bearbeitungs- und Downloadrechte für die Aufzeichnungen in diesem Ordner.

- Kanalmitglieder haben schreibgeschützten Zugriff, ohne die Möglichkeit zum Herunterladen.

Weitere Informationen zu bestimmten Besprechungstypen finden Sie in der folgenden Tabelle:

| Besprechungstyp  | Wer hat auf "Aufzeichnen" geklickt?| Wo landet die Aufzeichnung? | Wer hat Zugriff? Lese/Schreibzugriff, Lesezugriff oder Freigabe  |
|-------------|-----------------------|------------------------|------------------------|
|1:1-Anruf mit internen Parteien             |Anrufer                 |OneDrive-Konto des Anrufers                        |Der Anrufer ist der Besitzer und hat vollständige Rechte. <br /><br />Der Angerufene (wenn im selben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br /> Der Angerufene (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Anrufer muss es für den Angerufenen freigeben.|
|1:1-Anruf mit internen Parteien             |Angerufener                 |OneDrive-Konto des Angerufenen                        |Der Angerufene ist der Besitzer und hat vollständige Rechte. <br /><br />Der Anrufer (wenn im selben Mandanten) verfügt über schreibgeschützten Zugriff. Kein Freigabezugriff. <br /><br />Der Anrufer (wenn in einem anderen Mandanten) hat keinen Zugriff. Der Angerufene muss es für den Anrufer freigeben.|
|1:1-Anruf mit einem externen Anruf             |Anrufer                 |OneDrive-Konto des Anrufers                        |Der Anrufer ist der Besitzer und hat vollständige Rechte.<br /> <br />Der Angerufene hat keinen Zugriff. Der Anrufer muss es für den Angerufenen freigeben.|
|1:1-Anruf mit einem externen Anruf             |Angerufener                 |OneDrive-Konto des Angerufenen                        |Der Angerufene ist der Besitzer und hat vollständige Rechte.<br /><br />Der Anrufer hat keinen Zugriff. Der Angerufene muss es für den Anrufer freigeben.|
|Gruppenanruf                                 |Jedes Mitglied des Anrufs |Gruppenmitglied, das auf das OneDrive-Konto der Aufzeichnung geklickt hat  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte. <br /><br /> Andere Mitglieder von demselben Mandanten verfügen über Leserechte. <br /><br /> Andere Gruppenmitglieder aus unterschiedlichen Mandanten verfügen über keine Rechte darauf.|
|Spontane/Geplante Besprechung                    |Organisator              |OneDrive-Konto des Organisators                     |Der Organisator verfügt über die vollständigen Rechte für die Aufzeichnung. <br /><br /> Alle anderen Mitglieder verfügen über Lesezugriff, ohne herunterladen zu können.|
|Spontane/Geplante Besprechung                    |Anderes Besprechungsmitglied   |Besprechungsmitglied, das auf Aufzeichnung geklickt hat                                  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte auf die Aufzeichnung. <br /><br />Der Organisator verfügt über Bearbeitungsrechte und kann freigeben.<br /><br /> Alle anderen Besprechungsmitglieder verfügen über Lesezugriff, ohne herunterladen zu können.|
|Spontane/Geplante Besprechung mit externen Teilnehmern|Organisator              |OneDrive-Konto des Organisators                     |Der Organisator verfügt über die vollständigen Rechte für die Aufzeichnung.<br /> <br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator verfügen über Lesezugriff, ohne herunterladen zu können. <br /><br /> Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Spontane/Geplante Besprechung mit externen Teilnehmern|Anderes Besprechungsmitglied   |Mitglied, das auf Aufzeichnung geklickt hat                                  |Ein Mitglied, das auf Aufzeichnung geklickt hat, verfügt über vollständige Rechte auf die Aufzeichnung. Der Organisator verfügt über Bearbeitungsrechte und kann freigeben. <br /><br /> Alle anderen Besprechungsmitglieder aus demselben Mandanten wie der Organisator verfügen über Lesezugriff, ohne herunterladen zu können. <br /><br />Alle anderen externen Mitglieder haben keinen Zugriff, und der Organisator muss sie für sie freigeben.|
|Kanalbesprechung                            |Kanalmitglied         |SharePoint-Speicherort von Teams für diesen Kanal                   |Wenn "Set-CsTeamsMeetingPolicy -ChannelRecordingDownload" auf "Zulassen" (Standard) festgelegt ist, verfügt das Mitglied, das auf "Aufzeichnen" geklickt hat, über Bearbeitungsrechte für die Aufzeichnung. Die Berechtigungen jedes anderen Mitglieds basieren auf den SharePoint-Berechtigungen des Kanals.<Br><Br>Wenn "Set-CsTeamsMeetingPolicy -ChannelRecordingDownload" auf "Blockieren" festgelegt ist, haben Kanalbesitzer Vollzugriff auf die Aufzeichnung, aber Kanalmitglieder haben Lesezugriff, ohne herunterladen zu können.|

<a name="temp-storage"></a>

### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>Temporärer Speicher, wenn kein Upload auf OneDrive und SharePoint möglich ist

Wenn eine Besprechungsaufzeichnung nicht in OneDrive und SharePoint hochgeladen werden kann, steht sie vorübergehend 21 Tage lang über Teams zum Download zur Verfügung, bevor sie gelöscht wird. Derzeit kann ein Administrator dies weder steuern noch verwalten, einschließlich der Möglichkeit zum Löschen.

Besprechungsaufzeichnungen können aus den folgenden Gründen in diesem temporären Speicher abgelegt werden:

- Für Nicht-Kanal-Besprechungen, wenn der aufzeichnende Benutzer nicht über OneDrive verfügt, oder wenn sein OneDrive das Speicherkontingent erreicht hat
- Für eine Kanalbesprechung, wenn die SharePoint-Website ihr Speicherkontingent erreicht hat, oder wenn die Website noch nicht bereitgestellt wurde
- Wenn bestimmte OneDrive- und SharePoint-Richtlinien aktiviert sind, beschränken sie Benutzer dabei, Dateien hochzuladen, wenn sie sich nicht in bestimmten IP-Bereichen usw. befinden.

Die Aufzeichnung wird in diesem Fall im temporären Speicher aufbewahrt und sie wird von der Chat-Nachricht selbst beeinflusst. Daher führt das Löschen der Chatnachricht für die Aufzeichnung dazu, dass Benutzer nicht auf die Aufzeichnung zugreifen können. Es gibt zwei Szenarien, die sich hierauf auswirken können:

- **Ein Benutzer löscht die Chatnachricht manuell** – In diesem Szenario können Benutzer, da die ursprüngliche Nachricht nicht mehr vorhanden ist, nicht mehr auf die Aufzeichnung zugreifen, und es sind keine weiteren Downloads mehr möglich. Die Aufzeichnung selbst wird jedoch u. U. noch für eine gewisse Zeit in den internen Systemen von Microsoft aufbewahrt (dabei wird der ursprüngliche Zeitraum von 21 Tagen nicht überschritten).

- **Die Chatnachricht der Aufzeichnung wird über eine Aufbewahrungsrichtlinie für Chats gelöscht** – Aufzeichnungen zur temporären Speicherung sind direkt an die Chataufbewahrungsrichtlinie gebunden. Daher werden Aufzeichnungen im temporären Speicher von Teams standardmäßig 21 Tage aufbewahrt, bevor sie gelöscht werden. Wenn die Chatnachricht aufgrund von Aufbewahrungsrichtlinien für Chatnachrichten vor Ablauf der 21-Tage-Frist gelöscht wird, wird die Aufzeichnung ebenfalls gelöscht. Danach gibt es keine Möglichkeit, die Aufzeichnung wiederherzustellen.

### <a name="planning-for-storage"></a>Planung der Speicheranforderungen

Die Größe einer einstündigen Aufzeichnung beträgt 400 MB. Stellen Sie sicher, dass Sie die für aufgezeichnete Dateien erforderliche Kapazität kennen und über genügend Speicherplatz in OneDrive und SharePoint verfügen.  Lesen Sie [Festlegen des Standardspeicherplatzes für OneDrive](/onedrive/set-default-storage-space) und [Verwalten von Speicherlimits für SharePoint-Websites](/sharepoint/manage-site-collection-storage-limits), um den im Abonnement enthaltenen Basisspeicher zu verstehen und zu erfahren, wie Sie zusätzlichen Speicher erwerben können.
  
## <a name="manage-meeting-recordings"></a>Verwalten von Besprechungsaufzeichnungen

Besprechungsaufzeichnungen werden als Videodateien in OneDrive und SharePoint gespeichert und folgen den Verwaltungs- und Governanceoptionen, die auf diesen Plattformen verfügbar sind. Weitere Informationen finden Sie in [SharePoint-Governanceübersicht](/sharepoint/governance-overview).

Für Nicht-Kanal-Besprechungen werden die Aufnahmen im OneDrive des Aufzeichnenden gespeichert, so dass der Umgang mit dem Eigentum und der Aufbewahrung nach dem Ausscheiden eines Mitarbeiters dem normalen [OneDrive- und SharePoint-Prozess](/onedrive/retention-and-deletion#the-onedrive-deletion-process) folgt.

Besprechungsaufzeichnungen haben eine Standardablaufzeit von 120 Tagen. Sie können die Einstellung für das automatische Ablaufen von Besprechungen deaktivieren oder die Standardablaufzeit ändern. Erfahren Sie mehr darüber [, wie Besprechungsaufzeichnungen automatisch ablaufen](meetings-policies-recording-and-transcription.md#meetings-automatically-expire).

## <a name="closed-captions-for-recordings"></a>Untertitel für Aufzeichnungen

Untertitel für Teams-Besprechungsaufzeichnungen sind während der Wiedergabe nur verfügbar, wenn der Benutzer die Transkription zum Zeitpunkt der Aufzeichnung aktiviert hatte. Administratoren müssen die [Aufzeichnungstranskription über Richtlinien aktivieren](#turn-on-or-turn-off-recording-transcription) um sicherzustellen, dass ihre Benutzer die Möglichkeit haben, Besprechungen mit Transkription aufzeichnen zu können.

Untertitel helfen dabei, inklusive Inhalte für Zuschauer aller Fähigkeiten zu erstellen. Als Besitzer können Sie Untertitel in der Besprechungsaufzeichnung ausblenden, obwohl das Besprechungsprotokoll weiterhin in Teams verfügbar ist, es sei denn, Sie löschen es dort.

Heute sind Untertitel für die Aufzeichnungsvideodatei mit dem Teams-Besprechungstranskript verknüpft. Dieser Link bleibt in den meisten Fällen für die Lebensdauer der Datei bestehen, kann aber gebrochen werden, wenn die Videodatei innerhalb derselben OneDrive- oder SharePoint-Website kopiert wird, was dazu führen würde, dass die Untertitel für die kopierte Videodatei nicht verfügbar wären.

Zukünftige Änderungen an dem Link zwischen dem Transkript in Teams und der Aufzeichnung werden hier und in den Benachrichtigungen im Nachrichtencenter klargestellt. Sollten wir in Zukunft Änderungen vornehmen, werden wir sicherstellen, dass bei Aufzeichnungsdateien, die weniger als 60 Tage alt sind, das Transkript der Besprechung als Untertitel angezeigt wird.

> [!NOTE]
> Die Transkription von Besprechungen ist in GCC noch nicht verfügbar.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>eDiscovery und Compliance für Besprechungsaufzeichnungen

### <a name="ediscovery"></a>eDiscovery

Die Besprechungsaufzeichnungen werden in OneDrive und SharePoint gespeichert, was mit Microsoft 365 und Office 365 Stufe-D kompatibel ist. Um e-Discovery-Anforderungen für Compliance-Administratoren zu unterstützen, die an Besprechungen oder Anrufaufnahmen interessiert sind, steht die Meldung „Aufzeichnung abgeschlossen“ in der Funktionalität zur Inhaltssuche für Microsoft Teams zur Verfügung. Compliance-Administratoren können nach dem Stichwort „Aufzeichnung“ in der Betreffzeile des Elements in der Vorschau der Compliance-Inhaltssuche suchen und Besprechungen und Anrufaufnahmen in der Organisation entdecken.

Darüber hinaus kann die Videodatei der Besprechungsaufzeichnung über eDiscovery-Suchen nach Dateien auf SharePoint und OneDrive gefunden werden.

Weitere Informationen zu eDiscovery finden Sie im Artikel [eDiscovery-Lösungen für Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Mithilfe der ProgID-Eigenschaft können Sie automatische Aufbewahrungsbezeichnungen nur auf Videodateien von Aufzeichnungen von Teams-Besprechungen anwenden. Weitere Informationen finden Sie unter [Automatisches Anwenden einer Aufbewahrungsbezeichnung für Teams-Besprechungsaufzeichnungen](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings).

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Microsoft Purview-Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Sie können DLP-Richtlinien auch über die ProgID-Eigenschaft auf Besprechungsaufzeichnungsdateien anwenden. Legen Sie in der DLP-Regel für Dateien in SharePoint und OneDrive die Bedingungen wie folgt fest:

- Document-Eigenschaft = *ProgID*
- Value = *Media.Meeting*

Weitere Informationen zu DLP finden Sie im Artikel [Informationen zur Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="meeting-recording-diagnostic-tools"></a>Diagnosetools für Besprechungsaufzeichnungen

### <a name="user-cannot-record-meetings"></a>Benutzer kann keine Besprechungen aufzeichnen

Als Administrator können Sie das folgende Diagnosetool verwenden, um zu überprüfen, ob der Benutzer ordnungsgemäß zum Aufzeichnen einer Besprechung in Teams konfiguriert ist:

1. Wählen Sie unten **Tests ausführen** aus, um das Diagnosetool im Microsoft 365 Admin füllen.

   > [!div class="nextstepaction"]
   > [Ausführen von Tests: Besprechungsaufzeichnung](https://aka.ms/MeetingRecordingDiag)

2. Geben Sie im Bereich „Diagnose ausführen“ im Feld **Benutzername oder E-Mail-** die E-Mail-Adresse des Benutzers ein, der keine Besprechungen aufzeichnen kann, und wählen Sie dann **Test ausführen** aus.

3. Die Tests geben die besten nächsten Schritte für alle Mandanten- oder Richtlinienkonfigurationen an, um zu überprüfen, ob der Benutzer ordnungsgemäß für die Aufzeichnung einer Besprechung in Teams konfiguriert ist.
  
### <a name="meeting-record-is-missing"></a>Besprechungsdatensatz fehlt

Wenn Sie ein Administrator sind, können Sie mit dem folgenden Diagnosetool überprüfen, ob die Besprechungsaufzeichnung erfolgreich abgeschlossen wurde und basierend auf der Besprechungs-ID und der Startzeit der Aufzeichnung in Stream oder OneDrive hochgeladen wurde:

1. Wählen Sie unten **Tests ausführen** aus, um das Diagnosetool im Microsoft 365 Admin füllen.

   > [!div class="nextstepaction"]
   > [Ausführen von Tests: Fehlende Besprechungsaufzeichnung](https://aka.ms/MissingRecordingDiag)

2. Geben Sie im Diagnosebereich "Ausführen" die URL der Besprechung in die **URL der Besprechung ein, die aufgezeichnet wurde** (in der Regel in der Besprechungseinladung enthalten) sowie das Datum der Besprechung im Feld **"Wann wurde die Besprechung aufgezeichnet? ",** und wählen Sie dann **"Tests ausführen**" aus.

3. Die Tests überprüfen, ob die Besprechungsaufzeichnung erfolgreich abgeschlossen und in Stream oder OneDrive hochgeladen wurde.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
