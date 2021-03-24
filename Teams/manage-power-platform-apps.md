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
description: Erfahren Sie, wie Sie den Zugriff auf benutzerdefinierte Apps verwalten, die auf Microsoft Power Platform im Microsoft Teams Admin Center erstellt wurden.
ms.openlocfilehash: 03940d402bd2259287e1e69f844e6560424f15e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096159"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten von Microsoft Power Platform-Apps im Microsoft Teams Admin Center

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform-Apps in Teams

In diesem Artikel erhalten Sie eine Übersicht über die Verwaltung von [Microsoft Power Platform-Apps](https://powerplatform.microsoft.com/) im Microsoft Teams Admin Center.

> [!NOTE]
> Dieser Artikel bezieht sich auf benutzerdefinierte Apps, die von Hersteller in Ihrer Organisation mit Power Apps oder Power Virtual Agents erstellt wurden. Diese benutzerdefinierten Apps werden automatisch zu Teams hinzugefügt. Dieser Artikel gilt nicht für die Power Apps-App oder Power Virtual Agents-App, die von der Seite Apps installiert oder über eine App-Setuprichtlinie an Teams angeheftet wurden. Sie verwalten diese Apps wie für jede [](manage-apps.md) andere App auf der Seite Apps verwalten mithilfe von App-Berechtigungsrichtlinien [und](teams-app-permission-policies.md) [App-Setuprichtlinien.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) ist eine Anwendungsentwicklungsumgebung mit geringem Code/ohne Code, die Hersteller in Ihrer Organisation verwenden können, um benutzerdefinierte Apps zu erstellen, die eine Verbindung mit Ihren Geschäftsdaten herstellen. [Power Virtual Agents ist](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) eine Code-Bot-Gebäudeumgebung für Hersteller, die leistungsstarke Bots erstellen können. Mit der Integration von Microsoft Power Platform-Apps in Teams können Organisationen Geschäftsprozesse rationalisieren, schneller auf sich ändernde Geschäftliche Anforderungen reagieren, um eine bessere Zusammenarbeit zu fördern, und benutzerdefinierte Lösungen erstellen und freigeben, um produktiver zu sein.  

Microsoft Power Platform-Apps, die von Hersteller in Ihrer Organisation erstellt wurden, werden automatisch zu Teams hinzugefügt. Hersteller können steuern, wer auf ihre App zugreifen kann, indem sie das Freigabefeature [in Power Apps](/powerapps/maker/canvas-apps/share-app) und das [Freigabefeature in Power Virtual Agents verwenden.](/power-virtual-agents/admin-share-bots)

Wenn eine Microsoft Power Platform-App erstellt oder freigegeben wird, können Benutzer sie auf der Seite Apps anzeigen und installieren, indem sie zu **Für** Ihren Organisationsnamen erstellt von Ihren Kollegen  >  **wechseln.** (Es kann einige Minuten dauern, bis die App hier angezeigt wird, nachdem eine App erstellt oder freigegeben wurde.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite "Apps" mit Microsoft Power Platform-Apps, die unter Erstellt von Ihren Kollegen aufgeführt sind":::

Wenn die App eine der folgenden Bedingungen erfüllt, wird in **Built by your colleagues** eine App angezeigt.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die App wurde direkt für den Benutzer freigegeben.</li><li>Der Benutzer hat die App kürzlich verwendet. </li></ul>| <ul><li>Der Benutzer hat den Bot erstellt.</li><li>Der Bot gehört einem Team, dem der Benutzer gehört. </li></ul>        |

Benutzer installieren Microsoft Power Platform-Apps auf die gleiche Weise wie andere Teams-Apps. Beachten Sie, dass Benutzer Apps nur in dem Kontext installieren können, in dem sie über Berechtigungen verfügen, z. B. ein Team, das sie besitzen, einen Chat, zu dem sie gehören, oder ihren persönlichen Bereich.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten des Zugriffs auf Microsoft Power Platform-Apps im Microsoft Teams Admin Center

Als Administrator können Sie steuern, ob Microsoft Power Platform-Apps in **Erstellt** von Ihren Kollegen auf der Seite Apps in Teams aufgelistet sind. Sie können alle apps, die in Power Apps erstellt wurden, oder alle apps, die in Power Virtual Agents auf Organisationsebene erstellt wurden, auf der Seite Apps verwalten oder für bestimmte Benutzer mit App-Berechtigungsrichtlinien blockieren oder [zulassen.](teams-app-permission-policies.md) [](manage-apps.md)

Die **Apps "Shared Power Apps"** und **"Shared Power Virtual Agent Apps"** im App Store Ihrer Organisation stellen alle Apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide Apps auf Organisationsebene oder für bestimmte Benutzer blockieren, können diese Benutzer in **Erstellt** von Ihren Kollegen keine Apps von diesen Plattformen sehen und sie nicht in Teams installieren.  

Denken Sie daran, dass Sie den Zugriff auf alle apps steuern können, die in Power Apps und Power Virtual Agents erstellt wurden, aber Sie können einzelne Apps nicht zulassen oder blockieren. Hersteller entscheiden, wer über das Freigabefeature in Power Apps und Power Virtual Agents auf die von ihnen erstellten Apps zugreifen kann. Wenn ein Hersteller eine App, die er in Power Virtual Agents erstellt hat, für einen Benutzer freigegeben hat und Sie Apps für freigegebene **virtuelle Power-Agents** für diesen Benutzer blockiert haben, kann der Benutzer keine Apps von dieser Plattform in Teams sehen oder installieren.

Wenn ein Benutzer über Power Apps oder Power Virtual Agents auf Apps zugreifen darf und Sie dann den Zugriff auf Apps von einer oder beiden Plattformen blockieren, kann der Benutzer weiterhin auf Microsoft Power Platforms-Apps zugreifen und diese verwenden, die er installiert hat, bevor Sie die App oder die Apps blockiert haben. Der Benutzer kann jedoch in Built by your colleagues keine Apps von diesen Plattformen mehr **sehen oder installieren.**

> [!NOTE]
> Die **Organisationsweite** App-Einstellung Interaktion mit [](manage-apps.md) benutzerdefinierten Apps zulassen auf der Seite Apps verwalten gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie mit benutzerdefinierten Apps interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Diese Einstellung ist standardmäßig aktiviert. Wenn diese Einstellung deaktiviert ist, können Benutzer in Ihrer Organisation keine benutzerdefinierten Apps, einschließlich Microsoft Power Platform-Apps, sehen oder installieren. Weitere Informationen finden Sie unter [Verwalten von organisationsweiten App-Einstellungen.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für Ihre Organisation

Standardmäßig sind **freigegebene Power Apps** und Apps für freigegebene virtuelle **Power-Agent** für alle Teams-Benutzer in Ihrer Organisation zulässig. Sie können sie auf Organisationsebene auf der Seite Apps [verwalten](manage-apps.md) im Microsoft Teams Admin Center blockieren oder zulassen.  

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Gehen Sie in der Liste der Apps wie folgt vor:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite "Apps verwalten" mit freigegebenen Microsoft Power Platform-Apps":::

    - Wenn Sie Apps blockieren möchten, die in Power Apps oder Power Virtual Agents für alle Benutzer in Ihrer Organisation erstellt wurden, suchen Sie nach Freigegebene **Power Apps** oder **Freigegebene Power Virtual Agent-Apps,** wählen Sie sie aus, und klicken Sie dann auf **Blockieren.**
    - Um apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or Shared Power Virtual Agent **Apps,** select it, and then **click Allow**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für bestimmte Benutzer

Um bestimmten Benutzern in Ihrer Organisation den Zugriff auf in Power Apps oder Power Virtual Agents erstellte Apps zu gestatten oder zu blockieren, erstellen und weisen Sie eine oder mehrere benutzerdefinierte [App-Berechtigungsrichtlinien zu.](teams-app-permission-policies.md) 

Wenn Sie beispielsweise bestimmte Benutzer am Zugriff auf in Power Apps erstellte Apps blockieren möchten, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um freigegebene **Power Apps** zu blockieren, und weisen Sie die Richtlinie dann diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot einer Benutzerdefinierten App-Berechtigungsrichtlinie mit blockierten freigegebenen Power Apps":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Microsoft Power Platform-Installationsaktivität

Sie können Überwachungsprotokolle für Teams verwenden, um Ereignisse  zu untersuchen, bei denen Benutzer Microsoft Power Platform-Apps im Abschnitt Von Ihren Kollegen erstellt auf der Seite Apps in Teams installiert haben. Suchen Sie [](./audit-log-events.md) dazu im Überwachungsprotokoll nach dem Ereignis Installierte **App** Teams (unter dem **Vorgang AppInstalled)** nach einem Benutzer oder einer Gruppe von Benutzern. Wenn Sie apps finden möchten, die von **Ihren** Kollegen erstellt wurden, suchen Sie in den Details eines datensatzes nach dem **Wert TemplatedInstance** in der **AppDistributionMode-Eigenschaft.** 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot des Werts "TemplatedInstance" in der AppDistributionMode-Eigenschaft":::

> [!NOTE]
> Sie können Überwachungsdatensätze im CSV-Format exportieren, um das Filtern zu vereinfachen.

## <a name="related-topics"></a>Verwandte Themen

- [Freigeben einer Canvas-App in Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Freigeben Ihres Bots für andere Benutzer](/power-virtual-agents/admin-share-bots)
- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Veröffentlichen einer benutzerdefinierten App, die über die Übermittlungs-API für Teams-Apps übermittelt wird](submit-approve-custom-apps.md)