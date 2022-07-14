---
title: Verwalten von Geräten mit administrativen Einheiten
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie administrative Einheiten in Microsoft Teams verwenden
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5afbc4acd33acf7e950218e7cf2e30383b3b1d12
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790430"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Verwalten von Geräten im Teams Admin Center mit administrativen Einheiten

Administrative Einheiten im Teams Admin Center bieten detaillierten, rollenbasierten Zugriff für die Verwaltung von Teams-Geräten. Administrative Einheiten gewähren Teams-Administratoren Zugriff auf bestimmte Ressourcen, beschränken jedoch den Zugriff dieses Administrators auf andere Ressourcen. Dies ist besonders hilfreich, wenn Sie lokale Teams-Administratoren in verschiedenen Ländern oder Regionen haben.

So ist Contoso beispielsweise rund um den Globus tätig. Alice ist ein globaler IT-Administrator mit Sitz in London, während Prashant ein lokaler IT-Administrator mit Sitz in Bangalore, Indien, ist. Heute, wenn Prashant sich als Geräteadministrator beim Teams Admin Center anmeldet, kann er Teams-Geräte auf der ganzen Welt sehen. Alice möchte Prashants Zugriff auf Teams-Geräte nur in Bangalore einschränken. Verwaltungseinheiten lassen sie dies tun. Weitere Informationen finden Sie [unter Administrative Einheiten in Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Administrative Einheiten sind derzeit im Teams Admin Center nur für die Administratorrolle für Teams-Geräte verfügbar.

## <a name="add-administrative-units"></a>Hinzufügen von administrativen Einheiten

Sie müssen ein globaler Administrator sein, um administrative Einheiten hinzufügen zu können. Informationen dazu finden [Sie unter "Hinzufügen einer Administrativen Einheit"](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Zuweisen von Administratoren zu administrativen Einheiten

Sie müssen auch globaler Administrator sein, um administrative Einheiten zuweisen zu können. Sie können administrative Einheiten mithilfe von Azure-Portal, PowerShell oder der Microsoft Graph-API zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Azure AD-Rollen mit Administrativem Einheitenbereich](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Administrative Einheiten auswählen

Wenn Sie ein Administrator für Teams-Geräte sind, können Sie sich nach dem Zuweisen eines globalen Administrators zu einer Verwaltungseinheit beim Teams Admin Center anmelden, um Geräte zu verwalten. Wenn Sie nur einer administrativen Einheit zugewiesen sind, werden nur die Geräte angezeigt, die dieser Verwaltungseinheit zugewiesen sind. Wenn Sie mehreren administrativen Einheiten zugewiesen sind, können Sie zwischen diesen administrativen Einheiten wechseln, ohne sich vom Teams Admin Center abzumelden. 

1. Melden Sie sich beim [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) an.

2. Führen Sie im Dialogfeld **"Ihre administrativen Einheiten** " einen der folgenden Schritte aus:
    - Wählen Sie die administrative Einheit aus, die Sie verwalten möchten, oder 
    - Wählen Sie **"Alle Geräte** " aus, wenn Sie über die Berechtigung zum Verwalten aller Geräte für Ihre Organisation verfügen.

3. Klicken Sie auf **Speichern**.

## <a name="switch-administrative-units"></a>Wechseln von Administrativen Einheiten

Wenn Sie ein Administrator für Teams-Geräte sind, können Sie zwischen administrativen Einheiten wechseln, wenn Sie beim Teams Admin Center angemeldet sind. So wechseln Sie zu einer anderen Verwaltungseinheit:

1. Melden Sie sich beim [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) an.

2. Wählen Sie im linken Navigationsbereich **Teams-Geräte** aus.

3. Wählen Sie im rechten Bereich oben links die angezeigte Verwaltungseinheit aus.

4. Führen Sie im Dialogfeld **"Ihre administrativen Einheiten** " einen der folgenden Schritte aus:
    - Wählen Sie die administrative Einheit aus, die Sie verwalten möchten, oder 
    - Wählen Sie **"Alle Geräte** " aus, wenn Sie über die Berechtigung zum Verwalten aller Geräte für Ihre Organisation verfügen.

5. Klicken Sie auf **Speichern**.

## <a name="related-topics"></a>Verwandte Themen

- [Hinzufügen von Benutzern oder Gruppen zu einer Administrativen Einheit](/azure/active-directory/roles/admin-units-members-add)
