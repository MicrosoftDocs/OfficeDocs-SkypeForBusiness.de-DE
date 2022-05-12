---
title: Verwalten der Lob-App im Teams Admin Center
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Erfahren Sie, wie Sie die Lob-App im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: ff9985025146136ae78d8e822dd5b61903443605
ms.sourcegitcommit: 73df40ce6fbd1d305fd381140f293a2feb0d27bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "65359775"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der Lob-App im Microsoft Teams Admin Center

Die Lob-App in Microsoft Teams hilft Benutzern, Mitgliedern Ihrer Organisation oder Ihres Klassenzimmers Wertschätzung zu zollen. Die Badges in Lob sollen helfen, den Aufwand zu erkennen, der in die breite Palette von Arbeit fällt, die Teams Benutzer erledigen, von Lehrkräften bis hin zu Mitarbeitern in Service und Produktion. Weitere Informationen finden Sie unter ["Lob an Personen senden](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)".

Administratoren müssen über eine Teams Lizenz verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie versuchen, ohne eine Teams Lizenz auf dieses Feature zuzugreifen, wird eine Fehlermeldung angezeigt.

> [!NOTE]
> Die Lob-App ist für GCC Cloudumgebung verfügbar, jedoch nicht für GCC High oder DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Aktivieren oder Deaktivieren von Lob in Ihrer Organisation

Lob ist standardmäßig für alle Teams Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot der Seite Lob App-Details im Teams Admin Center mit der Umschaltfläche &quot;Status&quot;.":::

1. Wechseln Sie im linken Bereich des Microsoft Teams Admin Center zu **Teams** **appsManage-Apps** > .
2. Suchen Sie in der Liste der Apps nach der Lob App, wählen Sie sie aus, und schalten Sie dann die  Status-Umschaltfläche auf **"Blockiert**" oder "**Zulässig**".

Beachten Sie, dass sich diese Einstellung sowohl auf die Lob-App als auch auf das Lob-Feature in der Viva Insights-App in Teams auswirkt.

Wenn Sie den Status auf "Blockiert" festlegen, wird die Lob-App innerhalb weniger Minuten für Teams blockiert. Lob in Viva Insights kann jedoch 7-9 Tage dauern, bis sie blockiert werden.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von Lob für bestimmte Benutzer in Ihrer Organisation

Um bestimmten Benutzern in Ihrer Organisation die Verwendung von Lob zu ermöglichen oder zu blockieren, stellen Sie sicher, dass Lob für Ihre Organisation auf der Seite ["Apps verwalten"](manage-apps.md) aktiviert ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

## <a name="badges"></a>Abzeichen

Dies ist der Standardsatz von Signalen in Lob. Teams Benutzer in Ihrer Organisation können diese Signale verwenden, um ihre Kollegen zu erkennen, damit sie mit ihrer Arbeit darüber hinaus gehen.

:::image type="content" source="media/default-set-praise.png" alt-text="Abbildung von Signalen im Standardsignalsatz.":::

> [!NOTE]
> Ab Februar 2022 können Personen nur Standard-Badges senden und empfangen. Benutzerdefinierte Badges sind nicht mehr verfügbar, und Optionen für benutzerdefinierte Badges wurden aus dem Teams Admin Center entfernt.

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
