---
title: Übertragen von Besprechungsinhalten
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie NDI und SDI zum Übertragen von Besprechungsinhalten in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941880"
---
# <a name="broadcast-meeting-content"></a>Übertragen von Besprechungsinhalten 



Teams bietet zwei Optionen für die Übertragung Teams Besprechungsinhalten: Network Device Interface (NewTek NDI®) und Serial Digital Interface (SDI):

- Die NewTek NDI®-Technologie ist eine moderne Lösung zum Verbinden von Mediengeräten (z. B. Studiokamera und -mixer). Anstelle von physischen Verbindungen ermöglicht die NDI®-Technologie die Konnektivität über ein lokales Intranet, einschließlich über einen lokalen Computer.

  Die NDI®-Technologie wurde zu einer standardmäßigen Branchenlösung für die Erstellung von Liveinhalten für Datenströme und hat in der Welt der professionellen Übertragungen ein erhebliches Bewusstsein und die Akzeptanz gewonnen.

- SDI wird seit 1989 in Übertragungsproduktionen verwendet und wird auf den meisten älteren Studiohardwaregeräten unterstützt. Hardwaregeräte von AJA Video Systems und Blackanforderungen Design bieten Konnektivität zu älteren Übertragungsgeräten, die SDI verwenden.

> [!NOTE]
> Das Videohardware-Out-Feature, das SDI unterstützt, befindet sich derzeit in der Preview-Version.

Die NDI®- und SDI-Technologie wird in allen Locales unterstützt.

Der Zugriff auf die Verwendung von NDI und SDI wird durch die Besprechungsrichtlinie für den Benutzer bestimmt, der versucht, das Feature zu aktivieren. Für die sicherste Lösung sollten Sie den lokalen Streamingparameter nicht als globale Einstellung aktivieren.


## <a name="enable-broadcast-features"></a>Aktivieren von Übertragungsfeatures

So aktivieren Sie NDI®- und SDI-Übertragungsfunktionen für einen Benutzer:

1. Der Mandantenadministrator muss es dem Endbenutzer ermöglichen, lokales Streaming für seine Besprechungsrichtlinie zu aktivieren. 

2. Der Endbenutzer muss das lokale Streaming für den jeweiligen Client aktivieren.


Um den Endbenutzer zu aktivieren, können Sie Teams Admin Center oder PowerShell Teams wie folgt verwenden.

Wechseln Sie Teams Admin Center zu Besprechungsrichtlinien > **Audio & Video,** und wählen Sie **NDI-Streaming zulassen aus.**

Um PowerShell zu verwenden, verwenden Sie das Set-CsTeamsMeetingPolicy-Cmdlet wie folgt:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer das lokale Streaming für den jeweiligen Client über die Berechtigungen Einstellungen  >  **aktivieren.** Weitere Informationen finden Sie unter [Übertragen von Audio und Video von Teams.](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)





