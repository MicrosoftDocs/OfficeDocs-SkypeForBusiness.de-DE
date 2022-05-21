---
title: Musik im Haltebereich
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
description: Erfahren Sie, wie Sie das Feature Musik im Haltebereich in Telefonsystem verwalten.
ms.openlocfilehash: 4899ffd2a3b6bfda80164ca2df4a5460a2b005e2
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624242"
---
# <a name="music-on-hold"></a>Musik im Haltebereich

Wenn ein Microsoft Teams Benutzer einen eingehenden Anruf in den Haltebereich setzt, kann der Anrufer ausgewählte Musik hören.

Die wiedergegebene Musik ist entweder die von Microsoft bereitgestellte Standardmusik oder benutzerdefinierte Musik, die Sie hochladen und konfigurieren. Als Mandantenadministrator konfigurieren Sie, ob Musik im Haltebereich verfügbar ist, indem Sie eine Teams Anrufrichtlinie erstellen und die Richtlinie dem Teams Benutzer zuweisen.

Die Standardmusik, die in Microsoft Teams Anrufszenarien bereitgestellt wird, ist frei von Gebühren, die von Ihrer Organisation zu zahlen sind.

Beachten Sie, dass Anrufer auch in anderen Szenarien auf Musik im Haltebereich lauschen können, z. B. wenn sie sich in eine Cloudanrufwarteschleife einwähnen oder wenn ihr Anruf von einem Microsoft Teams Benutzer geparkt wird. Diese Szenarien werden von den in diesem Artikel erwähnten Features nicht abgedeckt oder gesteuert.

## <a name="configure-music-on-hold"></a>Konfigurieren von Musik im Haltebereich

So konfigurieren Sie Musik im Haltebereich:

1.  Wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **voIP-> Anrufrichtlinien**.

2.  Wählen Sie auf der Registerkarte " **Richtlinien verwalten** " eine der vorhandenen Richtlinien aus, oder erstellen Sie eine neue Richtlinie.

3.  Wählen Sie im **Feld Musik im Haltebereich für PSTN-Anrufer** im Dropdownmenü "**Aktiviert**" aus.

Sie können Musik im Haltebereich auch mithilfe des Teams PowerShell-Moduls konfigurieren. Ändern Sie in "TeamsCallingPolicy" den Parameter "MusicOnHoldEnabledType" in "Enabled", und gewähren Sie diese Richtlinieninstanz dann einem oder mehreren Benutzern.

Wenn ein Teams Benutzer über eine Teams Anrufrichtlinie verfügt, bei der Musik auf "Deaktiviert" festgelegt ist, wird keine Musik wiedergegeben, wenn der Teams Benutzer den Anruf in den Haltebereich setzt.

## <a name="configure-custom-music"></a>Konfigurieren von benutzerdefinierter Musik

Zusätzlich zur Wiedergabe von Standardmusik für Anrufer können Sie eine benutzerdefinierte Audiodatei mit Musik oder anderen Audioinhalten hochladen und diese Audiodatei so konfigurieren, dass sie für den Anrufer wiedergegeben wird.
Eine Abteilung oder Organisation möchte z. B. eine benutzerdefinierte Ankündigung oder benutzerdefinierte Musik wiedergeben, wenn externe PSTN-Anrufer in den Haltebereich gesetzt werden.  

> [!NOTE]
> Sie sind für das unabhängige Löschen und Sichern aller erforderlichen Rechte und Berechtigungen zur Verwendung von Musik- oder Audiodateien mit Ihrem Microsoft Teams-Dienst verantwortlich. Dies kann geistiges Eigentum und andere Rechte an Musik, Soundeffekten, Audio, Marken, Namen und anderen Inhalten in der Audiodatei aller relevanten Rechteinhaber umfassen. Zu den Inhabern können Künstler, Schauspieler, Interpreten, Musiker, Songwriter, Komponisten, Plattenlabels, Musikverleger, Gewerkschaften, Gilden, Rechtegesellschaften, Verwertungsgesellschaften und alle anderen Parteien gehören, die Die Urheberrechte, Soundeffekte, Audio- und andere Rechte an geistigem Eigentum besitzen, kontrollieren oder lizenzieren.

Um benutzerdefinierte Musik im Haltebereich zu konfigurieren, verwenden Sie die PowerShell-Cmdlets "New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy" und "Import/Get/Remove/Export-CsOnlineAudioFile" in Teams PowerShell-Modul 3.0.0 oder höher.

