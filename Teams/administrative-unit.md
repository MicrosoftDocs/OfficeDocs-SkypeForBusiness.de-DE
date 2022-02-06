---
title: Verwalten von Geräten mit Verwaltungseinheiten
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 'Erfahren Sie, wie Sie administrative Einheiten in Microsoft Teams'
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Verwalten von Geräten im Teams Admin Center mit Verwaltungseinheiten

Administrative Einheiten im Teams Admin Center bieten detaillierten rollenbasierten Zugriff für die Verwaltung Teams Geräten. Administrative Einheiten gewähren Teams Administratorzugriff auf bestimmte Ressourcen, aber den Zugriff dieses Administrator auf andere Ressourcen einschränken. Dies ist besonders hilfreich, wenn Sie lokale Teams in verschiedenen Ländern oder Regionen haben.

Contoso hat beispielsweise Vorgänge rund um den Globus. Andrea ist eine globale IT-Administratorin in London, während Prashant ein lokaler IT-Administrator in Indien ist. Wenn Prashant sich heute als Geräteadministrator beim Teams Admin Center meldet, sieht er Teams auf der ganzen Welt. Andrea möchte den Zugriff von Prashant auf Teams Geräte nur in Den usa einschränken. Verwaltungseinheiten lassen dies zu. Weitere Informationen finden Sie unter [Administrative Einheiten in Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Administrative Einheiten sind derzeit im Teams Admin Center nur für die Administratorrolle Teams Geräte verfügbar.

## <a name="add-administrative-units"></a>Hinzufügen administrativer Einheiten

Sie müssen ein globaler Administrator sein, um administrative Einheiten hinzufügen zu können. Informationen dazu finden Sie unter [Hinzufügen einer Verwaltungseinheit](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Zuweisen von Administratoren zu Verwaltungseinheiten

Sie müssen auch globaler Administrator sein, um administrative Einheiten zuweisen zu können. Sie können Verwaltungseinheiten über das Azure-Portal, PowerShell oder die Microsoft Graph-API zuweisen. Weitere Informationen finden Sie unter [Zuweisen Azure AD Rollen mit administrativem Einheitenbereich](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Administrative Einheiten auswählen

Wenn Sie Ein Teams sind, können Sie sich, nachdem Sie von einem globalen Administrator einer Verwaltungseinheit zugewiesen wurden, beim Teams Admin Center anmelden, um Geräte zu verwalten. Wenn Ihnen nur eine Verwaltungseinheit zugewiesen ist, werden nur die Geräte angezeigt, die dieser Verwaltungseinheit zugewiesen sind. Wenn Sie mehreren Verwaltungseinheiten zugewiesen sind, können Sie zwischen diesen Verwaltungseinheiten wechseln, ohne sich beim Teams Admin Center ab- zu verschreiben. 

1. Melden Sie sich beim [Teams Admin Center an](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Führen Sie **im Dialogfeld Ihre administrativen** Einheiten einen der folgenden Schritte aus:
    - Wählen Sie die Verwaltungseinheit aus, die Sie verwalten möchten, oder 
    - Wählen **Sie Alle Geräte** aus, wenn Sie über die Berechtigung zum Verwalten aller Geräte für Ihre Organisation verfügen.

3. Klicken Sie auf **Speichern**.

## <a name="switch-administrative-units"></a>Wechseln von Verwaltungseinheiten

Wenn Sie Ein Teams sind, können Sie zwischen administrativen Einheiten wechseln, wenn Sie beim Teams Admin Center angemeldet sind. So wechseln Sie zu einer anderen Verwaltungseinheit

1. Melden Sie sich beim [Teams Admin Center an](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Wählen Sie in der linken Navigationsleiste **Teams aus**.

3. Wählen Sie im rechten Bereich oben links die angezeigte Verwaltungseinheit aus.

4. Führen Sie **im Dialogfeld Ihre administrativen** Einheiten einen der folgenden Schritte aus:
    - Wählen Sie die Verwaltungseinheit aus, die Sie verwalten möchten, oder 
    - Wählen **Sie Alle Geräte** aus, wenn Sie über die Berechtigung zum Verwalten aller Geräte für Ihre Organisation verfügen.

5. Klicken Sie auf **Speichern**.
