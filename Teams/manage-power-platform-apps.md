---
title: Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center
author: cichur
ms.author: v-mahoffman
manager: serdars
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
description: Erfahren Sie, wie Sie den Zugriff auf benutzerdefinierte Apps verwalten, die auf der Microsoft Power Platform im Microsoft Teams Admin Center erstellt wurden.
ms.openlocfilehash: 5e372c69f30fc3c8758a389c705653b8ab04f310
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759277"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform-Apps in Teams

Dieser Artikel gibt Ihnen einen Überblick über das Verwalten von [Microsoft Power Platform-Apps](https://powerplatform.microsoft.com/) im Microsoft Teams Admin Center.

> [!NOTE]
> Dieser Artikel bezieht sich auf benutzerdefinierte Apps, die von Entscheidungsträgern in Ihrer Organisation mithilfe von Power Apps oder Power Virtual Agents. Diese benutzerdefinierten Apps werden automatisch zu Teams. Dieser Artikel gilt nicht für die Power Apps- oder Power Virtual Agents-App, die über die Seite Apps installiert oder über eine App-Setuprichtlinie an Teams angeheftet wurden. Sie verwalten diese Apps wie jede andere [](manage-apps.md) App auf der Seite "Apps verwalten", indem Sie App-Berechtigungsrichtlinien [und](teams-app-permission-policies.md)Richtlinien für die [App-Einrichtung verwenden.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) ist eine Anwendungsentwicklungsumgebung mit geringem Code/Code, die von Entscheidungsträgern in Ihrer Organisation zum Erstellen benutzerdefinierter Apps verwendet werden kann, die eine Verbindung mit Ihren Geschäftsdaten herstellen. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) ist eine Code-Bot-Umgebung zum Erstellen leistungsstarker Bots für Hersteller. Mit der Integration von Microsoft Power Platform-Apps in Teams können Organisationen Geschäftsprozesse optimieren, schneller auf sich ändernde Geschäftsanforderungen reagieren, um eine bessere Zusammenarbeit zu fördern, und benutzerdefinierte Lösungen erstellen und teilen, um produktiver zu sein.  

Microsoft Power Platform-Apps, die von Hersteller in Ihrer Organisation erstellt wurden, werden automatisch Teams. Entscheidungsträger können steuern, wer auf ihre App zugreifen kann, indem sie das [Freigabefeature in](/powerapps/maker/canvas-apps/share-app) Power Apps und das [Freigabefeature in Power Virtual Agents.](/power-virtual-agents/admin-share-bots)

