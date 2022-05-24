---
title: Streamen Teams von Besprechungen
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Erfahren Sie, wie Sie das Streaming für Ihre Teams Besprechungen einrichten und verwalten.
ms.openlocfilehash: 352a0c2e7a0584640e466b5e46456906e4912d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646344"
---
# <a name="stream-teams-meetings"></a>Streamen Teams von Besprechungen

Dieser Artikel hilft Ihnen beim Einrichten von Streaming für Teams Besprechungen.

## <a name="what-is-streaming-and-how-does-it-work"></a>Was ist Streaming und wie funktioniert es?

Streaming ermöglicht Es Ihrer Organisation, Ihre Reichweite zu erweitern und Besprechungsteilnehmern mehr Besprechungsoptionen zu bieten. Wenn Sie Streaming aktivieren, können Organisatoren Besprechungen und Webinare an externe Endpunkte streamen, indem sie eine RTMP-URL (Real-Time Messaging Protocol) und einen Schlüssel für die integrierte benutzerdefinierte Streaming-App in Teams bereitstellen.

> [!NOTE]
> Sie können keine Liveereignisse streamen.

## <a name="set-up-streaming-with-powershell"></a>Einrichten von Streaming mit PowerShell

Sie können Ihre Organisation für das Streaming mit PowerShell einrichten. Derzeit ist diese Richtlinie im Teams Admin Center nicht verfügbar. Die Richtlinie pro Benutzer wird verwendet, um anzugeben **, wer** Livestreaming aktivieren kann. Diese Option ist standardmäßig deaktiviert.

Sie können das folgende Attribut im cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** verwenden, um das Streaming einzurichten. Weitere Informationen zum Cmdlet finden [Sie unter Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

Legen Sie **"LiveStreamingMode** " auf **"Aktiviert** " fest, um Streamingfunktionen für einen oder mehrere Benutzer zu aktivieren.

> [!IMPORTANT]
> Sie müssen die Besprechungsregistrierung aktivieren, bevor Ihre Organisatoren Webinare streamen können. Weitere Informationen finden [Sie unter Einrichten von Webinaren](set-up-webinars.md).

### <a name="assign-the-policy"></a>Zuweisen der Richtlinie

Weitere Informationen zum Zuweisen von Richtlinien mit PowerShell finden [Sie unter Zuweisen von Richtlinien in Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien in Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Schnellstart: Besprechungen, Webinare und Liveereignisse](quick-start-meetings-live-events.md)