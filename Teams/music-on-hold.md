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
description: Hier erfahren Sie, wie Sie Musik Feature "In-Halte-Funktion" in Telefonsystem.
ms.openlocfilehash: a1e2662c04cfa9300d034aaaf8d7975e44e63f69
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514782"
---
# <a name="music-on-hold"></a>Musik im Halteraum

Wenn ein Microsoft Teams einen eingehenden Anruf aus dem öffentlichen Telefonnetz (PSTN) in den Halteraum setzt, kann der PstN-Anrufer ausgewählte Musik hören.

Bei der Abgespielten Musik handelt es sich entweder um die von Microsoft bereitgestellte Standardmusik oder um benutzerdefinierte Musik, die Sie hochladen und konfigurieren. Als Mandantenadministrator konfigurieren Sie, ob das Musik verfügbar ist, indem Sie eine Anrufrichtlinie für Teams erstellen und die Richtlinie dem Benutzer Teams zuweisen.

Die in den PSTN Microsoft Teams-Anrufszenarien bereitgestellte Standardmusik ist frei von Lizenzgebühren, die Von Ihrer Organisation zu zahlen sind.

Beachten Sie, dass PSTN-Anrufer Musik-On-Hold auch in anderen Szenarien hören können, z. B. wenn sie sich in eine Cloud-Anrufwarteschleife einrufen oder wenn ihr Anruf von einem Microsoft Teams-Benutzer geparkt wird. Diese Szenarien werden nicht von den in diesem Artikel erwähnten Features behandelt oder gesteuert.

## <a name="configure-music-on-hold"></a>Konfigurieren Musik im Halteraum

So konfigurieren Musik im Halteraum:

1.  Navigieren Sie in der linken Navigationsleiste Teams Admin Center zu Richtlinien **für Sprachanrufe > Sprachanrufe**.

2.  Wählen Sie **auf der Registerkarte** Richtlinien verwalten eine der vorhandenen Richtlinien aus, oder erstellen Sie eine neue.

3.  Wählen Sie **Musik für PSTN-Anrufer** im Wartebereich die Option Aktiviert **im** Dropdownmenü aus.

Sie können die Verwendung Musik auch mithilfe des PowerShell-Moduls Teams Konfigurieren. Ändern Sie in TeamsCallingPolicy den Parameter MusicOnHoldEnabledType in Enabled, und erteilen Sie dann diese Richtlinieninstanz einem oder mehreren Benutzern.

Wenn ein Teams-Benutzer eine Teams-Anrufrichtlinie mit Musik auf Halten deaktiviert festgelegt hat, wird keine Musik abgespielt, wenn der Teams-Benutzer den Anruf in die Warteschleife platziert.

## <a name="configure-custom-music"></a>Konfigurieren benutzerdefinierter Musik

Zusätzlich zur Wiedergabe von Standardmusik für PSTN-Anrufer können Sie eine benutzerdefinierte Audiodatei mit Musik oder anderen Audioinhalten hochladen und diese Audiodatei so konfigurieren, dass sie für den PSTN-Anrufer abgespielt wird.
So möchte beispielsweise eine Abteilung oder Organisation eine benutzerdefinierte Ankündigung oder benutzerdefinierte Musik hören, wenn externe PSTN-Anrufer im Warteschleifen-Speicher halten.  

> [!NOTE]
> Sie sind für das unabhängige Löschen und Sichern aller erforderlichen Rechte und Berechtigungen für die Verwendung von Musik- oder Audiodateien mit Ihrem Microsoft Teams verantwortlich. Dies kann geistiges Eigentum und andere Rechte an Musik, Soundeffekten, Audio, Marken, Namen und anderen Inhalten in der Audiodatei aller relevanten Rechteinhaber umfassen. Zu den Inhabern gehören möglicherweise Interpreten, Künstler, Künstler, Künstler, Kunst, Interpreten, Autoren, Musikherausgeber, Musikherausgeber, Union, Gilden, Rechteverwaltungsorganisationen und alle anderen Parteien, die die Urheberrechte an Musik, Soundeffekten, Audio und anderen geistigen Eigentumsrechten besitzen, kontrollieren oder lizenzieren.

