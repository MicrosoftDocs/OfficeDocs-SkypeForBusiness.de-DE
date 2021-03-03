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
- enabler-strategic
description: Erfahren Sie, wie Sie Einstellungen für Liveereignisse in Teams verwalten, die in Ihrer Organisation abgehalten werden.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831195"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams

Verwenden Sie die Einstellungen für Liveereignisse in Teams, um Einstellungen für Liveereignisse in Ihrer Organisation zu konfigurieren. Sie können eine Support-URL einrichten und einen Drittanbieter für die Videoverteilung konfigurieren. Diese Einstellungen gelten für alle Liveereignisse, die in Ihrer Organisation erstellt werden.

Sie können diese Einstellungen ganz einfach im Microsoft Teams Admin Center verwalten. Wechseln Sie in der linken Navigationsleiste zu den **Einstellungen** für  >  **Liveereignisse für Besprechungen.**

![Screenshot der Einstellungen für Liveereignisse in Teams](../media/teams-live-events-settings.png "Screenshot der Einstellungen für Liveereignisse in Teams, die Sie im Microsoft Teams Admin Center konfigurieren können")

## <a name="set-up-event-support-url"></a>Einrichten der Ereignisunterstützungs-URL

Diese URL wird Teilnehmern am Liveereignis angezeigt. Fügen Sie die Support-URL für Ihre Organisation hinzu, damit die Teilnehmer während eines Liveereignis Kontakt zum Support aufnehmen können.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu den **Einstellungen** für  >  **Liveereigniseinstellungen für Besprechungen.**
2. Geben **Sie unter "Support-URL"** die Support-URL Ihrer Organisation ein.

    ![Support-URL-Einstellung für Liveereignisse im Admin Center](../media/teams-live-events-settings-supporturl.png "Screenshot der Support-URL-Einstellung für Liveereignisse in Teams")

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Führen Sie Folgendes aus:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Weitere Informationen finden Sie unter ["Set-CsTeamsMeetingBroadcastConfiguration".](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>Konfigurieren eines Drittanbieters für die Videoverteilung 

Wenn Sie eine Softwarelösung für ein definiertes Netzwerk (Software Defined Network, SDN) oder eine Lösung für das Enterprise Content Delivery Network (eCDN) über einen Microsoft Video Delivery Partner erworben und eingerichtet haben, konfigurieren Sie den Anbieter für Liveereignisse in Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu den **Einstellungen** für  >  **Liveereigniseinstellungen für Besprechungen.**
2. Führen **Sie unter Den Videoverteilungsanbietern von** Drittanbietern die folgenden Schritte aus: 

    ![Einstellungen des Drittanbieters für die Videoverteilung im Admin Center](../media/teams-live-events-settings-distribution-provider.png "Screenshot der Einstellungen des Drittanbieters für die Videoverteilung für Liveereignisse")

    - **Verwenden eines Drittanbieters für die Verteilung** Aktivieren Sie diese Option, um den Videoverteilungsanbieter eines Drittanbieters zu aktivieren.
    - **Name des SDN-Anbieters** Wählen Sie den von Ihnen verwendeten Anbieter aus.
    - **Provider license key** Geben Sie die Lizenz-ID ein, die Sie von Ihrem Anbieterkontakt erhalten haben.
    - **URL der SDN-API-Vorlage** Geben Sie die API-Vorlagen-URL ein, die Sie von Ihrem Anbieterkontakt erhalten haben.

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell
Holen Sie sich die Lizenz-ID oder das API-Token und die API-Vorlage von Ihrem Anbieterkontakt, und führen Sie dann je nach verwendeten Anbieter eine der folgenden Optionen aus:

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

Weitere Informationen finden Sie unter ["Set-CsTeamsMeetingBroadcastConfiguration".](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> Wenn Sie planen, Liveereignisse mithilfe einer externen App oder eines externen Geräts zu erstellen, müssen Sie auch Ihren [eCDN-Anbieter mit Microsoft Stream konfigurieren.](https://docs.microsoft.com/stream/network-caching) 

>[!Note]
> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](../tmr-meeting-recording-change.md) erfolgt schrittweise. Beim Start können Sie sich für diese Umgebung entscheiden. Sie müssen sich im November abmelden, wenn Sie Stream weiterhin verwenden möchten. Anfang 2021 müssen alle Kunden OneDrive for Business und SharePoint für neue Besprechungsaufzeichungen verwenden.

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
