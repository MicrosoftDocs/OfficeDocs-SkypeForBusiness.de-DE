---
title: Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie den Zugriff auf benutzerdefinierte Apps verwalten, die auf Microsoft Power Platform basieren, im Microsoft Teams Admin Center.
ms.openlocfilehash: 9f212cf52ec757fc4860f081fb67da2cb1b4fcd5
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2022
ms.locfileid: "65136996"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform-Apps in Teams

In diesem Artikel erhalten Sie einen Überblick über die Verwaltung von [Microsoft Power Platform-Apps](https://powerplatform.microsoft.com/) im Microsoft Teams Admin Center.

> [!NOTE]
> Dieser Artikel bezieht sich auf benutzerdefinierte Apps, die von Herstellern in Ihrer Organisation mit Power Apps oder Power Virtual Agents erstellt wurden. Diese benutzerdefinierten Apps werden Teams automatisch hinzugefügt. Dieser Artikel gilt nicht für die Power Apps-App oder Power Virtual Agents App, die von der Seite "Apps" installiert oder über eine App-Setuprichtlinie an Teams angeheftet sind. Sie verwalten diese Apps wie jede andere App auf der Seite " [Apps verwalten](manage-apps.md) ", indem Sie [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) und [App-Setuprichtlinien](teams-app-setup-policies.md) verwenden.

[Power Apps](https://powerapps.microsoft.com) ist eine Entwicklungsumgebung mit geringem Code und ohne Code, mit der Entwickler in Ihrer Organisation benutzerdefinierte Apps erstellen können, die eine Verbindung mit Ihren Geschäftsdaten herstellen. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) ist eine Codefreie Bot-Erstellungsumgebung für Hersteller, um leistungsstarke Bots zu erstellen. Mit der Integration von Microsoft Power Platform-Apps in Teams können Organisationen Geschäftsprozesse optimieren, schneller auf sich ändernde Geschäftsanforderungen reagieren, um eine bessere Zusammenarbeit zu fördern, und benutzerdefinierte Lösungen erstellen und freigeben, um produktiver zu sein.  

Microsoft Power Platform-Apps, die von Herstellern in Ihrer Organisation erstellt wurden, werden Teams automatisch hinzugefügt. Entscheidungsträger können steuern, wer auf ihre App zugreifen kann, indem sie das [Freigabefeature in Power Apps](/powerapps/maker/canvas-apps/share-app) und das [Freigabefeature in Power Virtual Agents](/power-virtual-agents/admin-share-bots) verwenden.

Wenn eine Microsoft Power Platform-App erstellt oder freigegeben wird, können Benutzer sie auf der Seite "Apps" anzeigen und installieren, indem sie **von Ihren Kollegen** zu ***"Built for Your Organization NameBuilt*** > " wechseln. (Es kann einige Minuten dauern, nachdem eine App erstellt oder freigegeben wurde, bis die App hier angezeigt wird.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite &quot;Apps&quot; mit Microsoft Power Platform-Apps, die in &quot;Von Ihren Kollegen erstellt&quot; aufgeführt sind":::

Einem Benutzer wird eine **Von Ihren Kollegen erstellte** App angezeigt, wenn die App eine der folgenden Bedingungen erfüllt.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die App wurde direkt für den Benutzer freigegeben.</li><li>Der Benutzer hat die App kürzlich verwendet. </li></ul>| <ul><li>Der Benutzer hat den Bot erstellt.</li><li>Der Bot befindet sich im Besitz eines Teams, in dem der Benutzer Mitglied ist. </li></ul>        |

Benutzer installieren Microsoft Power Platform-Apps auf die gleiche Weise wie andere Teams-Apps. Beachten Sie, dass Benutzer Apps nur in dem Kontext installieren können, für den sie über Berechtigungen verfügen, z. B. ein Team, das sie besitzen, einen Chat, zu dem sie gehören, oder ihren persönlichen Bereich.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten des Zugriffs auf Microsoft Power Platform-Apps im Microsoft Teams Admin Center

Als Administrator können Sie steuern, ob Microsoft Power Platform-Apps auf der Seite "Apps" in Teams unter "**Von Ihren Kollegen erstellt**" aufgeführt sind. Sie können alle in Power Apps erstellten Apps oder alle in Power Virtual Agents erstellten Apps auf Organisationsebene auf der Seite ["Apps verwalten](manage-apps.md)" oder für bestimmte Benutzer, die [App-Berechtigungsrichtlinien verwenden,](teams-app-permission-policies.md) gemeinsam blockieren oder zulassen.

Die Apps **"Shared Power Apps**" und **"Shared Power Virtual Agent Apps**" im App Store Ihrer Organisation stellen alle Apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide apps auf Organisationsebene oder für bestimmte Benutzer blockieren, können diese Benutzer keine Apps von diesen Plattformen in **Built von Ihren Kollegen** sehen und sie nicht in Teams installieren.  

Denken Sie daran, dass Sie den Zugriff auf alle Apps steuern können, die in Power Apps und Power Virtual Agents erstellt wurden, aber Sie können einzelne Apps nicht zulassen oder blockieren. Entscheidungsträger entscheiden, wer über das Freigabefeature aus Power Apps und Power Virtual Agents auf die apps zugreifen kann, die sie erstellen. Wenn ein Hersteller eine App, die er in Power Virtual Agents erstellt hat, für einen Benutzer freigegeben hat und Sie **freigegebene Power Virtual Agents Apps** für diesen Benutzer blockiert haben, kann der Benutzer keine Apps von dieser Plattform in Teams sehen oder installieren.

Wenn ein Benutzer von Power Apps oder Power Virtual Agents aus auf Apps zugreifen darf und Sie dann den Zugriff des Benutzers auf Apps von einer oder beiden Plattformen aus blockieren, kann der Benutzer weiterhin auf die installierten Microsoft Power Platforms-Apps zugreifen und diese verwenden, bevor Sie die App oder Apps blockiert haben. Der Benutzer kann jedoch keine Apps mehr von diesen Plattformen sehen oder installieren, die **von Ihren Kollegen erstellt wurden**.

> [!NOTE]
> Die Einstellung " **Interaktion mit benutzerdefinierten Apps** organisationsweit zulassen" auf der Seite ["Apps verwalten](manage-apps.md) " gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie mit benutzerdefinierten Apps interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Diese Einstellung ist standardmäßig aktiviert. Wenn diese Einstellung deaktiviert ist, können Benutzer in Ihrer Organisation keine benutzerdefinierten Apps, einschließlich Microsoft Power Platform-Apps, sehen oder installieren. Weitere Informationen finden [Sie unter Verwalten organisationsweiter App-Einstellungen](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für Ihre Organisation

Standardmäßig sind **freigegebene Power Apps** und **freigegebene Power Virtual Agent-Apps** für alle Teams Benutzer in Ihrer Organisation zulässig. Sie können sie auf Organisationsebene auf der Seite ["Apps verwalten"](manage-apps.md) im Microsoft Teams Admin Center blockieren oder zulassen.  

1. Wechseln Sie im linken Bereich des Microsoft Teams Admin Center zu **Teams** **appsManage-Apps** > . Sie müssen ein globaler Administrator oder Teams Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Führen Sie in der Liste der Apps eine der folgenden Aktionen aus.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite &quot;Apps verwalten&quot; mit freigegebenen Microsoft Power Platform-Apps":::

    - Um Apps zu blockieren, die in Power Apps oder Power Virtual Agents für alle Benutzer in Ihrer Organisation erstellt wurden, suchen Sie nach **freigegebenen Power Apps**- oder **Shared Power Virtual Agent-Apps**, wählen Sie sie aus, und klicken Sie dann auf **"Blockieren**".
    - Um Apps zuzulassen, die in Power Apps oder Power Virtual Agents für alle Benutzer in Ihrer Organisation erstellt wurden, suchen Sie nach **freigegebenen Power Apps**- oder **freigegebenen Power Virtual Agent-Apps**, wählen Sie sie aus, und klicken Sie dann auf **"Zulassen**".

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für bestimmte Benutzer

Um bestimmten Benutzern in Ihrer Organisation den Zugriff auf Apps zu ermöglichen oder zu blockieren, die in Power Apps oder Power Virtual Agents erstellt wurden, erstellen und weisen Sie eine oder mehrere benutzerdefinierte [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) zu.

Um beispielsweise bestimmten Benutzern den Zugriff auf apps zu blockieren, die in Power Apps erstellt wurden, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um **freigegebene Power Apps** zu blockieren, und weisen Sie die Richtlinie dann diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot eines Beispiels für eine benutzerdefinierte App-Berechtigungsrichtlinie mit blockierten freigegebenen Power Apps.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Installationsaktivitäten von Microsoft Power Platform

Sie können Überwachungsprotokolle für Teams verwenden, um Ereignisse zu untersuchen, bei denen Benutzer Microsoft Power Platform-Apps über den Abschnitt **"Von Ihren Kollegen erstellt**" auf der Seite "Apps" in Teams installiert haben. Durchsuchen Sie hierzu [das Überwachungsprotokoll](./audit-log-events.md) nach dem Ereignis **"Installierte App** Teams" (unter dem **Vorgang "AppInstalled**") nach einem Benutzer oder einer Gruppe von Benutzern. Um Apps zu finden, die **von Ihren Kollegen installiert** wurden, suchen Sie in den Details eines bestimmten Datensatzes nach dem **TemplatedInstance-Wert** in der **AppDistributionMode-Eigenschaft** .

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot des TemplatedInstance-Werts in der AppDistributionMode-Eigenschaft.":::

> [!NOTE]
> Sie können Überwachungsdatensätze im CSV-Format exportieren, um die Filterung zu vereinfachen.

## <a name="related-topics"></a>Verwandte Themen

- [Freigeben einer Canvas-App in Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Freigeben Ihres Bots für andere Benutzer](/power-virtual-agents/admin-share-bots)
- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Veröffentlichen einer benutzerdefinierten App, die über die Teams App-Übermittlungs-API übermittelt wurde](submit-approve-custom-apps.md)
