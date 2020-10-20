---
title: Verwalten von Power Platform-apps im Microsoft Teams Admin Center
author: lanachin
ms.author: v-lanac
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
description: Erfahren Sie, wie Sie den Zugriff auf Power Platform-apps im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: a380a7d8803fc32393f5c99c576cb304e563c296
ms.sourcegitcommit: 96febfae562d604d9affc60028975881f5d6fb7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48599550"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten von Power Platform-apps im Microsoft Teams Admin Center

## <a name="power-platform-apps-in-teams"></a>Power Platform-apps in Teams

In diesem Artikel erhalten Sie einen Überblick über das Verwalten von [Power Platform](https://powerplatform.microsoft.com/) -apps, die Teams im Microsoft Teams Admin Center hinzugefügt wurden.

[Power apps](https://powerapps.microsoft.com) ist eine Anwendungsentwicklungsumgebung mit geringem Code/ohne Code, die Entscheidungsträger in Ihrer Organisation zum Erstellen benutzerdefinierter Apps verwenden können, die eine Verbindung mit ihren Geschäftsdaten herstellen. [Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) ist eine nicht-Code-bot-Gebäudeumgebung für Entscheidungsträger, um leistungsfähige Bots zu erstellen. Durch die Integration von Power-Platform-apps in Teams können Unternehmen Geschäftsprozesse rationalisieren, auf sich verändernde geschäftliche Anforderungen schneller reagieren, um eine größere Zusammenarbeit zu fördern sowie benutzerdefinierte Lösungen zu erstellen und freizugeben, um produktiver zu arbeiten.  

Power Platform-apps, die von Entscheidungsträgern in Ihrer Organisation erstellt wurden, werden automatisch zu Teams hinzugefügt. Entscheidungsträger können mithilfe der [Freigabefunktion in Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) und der [Freigabefunktion in Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)steuern, wer auf Ihre App zugreifen kann. 

Wenn eine Power Platform-App erstellt oder freigegeben wird, können Benutzer Sie auf der Seite "Apps" anzeigen und installieren, indem Sie **für *Ihren Organisationsnamen***, der  >  **von ihren Kollegen erstellt wurde**, auf "erstellt" klicken. (Es kann einige Minuten dauern, nachdem eine App erstellt oder freigegeben wurde, damit die app hier angezeigt wird.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite "Apps" mit Power Platform-apps, die von ihren Kollegen erstellt wurden":::

Ein Benutzer sieht eine Power Platform-App **, die von ihren Kollegen erstellt wird,** wenn die APP eine der folgenden Bedingungen erfüllt.

|Power-apps |Power Virtual-Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die APP wurde direkt für den Benutzer freigegeben.</li><li>Der Benutzer hat die APP zuletzt verwendet. </li></ul>| <ul><li>Der Benutzer hat den bot erstellt.</li><li>Der Bot ist Eigentum eines Teams, in dem der Benutzer Mitglied ist. </li></ul>        |

Benutzer installieren Power Platform-apps auf die gleiche Weise wie jede andere Teams-app. Beachten Sie, dass Benutzer nur apps in dem Kontext installieren können, in dem Sie über Berechtigungen verfügen, beispielsweise ein Team, dem Sie angehören, ein Chat, zu dem Sie gehören, oder Ihr persönlicher Bereich.

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Verwalten des Zugriffs auf Power Platform-apps im Microsoft Teams Admin Center

Als Administrator können Sie steuern, ob Power Platform-apps in Teams **von ihren Kollegen** auf der Seite "Apps" erstellt werden. Auf der Seite " [apps verwalten](manage-apps.md) " oder für bestimmte Benutzer, die [App-Berechtigungsrichtlinien](teams-app-permission-policies.md)verwenden, können Sie alle apps, die in Power-Apps oder in allen Apps erstellt wurden, in Power Virtual Agents auf Organisationsebene erstellen.

Die apps im App Store der **freigegebenen Power apps** -und **Shared Power Virtual Agent** -apps stellen alle apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide dieser Apps auf Organisationsebene oder für bestimmte Benutzer blockieren, können diese Benutzer keine apps von diesen Plattformen sehen, die **von ihren Kollegen erstellt** wurden, und können diese nicht in Teams installieren.  

Beachten Sie, dass Sie den Zugriff auf alle apps steuern können, die in Power apps und Power Virtual-Agents erstellt wurden, aber Sie können einzelne apps nicht zulassen oder blockieren. Entscheidungsträger entscheiden, wer auf die apps zugreifen kann, die Sie über das Freigabefeature in Power apps und Power Virtual-Agents erstellen. Wenn ein Hersteller eine APP freigegeben hat, die Sie in Power Virtual Agents mit einem Benutzer erstellt haben, und Sie für diesen Benutzer **freigegebene Power Virtual Agents-apps** blockiert haben, ist der Benutzer nicht in der Lage, Apps von dieser Plattform in Teams anzuzeigen oder zu installieren.

Wenn ein Benutzer auf apps von Power Apps oder Power Virtual Agents zugreifen darf und Sie den Benutzer dann daran hindern, auf apps von einer oder beiden dieser Plattformen zuzugreifen, kann der Benutzer weiterhin auf die von Ihnen installierten Power Platform-apps zugreifen und diese verwenden, bevor Sie die APP oder die apps blockiert haben. Der Benutzer kann jedoch keine apps mehr von diesen Plattformen sehen oder installieren, die von **ihren Kollegen erstellt wurden**.

> [!NOTE]
> Die Einstellung " **Interaktion mit benutzerdefinierten apps** auf Organisationsebene zulassen" auf der Seite " [apps verwalten](manage-apps.md) " gilt für alle Personen in Ihrer Organisation und steuert, ob Sie mit benutzerdefinierten apps interagieren können. Organisationsweite App-Einstellungen Regeln das Verhalten für alle Benutzer und überschreiben alle anderen APP-Berechtigungsrichtlinien, die Benutzern zugewiesen sind. Diese Einstellung ist standardmäßig aktiviert. Wenn diese Einstellung deaktiviert ist, können Benutzer in Ihrer Organisation keine benutzerdefinierten apps sehen oder installieren, einschließlich Power Platform-apps. Weitere Informationen finden Sie unter [Verwalten von organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a>Zulassen oder Blockieren von Power Platform-Apps für Ihre Organisation

Standardmäßig sind **freigegebene Power apps** -und **Shared Power Virtual Agent-apps** für alle Teams-Benutzer in Ihrer Organisation zugelassen. Sie können Sie auf der Organisationsebene auf der Seite " [apps verwalten](manage-apps.md) " im Microsoft Teams Admin Center blockieren oder zulassen.  

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**. Sie müssen ein globaler Administrator oder Team Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Führen Sie in der Liste der apps eine der folgenden Aktionen aus:

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite "Apps verwalten" mit freigegebenen Power Platform-apps":::

    - Wenn Sie apps, die in Power Apps oder Power Virtual-Agents erstellt wurden, für alle Benutzer in Ihrer Organisation blockieren möchten, suchen Sie nach **freigegebenen Power apps** oder **virtuellen Agent-apps**, wählen Sie Sie aus, und klicken Sie dann auf **blockieren**.
    - Wenn Sie apps, die in Power Apps oder Power Virtual-Agents erstellt wurden, für alle Benutzer in Ihrer Organisation zulassen möchten, suchen Sie nach **freigegebenen Power apps** oder **Virtual Agent-Apps für gemeinsame Power**, wählen Sie Sie aus, und klicken Sie dann auf **zulassen**.

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a>Zulassen oder Blockieren von Power Platform-Apps für bestimmte Benutzer

Wenn Sie bestimmten Benutzern in Ihrer Organisation den Zugriff auf apps erlauben oder blockieren möchten, die in Power Apps oder Power Virtual-Agents erstellt wurden, erstellen Sie eine oder mehrere benutzerdefinierte [App-Berechtigungsrichtlinien](teams-app-permission-policies.md), und weisen Sie diese zu. 

Wenn Sie beispielsweise verhindern möchten, dass bestimmte Benutzer auf apps zugreifen können, die in Power Apps erstellt wurden, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um **freigegebene Power apps**zu blockieren, und weisen Sie die Richtlinie diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permissions-policy.png" alt-text="Screenshot einer benutzerdefinierten Beispiel-App-Berechtigungsrichtlinie mit blockierten freigegebenen Power apps":::

### <a name="use-audit-logs-to-investigate-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Power Platform-Installationsaktivitäten

Sie können Überwachungsprotokolle für Teams verwenden, um Ereignisse zu untersuchen, bei denen Benutzer Power Platform-Apps über den Abschnitt " **von ihren Kollegen erstellt** " auf der Seite "Apps" in Microsoft Teams installiert haben. Durchsuchen Sie dazu [das Überwachungsprotokoll](https://docs.microsoft.com/microsoftteams/audit-log-events) für das **installierte App** Teams-Ereignis (unter dem **AppInstalled** -Vorgang) für einen bestimmten Benutzer oder eine Gruppe von Benutzern. Suchen Sie nach dem **TemplatedInstance** -Wert unter der **AppDistributionMode** -Eigenschaft in den Details eines bestimmten Datensatzes, um apps zu finden, die im Abschnitt " **von ihren Kollegen erstellt** " installiert sind. 

> [!NOTE]
> Sie können Überwachungsdatensätze im CSV-Format exportieren, um die Filterung zu vereinfachen.

## <a name="related-topics"></a>Verwandte Themen

- [Freigeben einer Canvas-app in Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Freigeben Ihres bot für andere Benutzer](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Verwalten von apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Veröffentlichen einer benutzerdefinierten APP, die über die APP-Übermittlungs-API der Teams gesendet wird](submit-approve-custom-apps.md)
