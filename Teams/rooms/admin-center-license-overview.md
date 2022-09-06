---
title: Microsoft Teams-Räume Lizenzübersicht im Teams Admin Center
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Erfahren Sie mehr über und vergleichen Sie Teams-Räume Lizenzierung und Featureverfügbarkeit im Teams Admin Center.
ms.openlocfilehash: f880f2878c98e739c0367faafed252f93f4cd3d5
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606875"
---
# <a name="microsoft-teams-rooms-license-overview-in-teams-admin-center"></a>Microsoft Teams-Räume Lizenzübersicht im Teams Admin Center

Im Teams Admin Center können Sie Teams-Räume Geräte und deren Peripheriegeräte zentral anzeigen und verwalten. In diesem Artikel erfahren Sie[, über welche Verwaltungsfunktionen](#comparison-of-teams-rooms-feature-availability-by-license) Sie verfügen, je nachdem, ob einem Teams-Räume Gerät eine Microsoft Teams-Räume Basic- oder Microsoft Teams-Räume Pro-Lizenz zugewiesen ist.

Weitere Informationen zu Microsoft Teams-Räume Lizenzen finden Sie [unter Microsoft Teams-Räume Lizenzen](rooms-licensing.md).

## <a name="see-which-licenses-are-assigned-to-teams-rooms-devices"></a>Anzeigen, welche Lizenzen Teams-Räume Geräten zugewiesen sind

Sie können sehen, über welche Lizenz Ihre Geräte verfügen, indem Sie im Teams Admin Center zu **Teams-Geräten** wechseln und dann die Gerätekategorie auswählen, die Sie anzeigen möchten. Wenn Sie z. B. **Teams-Geräte** >  **auswählen Teams-Räume unter Windows**, sehen Sie etwas ähnliches wie in der folgenden Abbildung. Die Spalte **"Lizenz"** zeigt die Teams-Räume Lizenz, die jedem Gerät zugewiesen ist.

:::image type="content" source="../media/mtr-device-inventory-license-focus.png" alt-text="Teams-Räume Bestandsliste mit Fokus auf Standard-, Pro- und Pro-Lizenzen (Testversion).":::

Geräte **mit Pro-** oder **Pro-Lizenzen (Testversion)** können auf alle Features des Teams Admin Centers zugreifen. Geräte mit anderen Lizenzen können auf eine Teilmenge dieser Features zugreifen. Im [Vergleich zur Verfügbarkeit von Teams-Räume Features nach Lizenz](#comparison-of-teams-rooms-feature-availability-by-license) können Sie sehen, welche Features für jede Lizenz verfügbar sind.

> [!IMPORTANT]
> Wenn Sie mehrere Geräte auswählen, die sowohl Microsoft Teams-Räume Basic- als auch Microsoft Teams-Räume Pro-Lizenzen enthalten, werden Aktionen, die eine Microsoft Teams-Räume Pro-Lizenz erfordern, nur auf Geräten ausgeführt, denen diese Lizenz zugewiesen wurde. Die Aktion wird nicht auf Geräten ausgeführt, die der Microsoft Teams-Räume Standardlizenz zugewiesen sind.

## <a name="see-which-features-require-a-microsoft-teams-rooms-pro-license"></a>Anzeigen, welche Features eine Microsoft Teams-Räume Pro-Lizenz erfordern

Features, die eine Microsoft Teams-Räume Pro-Lizenz erfordern, können identifiziert werden, indem Sie auf der Detailseite eines Geräts nach dem :::image type="icon" source="../media/mtr-pro-icon.png" border="false"::: Symbol suchen. Wenn dem aktuell ausgewählten Gerät keine Microsoft Teams-Räume Pro-Lizenz zugewiesen ist, können Sie die Aktion nicht ausführen und sehen eine Aufforderung zum Upgrade.

:::image type="content" source="../media/mtr-restart-device-dialog.png" alt-text="Teams-Räume Dialogfeld &quot;Geräteneustart&quot; mit dem Pro-Symbol.":::

## <a name="comparison-of-teams-rooms-feature-availability-by-license"></a>Vergleich der Verfügbarkeit Teams-Räume Features nach Lizenz

In der folgenden Tabelle sind die Verwaltungsfunktionen aufgeführt, die im Teams Admin Center für jede Microsoft Teams-Räume Lizenz verfügbar sind.

|                                               | Microsoft Teams-Räume Basic | Microsoft Teams-Räume Pro |
|:----------------------------------------------|:---------------------------:|:-------------------------:|
| **Automatische Geräteupdates**                  | &#x2714;                    | &#x2714;                  |
| **Grundlegende Geräteanalysen**                    | &#x2714;                    | &#x2714;                  |
| **Grundlegende Geräteintegrität**                       | &#x2714;                    | &#x2714;                  |
| **Anrufqualitäts-Dashboard**                    | &#x2714;                    | &#x2714;                  |
| **Erstellen und Anzeigen von Arbeitsbereichen**                | &#x2714;                    | &#x2714;                  |
| **Telemetrie in Echtzeit**                       | &#x2714;                    | &#x2714;                  |
| **Regelmäßige Funktionsupdates**                   | &#x2714;                    | &#x2714;                  |
| **Remoteanmeldung und -abmeldung**               | &#x2714;                    | &#x2714;                  |
| **Android-Gerätekonfigurationen**             |                             | &#x2714;                  |
| **Gerätewarnungen**                             |                             | &#x2714;                  |
| **Geräteanalysen – Integrität und Nutzung** |                             | &#x2714;                  |
| **Gerätedetailansicht**                        |                             | &#x2714;                  |
| **Geräteintegritätsdetails**                     |                             | &#x2714;                  |
| **Gerätetags**                               |                             | &#x2714;                  |
| **Graph-APIs**                                |                             | &#x2714;                  |
| **Manuelle Geräteupdates**                     |                             | &#x2714;                  |
| **Remoteneustart**                            |                             | &#x2714;                  |
| **Verwaltung von Windows-Geräteperipheriegeräten**     |                             | &#x2714;                  |
| **Windows-Geräteeinstellungen**                   |                             | &#x2714;                  |