Unterstützte Audioformate und maximale Dateigröße finden Sie unter [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)


1. Stellen Sie sicher, dass der Teams Benutzer Musik für PSTN-Anrufer in der Teams Anrufrichtlinie auf "Aktiviert" festgelegt hat. 

2. Hochladen der benutzerdefinierten Audiodatei.

3. Erstellen Sie eine Teams Richtlinie für den Anrufspeicher, die auf die benutzerdefinierte Audiodatei verweist, und weisen Sie sie dem Teams Benutzer zu.

### <a name="upload-the-custom-audio-file"></a>Hochladen der benutzerdefinierten Audiodatei

Die Konfiguration der benutzerdefinierten Musik im Haltebereich beginnt mit dem Hochladen der Audiodatei. Zu diesem Zweck verwenden Sie das PowerShell-Cmdlet [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Nachfolgend sehen Sie ein Beispiel für das Hochladen einer MP3-Audiodatei mit Windows PowerShell 5.1. Weitere Beispiele finden Sie unter [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Verweisen auf die Audiodatei in einer Teams Richtlinie zum Anhalten von Anrufen

Nachdem Sie die Audiodatei hochgeladen haben, müssen Sie auf die Datei in einer Teams Richtlinie für den Anrufspeicher verweisen, indem Sie die ID der Datei verwenden, wenn Sie eine Teams Richtlinie für den Anrufspeicher erstellen oder festlegen. Zum Beispiel: 

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Nachdem Sie die neue Teams Anrufwarterichtlinie erstellt haben, können Sie sie Ihren Benutzern mithilfe Grant-CsTeamsCallHoldPolicy wie folgt gewähren:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Verwenden Sie das cmdlet Get-CsOnlineAudioFile, um Informationen zu Ihren hochgeladenen Audiodateien abzurufen.

Verwenden Sie das cmdlet Remove-CsOnlineAudioFile, um eine hochgeladene Audiodatei zu entfernen. Überprüfen Sie vor dem Entfernen einer Audiodatei, ob Sie diese Audiodatei nicht in einer TeamsCallHoldPolicy verwenden.

Verwenden Sie das cmdlet Export-CsOnlineAudioFile, um eine hochgeladene Audiodatei zu exportieren.

## <a name="feature-availability"></a>Verfügbarkeit von Features

Die folgende Tabelle zeigt, welche Features auf welchen Clients und Geräten Musik im Haltebereich und benutzerdefinierte Musik im Haltebereich unterstützt werden. Microsoft fügt weiterhin Featureunterstützung hinzu. Überprüfen Sie daher häufig nach zusätzlicher Verfügbarkeit.


| Feature | Desktop <br> Windows/Mac OS | Browser | Mobil <br> iOS | Mobil <br> Android | Teams Telefon |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 1:1 PSTN-Anruf halten | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich |
| Halten Sie 1:1 Teams Anruf | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich |
| Halten Sie den Beratungstransfer bei einem PSTN-Anruf von 1:1 |-Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich || -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich |
| Halten Sie die Beratungsübertragung am 1:1-Teams-Anruf fest |-Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich || -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich | -Musik im Haltebereich<br>-Benutzerdefinierte Musik im Haltebereich |

## <a name="restrictions"></a>Einschränkungen

- Musik on Hold ist nur in kommerziellen und GCC Cloud-Instanzen verfügbar.

- Musik im Haltebereich ist nur verfügbar, wenn sich der Benutzer im TeamsOnly-Modus befindet.

- Wenn der aufgerufene Teams Benutzer für Location-Based Routing aktiviert ist, kann Musik im Haltebereich für den Anrufer nicht wiedergegeben werden.

- Benutzerdefinierte Musik im Haltebereich ist nicht für Benutzer verfügbar, die für die gemeinsame Liniendarstellung (Delegierung) und die Verwendung des Parkens von Anrufen konfiguriert sind. Die Standard-Musik im Haltebereich wird wiedergegeben.

- In einigen Szenarien wird ein Direct Routing-Medienumgehungsaufruf für die Wiedergabe von Musik im Haltebereich in die Nicht-Medienumgehung konvertiert, und der Anruf bleibt als Nicht-Medienumgehung, bis der Anruf beendet wird.

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

