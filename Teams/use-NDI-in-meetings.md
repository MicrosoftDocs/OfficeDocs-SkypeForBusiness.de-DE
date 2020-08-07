---
title: Verwenden von ndi in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie ndi in Microsoft Teams verwenden.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588289"
---
# <a name="use-ndi-in-microsoft-teams"></a>Verwenden von ndi in Microsoft Teams

[!INCLUDE [template](includes/preview-feature.md)]

Die Netzwerkgeräte Schnittstelle (NDI) ist eine moderne Lösung zum Verbinden von Mediengeräten (wie einer Studio Kamera und einem Mixer). Anstatt physische Verbindungen zu verwenden, ermöglicht ndi die Konnektivität über ein lokales Intranet, einschließlich auf einem lokalen Computer.

NewTek ndi® hat sich zu einer standardmäßigen Branchenlösung für die Erstellung von Live-Inhalten für Streams und hat in der professionellen Broadcast-Welt ein erhebliches Bewusstsein und Akzeptanz erlangt.

Skype hat zuvor ndi-Funktionalität für Skype in späten 2018 hinzugefügt. Microsoft Teams nutzt diese Funktion, um die Besprechungs Erfahrung zu verbessern.

NDI ist auf ein lokales Netzwerk limitiert und sollte nur als Teil des Produktionsworkflows, keine Broadcast-Lösung, betrachtet werden.

## <a name="turn-on-ndi"></a>Aktivieren von ndi

NDI erfordert zwei Schritte, die für einen Benutzer aktiviert werden müssen.

1. Der mandantenadministrator muss die Eigenschaft "AllowNDIStreaming" in CsTeamsMeetingPolicy aktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer ndi für seinen jeweiligen Client über **Einstellungs**  >  **Berechtigungen**aktivieren.

Wenn ein Benutzer einer Besprechung Beitritt, wird eine Meldung angezeigt, die Sie darüber informiert, dass die Besprechung übertragen wird. Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen Sie von der Besprechung abfallen.

Die folgende Abbildung zeigt die Banner Nachricht, die ein Benutzer in einer Teams-Besprechung sieht.

![Abbildung des ndi-Banners, das in einer Teams-Besprechung angezeigt wird.](media/NDI-disclosure.png)

Das Banner enthält einen Link zu den [Microsoft-Datenschutzrichtlinien](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Unterstützte Gebietsschemas und Benutzertypen

NDI wird in allen Gebietsschemas unterstützt. Die folgenden Benutzer werden in einer ndi-Besprechung unterstützt:

- In-Tenant – vollständige Unterstützung, bereitgestellt basierend auf Ring/Mandanten-ID/UserID (gesteuert durch die Richtlinien für Besprechungen)
- Federated – Nein (auch wenn ndi aktiviert ist)<sup>1</sup>
- Freemium-Nein (Standardwert)
- Anonym – Nein (Standardwert)
- Gast – Nein (Standardwert)

<sup>1</sup> Geräte verfügen über eine ndi-Einstellung, die standardmäßig aktiviert ist. Wenn ein Besprechungsteilnehmer ein Gerät mit ndi off verwendet, müssen Sie ndi aktivieren.
