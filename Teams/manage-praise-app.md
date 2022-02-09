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
ms.openlocfilehash: 064a1b90db44971e2fd796ea96de2a3523f7f380
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401609"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der Lob-App im Microsoft Teams Admin Center

Die Lob-App in Microsoft Teams hilft Benutzern, Den Mitgliedern Ihrer Organisation oder Ihres Klassenzimmers Anerkennung zu zeigen. Die Badges in Lob sollen Ihnen helfen, die Anstrengungen zu erkennen, die in die breite Palette an Arbeit eingeht, die Teams Benutzer tun, von Lehrkräften bis zu Mitarbeitern an vorderer Front. Weitere Informationen finden Sie unter [Senden Lob an Personen](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Administratoren müssen über eine Lizenz Teams verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie versuchen, ohne eine Lizenz für Teams auf dieses Feature zu zugreifen, wird eine Fehlermeldung angezeigt.

> [!NOTE]
> Die Lob-App ist für GCC Cloudumgebung, aber nicht für GCC High oder DoD verfügbar.

## <a name="enable-or-disable-praise-in-your-organization"></a>Aktivieren oder deaktivieren Lob in Ihrer Organisation

Lob ist standardmäßig für alle Benutzer Teams in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot der Seite "Lob"-App-Details" im Teams Admin Center mit der Umschaltleiste "Status".":::

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Suchen Sie in der Liste der Apps nach der Lob-App, wählen Sie sie aus, und wechseln Sie dann zur Umschaltfunktion **Status** in **Blockiert** oder **Zulässig**.

Beachten Sie, dass sich diese Einstellung sowohl auf die Lob-App als auch Lob Feature in der App "Viva Insights" in Teams.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Aktivieren oder deaktivieren Lob für bestimmte Benutzer in Ihrer Organisation

Wenn Sie zulassen oder blockieren möchten, dass bestimmte Benutzer in Ihrer Organisation Lob, stellen Sie sicher, dass Lob auf der Seite Apps verwalten für Ihre [Organisation aktiviert](manage-apps.md) ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

## <a name="badges"></a>Badges

Dies ist der Standardsatz von Signalen in Lob. Teams Benutzer in Ihrer Organisation können diese Badges verwenden, um ihre Kollegen zu erkennen, damit sie mit ihrer Arbeit über- und hinaus gehen können.

:::image type="content" source="media/default-set-praise.png" alt-text="Abbildung von Signalen im Standardabzeichensatz.":::

> [!NOTE]
> Ab Februar 2022 können Personen nur Standardabzeichen senden und empfangen. Benutzerdefinierte Badges sind nicht mehr verfügbar, und Optionen für benutzerdefinierte Badges werden bald von der Einstellungen-Seite der App im Teams Admin Center entfernt.

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)