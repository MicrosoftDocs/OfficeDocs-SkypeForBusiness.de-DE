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
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308168"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Verwenden von ndi®-Technologie in Microsoft Teams

 NewTek ndi® (Network Device Interface)-Technologie ist eine moderne Lösung für den Anschluss von Mediengeräten (wie Studio Kamera und Mixer). Anstatt physische Verbindungen zu verwenden, ermöglicht die ndi-® Technologie die Konnektivität über ein lokales Intranet, auch auf einem lokalen Computer.

NDI® Technology ist zu einer standardmäßigen Branchenlösung geworden, um Live-Inhalte für Streams zu produzieren, und hat in der professionellen Broadcast-Welt erhebliches Bewusstsein und Akzeptanz erlangt.

Skype hat zuvor ndi-® Funktionen zu Skype in späten 2018 hinzugefügt. Microsoft Teams verwendet diese Funktion, um die Besprechungs Erfahrung zu verbessern.

NDI®-Technologie ist auf ein lokales Netzwerk limitiert und sollte nur als Teil des Produktionsworkflows, keine Broadcast-Lösung, betrachtet werden.

## <a name="turn-on-ndi-technology"></a>Aktivieren der ndi®-Technologie

NDI®-Technologie erfordert zwei Schritte, die für einen Benutzer aktiviert werden müssen.

1. Der mandantenadministrator muss die Eigenschaft "AllowNDIStreaming" in CsTeamsMeetingPolicy aktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer die ndi-® Technologie für seinen jeweiligen Client über **Einstellungs**  >  **Berechtigungen**aktivieren.

Wenn ein Benutzer einer Besprechung Beitritt, wird eine Meldung angezeigt, die Sie darüber informiert, dass die Besprechung übertragen wird. Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen Sie von der Besprechung abfallen.

Die folgende Abbildung zeigt die Banner Nachricht, die ein Benutzer in einer Teams-Besprechung sieht.

![Ein Bild des ndi® Technology-Banners, das in einer Teams-Besprechung angezeigt wird.](media/NDI-disclosure.png)

Das Banner enthält einen Link zu den [Microsoft-Datenschutzrichtlinien](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Unterstützte Gebietsschemas und Benutzertypen

NDI®-Technologie wird in allen Gebietsschemas unterstützt. Die folgenden Benutzer sind in einem ndi-®-Technologiedaten Strom enthalten, aber nicht alle Benutzer können auf den ndi-®-Technologiedaten Strom zugreifen:

- In-Tenant – vollständige Unterstützung, bereitgestellt basierend auf Ring/Mandanten-ID/UserID (gesteuert durch die Richtlinien für Besprechungen)
- Federated – kein Datenstrom Zugriff (auch wenn Sie über ndi® Technologie verfügen)<sup>1</sup>
- Freemium-kein Datenstrom Zugriff
- Anonym – kein Datenstrom Zugriff
- Gast – kein Datenstrom Zugriff  

<sup>1</sup> Geräte verfügen über eine ndi-® Technologie Einstellung, die standardmäßig aktiviert ist. Wenn ein Besprechungsteilnehmer ein Gerät mit ndi®-Technologie verwendet, müssen Sie die ndi-® Technologie aktivieren.
