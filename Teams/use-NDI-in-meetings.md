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
ms.openlocfilehash: 2a9eed33ba105584379f207697c27e8d6bd6cde5
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359182"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Verwenden der NDI®Technologie in Microsoft Teams

 Die NewTek NDI® (Network Device Interface)-Technologie ist eine moderne Lösung zum Verbinden von Mediengeräten (z. B. studiokamera und -mixer). Anstelle von physischen Verbindungen ermöglicht die NDI®-Technologie die Konnektivität über ein lokales Intranet, einschließlich über einen lokalen Computer.

Die NDI®-Technologie wurde zu einer standardmäßigen Branchenlösung für die Erstellung von Liveinhalten für Datenströme und hat in der Welt der professionellen Übertragungen ein erhebliches Bewusstsein und die Akzeptanz gewonnen.

Skype NDI®-Out-Funktionalität zu Skype Ende 2018 hinzugefügt. Microsoft Teams verwendet diese Funktionalität, um die Besprechungserfahrung zu verbessern.

Die NDI®-Technologie ist auf ein lokales Netzwerk beschränkt und sollte nur als Teil des Produktionsworkflows betrachtet werden, nicht als Übertragungslösung.

## <a name="turn-on-ndi-technology"></a>Aktivieren der NDI®Technologie

NDI® Technologie muss für einen Benutzer in zwei Schritten aktiviert werden.

1. Der Mandantenadministrator muss es dem Endbenutzer ermöglichen, NDI für seine Besprechungsrichtlinie aktiviert zu lassen. Dies kann einzeln im Teams-Verwaltungsportal oder über die Teams PowerShell über die _AllowNDIStreaming-Eigenschaft_ in CsTeamsMeetingPolicy erfolgen.

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer die NDI® Technologie für den jeweiligen Client über Einstellungen  >  **aktivieren.**

Nachdem er für einen Benutzer und seinen jeweiligen Client aktiviert wurde, kann er NDI über das Überlaufmenü aktivieren und "Über NDI übertragen" auswählen.

Nachdem sie den NDI-Feed gestartet und einen Endpunkt einen NDI-Feed abonniert haben, wird eine Meldung angezeigt, die sie benachrichtigt, dass die Besprechung übertragen wird. Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen sie die Besprechung löschen.

Die folgende Abbildung zeigt die Bannernachricht, die ein Benutzer in einer Besprechung Teams sieht.

![er NDI® Banner, das in einer Besprechung Teams wird.](media/NDI-disclosure.png)

Das Banner hat einen Link zur [Microsoft-Datenschutzrichtlinie](https://aka.ms/teamsprivacy).

> [!NOTE]
> NDI® wird nur pro Sitzung aktiviert. In der nächsten Besprechung muss der Benutzer sie aktivieren, bevor sie NDI®.

## <a name="supported-locales-and-user-types"></a>Unterstützte Locales und Benutzertypen

Die NDI®-Technologie wird in allen Locales unterstützt.

Der Zugriff auf die Verwendung von NDI wird durch die Besprechungsrichtlinie für den Benutzer bestimmt, der versucht, das Feature zu aktivieren. Für die sicherste Lösung sollten Sie die NDI-Richtlinie nicht als globale Einstellung aktivieren.
