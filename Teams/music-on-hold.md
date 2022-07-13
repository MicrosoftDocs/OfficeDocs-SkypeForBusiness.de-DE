---
title: Wartemusik
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: Erfahren Sie, wie Sie das Feature "Musik im Haltebereich" im Telefonsystem verwalten.
ms.openlocfilehash: 9d8fa247ffdc982c5d41777c68f6b620a92644e3
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773754"
---
# <a name="music-on-hold"></a>Wartemusik

Wenn ein Microsoft Teams-Benutzer einen eingehenden Anruf in den Haltebereich setzt, kann der Anrufer ausgewählte Musik hören.

Die wiedergegebene Musik ist entweder die von Microsoft bereitgestellte Standardmusik oder benutzerdefinierte Musik, die Sie hochladen und konfigurieren. Als Mandantenadministrator konfigurieren Sie, ob "Musik im Haltebereich" verfügbar ist, indem Sie eine Teams-Anrufrichtlinie erstellen und die Richtlinie dem Teams-Benutzer zuweisen.

Die in Microsoft Teams-Anrufszenarien bereitgestellte Standardmusik ist frei von Gebühren, die von Ihrer Organisation zu zahlen sind.

Beachten Sie, dass Anrufer auch in anderen Szenarien Musik im Haltebereich hören können. beispielsweise, wenn sie sich in eine Cloud-Anrufwarteschleife einwähnen oder wenn ihr Anruf von einem Microsoft Teams-Benutzer geparkt wird. Diese Szenarien werden von den in diesem Artikel erwähnten Features nicht abgedeckt oder gesteuert.

## <a name="configure-music-on-hold"></a>Konfigurieren von Wartemusik

So konfigurieren Sie "Wartemusik":

1. Wechseln Sie im linken Navigationsbereich des Teams Admin Centers zu **voIP-> Anrufrichtlinien**.

2. Wählen Sie auf der Registerkarte " **Richtlinien verwalten** " eine der vorhandenen Richtlinien aus, oder erstellen Sie eine neue Richtlinie.

3. Wählen Sie im Feld **"Wartemusik für PSTN-Anrufer** " im Dropdownmenü " **Aktiviert** " aus.

Sie können "Wartemusik" auch mithilfe des Teams PowerShell-Moduls konfigurieren. Ändern Sie in "TeamsCallingPolicy" den Parameter "MusicOnHoldEnabledType" in "Enabled", und gewähren Sie diese Richtlinieninstanz dann einem oder mehreren Benutzern.

Wenn ein Teams-Benutzer eine Teams-Anrufrichtlinie mit deaktivierter Wartemusik hat, wird keine Musik wiedergegeben, wenn der Teams-Benutzer den Anruf in den Haltebereich setzt.

## <a name="configure-custom-music"></a>Konfigurieren von benutzerdefinierter Musik

Zusätzlich zur Wiedergabe von Standardmusik für Anrufer können Sie eine benutzerdefinierte Audiodatei mit Musik oder anderen Audioinhalten hochladen und diese Audiodatei so konfigurieren, dass sie für den Anrufer wiedergegeben wird.
Eine Abteilung oder Organisation möchte z. B. eine benutzerdefinierte Ankündigung oder benutzerdefinierte Musik wiedergeben, wenn externe PSTN-Anrufer in den Haltebereich gesetzt werden.

Die Konfiguration erfolgt mithilfe von Anrufhalterichtlinien.

> [!NOTE]
> Sie sind für das unabhängige Löschen und Sichern aller erforderlichen Rechte und Berechtigungen zur Verwendung von Musik oder Audiodateien mit Ihrem Microsoft Teams-Dienst verantwortlich. Dies kann geistiges Eigentum und andere Rechte an Musik, Soundeffekten, Audio, Marken, Namen und anderen Inhalten in der Audiodatei aller relevanten Rechteinhaber umfassen. Zu den Inhabern können Künstler, Schauspieler, Interpreten, Musiker, Songwriter, Komponisten, Plattenlabels, Musikverleger, Gewerkschaften, Gilden, Rechtegesellschaften, Verwertungsgesellschaften und alle anderen Parteien gehören, die Die Urheberrechte, Soundeffekte, Audio- und andere Rechte an geistigem Eigentum besitzen, kontrollieren oder lizenzieren.

### <a name="use-the-teams-admin-center"></a>Verwenden des Teams Admin Centers
Sie können das Teams Admin Center verwenden, um benutzerdefinierte Wartemusik für Ihre Benutzer zu konfigurieren, indem Sie Richtlinien für die Anrufwarteschleife erstellen oder bearbeiten.

So konfigurieren Sie eine neue Anrufhalterichtlinie:

1. Wechseln Sie im Teams Admin Center zu **den Aufbewahrungsrichtlinien für** **VoIP-Anrufe** > .

2. Wählen Sie die Registerkarte **"Hinzufügen** " aus.

