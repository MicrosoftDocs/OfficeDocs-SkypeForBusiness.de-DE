---
title: Verwalten der Lob-App im Teams Admin Center
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Erfahren Sie, wie Sie die Lob-App im Microsoft Teams Admin Center verwalten.
ms.collection:
- M365-collaboration
ms.openlocfilehash: 0f30a508fd1c0f2e82dcab3c22d3ade94d4e0118
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269420"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der Lob-App im Microsoft Teams Admin Center

Die Praise-App in Microsoft Teams hilft Benutzern, Mitgliedern Ihrer Organisation oder Ihres Klassenzimmers Wertschätzung zu zeigen. Die Badges in Praise sollen dabei helfen, den Aufwand zu erkennen, der in die breite Palette von Aufgaben fällt, die Teams-Benutzer erledigen, von Lehrkräften bis hin zu Mitarbeitern in Service und Produktion. Weitere Informationen finden Sie unter ["Lob an Andere senden"](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Administratoren müssen über eine Teams-Lizenz verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie versuchen, ohne Teams-Lizenz auf dieses Feature zuzugreifen, wird eine Fehlermeldung angezeigt.

> [!NOTE]
> Die Praise-App ist für die GCC-Cloudumgebung verfügbar, jedoch nicht für GCC High oder DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Aktivieren oder Deaktivieren von Lob in Ihrer Organisation

Lob ist standardmäßig für alle Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot der Detailseite der Lob-App im Teams Admin Center mit der Umschaltfläche &quot;Status&quot;.":::

1. Wechseln Sie im linken Bereich des Microsoft Teams Admin Centers zu **"Teams-Apps** > **verwalten"**.
2. Suchen Sie in der Liste der Apps nach der Lob-App, wählen Sie sie aus, und wechseln Sie dann auf " **Status** " auf **"Blockiert** " oder " **Zulässig**".

Beachten Sie, dass sich diese Einstellung sowohl auf die Lob-App als auch auf die Lob-Funktion in der Viva Insights-App in Teams auswirkt.

Wenn Sie den Status auf "Blockiert" festlegen, wird die Lob-App für Teams innerhalb weniger Minuten blockiert. Lob in Viva Insights kann jedoch 7-9 Tage dauern, bis sie blockiert werden.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von Lob für bestimmte Benutzer in Ihrer Organisation

Um bestimmten Benutzern in Ihrer Organisation die Verwendung von Lob zu erlauben oder zu blockieren, stellen Sie sicher, dass Lob für Ihre Organisation auf der Seite ["Apps verwalten"](manage-apps.md) aktiviert ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

## <a name="badges"></a>Abzeichen

Hier ist der Standardsatz von Signalen in Lob. Teams-Benutzer in Ihrer Organisation können diese Badges verwenden, um ihre Kollegen dafür zu erkennen, dass sie mit ihrer Arbeit darüber hinaus gehen.

:::image type="content" source="media/default-set-praise.png" alt-text="Abbildung von Signalen im Standardsignalsatz.":::

> [!NOTE]
> Ab Februar 2022 können Personen nur Standard-Badges senden und empfangen. Benutzerdefinierte Badges sind nicht mehr verfügbar, und Optionen für benutzerdefinierte Badges wurden aus dem Teams Admin Center entfernt.

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten Sie Ihre Apps im Microsoft Teams Admin Center](manage-apps.md)
