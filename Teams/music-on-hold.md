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
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 5e28aa4774d105b687551601ba89657d91a08170
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356553"
---
# <a name="music-on-hold"></a>Musik im Halteraum

Wenn ein Microsoft Teams einen eingehenden Anruf aus dem öffentlichen Telefonnetz (PSTN) in den Halteraum setzt, kann der PstN-Anrufer ausgewählte Musik anhören.

Bei der Abgespielten Musik handelt es sich entweder um die von Microsoft bereitgestellte Standardmusik oder um benutzerdefinierte Musik, die Sie hochladen und konfigurieren. Als Mandantenadministrator konfigurieren Sie, ob das Musik verfügbar ist, indem Sie eine Anrufrichtlinie für Teams erstellen und die Richtlinie dem Benutzer Teams zuweisen. 

Beachten Sie, dass PSTN-Anrufer Musik "Halten" auch in anderen Szenarien hören können. Dies kann z. B. der Benutzer sein, wenn er sich in eine Cloud-Anrufwarteschleife einreiht oder wenn der Anruf von einem Anderen geparkt Microsoft Teams wird. Diese Szenarien werden nicht von den in diesem Artikel erwähnten Features behandelt oder gesteuert. 

## <a name="configure-music-on-hold"></a>Konfigurieren Musik im Halteraum

So konfigurieren Musik im Halteraum:

1.  Wechseln Sie in der linken Navigationsleiste Teams Admin Center zu **Richtlinien für Sprachanrufe > .**

2.  Wählen Sie **auf der Registerkarte** Richtlinien verwalten eine der vorhandenen Richtlinien aus, oder erstellen Sie eine neue.

3.  Wählen Sie **Musik wartebereich für PSTN-Anrufer** im Dropdownmenü die **Option** Aktiviert aus.

Mithilfe des PowerShell Musik Moduls "Halten" können Sie die Teams konfigurieren. Ändern Sie in TeamsCallingPolicy den Parameter MusicOnHoldEnabledType in Enabled, und erteilen Sie dann diese Richtlinieninstanz einem oder mehreren Benutzern.

Wenn ein Teams-Benutzer eine Richtlinie für Teams-Anrufe mit Musik auf Halten deaktiviert festgelegt hat, wird keine Musik abgespielt, wenn der Teams-Benutzer den Anruf in die Warteschleife setzt.

## <a name="configure-custom-music"></a>Konfigurieren benutzerdefinierter Musik

> [!NOTE]
> Dieses Feature steht als Public Preview-Version zur Verfügung.

Zusätzlich zur Wiedergabe von Standardmusik für PSTN-Anrufer können Sie eine benutzerdefinierte Audiodatei mit Musik oder anderen Audioinhalten hochladen und diese Audiodatei so konfigurieren, dass sie für den PSTN-Anrufer abgespielt wird.
So möchte beispielsweise eine Abteilung oder Organisation eine benutzerdefinierte Ankündigung oder benutzerdefinierte Musik hören, wenn externe PSTN-Anrufer im Warteschleifen-Speicher halten.  

> [!NOTE]
> Sie sind für das unabhängige Löschen und Sichern aller erforderlichen Rechte und Berechtigungen für die Verwendung von Musik- oder Audiodateien mit Ihrem Microsoft Teams verantwortlich. Dies kann geistiges Eigentum und andere Rechte an Musik, Soundeffekten, Audio, Marken, Namen und anderen Inhalten in der Audiodatei aller relevanten Rechteinhaber umfassen. Zu den Inhabern gehören möglicherweise Interpreten, Künstler, Künstler, Künstler, Kunst, Interpreten, Autoren, Musikherausgeber, Musikherausgeber, Union, Gilden, Rechteverwaltungsorganisationen und alle anderen Parteien, die die Urheberrechte an Musik, Soundeffekten, Audio und anderen geistigen Eigentumsrechten besitzen, kontrollieren oder lizenzieren.

Zum Konfigurieren von benutzerdefinierten Musik im Halteraum verwenden Sie die PowerShell-Cmdlets New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy und Import/Get/Remove-CsOnlineAudioFile im Teams PowerShell-Modul 2.5.0 oder höher.