3. Geben Sie der Richtlinie einen Namen und eine Beschreibung.

4. Wählen Sie **"Datei hochladen** " aus, um die benutzerdefinierte Musikaudiodatei hochzuladen.

5. Wählen Sie **"Übernehmen" aus**.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufhalterichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>Verwenden von PowerShell
Um benutzerdefinierte Wartemusik zu konfigurieren, verwenden Sie die PowerShell-Cmdlets New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy und Import/Get/Remove/Export-CsOnlineAudioFile in Teams PowerShell-Modul 3.0.0 oder höher.

Unterstützte Audioformate und maximale Dateigröße finden Sie unter [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Stellen Sie sicher, dass für den Teams-Benutzer "Musik im Haltebereich" für PSTN-Anrufer in der Teams-Anrufrichtlinie auf "Aktiviert" festgelegt ist. 

2. Laden Sie die benutzerdefinierte Audiodatei hoch.

3. Erstellen Sie eine Teams-Anrufhalterichtlinie, die auf die benutzerdefinierte Audiodatei verweist, und weisen Sie sie dem Teams-Benutzer zu.

### <a name="upload-the-custom-audio-file"></a>Hochladen der benutzerdefinierten Audiodatei

Die Konfiguration der benutzerdefinierten Wartemusik beginnt mit dem Hochladen der Audiodatei. Zu diesem Zweck verwenden Sie das PowerShell-Cmdlet [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Nachfolgend sehen Sie ein Beispiel für das Hochladen einer MP3-Audiodatei mit Windows PowerShell 5.1. Weitere Beispiele finden Sie unter [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Verweisen auf die Audiodatei in einer Microsoft Teams-Anrufhalterichtlinie

Nachdem Sie die Audiodatei hochgeladen haben, müssen Sie mithilfe der ID der Datei auf die Datei in einer Teams-Anrufhalterichtlinie verweisen, wenn Sie eine Teams-Anrufhalterichtlinie erstellen oder festlegen. Zum Beispiel: 

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Nachdem Sie die neue Microsoft Teams-Richtlinie für die Anrufsicherung erstellt haben, können Sie sie Ihren Benutzern mithilfe von Grant-CsTeamsCallHoldPolicy wie folgt gewähren:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Verwenden Sie das cmdlet Get-CsOnlineAudioFile, um Informationen zu Ihren hochgeladenen Audiodateien abzurufen.

Verwenden Sie das cmdlet Remove-CsOnlineAudioFile, um eine hochgeladene Audiodatei zu entfernen. Überprüfen Sie vor dem Entfernen einer Audiodatei, ob Sie diese Audiodatei nicht in einer TeamsCallHoldPolicy verwenden.

Verwenden Sie das cmdlet Export-CsOnlineAudioFile, um eine hochgeladene Audiodatei zu exportieren.

## <a name="feature-availability"></a>Verfügbarkeit von Features

In der folgenden Tabelle ist aufgeführt, welche Features auf welchen Clients und Geräten "Music on Hold" und "Custom Music on Hold" unterstützt werden. Microsoft fügt weiterhin Featureunterstützung hinzu. Überprüfen Sie daher häufig nach zusätzlicher Verfügbarkeit.

| Feature | Desktop <br> Windows/Mac OS | Browser | Mobil <br> iOS | Mobil <br> Android | Teams-Telefon |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 1:1 PSTN-Anruf halten | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik |
| Halten Sie den 1:1-Teams-Anruf gedrückt | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik |
| Halten Sie den Beratungstransfer bei einem PSTN-Anruf von 1:1 |-Wartemusik<br>-Benutzerdefinierte Wartemusik || -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik |
| Halten Sie die Beratungsübertragung am 1:1 Teams-Anruf fest |-Wartemusik<br>-Benutzerdefinierte Wartemusik || -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik | -Wartemusik<br>-Benutzerdefinierte Wartemusik |

## <a name="restrictions"></a>Einschränkungen

- Wartemusik ist nur in kommerziellen und GCC-Cloudinstanzen verfügbar.

- Wartemusik ist nur verfügbar, wenn sich der Benutzer im TeamsOnly-Modus befindet.

- Wenn der aufgerufene Teams-Benutzer für Location-Based Routing aktiviert ist, kann dem Anrufer keine Wartemusik wiedergegeben werden.

- Benutzerdefinierte Wartemusik ist nicht für Benutzer verfügbar, die für die gemeinsame Liniendarstellung (Delegierung) konfiguriert sind und wenn das Parken von Anrufen verwendet wird. Die Standard-Wartemusik wird wiedergegeben.

- In einigen Szenarien wird ein Direct Routing-Medienumgehungsaufruf für die Wiedergabe von Wartemusik in eine Nicht-Medienumgehung konvertiert, und der Anruf bleibt als Nicht-Medienumgehung, bis der Anruf beendet wird.

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
