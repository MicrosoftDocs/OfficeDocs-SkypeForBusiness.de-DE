---
title: Musik im Halteraum
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
description: Erfahren Sie, wie Sie die Musik im Halteschleifenfeature in Telefonsystem.
ms.openlocfilehash: d3fa7188e3d2320ba4eeb17ca95d28d1f57c18c4
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767408"
---
# <a name="music-on-hold"></a>Musik im Halteraum

Wenn ein Microsoft Teams einen eingehenden Anruf aus dem öffentlichen Telefonnetz (PSTN) in den Halte haltet, kann der PSTN-Anrufer ausgewählte Musik hören.

Bei der Abgespielten Musik handelt es sich entweder um die von Microsoft bereitgestellte Standardmusik oder um benutzerdefinierte Musik, die Sie hochladen und konfigurieren. Als Mandantenadministrator konfigurieren Sie, ob das Musik verfügbar ist, indem Sie eine Teams-Anrufrichtlinie erstellen und die Richtlinie dem benutzer Teams zuweisen.

Die in den PSTN Microsoft Teams-Anrufszenarien bereitgestellte Standardmusik ist frei von Lizenzgebühren, die Ihre Organisation zu zahlen hat.

Beachten Sie, dass PSTN-Anrufer Musik-On-Hold auch in anderen Szenarien hören können, z. B. wenn sie sich in eine Cloud-Anrufwarteschleife einrufen oder wenn ihr Anruf von einem Microsoft Teams-Benutzer geparkt wird. Diese Szenarien werden nicht von den in diesem Artikel erwähnten Features behandelt oder gesteuert.

## <a name="configure-music-on-hold"></a>Konfigurieren Musik im Halteraum

So konfigurieren Musik im Halteraum:

1.  Navigieren Sie in der linken Navigationsleiste Teams Admin Center zu **Richtlinien für Sprachanrufe >**.

2.  Wählen Sie **auf der Registerkarte** Richtlinien verwalten eine der vorhandenen Richtlinien aus, oder erstellen Sie eine neue.

3.  Wählen Sie **Musik wartebereich für PSTN-Anrufer** **im** Dropdownmenü die Option Aktiviert aus.

Sie können die Musik auch mithilfe des PowerShell-Moduls Teams konfigurieren. Ändern Sie in TeamsCallingPolicy den Parameter MusicOnHoldEnabledType in Enabled, und erteilen Sie dann diese Richtlinieninstanz einem oder mehreren Benutzern.

Wenn ein Teams-Benutzer eine Teams-Anrufrichtlinie mit Musik auf "Halten" deaktiviert festgelegt hat, wird keine Musik abgespielt, wenn der Teams-Benutzer den Anruf in die Warteschleife setzt.

## <a name="configure-custom-music"></a>Konfigurieren benutzerdefinierter Musik

Zusätzlich zur Wiedergabe von Standardmusik für PSTN-Anrufer können Sie eine benutzerdefinierte Audiodatei mit Musik oder anderen Audioinhalten hochladen und diese Audiodatei so konfigurieren, dass sie für den PSTN-Anrufer abgespielt wird.
So möchte beispielsweise eine Abteilung oder Organisation eine benutzerdefinierte Ankündigung oder benutzerdefinierte Musik hören, wenn externe PSTN-Anrufer im Warteschleifen-Speicher halten.  

> [!NOTE]
> Sie sind für das unabhängige Löschen und Sichern aller erforderlichen Rechte und Berechtigungen für die Verwendung von Musik- oder Audiodateien mit Ihrem Microsoft Teams verantwortlich. Dies kann geistiges Eigentum und andere Rechte an Musik, Soundeffekten, Audio, Marken, Namen und anderen Inhalten in der Audiodatei aller relevanten Rechteinhaber umfassen. Zu den Inhabern gehören möglicherweise Interpreten, Künstler, Künstler, Künstler, Kunst, Interpreten, Autoren, Musikherausgeber, Musikherausgeber, Union, Gilden, Rechteverwaltungsorganisationen und alle anderen Parteien, die die Urheberrechte an Musik, Soundeffekten, Audio und anderen geistigen Eigentumsrechten besitzen, kontrollieren oder lizenzieren.

