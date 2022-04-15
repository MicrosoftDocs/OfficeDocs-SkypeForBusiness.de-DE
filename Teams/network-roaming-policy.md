---
title: Richtlinie für Netzwerkroaming
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Erfahren Sie, wie Sie die Einstellungen der Richtlinie für das Teams-Netzwerkroaming verwalten.
ms.openlocfilehash: c26cdec0fc41e40a9c3eac7d0324050740cf05ef
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853236"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>Video- und Medieneinstellungen mit der Richtlinie für das Netzwerkroaming verwalten

Zusätzlich zur Verwaltung von Video- und Medieneinstellungen mit Besprechungsrichtlinien können Sie jetzt mit der TeamsNetworkRoamingPolicy die Verwendung der folgenden Attribute, die vom Microsoft Teams-Client verwendet werden, dynamisch steuern: 

- IP-Video
- Medien-Bitrate

Mit dieser Richtlinie können Sie Netzwerkstandorten Einstellungen zuweisen. Der Teams-Client übernimmt die Einstellungen dynamisch basierend auf dem Netzwerkstandort, mit dem er eine Verbindung herstellt. Wenn sich der Teams-Client von einem Netzwerkstandort mit zugewiesener Roamingrichtlinie anmeldet, wird diese Richtlinie verwendet. Wenn keine Richtlinie zugewiesen ist, werden die in der Besprechungsrichtlinie festgelegten Werte verwendet. Weitere Informationen zu Einstellungen für Besprechungsrichtlinien für Audio und Video finden Sie unter [Einstellungen für Besprechungsrichtlinien für Audio und Video](meeting-policies-audio-and-video.md).

## <a name="configure-the-teamsnetworkroamingpolicy"></a>Konfigurieren der TeamsNetworkRoamingPolicy

Verwenden Sie zum Konfigurieren der TeamsNetworkRoamingPolicy die folgenden PowerShell-Cmdlets:

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

Die TeamsNetworkRoamingPolicy enthält die folgenden Parameter:

- AllowIPVideo – Diese Einstellung steuert, ob Video in Besprechungen, die von einem Benutzer gehostet werden, und in 1:1- und Gruppenanrufen, die von einem Benutzer gestartet werden, aktiviert werden kann.

- MediaBitRateKb – Diese Einstellung bestimmt die durchschnittliche Medien-Bitrate für Audio-, Video- und videobasierte App-Übertragungen in Anrufen und Besprechungen für den Benutzer.

Nachdem Sie die Richtlinie konfiguriert haben, weisen Sie sie einem oder mehreren Netzwerkstandorten zu, indem Sie das Cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) wie folgt verwenden:

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 Verwenden Sie das folgende Cmdlet, um eine Richtlinie von einem Netzwerkstandort zu entfernen:
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

Um die Richtlinie für das Netzwerkroaming für Benutzer zu aktivieren, die nicht für Enterprise-VoIP aktiviert sind, müssen Sie auch die Einstellung „AllowNetworkConfigurationSettingsLookup“ in der TeamsMeetingPolicy aktivieren. Diese Einstellung ist standardmäßig deaktiviert.

Weitere Informationen zum Erstellen von Netzwerkstandorten finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md). 

## <a name="examples"></a>Beispiele

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>Unterstützte Clients

- Windows 
- MacOS-Desktop

## <a name="known-issues"></a>Bekannte Probleme

Wenn Sie New- und Get-CsTeamsNetworkRoamingPolicy in Teams Online PowerShell v 2.0.0 angeben, werden zusätzliche Daten angezeigt.


## <a name="related-topics"></a>Verwandte Themen

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
