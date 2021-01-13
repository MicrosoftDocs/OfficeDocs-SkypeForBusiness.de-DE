---
title: Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie den Zugriff auf benutzerdefinierte Apps verwalten, die auf der Microsoft Power Platform im Microsoft Teams Admin Center erstellt werden.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831295"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform apps in Teams

Dieser Artikel enthält eine Übersicht über das Verwalten von [Microsoft Power Platform-Apps](https://powerplatform.microsoft.com/) im Microsoft Teams Admin Center.

> [!NOTE]
> Dieser Artikel bezieht sich auf benutzerdefinierte Apps, die von Entscheidungsträgern in Ihrer Organisation mit Power Apps oder virtuellen Power Agents erstellt wurden. Diese benutzerdefinierten Apps werden automatisch zu Teams hinzugefügt. Dieser Artikel gilt nicht für die Power Apps- oder Power Virtual Agents-App, die über die Seite "Apps" installiert oder über eine App-Setuprichtlinie an Teams angeheftet sind. Sie verwalten diese Apps wie jede andere [](manage-apps.md) App auf der Seite "Apps verwalten", indem Sie Berechtigungsrichtlinien für Apps und Richtlinien für [die](teams-app-permission-policies.md)Einrichtung von [Apps verwenden.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) ist eine Anwendungsentwicklungsumgebung mit geringem Code und keinem Code, die Entscheidungsträger in Ihrer Organisation zum Erstellen benutzerdefinierter Apps verwenden können, die eine Verbindung mit Ihren Geschäftsdaten herstellen. [Power Virtual Agents ist](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) eine Code-Bot-Erstellungsumgebung für Hersteller, die leistungsstarke Bots erstellen können. Mit der Integration von Microsoft Power Platform-Apps in Teams können Organisationen Geschäftsprozesse optimieren, schneller auf sich ändernde Geschäftsanforderungen reagieren, um eine bessere Zusammenarbeit zu fördern, und benutzerdefinierte Lösungen erstellen und teilen, um produktiver zu sein.  

Microsoft Power Platform-Apps, die von Entscheidungsträgern in Ihrer Organisation erstellt wurden, werden automatisch zu Teams hinzugefügt. Entscheidungsträger können steuern, wer auf ihre App zugreifen kann, indem sie das [Freigabefeature in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) und das Freigabefeature in Power Virtual Agents [verwenden.](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)

Wenn eine Microsoft Power Platform-App erstellt oder freigegeben wird, können Benutzer **** sie auf der Seite "Apps" anzeigen und installieren, indem sie zu "Für Ihren Unternehmensnamen erstellt" wechseln, der von Ihren Kollegen  >  **erstellt wurde.** (Es kann einige Minuten dauern, bis eine App hier erstellt oder freigegeben wurde.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite "Apps" mit microsoft Power Platform-Apps, die von Ihren Kollegen erstellt wurden":::

Einem Benutzer wird eine von Ihren Kollegen **integrierte** App angezeigt, wenn die App eine der folgenden Bedingungen erfüllt.

|Power Apps |Virtuelle Power Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die App wurde direkt mit dem Benutzer geteilt.</li><li>Der Benutzer hat die App kürzlich verwendet. </li></ul>| <ul><li>Der Benutzer hat den Bot erstellt.</li><li>Der Bot gehört einem Team, in dem der Benutzer Mitglied ist. </li></ul>        |

Benutzer installieren Microsoft Power Platform-Apps auf die gleiche Weise wie jede andere Teams-App. Denken Sie daran, dass Benutzer Apps nur in dem Kontext installieren können, in dem sie über Berechtigungen verfügen, z. B. ein Team, das er besitzt, einen Chat, zu dem er gehört, oder seinen persönlichen Bereich.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten des Zugriffs auf Microsoft Power Platform-Apps im Microsoft Teams Admin Center

Als Administrator können Sie steuern, ob Microsoft Power Platform-Apps **auf** der Seite "Apps" in Teams von Ihren Kollegen erstellt aufgeführt werden. Sie können alle in Power Apps oder in Power Virtual Agents erstellten Apps [](manage-apps.md) auf Organisationsebene auf der Seite "Apps verwalten" oder für bestimmte Benutzer, die Berechtigungsrichtlinien für Apps verwenden, gemeinsam blockieren oder [zulassen.](teams-app-permission-policies.md)

Die **gemeinsam genutzten Power Apps** und die gemeinsam genutzten virtuellen Power **-Agent-Apps** im App Store Ihrer Organisation stellen alle Apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide Apps auf Organisationsebene oder für bestimmte Benutzer blockieren, können diese Benutzer **keine** Apps von diesen Plattformen in "Von Ihren Kollegen erstellt" sehen und können sie nicht in Teams installieren.  

Denken Sie daran, dass Sie den Zugriff auf alle in Power Apps und Power Virtual Agents erstellten Apps steuern können, aber Sie können einzelne Apps nicht zulassen oder blockieren. Entscheidungsträger entscheiden, wer über das Freigabefeature in Power Apps und virtuellen Power Agents auf die von ihnen erstellten Apps zugreifen kann. Wenn ein Ersteller eine App, die er in Power Virtual Agents erstellt hat, für einen Benutzer freigegeben hat und Sie freigegebene **Power Virtual Agents-Apps** für diesen Benutzer blockiert haben, kann der Benutzer keine Apps von dieser Plattform in Teams sehen oder installieren.

Wenn ein Benutzer auf Apps von Power Apps oder Power Virtual Agents zugreifen darf und Sie den Zugriff des Benutzers auf Apps von einer oder beiden Plattformen blockieren, kann der Benutzer weiterhin auf microsoft Power Platforms-Apps zugreifen und diese verwenden, die er installiert hat, bevor Sie die App oder Apps blockiert haben. Der Benutzer kann jedoch keine Apps von diesen Plattformen mehr sehen oder installieren, die von Ihren Kollegen **entwickelt wurden.**

> [!NOTE]
> Die **Einstellung "Interaktion mit benutzerdefinierten** [](manage-apps.md) Apps organisationsweit zulassen" auf der Seite "Apps verwalten" gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie mit benutzerdefinierten Apps interagieren können. Organisationsweite App-Einstellungen steuern das Verhalten aller Benutzer und setzen alle anderen Benutzerberechtigungsrichtlinien für Apps außer Kraft. Diese Einstellung ist standardmäßig aktiviert. Wenn diese Einstellung deaktiviert ist, können die Benutzer in Ihrer Organisation keine benutzerdefinierten Apps, einschließlich Microsoft Power Platform-Apps, sehen oder installieren. Weitere Informationen finden Sie unter ["Verwalten von organisationsweiten App-Einstellungen".](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für Ihre Organisation

Standardmäßig sind **freigegebene Power Apps** und gemeinsame virtuelle Power **-Agent-Apps** für alle Benutzer von Teams in Ihrer Organisation zulässig. Sie können sie auf Organisationsebene auf der Seite ["Apps verwalten"](manage-apps.md) im Microsoft Teams Admin Center blockieren oder zulassen.  

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".** Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Gehen Sie in der Liste der Apps wie folgt vor:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite "Apps verwalten" mit freigegebenen Microsoft Power Platform-Apps":::

    - Um apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or Shared Power Virtual Agent **Apps, select** it, and then click **Block.**
    - Um apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or Shared Power Virtual Agent **Apps, select** it, and then click **Allow.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für bestimmte Benutzer

Wenn Sie bestimmten Benutzern in Ihrer Organisation den Zugriff auf Apps gestatten oder blockieren möchten, die in Power Apps oder power Virtual Agents erstellt wurden, erstellen und weisen Sie mindestens eine benutzerdefinierte [Berechtigungsrichtlinien für Apps zu.](teams-app-permission-policies.md) 

Um beispielsweise bestimmte Benutzer am Zugriff auf apps zu blockieren, die in Power Apps erstellt wurden, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um freigegebene **Power Apps** zu blockieren, und weisen Sie die Richtlinie dann diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot eines Beispiels für eine benutzerdefinierte App-Berechtigungsrichtlinie mit blockierten gemeinsam genutzten Power Apps":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Installationsaktivitäten der Microsoft Power Platform

Sie können Überwachungsprotokolle für Teams verwenden, um Ereignisse  zu untersuchen, bei denen Benutzer Microsoft Power Platform-Apps über den Abschnitt "Von Ihren Kollegen erstellt" auf der Seite "Apps" in Teams installiert haben. Durchsuchen Sie [](https://docs.microsoft.com/microsoftteams/audit-log-events) dazu das Überwachungsprotokoll nach dem Ereignis "Installierte App **Teams"** (unter dem Vorgang **"AppInstalled")** nach einem Benutzer oder einer Gruppe von Benutzern. Um Apps zu **finden,** die von Ihren Kollegen erstellt wurden, suchen Sie in den Details eines bestimmten Datensatzes in der Eigenschaft **"AppDistributionMode"** nach dem Wert **"TemplatedInstance".** 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot des Werts "TemplatedInstance" in der Eigenschaft "AppDistributionMode"":::

> [!NOTE]
> Zur einfacheren Filterung können Sie Überwachungsdatensätze im CSV-Format exportieren.

## <a name="related-topics"></a>Verwandte Themen

- [Teilen einer Canvas-App in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Freigeben Ihres Bots für andere Benutzer](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird](submit-approve-custom-apps.md)
