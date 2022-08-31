---
title: Verwalten von Besprechungsrichtlinien für Aufzeichnung und Transkription
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für die Aufzeichnung und Transkription verwalten.
ms.openlocfilehash: 57e90984cde312f1804d5d2144c82a4d252822b6
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466203"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Besprechungsrichtlinieneinstellungen für die Aufzeichnung & Transkription

In diesem Artikel werden die Besprechungsrichtlinieneinstellungen für die Aufzeichnung und Transkription in einer Teams-Besprechung beschrieben. Diese Einstellungen finden Sie im Team Admin Center unter den **Richtlinien für Besprechungsbesprechungen** > .

## <a name="transcription"></a>Transkription

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktiviert haben, damit diese Features mit der Aufzeichnung funktionieren können.

Wenn Sie diese Einstellung aktivieren, wird eine Kopie des Transkripts erstellt, das mit der Besprechungsaufzeichnung gespeichert wird. Dadurch werden für die Besprechungsaufzeichnung **"Suchen"**, **"Cc"** und **"Transkripte"** aktiviert.

Die Transkription für aufgezeichnete Besprechungen wird derzeit nur für Benutzer unterstützt, die ihre Sprache in Teams-Besprechungen festlegen oder Englisch sprechen.

## <a name="cloud-recording"></a>Cloudaufzeichnung

Diese Einstellung ist eine Kombination aus einer Organisator- und Benutzerrichtlinie und steuert, ob die Besprechungen aufgezeichnet werden können. Die Aufzeichnung kann vom Besprechungsorganisator oder von einem anderen Besprechungsteilnehmer gestartet werden, wenn die Richtlinieneinstellung für den Teilnehmer aktiviert ist, und wenn es sich um einen authentifizierten Benutzer aus derselben Organisation handelt.

Personen außerhalb Ihrer Organisation, z. b. Partner- oder anonyme Benutzer, können die Aufzeichnung nicht starten. Gäste können die Aufzeichnung nicht starten oder beenden.

![Screenshot mit Aufzeichnungsoptionen](media/meeting-policies-recording.png)

Sehen Sie sich das folgende Beispiel an.

| Benutzer                 | Besprechungsrichtlinie         | Cloud-Aufnahme zulassen |
|----------------------|------------------------|-----------------------|
| Daniela              | Global                 | Aus                   |
| Amalia               | Location1MeetingPolicy | Ein                    |
| John (extern) | Nicht zutreffend         | Nicht zutreffend        |

- Von Daniela organisierte Besprechungen können nicht aufgezeichnet werden.
- Amanda kann keine von Daniela organisierten Besprechungen aufzeichnen.
- Von Amanda organisierte Besprechungen können aufgezeichnet werden.
- Daniela kann keine von Amanda organisierten Besprechungen aufzeichnen.
- John kann keine von Amanda organisierten Besprechungen aufzeichnen.

