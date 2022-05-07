---
title: Weiterleiten von Anrufen an nicht zugewiesene Nummern
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Erfahren Sie, wie Sie Anrufe an nicht zugewiesene Nummern in Ihrer Organisation weiterleiten.
ms.openlocfilehash: cc464419375b6391d0d95d6e99441777a40da9cb
ms.sourcegitcommit: bc73017b4a3fe6271830bc8c5044bfd43eec80c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2022
ms.locfileid: "65266922"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Weiterleiten von Anrufen an nicht zugewiesene Nummern

Als Administrator können Sie Anrufe an nicht zugewiesene Nummern in Ihrer Organisation weiterleiten. Sie können z. B. Anrufe wie folgt an nicht zugewiesene Nummern weiterleiten: 

- Leiten Sie alle Anrufe an eine bestimmte nicht zugewiesene Nummer an eine benutzerdefinierte Ankündigung weiter.

- Leiten Sie alle Anrufe an eine bestimmte nicht zugewiesene Nummer an die Hauptschaltfläche weiter.

Sie können Anrufe an nicht zugewiesene Nummern an einen Benutzer, an ein Ressourcenkonto, das einer automatischen Telefonzentrale oder einer Anrufwarteschleife zugeordnet ist, oder an einen Ankündigungsdienst weiterleiten, der eine benutzerdefinierte Audiodatei an den Anrufer wiedergibt.

## <a name="configuration"></a>Konfiguration

Um Anrufe an eine nicht zugewiesene Nummer weiterzuleiten, verwenden Sie das Cmdlet "New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment", das in Teams PowerShell-Modul 2.5.1 oder höher verfügbar ist.

Sie müssen die aufgerufene Nummer oder den Nummernbereich und die zugehörige Weiterleitung für Anrufe an diese Nummern angeben. Der folgende Befehl gibt beispielsweise an, dass alle Aufrufe der Nummer +1 (555) 222-3333 an das Ressourcenkonto aa@contoso.com weitergeleitet werden:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

Im nächsten Beispiel wird angegeben, dass alle Aufrufe des Nummernbereichs +1 (555) 333-0000 bis +1 (555) 333-9999 an den Ankündigungsdienst weitergeleitet werden, der die Audiodatei "MainAnnouncement.wav" an den Aufrufer wiedergibt.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Hinweise

- Beim Weiterleiten an eine Ankündigung wird die Audiodatei einmal an den Anrufer wiedergegeben.

- Um Anrufe an nicht zugewiesene Abonnentennummern des Microsoft-Anrufplans weiterzuleiten, muss Ihr Mandant über verfügbare [Guthaben für Kommunikationen](what-are-communications-credits.md) verfügen.

- Um Anrufe an nicht zugewiesene Microsoft Calling Plan-Dienstnummern weiterzuleiten, muss Ihr Mandant über mindestens eine Telefonsystem – virtuelle Benutzerlizenz verfügen.

- Die unterstützten benutzerdefinierten Audiodateiformate sind WAV (unkomprimierte, lineare PCM mit 8/16/32-Bit-Tiefe in Mono oder Stereo), WMA (nur Mono) und MP3. Der Inhalt der Audiodatei darf nicht mehr als 5 MB betragen.

- Sowohl eingehende Anrufe an Microsoft Teams als auch ausgehende Anrufe von Microsoft Teams haben die aufgerufene Nummer im Bereich der nicht zugewiesenen Nummer überprüft.

- Wenn ein angegebenes Muster/bereich Telefonnummern enthält, die einem Benutzer- oder Ressourcenkonto im Mandanten zugewiesen sind, werden Anrufe zu diesen Telefonnummern an das entsprechende Ziel weitergeleitet und nicht an die angegebene Behandlung nicht zugewiesener Nummern weitergeleitet. Es gibt keine weiteren Überprüfungen der Zahlen im Bereich. Wenn der Bereich eine gültige externe Telefonnummer enthält, werden ausgehende Anrufe von Microsoft Teams an diese Telefonnummer entsprechend der Behandlung weitergeleitet.

## <a name="related-topics"></a>Verwandte Themen

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
