---
title: Verwenden von NDI in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie NDI in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598464"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Verwenden der NDI®Technologie in Microsoft Teams

 Die NewTek NDI®(Network Device Interface)-Technologie ist eine moderne Lösung zum Verbinden von Mediengeräten (z. B. Studiokamera und -mixer). Anstelle von physischen Verbindungen ermöglicht die NDI®-Technologie die Konnektivität über ein lokales Intranet, einschließlich über einen lokalen Computer.

Die NDI®-Technologie wurde zu einer standardmäßigen Branchenlösung für die Erstellung von Liveinhalten für Datenströme und hat in der Welt der professionellen Übertragungen ein erhebliches Bewusstsein und die Akzeptanz gewonnen.

Skype NDI®-Out-Funktionalität zu Skype Ende 2018 hinzugefügt. Microsoft Teams verwendet diese Funktionalität, um die Besprechungserfahrung zu verbessern.

Die NDI®-Technologie ist auf ein lokales Netzwerk beschränkt und sollte nur als Teil des Produktionsworkflows betrachtet werden, nicht als Übertragungslösung.

## <a name="turn-on-ndi-technology"></a>Aktivieren der NDI® Technologie

NDI® Technologie erfordert, dass zwei Schritte für einen Benutzer aktiviert sind.

1. Der Mandantenadministrator muss die Eigenschaft "AllowNDIStreaming" in CsTeamsMeetingPolicy aktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer die NDI®Technologie für den jeweiligen Client über Einstellungen  >  **aktivieren.**

Wenn ein Benutzer einer Besprechung beitritt, wird eine Meldung angezeigt, in der er darüber informiert wird, dass die Besprechung übertragen wird. Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen sie die Besprechung löschen.

Die folgende Abbildung zeigt die Bannernachricht, die einem Benutzer in einer Besprechung Teams wird.

![er NDI® Technologiebanner, der in einer Besprechung Teams wird.](media/NDI-disclosure.png)

Das Banner hat einen Link zur [Microsoft-Datenschutzrichtlinie](https://aka.ms/teamsprivacy).

> [!NOTE]
> NDI® wird nur pro Sitzung aktiviert. Bei der nächsten Anmeldung muss der Benutzer sie aktivieren, bevor er NDI®.

## <a name="supported-locales-and-user-types"></a>Unterstützte Locales und Benutzertypen

NDI® Technologie wird in allen Locales unterstützt. Die folgenden Benutzer sind in einem NDI®Technologiestream enthalten, aber nicht alle Benutzer können auf den NDI®-Datenstrom zugreifen:

- In-Mandant – vollständiger Support, geliefert basierend auf der Ring-/Mandanten-ID/Benutzer-ID (gesteuert durch Besprechungsrichtlinie)
- Verbund – kein Streamzugriff (auch dann nicht, wenn NDI®)<sup>1</sup>
- Premium – kein Streamzugriff
- Anonym – kein Streamzugriff
- Gast – kein Streamzugriff  

<sup>1</sup> Geräte verfügen über eine NDI®-Technologieeinstellung, die standardmäßig aktiviert ist. Wenn ein Besprechungsteilnehmer ein Gerät mit deaktivierter NDI®-Technologie verwendet, muss er die NDI® aktivieren.
