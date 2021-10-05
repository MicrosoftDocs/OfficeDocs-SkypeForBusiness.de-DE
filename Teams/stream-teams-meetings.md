---
title: Streamen Teams Besprechungen
author: KarliStites
ms.author: kastites
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
description: Erfahren Sie, wie Sie das Streaming für Ihre Besprechungen Teams verwalten.
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127545"
---
# <a name="stream-teams-meetings"></a>Streamen Teams Besprechungen

Dieser Artikel hilft Ihnen beim Einrichten des Streamings für Teams Besprechungen.

## <a name="what-is-streaming-and-how-does-it-work"></a>Was ist Streaming, und wie funktioniert es?

Streaming ermöglicht es Ihrer Organisation, Ihre Reichweite zu erweitern und den Besprechungsteilnehmern mehr Besprechungsoptionen zu bieten. Wenn Sie das Streaming aktivieren, können Organisatoren Besprechungen und Webinare an externe Endpunkte streamen, indem sie eine RTMP-URL (Real-Time Messaging Protocol) und einen Schlüssel zur integrierten benutzerdefinierten Streaming-App in Teams.

> [!NOTE]
> Sie können keine Liveereignisse streamen.

## <a name="set-up-streaming-with-powershell"></a>Einrichten des Streamings mit PowerShell

Sie können Ihre Organisation für das Streaming mit PowerShell einrichten. Diese Richtlinie ist derzeit nicht im Admin Center Teams verfügbar. Die Richtlinie pro Benutzer wird verwendet, um **anzugeben, wer Live-Streaming** aktivieren kann. Diese Option ist standardmäßig deaktiviert.

Sie können das folgende Attribut innerhalb des Windows PowerShell **Set-CsTeamsMeetingPolicy-Cmdlets** zum Einrichten des Streamings verwenden. Weitere Informationen zum Cmdlet finden Sie unter [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

- LiveStreamingMode

Legen **Sie LiveStreamingMode** auf **Aktiviert festgelegt,** um die Streamingfunktionen für einen oder mehrere Benutzer zu aktivieren.

> [!IMPORTANT]
> Sie müssen die Besprechungsregistrierung aktivieren, bevor Ihre Organisatoren Webinare streamen können. Weitere Informationen finden Sie unter [Einrichten von Webinaren.](set-up-webinars.md)

### <a name="assign-the-policy"></a>Zuweisen der Richtlinie

Weitere Informationen zum Zuweisen von Richtlinien mit PowerShell finden Sie unter [Zuweisen von Richtlinien in Teams.](policy-assignment-overview.md)

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien in Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Schnellstart: Besprechungen, Webinare und Liveereignisse](quick-start-meetings-live-events.md)