Zum Konfigurieren von benutzerdefinierten Musik im Halteraum verwenden Sie die PowerShell-Cmdlets New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy und Import/Get/Remove/Export-CsOnlineAudioFile in Teams PowerShell-Modul 3.0.0 oder höher.

Unterstützte Audioformate und maximale Dateigröße finden Sie unter [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).


1. Stellen Sie sicher, Teams Benutzer die Musik für PSTN-Anrufer in der Richtlinie für Anrufe über das Festnetz auf Aktiviert Teams festgelegt hat. 

2. Hochladen Sie die benutzerdefinierte Audiodatei.

3. Erstellen Sie Teams Anruf-Hold-Richtlinie, die auf die benutzerdefinierte Audiodatei bezugt, und weisen Sie sie dem Teams zu.

### <a name="upload-the-custom-audio-file"></a>Hochladen der benutzerdefinierten Audiodatei

Die Konfiguration von benutzerdefinierten Musik im Halteraum beginnt mit dem Hochladen der Audiodatei. Zu diesem Zweck verwenden Sie das [PowerShell-Cmdlet Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Ein Beispiel für das Hochladen einer MP3-Audiodatei mithilfe der PowerShell-Oberfläche wird unten gezeigt:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Verweisen auf die Audiodatei in einer Anruf-Teams Anruf-Halterichtlinie

Nachdem Sie die Audiodatei hochgeladen haben, müssen Sie in einer Teams-Anruf-Halterichtlinie auf die Datei verweisen, indem Sie beim Erstellen oder Festlegen einer Anruf-Halterichtlinie die ID der Datei Teams festlegen. Zum Beispiel: 

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Nachdem Sie die neue Richtlinie für Teams Anruf halten erstellt haben, können Sie sie ihren Benutzern mithilfe der folgenden Grant-CsTeamsCallHoldPolicy gewähren:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Um Informationen zu Ihren hochgeladenen Audiodateien zu erhalten, verwenden Sie das cmdlet Get-CsOnlineAudioFile Audio.

Um eine hochgeladene Audiodatei zu entfernen, verwenden Sie das Remove-CsOnlineAudioFile-Cmdlet. Bevor Sie eine Audiodatei entfernen, vergewissern Sie sich, dass Sie diese Audiodatei nicht in teamsCallHoldPolicy verwenden.

Um eine hochgeladene Audiodatei zu exportieren, verwenden Sie das Export-CsOnlineAudioFile-Cmdlet.

## <a name="feature-availability"></a>Verfügbarkeit von Features

In der folgenden Tabelle ist aufgeführt, welche Features auf welchen Clients und Geräten die Musik "Halten" und "Musik im Halteraum" unterstützen. Da Microsoft weiterhin Featureunterstützung hinzu addieren, überprüfen Sie daher häufig, ob weitere Verfügbarkeit verfügbar ist.


| Feature | Desktop <br> Windows/Mac OS | Browser | Mobil <br> iOS | Mobil <br> Android | Teams Telefon |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Halten eines 1:1-PSTN-Anrufs | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum |
| Halten der Durchsetzung durch durch eine Funktion bei einem 1:1 PSTN-Anruf |-Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | -Musik im Halteraum<br>-Benutzerdefinierte Musik im Halteraum | |

## <a name="restrictions"></a>Einschränkungen

- Musik "On Hold" ist nur in kommerziellen und Cloudinstanzen GCC verfügbar.

- Musik "Halten" ist nur verfügbar, wenn sich der Benutzer im TeamsOnly-Modus befindet.

- Wenn der aufgerufene Teams für Routing aktiviert Location-Based, Musik die Option "Halten" nicht für den Anrufer abgespielt werden.

- Benutzerdefinierte Musik "Halten" ist für Benutzer, die für die Darstellung freigegebener Zeilen (Delegierung) konfiguriert sind, und bei Verwendung des Anrufparks nicht verfügbar. Die Standardmäßige Musik im Halteraum wird abgespielt.

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
