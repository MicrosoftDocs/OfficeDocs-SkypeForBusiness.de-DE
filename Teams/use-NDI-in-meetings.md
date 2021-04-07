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
description: Erfahren Sie, wie Sie NDI in Microsoft Teams verwenden.
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
# <a name="use-ndi-technology-in-microsoft-teams"></a>Verwenden von NDI® in Microsoft Teams

 NewTek NDI® (Network Device Interface) ist eine moderne Lösung zum Verbinden von Mediengeräten (z. B. einer Studiokamera und einem Mixer). Statt physische Verbindungen zu verwenden, ermöglicht die NDI®-Technologie die Konnektivität über ein lokales Intranet, auch auf einem lokalen Computer.

Die NDI®-Technologie ist zu einer branchenüblichen Lösung für die Erstellung von Liveinhalten für Datenströme geworden und hat in der professionellen Übertragungswelt an Bekanntheit und Akzeptanz gewonnen.

Skype hat Skype ende 2018 ® NDI-Out-Funktionalität hinzugefügt. Microsoft Teams verwendet diese Funktionalität, um die Besprechungserfahrung zu verbessern.

Die NDI®-Technologie ist auf ein lokales Netzwerk beschränkt und sollte nur als Teil des Produktionsworkflows und nicht als Übertragungslösung betrachtet werden.

## <a name="turn-on-ndi-technology"></a>Aktivieren der NDI® Technologie

Die NDI®-Technologie erfordert zwei Schritte, um für einen Benutzer aktiviert zu sein.

1. Der Mandantenadministrator muss die Eigenschaft "AllowNDIStreaming" in CsTeamsMeetingPolicy aktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Nachdem diese Änderung ausgefüllt wurde, muss der Endbenutzer die NDI®-Technologie für den jeweiligen Client über **Einstellungenberechtigungen**  >  **aktivieren.**

Wenn ein Benutzer einer Besprechung beitritt, wird eine Meldung angezeigt, die ihn darüber informiert, dass die Besprechung übertragen wird. Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen sie die Besprechung löschen.

Die folgende Abbildung zeigt die Bannernachricht, die einem Benutzer in einer Teams-Besprechung angezeigt wird.

![das NDI®-Technologiebanner, das in einer Teams-Besprechung angezeigt wird.](media/NDI-disclosure.png)

Das Banner verfügt über einen Link zur [Microsoft-Datenschutzrichtlinie.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® wird nur pro Sitzung aktiviert. Bei der nächsten Anmeldung muss der Benutzer sie aktivieren, bevor er NDI®.

## <a name="supported-locales-and-user-types"></a>Unterstützte Locales und Benutzertypen

Die NDI®-Technologie wird in allen Locales unterstützt. Die folgenden Benutzer sind in einem NDI®-Technologiestream enthalten, aber nicht alle Benutzer können auf den NDI®-Technologiestream zugreifen:

- In-Mandant – vollständiger Support, basierend auf ring/tenantId/userId (gesteuert durch Besprechungsrichtlinie)
- Verbund – kein Streamzugriff (auch dann nicht, wenn NDI®<sup>auf) 1</sup>
- Premium – kein Streamzugriff
- Anonym – kein Streamzugriff
- Gast – kein Streamzugriff  

<sup>1</sup> Geräte verfügen über eine NDI®-Technologieeinstellung, die standardmäßig aktiviert ist. Wenn ein Besprechungsteilnehmer ein Gerät mit deaktivierter NDI®-Technologie verwendet, muss er die NDI® aktivieren.
