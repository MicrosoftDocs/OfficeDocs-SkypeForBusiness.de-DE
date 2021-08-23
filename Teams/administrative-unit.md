---
title: Verwenden von Verwaltungseinheitenfunktionen in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Verwaltungseinheitenfunktionen in Ihrer Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93add1771e76f6640b6f1fde3ee6e732499aa329
ms.sourcegitcommit: 9062b2c81c582ddc878c825ba1b22a6c23ca4b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2021
ms.locfileid: "58399361"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>Verwaltungseinheitsfunktionen für die Geräteverwaltung in Teams

Genaueres Rollenbasierter Zugriff für die Geräteverwaltung mithilfe des Microsoft Teams Admin Centers. Wir haben das Verwaltungseinheitskonzept für die Geräteverwaltung über das Teams Admin Center implementiert.

Mit dem Konzept der Verwaltungseinheiten stellen Sie den Zugriff auf eine bestimmte Gruppe von Ressourcen für einen dedizierten Administrator sicher. Die Verwaltungseinheit beschränkt den Zugriff auf alle Ressourcen. Sie können die gleiche Funktionalität für die Verwaltung Teams Geräte erweitern.

> [!NOTE]
> Das Verwaltungseinheitskonzept ist derzeit nur für die Rolle Teams Geräteadministrator verfügbar.

Contoso verfügt beispielsweise über Vorgänge in verschiedenen Ländern/Regionen. Andrea ist globale IT-Administratorin in London, Während Prashant IT-Administrator für Indien ist. Wenn Prashant sich heute mit der Rolle "Geräteadministrator" beim Teams Admin Center meldet, sieht er Geräte auf der ganzen Welt. Andrea möchte den Zugriff von Prashant auf die in Indien vorhandenen Geräte einschränken. Das Konzept der administrativen Einheiten hilft bei der Lösung dieses Problems. Erfahren Sie mehr [über das Verwaltungseinheitskonzept.](/azure/active-directory/roles/administrative-units)

![Diagramm mit Szenarien](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>Erstellung administrativer Einheiten

Erstellen Sie administrative Einheiten im Azure-Portal, und weisen Sie Administratoren für die entsprechenden administrativen Einheiten zu. Weitere Informationen zum Zuweisen von Verwaltungseinheiten finden Sie unter [Verwalten von Administratoreinheiten.](/azure/active-directory/roles/admin-units-manage)

![Beispiel für unternehmensverwaltungseinheiten](media/au-example.png)

Nach der Einrichtung kann der globale IT-Administrator Dann Gerätebenutzer hinzufügen, die dieser Verwaltungseinheit entsprechen.

![Beispielunternehmen mit Vorschau für Benutzer](media/au-example2.png)

Die Zuweisung der Rolle kann über PowerShell mithilfe des [Cmdlets Add-AzureADMSScopedRoleMembership](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0) durchgeführt werden.

Nachdem Sie Benutzern für administrative Einheiten Rollen zugewiesen haben, müssen sich die Benutzer beim Teams Admin Center anmelden, um mit der Verwaltung von Geräten mit Bereichsbereich zu beginnen.

## <a name="experience-for-administrative-unit-admin"></a>Benutzererfahrung für Administratoren von Verwaltungseinheiten

Wenn denselben Administratoren die Zuständigkeit für mehrere administrative Einheiten zugewiesen ist, können sie zwischen administrativen Einheiten wechseln, ohne sich vom Portal ab- ab- zu ab registrieren. In der geänderten Ansicht "Verwaltungseinheiten" werden ihnen nur die Geräte angezeigt, die der neuen Verwaltungseinheit zugeordnet sind.
