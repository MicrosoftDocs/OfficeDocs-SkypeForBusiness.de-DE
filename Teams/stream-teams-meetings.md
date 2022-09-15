---
title: Streamen von Teams-Besprechungen
author: MicrosoftHeidi
ms.author: heidip
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
description: Erfahren Sie, wie Sie Streaming für Ihre Teams-Besprechungen einrichten und verwalten.
ms.openlocfilehash: b8394abfe66ecde6813e383e0473bcdca2a0ad9f
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67707002"
---
# <a name="stream-teams-meetings"></a>Streamen von Teams-Besprechungen

Dieser Artikel hilft Ihnen beim Einrichten von Streaming für Teams-Besprechungen.

## <a name="what-is-streaming-and-how-does-it-work"></a>Was ist Streaming und wie funktioniert es?

Streaming ermöglicht Es Ihrer Organisation, Ihre Reichweite zu erweitern und Besprechungsteilnehmern mehr Besprechungsoptionen zu bieten. Wenn Sie Streaming aktivieren, können Organisatoren Besprechungen und Webinare an externe Endpunkte streamen, indem sie eine Real-Time Messaging Protocol (RTMP)-URL und den Schlüssel für die integrierte benutzerdefinierte Streaming-App in Teams bereitstellen.

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