Wenn eine Microsoft Power Platform-App erstellt oder freigegeben wird, können Benutzer **** sie auf der Seite Apps anzeigen und  >  **installieren.** Wechseln Sie dazu zu Für Ihre Organisation erstellter Name Von Ihren Kollegen erstellt . (Nach dem Erstellen oder Teilen einer App kann es einige Minuten dauern, bis die App hier angezeigt wird.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite "Apps", auf der microsoft Power Platform-Apps in der Liste "Von Ihren Kollegen erstellt" aufgeführt sind":::

Wenn die App eine der folgenden Bedingungen **erfüllt,** wird dem Benutzer eine von Ihren Kollegen selbst erstellten App angezeigt.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die App wurde direkt mit dem Benutzer geteilt.</li><li>Der Benutzer hat die App kürzlich verwendet. </li></ul>| <ul><li>Der Benutzer hat den Bot erstellt.</li><li>Der Bot gehört einem Team, in dem der Benutzer Mitglied ist. </li></ul>        |

Benutzer installieren Microsoft Power Platform-Apps auf die gleiche Weise wie alle anderen Teams Apps. Beachten Sie, dass Benutzer Apps nur in dem Kontext installieren können, in dem sie Berechtigungen besitzen, z. B. ein Team, das sie besitzen, einen Chat, zu dem sie gehören, oder einen Chat, zu dem sie gehören, oder ihren persönlichen Bereich.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten des Zugriffs auf Microsoft Power Platform-Apps im Microsoft Teams Admin Center

Als Administrator können Sie steuern, ob Microsoft Power Platform-Apps **unter** Von Ihren Kollegen erstellt auf der Seite Apps in Teams. Sie können alle in Power Apps erstellten Apps oder alle in Power Virtual Agents erstellten Apps auf [](manage-apps.md) Organisationsebene auf der Seite Apps verwalten oder für bestimmte Benutzer mithilfe von App-Berechtigungsrichtlinien gemeinsam blockieren oder [zulassen.](teams-app-permission-policies.md)

Die **Apps Shared Power Apps** und Shared Power Virtual Agent **Apps** im App Store Ihrer Organisation stellen alle Apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide Apps auf Organisationsebene oder für bestimmte Benutzer blockieren, können diese Benutzer **keine** Apps von diesen Plattformen unter Von Ihren Kollegen erstellt sehen und können sie nicht in Teams.  

Denken Sie daran, dass Sie den Zugriff auf alle in Power Apps und Power Virtual Agents erstellten Apps steuern können, aber Sie können keine einzelnen Apps zulassen oder blockieren. Entscheidungsträger entscheiden, wer über das Freigabefeature innerhalb von Apps Power Apps und Power Virtual Agents. Wenn ein Ersteller eine app, die er in Power Virtual Agents erstellt hat, für einen Benutzer freigegeben hat und Sie Freigegebene **Power Virtual Agents-Apps** für diesen Benutzer blockiert haben, kann der Benutzer in Teams keine Apps auf dieser Plattform sehen oder installieren.

Wenn ein Benutzer auf Apps von Power Apps oder Power Virtual Agents zugreifen darf und Sie den Zugriff des Benutzers auf Apps von einer oder beiden Plattformen blockieren, kann der Benutzer weiterhin auf die Microsoft Power Platforms-Apps zugreifen und diese verwenden, die er installiert hat, bevor Sie die App oder die Apps blockiert haben. Der Benutzer kann jedoch keine Apps von diesen Plattformen mehr unter Von Ihren Kollegen **erstellt sehen oder installieren.**

> [!NOTE]
> Die **Einstellung Interaktion mit benutzerdefinierten** Apps [](manage-apps.md) organisationsweit zulassen auf der Seite Apps verwalten gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie mit benutzerdefinierten Apps interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Diese Einstellung ist standardmäßig aktiviert. Wenn diese Einstellung deaktiviert ist, können die Benutzer in Ihrer Organisation keine benutzerdefinierten Apps, einschließlich Microsoft Power Platform-Apps, sehen oder installieren. Weitere Informationen finden Sie unter [Verwalten von organisationsweiten App-Einstellungen.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für Ihre Organisation

Standardmäßig sind **freigegebene Power Apps** **und virtuelle Power-Agent-Apps** für alle Teams in Ihrer Organisation zulässig. Sie können sie auf Organisationsebene auf [](manage-apps.md) der Seite Apps verwalten im Admin Center Microsoft Teams zulassen.  

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder ein Teams sein, um auf die Seite zugreifen zu können.
2. Gehen Sie in der Liste der Apps wie folgt vor:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite "Apps verwalten" mit freigegebenen Microsoft Power Platform-Apps":::

    - Um in Power Apps oder Power Virtual Agents erstellte Apps für alle Benutzer in Ihrer Organisation zu blockieren, suchen Sie nach **Freigegebene Power Apps-** oder **Virtuelle Power Virtual Agent-Apps,** wählen Sie sie aus, und klicken Sie dann auf **Blockieren.**
    - Um apps created in Power Apps or Power Virtual Agents for all users in your **organization,** search for Shared **Power Apps** or Shared Power Virtual Agent Apps , select it, and then click **Allow**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für bestimmte Benutzer

Wenn Sie bestimmten Benutzern in Ihrer Organisation den Zugriff auf in Power Apps oder Power Virtual Agents erstellte Apps gestatten oder blockieren möchten, erstellen Sie eine oder mehrere benutzerdefinierte [App-Berechtigungsrichtlinien,](teams-app-permission-policies.md)und weisen Sie sie zu. 

Um beispielsweise für bestimmte Benutzer den Zugriff auf in Power Apps erstellte Apps zu blockieren, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um **freigegebene Power Apps** zu blockieren, und weisen Sie die Richtlinie dann diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot eines Beispiels für eine benutzerdefinierte App-Berechtigungsrichtlinie mit Power Apps Freigabe.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Installationsaktivitäten der Microsoft Power Platform

Mithilfe von Überwachungsprotokollen für Teams Ereignisse untersuchen, bei denen Benutzer  Microsoft Power Platform-Apps im Abschnitt Von Ihren Kollegen erstellt auf der Seite Apps in Teams. Durchsuchen Sie [](./audit-log-events.md) dazu das Überwachungsprotokoll  nach dem Teams-Ereignis der installierten App (unter dem Vorgang **"AppInstalled")** nach einem Benutzer oder einer Gruppe von Benutzern. Um Apps zu finden, die unter Von Ihren Kollegen erstellt installiert **wurden,** suchen Sie in den Details eines bestimmten Datensatzes in der **AppDistributionMode-Eigenschaft** nach dem **TemplatedInstance-Wert.** 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot des TemplatedInstance-Werts in der Eigenschaft "AppDistributionMode".":::

> [!NOTE]
> Zur einfacheren Filterung können Sie Überwachungsdatensätze im CSV-Format exportieren.

## <a name="related-topics"></a>Verwandte Themen

- [Freigeben einer Canvas-App in Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Freigeben Ihres Bots für andere Benutzer](/power-virtual-agents/admin-share-bots)
- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Veröffentlichen einer benutzerdefinierten App, die über die API Teams Übermittlung von Apps übermittelt wird](submit-approve-custom-apps.md)