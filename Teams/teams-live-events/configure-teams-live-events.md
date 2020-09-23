---
title: Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie Einstellungen für Live-Ereignisse von Teams verwalten, die in Ihrer Organisation gespeichert sind.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0e949b2773baa2cc819629133396020dee7d7d7
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203948"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams

Verwenden Sie die Einstellungen für Live Ereignisse von Teams, um Einstellungen für Live Ereignisse zu konfigurieren, die in Ihrer Organisation stattfinden. Sie können eine Support-URL einrichten und einen Drittanbieter für Videoverteilung konfigurieren. Diese Einstellungen gelten für alle Live Ereignisse, die in Ihrer Organisation erstellt wurden.

Sie können diese Einstellungen im Microsoft Teams Admin Center ganz einfach verwalten. Wechseln Sie in der linken Navigationsleiste zu **Besprechungen**  >  **Live Events-Einstellungen**.

![Screenshot der Einstellungen für Live-Events in Teams](../media/teams-live-events-settings.png "Screenshot der Einstellungen für Teams-Live Ereignisse, die Sie im Microsoft Teams Admin Center konfigurieren können")

## <a name="set-up-event-support-url"></a>Einrichten der URL für die Ereignisunterstützung

Diese URL wird für Live-Event-Teilnehmer angezeigt. Fügen Sie die Support-URL für Ihre Organisation hinzu, um Teilnehmern eine Möglichkeit zu geben, den Support während eines Liveereignisses zu kontaktieren.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste **Meetings**zu  >  **Live-Ereigniseinstellungen**für Besprechungen.
2. Geben Sie unter **Support-URL**die Support-URL Ihrer Organisation ein.

    ![Support-URL-Einstellung für Live-Ereignisse im Admin Center](../media/teams-live-events-settings-supporturl.png "Screenshot der Support-URL-Einstellung für Live-Events in Teams")

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Führen Sie Folgendes aus:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Weitere Informationen finden Sie unter [Satz-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Konfigurieren eines Drittanbieters für Videoverteilung 

Wenn Sie eine Lösung für Software Defined Network (SDN) oder Enterprise Content Delivery Network (ECDN) über einen Microsoft Video Delivery-Partner erworben und eingerichtet haben, konfigurieren Sie den Anbieter für Live Ereignisse in Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste **Meetings**zu  >  **Live-Ereigniseinstellungen**für Besprechungen.
2. Führen Sie unter **Anbieter von Video Verteilern von Drittanbietern**die folgenden Schritte aus: 

    ![Einstellungen für Video Verteilungs Anbieter von Drittanbietern im Admin Center](../media/teams-live-events-settings-distribution-provider.png "Screenshot der Einstellungen des Drittanbieters für Videoverteiler für Live Ereignisse")

    - **Verwenden eines Dritt** Anbieters für die Verteilung Aktivieren Sie diese Option, um den Video Verteilungs Anbieter eines Drittanbieters zu aktivieren.
    - **Sdn-Anbietername** Wählen Sie den von Ihnen verwendeten Anbieter aus.
    - **Anbieter-Lizenzschlüssel** Geben Sie die Lizenz-ID ein, die Sie von Ihrem Anbieter Kontakt erhalten haben.
    - **Sdn-API-Vorlagen-URL** Geben Sie die API-Vorlagen-URL ein, die Sie von Ihrem Anbieter Kontakt erhalten haben.

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell
Rufen Sie die Lizenz-ID oder das API-Token und die API-Vorlage von Ihrem Anbieter Kontakt ab, und führen Sie je nach verwendetem Anbieter eine der folgenden Aktionen aus:

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

Weitere Informationen finden Sie unter [Satz-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Wenn Sie planen, Live Ereignisse mithilfe einer externen APP oder eines externen Geräts zu erstellen, müssen Sie auch [ihren ECDN-Anbieter mit Microsoft Stream konfigurieren](https://docs.microsoft.com/stream/network-caching). 

>[!Note]
> Die Änderung von der Verwendung von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](../tmr-meeting-recording-change.md) ist ein Phasen orientierter Ansatz. Beim Start können Sie sich für diese Erfahrung entscheiden, im November müssen Sie sich abmelden, wenn Sie den Datenstrom weiterhin verwenden möchten, und einige Zeit in frühen 2021 werden wir alle Kunden dazu auffordern, OneDrive for Business und SharePoint für neue Besprechungsaufzeichnungen zu verwenden.

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)