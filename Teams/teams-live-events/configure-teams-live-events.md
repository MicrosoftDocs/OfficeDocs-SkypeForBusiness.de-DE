---
title: Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Erfahren Sie, wie Sie Einstellungen für Liveereignisse in Teams verwalten, die in Ihrer Organisation abgehalten werden.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5f19aa6cfee7d4cce19ef5a0936a5a72e954648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119344"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams

Verwenden Sie die Einstellungen für Liveereignisse in Teams, um Einstellungen für Liveereignisse zu konfigurieren, die in Ihrer Organisation abgehalten werden. Sie können eine Support-URL einrichten und einen Videoverteilungsanbieter von Drittanbietern konfigurieren. Diese Einstellungen gelten für alle Liveereignisse, die in Ihrer Organisation erstellt werden.

Sie können diese Einstellungen ganz einfach im Microsoft Teams Admin Center verwalten. Wechseln Sie im linken Navigationsbereich zu   >  **Besprechungs-Liveereignisse-Einstellungen.**

![Screenshot der Einstellungen für Liveereignisse in Teams](../media/teams-live-events-settings.png "Screenshot der Einstellungen für Liveereignisse in Teams, die Sie im Microsoft Teams Admin Center konfigurieren können")

## <a name="set-up-event-support-url"></a>Einrichten der URL für die Ereignisunterstützung

Diese URL wird den Liveereignisteilnehmern angezeigt. Fügen Sie die Support-URL für Ihre Organisation hinzu, um den Teilnehmern eine Möglichkeit zu geben, den Support während eines Liveereigniss zu kontaktieren.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu  >  **Besprechungs-Live-Ereigniseinstellungen.**
2. Geben **Sie unter Support-URL** die Support-URL Ihrer Organisation ein.

    ![Support-URL-Einstellung für Liveereignisse im Admin Center](../media/teams-live-events-settings-supporturl.png "Screenshot der Support-URL-Einstellung für Liveereignisse in Teams")

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Führen Sie Folgendes aus:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Konfigurieren eines Videoverteilungsanbieters eines Drittanbieters 

Wenn Sie eine Software defined Network (SDN)-Lösung oder eine eCDN-Lösung (Enterprise Content Delivery Network) über einen Microsoft Video Delivery Partner erworben und eingerichtet haben, konfigurieren Sie den Anbieter für Liveereignisse in Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu  >  **Besprechungs-Live-Ereigniseinstellungen.**
2. Führen **Sie unter Videoverteilungsanbieter von** Drittanbietern die folgenden Schritte aus: 

    ![Einstellungen des Videoverteilungsanbieters von Drittanbietern im Admin Center](../media/teams-live-events-settings-distribution-provider.png "Screenshot der Einstellungen des Drittanbieters für den Videoverteilungsanbieter für Liveereignisse")

    - **Verwenden eines Drittanbietervertriebsanbieters** Aktivieren Sie diese Option, um den Videoverteilungsanbieter von Drittanbietern zu aktivieren.
    - **Name des SDN-Anbieters** Wählen Sie den von Ihnen verwendeten Anbieter aus.
    - **Lizenzschlüssel des Anbieters** Geben Sie die Lizenz-ID ein, die Sie von Ihrem Anbieterkontakt erhalten haben.
    - **URL der SDN-API-Vorlage** Geben Sie die API-Vorlagen-URL ein, die Sie von Ihrem Anbieterkontakt erhalten haben.

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell
Holen Sie sich die Lizenz-ID oder das API-Token und die API-Vorlage von Ihrem Anbieterkontakt, und führen Sie dann je nach verwendeten Anbieter eine der folgenden Schritte aus:

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

Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Wenn Sie planen, Liveereignisse mit einer externen App oder einem externen Gerät zu erstellen, müssen Sie Ihren [eCDN-Anbieter](/stream/network-caching)auch mit Microsoft Stream konfigurieren. 

>[!Note]
> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](../tmr-meeting-recording-change.md) erfolgt schrittweise. Beim Start können Sie sich für diese Umgebung entscheiden. Sie müssen sich im November abmelden, wenn Sie Stream weiterhin verwenden möchten. Anfang 2021 müssen alle Kunden OneDrive for Business und SharePoint für neue Besprechungsaufzeichungen verwenden.

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)