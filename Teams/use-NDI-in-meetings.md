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
description: Erfahren Sie, wie Sie NDI und SDI zum Übertragen von Besprechungsinhalten in Microsoft Teams verwenden.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d048063f7b8efa6b853aa7273e0bcefaeb41b1f
ms.sourcegitcommit: 9175c6d542dd825ce965d0cb7c67264f22315202
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687821"
---
# <a name="broadcast-meeting-content"></a>Übertragen von Besprechungsinhalten 



Teams bietet zwei Optionen für die Übertragung von Teams-Besprechungsinhalten: Network Device Interface (NewTek NDI®) und Serial Digital Interface (SDI):

- Die NewTek NDI-Technologie® ist eine moderne Lösung zum Verbinden von Mediengeräten (z. B. Studiokamera und Mischer). Anstatt physische Verbindungen zu verwenden, ermöglicht die NDI-Technologie® die Konnektivität über ein lokales Intranet, auch auf einem lokalen Computer.

  Die NDI-Technologie® ist zu einer Branchenstandardlösung für die Produktion von Live-Inhalten für Streams geworden und hat in der professionellen Übertragungswelt ein erhebliches Bewusstsein und eine große Akzeptanz erlangt.

- SDI wird seit 1989 in Broadcastproduktionen verwendet und wird auf den meisten älteren Studio-Hardwaregeräten unterstützt. Hardwaregeräte von AJA Video Systems und Blackmagic Design bieten Konnektivität zu älteren Übertragungsgeräten, die SDI verwenden.

> [!NOTE]
> Das Videohardware-Out-Feature, das SDI unterstützt, befindet sich derzeit in der Vorschauversion.

NDI®- und SDI-Technologie wird in allen Gebietsschemas unterstützt.

Der Zugriff auf die Verwendung von NDI und SDI wird durch die Besprechungsrichtlinie für den Benutzer bestimmt, der versucht, das Feature zu aktivieren. Aktivieren Sie für die sicherste Lösung nicht den lokalen Streamingparameter als globale Einstellung.


## <a name="enable-broadcast-features"></a>Aktivieren von Übertragungsfeatures

So aktivieren Sie NDI®- und SDI-Übertragungsfeatures für einen Benutzer:

1. Der Mandantenadministrator muss dem Endbenutzer ermöglichen, lokales Streaming für seine Besprechungsrichtlinie aktiviert zu haben. 

2. Der Endbenutzer muss das lokale Streaming für den jeweiligen Client aktivieren.


Um den Endbenutzer zu aktivieren, können Sie das Teams Admin Center oder Teams PowerShell wie folgt verwenden.

Wechseln Sie im Teams Admin Center zu **Besprechungsrichtlinien > Audio & Video** , und wählen Sie **"Lokale Übertragung" aus**.

Verwenden Sie zum Verwenden von PowerShell das cmdlet Set-CsTeamsMeetingPolicy wie folgt:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer das lokale Streaming für den jeweiligen Client über **Einstellungen-Berechtigungen** >  aktivieren. Weitere Informationen finden Sie [unter Übertragen von Audio und Video aus Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





