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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a82174fd09106f623bcf0f9a03a99c2978253ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615111"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Verwenden der NDI®Technologie in Microsoft Teams

 Die NewTek NDI®(Network Device Interface)-Technologie ist eine moderne Lösung zum Verbinden von Mediengeräten (z. B. Studiokamera und -mixer). Anstelle von physischen Verbindungen ermöglicht die NDI®-Technologie die Konnektivität über ein lokales Intranet, einschließlich über einen lokalen Computer.

Die NDI®-Technologie wurde zu einer standardmäßigen Branchenlösung für die Erstellung von Liveinhalten für Datenströme und hat sich in der Welt der professionellen Übertragungen zu einem erheblichen Bekanntheitsgrad und zur Verbreitung entwickelt.

Skype NDI®-Out-Funktionalität zu Skype Ende 2018 hinzugefügt. Microsoft Teams verwendet diese Funktionalität, um die Besprechungserfahrung zu verbessern.

Die NDI®-Technologie ist auf ein lokales Netzwerk beschränkt und sollte nur als Teil des Produktionsworkflows betrachtet werden, nicht als Übertragungslösung.

## <a name="turn-on-ndi-technology"></a>Aktivieren der NDI®Technologie

NDI® Technologie muss für einen Benutzer in zwei Schritten aktiviert sein.

1. Der Mandantenadministrator muss es dem Endbenutzer ermöglichen, NDI für seine Besprechungsrichtlinie aktiviert zu lassen. Dies kann einzeln im Teams-Verwaltungsportal oder über die Teams PowerShell über die _AllowNDIStreaming-Eigenschaft_ in CsTeamsMeetingPolicy erfolgen.

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer die NDI® Technologie für den jeweiligen Client über Einstellungen  >  **aktivieren.**

Nachdem er für einen Benutzer und seinen jeweiligen Client aktiviert wurde, kann er NDI über das Überlaufmenü aktivieren und "Über NDI übertragen" auswählen.

Nachdem sie den NDI-Feed gestartet und einen Endpunkt einen NDI-Feed abonniert haben, wird eine Meldung angezeigt, die sie benachrichtigt, dass die Besprechung übertragen wird. Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen sie die Besprechung löschen.

Die folgende Abbildung zeigt die Bannernachricht, die ein Benutzer in einer Besprechung Teams sieht.

![er NDI® Technologiebanner, das in einer Besprechung Teams wird.](media/NDI-disclosure.png)

Das Banner hat einen Link zur [Microsoft-Datenschutzrichtlinie](https://aka.ms/teamsprivacy).

> [!NOTE]
> NDI® nur pro Sitzung aktiviert. In der nächsten Besprechung muss der Benutzer sie aktivieren, bevor sie NDI®.

## <a name="supported-locales-and-user-types"></a>Unterstützte Locales und Benutzertypen

Die NDI®-Technologie wird in allen Locales unterstützt.

Der Zugriff auf die Verwendung von NDI wird durch die Besprechungsrichtlinie für den Benutzer bestimmt, der versucht, das Feature zu aktivieren. Für die sicherste Lösung sollten Sie die NDI-Richtlinie nicht als globale Einstellung aktivieren.