Näheres zur Aufzeichnung von Cloud-Besprechungen erfahren Sie unter [Aufzeichnen von Microsoft Teams-Cloudbesprechungen](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>Besprechungen laufen automatisch ab

Diese Einstellung steuert, ob Besprechungsaufzeichnungen automatisch ablaufen. Nachdem Sie diese Einstellung aktiviert haben, erhalten Sie die Möglichkeit, eine Standardablaufzeit (gemessen in Tagen) festzulegen.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Screenshot der Einstellung für den automatischen Ablauf von Besprechungen im Teams Admin Center.":::

Diese Einstellung bietet Ihnen ein einfaches Tool, mit dem die Speichermenge reduziert wird, die ältere Aufzeichnungen verwenden. Das OneDrive- und SharePoint-System überwacht den Ablaufsatz für alle Besprechungsaufzeichnungen und verschiebt Aufzeichnungen automatisch an ihrem Ablaufdatum in den Papierkorb.

### <a name="default-expiration-time"></a>Standardablaufzeit

Alle neu erstellten Besprechungsaufzeichnungen haben einen Standardablauf von 120 Tagen. alle Aufzeichnungen, die nach dem Aktivieren dieses Features erstellt wurden, werden 120 Tage nach ihrem Erstellungsdatum gelöscht.

> [!NOTE]
> Die maximale Standardablaufzeit für A1-Benutzer beträgt 30 Tage.

#### <a name="changing-default-expiration-time"></a>Ändern der Standardablaufzeit

Administratoren können die Einstellung für die Standardablaufzeit in PowerShell oder im Teams Admin Center bearbeiten. Alle Änderungen wirken sich ab diesem Zeitpunkt nur noch auf neu erstellte Besprechungsaufzeichnungen aus. sie wirken sich nicht auf Aufzeichnungen aus, die vor diesem Datum erstellt wurden.

Administratoren können die Ablaufzeit für vorhandene Besprechungsaufzeichnungen nicht ändern. Dies geschieht, um die Entscheidung des Benutzers zu schützen, der die Aufzeichnung besitzt. Sowohl Besprechungen als auch Anrufe können durch diese Einstellung gesteuert werden.

Der Ablaufwert ist eine ganze Zahl für Tage.  Dies kann wie folgt festgelegt werden:

- Mindestwert: **1**
- Höchstwert: **99999**
- Sie können die Ablaufzeit auch in PowerShell auf **-1** festlegen, damit die Aufzeichnungen nie ablaufen.

Beispiel für einen PowerShell-Befehl:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Compliance

Sie sollten sich aus rechtlichem Schutz nicht auf Besprechungsablaufeinstellungen verlassen, da Endbenutzer das Ablaufdatum aller aufzeichnungen ändern können, die sie steuern.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Aufzeichnungsablaufeinstellungen und Microsoft 365-Aufbewahrungsrichtlinien in Microsoft Purview

Die Aufbewahrung von Dateien hat Vorrang vor dem Löschen von Dateien. Eine Teams-Besprechungsaufzeichnung mit einer Purview-Aufbewahrungsrichtlinie kann erst nach Abschluss des Aufbewahrungszeitraums von einer Ablaufrichtlinie für Teams-Besprechungsaufzeichnungen gelöscht werden. Wenn Sie beispielsweise über eine Purview-Aufbewahrungsrichtlinie verfügen, die besagt, dass eine Datei fünf Jahre lang aufbewahrt wird und eine Ablaufrichtlinie für Teams-Besprechungsaufzeichnungen für 60 Tage festgelegt ist, löscht die Ablaufrichtlinie für Teams-Besprechungsaufzeichnungen die Aufzeichnung nach fünf Jahren.

Wenn Sie über eine Ablaufrichtlinie für Teams-Besprechungsaufzeichnungen und eine Purview-Löschrichtlinie mit unterschiedlichen Löschdaten verfügen, wird die Datei frühestens zu den beiden Datumsangaben gelöscht. Wenn Sie beispielsweise über eine Purview-Löschrichtlinie verfügen, die besagt, dass eine Datei nach einem Jahr gelöscht wird und der Ablauf einer Teams-Besprechungsaufzeichnung 120 Tage lang festgelegt ist, löscht die Ablaufrichtlinie für Teams-Besprechungsaufzeichnungen die Datei nach 120 Tagen.

Benutzer können ihre Aufzeichnungen vor dem Ablaufdatum manuell löschen, es sei denn, es gibt eine Purview-Aufbewahrungsrichtlinie, die dies verhindert.

### <a name="deletion-of-recordings"></a>Löschen von Aufzeichnungen

Die Aufzeichnung wird in der Regel innerhalb eines Tages nach dem Ablaufdatum gelöscht, in seltenen Fällen kann dies jedoch bis zu fünf Tage dauern. Der Dateibesitzer erhält eine E-Mail-Benachrichtigung, wenn die Aufzeichnung abläuft, und wird zum Papierkorb geleitet, um die Aufzeichnung wiederherzustellen.

> [!NOTE]
> Am Ablaufdatum wird die Aufzeichnung in den Papierkorb verschoben, und das Ablaufdatumsfeld wird gelöscht. Wenn Sie die Aufzeichnung aus dem Papierkorb wiederherstellen, wird sie von diesem Feature nicht erneut gelöscht, da das Ablaufdatum gelöscht wurde.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Ablauf der migrierten Aufzeichnungen von Stream (klassisch)

Migrierte Aufzeichnungen aus Stream (klassisch) enthalten keinen Ablaufsatz. Stattdessen empfehlen wir Administratoren, nur Aufzeichnungen zu migrieren, die sie aufbewahren möchten. Weitere Details finden Sie in [der Stream (klassisch) Migrationsdokumentation](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Speichern von Aufzeichnungen außerhalb Ihres Landes oder Ihrer Region

Diese Richtlinie steuert, ob Besprechungsdatensätze dauerhaft in einem anderen Land oder einer anderen Region gespeichert werden können. Wenn sie aktiviert ist, können die Aufzeichnungen nicht migriert werden. Weitere Informationen zu Cloudbesprechungen und wo Aufzeichnungen gespeichert werden, finden Sie unter [Teams Cloud Meeting Recording](cloud-recording.md).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)
- [Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
- [Aufzeichnung von Cloudbesprechungen](cloud-recording.md)
- [Verwalten, wer Besprechungen planen kann](manage-who-can-schedule-meetings.md)
