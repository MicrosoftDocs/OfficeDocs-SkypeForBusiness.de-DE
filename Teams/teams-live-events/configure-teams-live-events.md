---
title: Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Erfahren Sie, wie Sie Einstellungen für Teams-Liveereignisse verwalten, die in Ihrer Organisation stattfinden.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ac5bf29fbbe61b2e2224aeccb2082e31742816b
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794163"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams

Verwenden Sie Die Einstellungen für Teams-Liveereignisse, um Einstellungen für Liveereignisse zu konfigurieren, die in Ihrer Organisation stattfinden. Sie können eine Support-URL einrichten und einen Videoverteilungsanbieter eines Drittanbieters konfigurieren. Diese Einstellungen gelten für alle Liveereignisse, die in Ihrer Organisation erstellt werden.

Sie können diese Einstellungen ganz einfach im Microsoft Teams Admin Center verwalten. Wechseln Sie im linken Navigationsbereich zu den **Einstellungen für Liveereignisse** für **Besprechungen** > .

![Screenshot der Einstellungen für Teams-Liveereignisse.](../media/teams-live-events-settings-new.png "Screenshot der Einstellungen für Teams-Liveereignisse, die Sie im Microsoft Teams Admin Center konfigurieren können")

## <a name="set-up-event-support-url"></a>Einrichten der Ereignisunterstützungs-URL

Diese URL wird Liveereignisteilnehmern angezeigt. Fügen Sie die Support-URL für Ihre Organisation hinzu, um Teilnehmern eine Möglichkeit zu geben, den Support während eines Liveereignisses zu kontaktieren.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu den **Einstellungen für Liveereignisse** für **Besprechungen** > .
2. Geben Sie unter **"Support-URL**" die Support-URL Ihrer Organisation ein.

    ![Support-URL-Einstellung für Liveereignisse im Admin Center.](../media/teams-live-events-settings-supporturl.png "Screenshot der Einstellung der Support-URL für Teams-Liveereignisse")

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Führen Sie Folgendes aus:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).
## <a name="configure-a-third-party-video-distribution-provider"></a>Konfigurieren eines Videoverteilungsanbieters eines Drittanbieters 

Wenn Sie eine Software Defined Network (SDN)-Lösung oder eCDN-Lösung (Enterprise Content Delivery Network) über einen Microsoft-Videobereitstellungspartner erworben und eingerichtet haben, konfigurieren Sie den Anbieter für Liveereignisse in Teams. 

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu den **Einstellungen für Liveereignisse** für **Besprechungen** > .
2. Führen Sie unter **Videoverteilungsanbietern von Drittanbietern** Folgendes aus: 

    ![Einstellungen für Videoverteilungsanbieter von Drittanbietern im Admin Center.](../media/teams-live-events-settings-distribution-provider-new.png "Screenshot der Einstellungen des Drittanbieters für Videoverteilung für Liveereignisse")

    - **Drittanbieter für Verteiler** Aktivieren Sie diese Option, um den Videoverteilungsanbieter eines Drittanbieters zu aktivieren.
    - **SDN-Anbietername** Wählen Sie den anbieter, den Sie verwenden.
    - **SDN-Konfiguration** Geben Sie DETAILS zur SDN-Konfiguration ein.
        
### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell
Rufen Sie die Lizenz-ID oder die API-Token- und API-Vorlage von Ihrem Anbieterkontakt ab, und führen Sie dann je nach verwendeter Anbieter eine der folgenden Aktionen aus:

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```
**Peer5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

> [!NOTE]
> Wenn Sie planen, Liveereignisse mit einer externen App oder einem externen Gerät zu erstellen, müssen Sie [Ihren eCDN-Anbieter auch mit Microsoft Stream konfigurieren](/stream/network-caching). 

>[!Note]
> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](../tmr-meeting-recording-change.md) erfolgt schrittweise. Beim Start können Sie sich für diese Umgebung entscheiden. Sie müssen sich im November abmelden, wenn Sie Stream weiterhin verwenden möchten. Anfang 2021 müssen alle Kunden OneDrive for Business und SharePoint für neue Besprechungsaufzeichungen verwenden.

>[!Note]
> Ihre ausgewählte eCDN-Lösung unterliegt den Nutzungsbedingungen und Datenschutzrichtlinien des ausgewählten Drittanbieters, die Ihre Nutzung der Lösung des eCDN-Anbieters regeln. Ihre Nutzung der Lösung des eCDN-Anbieters unterliegt nicht den Microsoft-Volumenlizenzbedingungen oder Onlinedienstbedingungen. Wenn Sie den Bedingungen des Drittanbieters nicht zustimmen, aktivieren Sie die eCDN-Lösung nicht in Microsoft Teams.

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
