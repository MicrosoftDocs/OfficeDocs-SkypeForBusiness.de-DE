---
title: Konfigurieren von live-Ereignis Einstellungen in Microsoft-Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Informationen Sie zum Verwalten von Einstellungen für Teams live Ereignisse, die in Ihrer Organisation befinden.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8e12b6b85b61bb8c6312054be07dc37365c62c0
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748149"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Konfigurieren von live-Ereignis Einstellungen in Microsoft-Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Verwenden Sie Teams live Ereignisse Einstellungen zum Konfigurieren von Einstellungen für live Ereignisse, die gehalten werden in Ihrer Organisation. Sie können eine Support-URL einrichten und Konfigurieren eines Anbieters video Verteilung von Drittanbietern für. Diese Einstellungen gelten für alle live Ereignisse, die in Ihrer Organisation erstellt werden. 

Sie können diese Einstellungen in der Microsoft-Teams & Skype für Business Administrationscenter auf einfache Weise verwalten. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live Ereignisse Einstellungen**. 

![Live-Ereignis-settings.png] (../media/teams-live-events-settings.png "Screenshot des Teams live Ereignisse Einstellungen, die Sie in der Microsoft-Teams & Skype für Business-Verwaltungskonsole konfigurieren können") 

## <a name="set-up-event-support-url"></a>Einrichten von Ereignis Support-URL

Diese URL wird Live Ereignis Teilnehmer angezeigt. Fügen Sie die Support-URL für Ihre Organisation, um Teilnehmer eine Möglichkeit zum Kontaktieren des Supports während einer live-Ereignis übergeben.

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![Teams-Logo-30x30.png](../media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business Administrationscenter

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live-Ereignis Einstellungen**.
2. Geben Sie unter **URL unterstützen**Ihrer Organisation Support-URL ein. 

    ![Support-URL-Einstellung für live Ereignisse in der Microsoft-Teams & Skype für Business Administrationscenter] (../media/teams-live-events-settings-supporturl.png "Screenshot der URL-Einstellung für Teams live Ereignisse unterstützen")

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell
Führen Sie Folgendes aus:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Konfigurieren eines Anbieters Drittanbieter-video-Verteilung 

Wenn Sie erworben und eine softwarelösung definiert Netzwerk (SDN) oder Enterprise Content Delivery Network (eCDN) Lösung über einen Microsoft video Partner einrichten, konfigurieren Sie den Anbieter für live Ereignisse im Teams. 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![Teams-Logo-30x30.png](../media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business Administrationscenter

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live-Ereignis Einstellungen**.
2. Führen Sie unter **video Verteilung Drittanbieter**die folgenden Schritte aus: 

    ![Drittanbieter - video Verteilung Anbieter Einstellungen in der Microsoft-Teams & Skype für Business Administrationscenter] (../media/teams-live-events-settings-distribution-provider.png "Screenshot der Anbieter video Verteilung von Drittanbieter - Einstellungen für live Ereignisse")

    - **Verwenden Sie einen Anbieter für Drittanbieter - Verteilung** Deaktivieren Sie diese Aktivieren der video Verteilung von Drittanbieter-Anbieter.
    - **Name des Anbieters SDN** Wählen Sie den Anbieter, den Sie verwenden.
    - **Anbieter License Product key** Geben Sie die Lizenz-ID, die Sie von Ihrem Anbieter Kontakt erhalten haben.
    - **URL der SDN-API-Vorlage** Geben Sie die URL der API-Vorlage, die Sie von Ihrem Anbieter Kontakt erhalten haben.

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell
Möchten Sie die ID oder API-Lizenztoken und die API-Vorlage von Ihrem Anbieter Kontakt erhalten, und führen Sie eine der folgenden, abhängig von des verwendeten Anbieters:

**Struktur** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Wenn Sie planen, live Ereignisse erstellen, die externe Encoder verwenden, müssen Sie auch so [Konfigurieren Sie Ihren eCDN-Anbieter Microsoft-Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams live Ereignisse?](what-are-teams-live-events.md)
- [Planen von Teams live-Ereignisse](plan-for-teams-live-events.md)
- [Einrichten von für Teams live Ereignisse](set-up-for-teams-live-events.md)