Verwenden Sie zum Konfigurieren von benutzerdefinierten Musik im Halteraum die PowerShell-Cmdlets New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy und Import/Get/Remove/Export-CsOnlineAudioFile in Teams PowerShell-Modul 3.0.0 oder höher.

Unterstützte Audioformate und maximale Dateigröße finden Sie unter [Import-CsOnlineAudioFile.](/powershell/module/skype/import-csonlineaudiofile)


1. Stellen Sie sicher, Teams Benutzer die Musik für PSTN-Anrufer in der Richtlinie für Anrufe über das Festnetz auf Aktiviert Teams festgelegt hat. 

2. Hochladen Sie die benutzerdefinierte Audiodatei.

3. Erstellen Sie Teams Anruf hold policy referinging the custom audio file and assign it to the Teams user.

### <a name="upload-the-custom-audio-file"></a>Hochladen der benutzerdefinierten Audiodatei

Die Konfiguration von benutzerdefinierten Musik im Halteraum beginnt mit dem Hochladen der Audiodatei. Zu diesem Zweck verwenden Sie das [PowerShell-Cmdlet Import-CsOnlineAudioFile.](/powershell/module/skype/import-csonlineaudiofile)

Ein Beispiel für das Hochladen einer MP3-Audiodatei mithilfe der PowerShell-Oberfläche wird unten gezeigt:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Verweisen auf die Audiodatei in einer Anruf Teams Anruf-Halterichtlinie

Nachdem Sie die Audiodatei hochgeladen haben, müssen Sie in einer Teams-Anruf-Halterichtlinie auf die Datei verweisen, indem Sie beim Erstellen oder Festlegen einer Anruf-Halterichtlinie die Teams ID der Datei verwenden. Zum Beispiel: 

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Nachdem Sie die neue Richtlinie für Teams Anruf halten erstellt haben, können Sie sie ihren Benutzern mithilfe der folgenden Grant-CsTeamsCallHoldPolicy erteilen:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Um Informationen zu Ihren hochgeladenen Audiodateien zu erhalten, verwenden Sie das cmdlet Get-CsOnlineAudioFile Audio.

Wenn Sie eine hochgeladene Audiodatei entfernen möchten, verwenden Sie das Remove-CsOnlineAudioFile-Cmdlet. Bevor Sie eine Audiodatei entfernen, vergewissern Sie sich, dass Sie diese Audiodatei nicht in teamsCallHoldPolicy verwenden.

Um eine hochgeladene Audiodatei zu exportieren, verwenden Sie das Export-CsOnlineAudioFile-Cmdlet.

## <a name="feature-availability"></a>Verfügbarkeit von Features

In der folgenden Tabelle ist aufgeführt, welche Features auf welchen Clients und Geräten die Musik "Halten" und "Musik im Halteraum" unterstützen. Da Microsoft weiterhin Featureunterstützung hinzu addieren, überprüfen Sie daher häufig, ob weitere Verfügbarkeit verfügbar ist.


| Feature | Desktop <br> Windows/Mac OS | Browser | Mobil <br> iOS | Mobil <br> Android | Teams Telefon |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Halten eines 1:1-PSTN-Anrufs | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum |
| Halten der Durchsetzung durch durch eine Funktion bei einem 1:1 PSTN-Anruf |-Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | |

## <a name="restrictions"></a>Einschränkungen

- Musik "On-Hold" ist nur in der kommerziellen Cloud verfügbar.

- Musik "Halten" ist nur verfügbar, wenn sich der Benutzer im TeamsOnly-Modus befindet.

- Wenn der aufgerufene Teams-Benutzer für das Routing Location-Based ist, Musik die Option "Halten" nicht für den Anrufer abgespielt werden.

- Benutzerdefinierte Musik "Halten" ist für Benutzer, die für die Darstellung freigegebener Zeilen (Delegierung) konfiguriert sind, und bei Verwendung des Anrufparks nicht verfügbar. Die Standard-Musik im Halteraum wird abgespielt.

- In einigen Szenarien wird ein Direct-Routingmedienumgehungsaufruf zur Wiedergabe von Musik im Haltefeld in eine Nicht-Medienumgehung konvertiert, und der Aufruf bleibt als nicht medienfreie Umgehung, bis der Aufruf beendet wird.

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)