1. Stellen Sie sicher, Teams Benutzer die Musik für PSTN-Anrufer in der Richtlinie für Anrufe über das Festnetz auf Aktiviert Teams festgelegt hat. 

2. Hochladen Sie die benutzerdefinierte Audiodatei.

3. Erstellen Sie Teams Anruf-Hold-Richtlinie, die auf die benutzerdefinierte Audiodatei bezugt, und weisen Sie sie dem Benutzer Teams zu.

### <a name="upload-the-custom-audio-file"></a>Hochladen der benutzerdefinierten Audiodatei

Die Konfiguration von benutzerdefinierten Musik im Halteraum beginnt mit dem Hochladen der Audiodatei. Zu diesem Zweck verwenden Sie Import-CsOnlineAudioFile PowerShell-cmdlet. Ein Beispiel für das Hochladen einer MP3-Audiodatei mithilfe der PowerShell-Oberfläche wird unten gezeigt:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Verweisen auf die Audiodatei in einer Richtlinie für Teams-Anruf halten

Nachdem Sie die Audiodatei hochgeladen haben, müssen Sie in einer Anruf-Halterichtlinie für Teams auf die Datei verweisen, indem Sie beim Erstellen oder Festlegen einer Anruf-Halterichtlinie die ID der Datei Teams festlegen. Zum Beispiel: 

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Nachdem Sie die neue Richtlinie für Teams Anruf halten erstellt haben, können Sie sie ihren Benutzern mithilfe der folgenden Grant-CsTeamsCallHoldPolicy erteilen:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Um Informationen zu Ihren hochgeladenen Audiodateien zu erhalten, verwenden Sie das cmdlet Get-CsOnlineAudioFile Audio.

Zum Entfernen einer hochgeladenen Audiodatei verwenden Sie das cmdlet Remove-CsOnlineAudioFile Audio. Bevor Sie eine Audiodatei entfernen, vergewissern Sie sich, dass Sie diese Audiodatei nicht in teamsCallHoldPolicy verwenden.

## <a name="feature-availability"></a>Verfügbarkeit von Features

In der folgenden Tabelle ist aufgeführt, welche Features auf welchen Clients und Geräten die Musik "Halten" und "Musik im Halteraum" unterstützen. Da Microsoft weiterhin Featureunterstützung hinzu addieren, überprüfen Sie daher häufig, ob zusätzliche Verfügbarkeit verfügbar ist.


| Feature | Desktop <br> Windows/Mac OS | Browser | Mobil <br> iOS | Mobil <br> Android | Teams Telefon |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Halten eines 1:1-PSTN-Anrufs | -Musik im Halteraum<br>-Custom Musik on Hold | -Musik im Halteraum<br>-Custom Musik on Hold | -Musik im Halteraum<br>-Custom Musik on Hold | Musik im Halteraum | Musik im Halteraum |
| Halten der Durchsetzung durch durch eine Funktion bei einem 1:1 PSTN-Anruf |-Musik im Halteraum<br>-Custom Musik on Hold | | | | |

## <a name="restrictions"></a>Einschränkungen

- Musik "On-Hold" ist nur in der kommerziellen Cloud verfügbar.

- Musik "Halten" ist nur verfügbar, wenn sich der Benutzer im TeamsOnly-Modus befindet.

- Wenn der aufgerufene Teams für das Routing Location-Based ist, Musik anrufer die Option "Halten" nicht abgespielt werden.

- Sie können die Audiodatei nach dem Hochladen nicht exportieren. können Sie sie nur entfernen.

- Benutzerdefinierte Musik "Halten" ist für Benutzer, die für die Darstellung freigegebener Zeilen (Delegierung) und die Verwendung von Anrufparken konfiguriert sind, nicht verfügbar. Die Standard-Musik im Halteraum wird abgespielt.

- In einigen Szenarien wird ein Direct-Routingmedienumgehungsaufruf zur Wiedergabe von Musik im Haltefeld in eine Nicht-Medienumgehung konvertiert, und der Aufruf bleibt als nicht medienfreie Umgehung, bis der Aufruf beendet wird.


## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





