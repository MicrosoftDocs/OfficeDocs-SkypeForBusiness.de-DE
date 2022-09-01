---
title: Verwalten Sie Microsoft Power Platform-Apps im Microsoft Teams Admin Center
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: Erfahren Sie, wie Sie den Zugriff auf benutzerdefinierte Apps verwalten, die mit Microsoft Power Platform im Teams Admin Center erstellt wurden.
ms.openlocfilehash: b257c4cb32e236d427d58063d340c2bb1c743292
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486730"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Verwalten Sie Microsoft Power Platform-Apps im Teams Admin Center

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform-Apps in Teams

Dieser Artikel gibt Ihnen einen Überblick darüber, wie Sie [Microsoft Power Platform](https://powerplatform.microsoft.com/)-Apps im Microsoft Teams Admin Center verwalten.

> [!NOTE]
> Dieser Artikel gilt für benutzerdefinierte Apps, die von Entwicklern in Ihrer Organisation mit Power Apps oder Power Virtual Agents erstellt wurden. Dieser Artikel gilt nicht für die Power Apps-App oder die Power Virtual Agents-App, die über die Apps-Seite installiert oder über eine App-Setup-Richtlinie an Teams angeheftet werden. Sie können die Store-Apps mithilfe von [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) und [App-Setuprichtlinien](teams-app-setup-policies.md) verwalten.

[Power Apps](https://powerapps.microsoft.com) ist eine Low-Code- oder codefreie-Anwendungsentwicklungsumgebung, die App-Ersteller in Ihrer Organisation verwenden können, um benutzerdefinierte Apps zu erstellen, die eine Verbindung zu Ihren Geschäftsdaten herstellen. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) ist eine codefreie Bot-Erstellungsumgebung für App-Entwickler zum Erstellen leistungsstarker Bots. Durch die Integration von Microsoft Power Platform-Apps in Teams können Organisationen Geschäftsprozesse optimieren, schneller auf sich ändernde Geschäftsanforderungen reagieren, um eine bessere Zusammenarbeit zu fördern, und benutzerdefinierte Lösungen erstellen und freigeben, um produktiver zu sein.  

Microsoft Power Platform Apps, die von Entwicklern in Ihrer Organisation erstellt wurden, werden Teams automatisch hinzugefügt. Entwickler können steuern, wer auf ihre App zugreifen kann, indem sie das [Freigabefeature in Power Apps](/powerapps/maker/canvas-apps/share-app) und das [Freigabefeature in Power Virtual Agents](/power-virtual-agents/admin-share-bots) verwenden.

Wenn eine Microsoft Power Platform-App erstellt oder freigegeben wird, können Benutzer sie auf der Seite „Apps“ anzeigen und installieren, indem sie zu **Gebaut mit Power Platform**. (Nach dem Erstellen oder Freigeben einer App kann es einige Minuten dauern, bis die App hier angezeigt wird.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite &quot;Apps&quot;, auf der Microsoft Power Platform-Anwendungen unter &quot;Mit Power Platform erstellt&quot; aufgeführt sind.":::

Endbenutzer sehen eine App in **Mit Power Platform erstellt**, wenn die App eine der folgenden Bedingungen erfüllt.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die App wurde direkt für den Benutzer freigegeben.</li><li>Der Benutzer hat die App kürzlich verwendet. </li></ul>| <ul><li>Der Benutzer hat den Bot erstellt.</li><li>Der Bot gehört einem Team, in dem der Benutzer Mitglied ist. </li></ul>        |

Benutzer installieren Microsoft Power Platform-Apps auf die gleiche Weise wie alle anderen Teams-Apps. Beachten Sie, dass Benutzer Apps nur in dem Kontext installieren können, für den sie über Berechtigungen verfügen. Zum Beispiel ein Team, das einem Benutzer gehört, ein Chat, an dem der Benutzer beteiligt ist, oder sein persönlicher Bereich.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Verwalten Sie den Zugriff auf Microsoft Power Platform-Anwendungen im Teams-Verwaltungszentrum

Als Administrator können Sie steuern, ob Microsoft Power Platform-Anwendungen auf der Apps-Seite in Teams unter **Mit Power Platform erstellt** aufgelistet werden. Sie können alle in Power Apps erstellten Apps oder alle in Power Virtual Agents erstellten Apps auf Organisationsebene auf der Seite [Apps verwalten](manage-apps.md) oder für bestimmte Benutzer mithilfe von [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) kollektiv blockieren oder zulassen.

Die Apps **Freigegebene Power Apps** und **Freigegebene Power Virtual Agent-Apps** im App Store Ihrer Organisation stellen alle Apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide Apps für die gesamte Organisation oder für bestimmte Benutzer blockieren, können die Benutzer Apps wie blockierte Apps anzeigen, aber nicht in Teams installieren. Die Benutzer können die [Administratorgenehmigung anfordern, um Apps zuzulassen](manage-apps.md#manage-user-requests-to-allow-apps).

Beachten Sie, dass Sie den Zugriff auf alle in Power Apps und Power Virtual Agents erstellten Anwendungen kontrollieren können, nicht aber einzelne Anwendungen zulassen oder sperren können. Der App-Ersteller entscheidet, wer über die Freigabefunktion in Power Apps und Power Virtual Agents auf die von ihm erstellten Apps zugreifen kann. Wenn ein Hersteller eine App, die er in Power Virtual Agents erstellt hat, mit einem Benutzer geteilt hat und Sie **Freigegebene Power Virtual Agents-Apps** für diesen Benutzer blockiert haben, kann der Benutzer keine Apps von dieser Plattform in Teams sehen oder installieren.

Wenn ein Benutzer auf Anwendungen von Power Apps oder Power Virtual Agents zugreifen darf und Sie dann den Zugriff des Benutzers auf Anwendungen von einer oder beiden Plattformen sperren, kann der Benutzer weiterhin auf Microsoft Power Platforms-Anwendungen zugreifen, die er installiert hat, bevor Sie die Anwendung(en) gesperrt haben, und diese verwenden. Der Nutzer kann jedoch keine Anwendungen von diesen Plattformen mehr in **Mit Power Platform erstellt** installieren.

> [!NOTE]
> Die organisationsweit App-Einstellung **Interaktion mit benutzerdefinierten Apps zulassen** auf der Seite [Apps verwalten](manage-apps.md) gilt für alle Mitglieder Ihrer Organisation und legt fest, ob sie mit benutzerdefinierten Apps interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Wenn diese Einstellung deaktiviert ist, können Benutzer in Ihrer Organisation keine benutzerdefinierten Apps installieren, einschließlich Microsoft Power Platform-Apps. Weitere Informationen finden Sie unter [Verwalten von organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Zulassen oder Sperren von Microsoft Power Platform-Apps für Ihr Unternehmen

Standardmäßig sind **freigegebene Power-Apps** und **freigegebene Power Virtual Agent-Apps** für alle Teams-Benutzer in Ihrer Organisation zulässig. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.  

1. Melden Sie sich beim Teams Admin Center an und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)** Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.
1. Führen Sie in der Liste der Apps einen der folgenden Schritte aus.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite &quot;Apps verwalten&quot; mit freigegebenen Microsoft Power Platform-Apps.":::

    * Um Apps zu blockieren, die in Power Apps oder Power Virtual Agents für alle Benutzer in Ihrer Organisation erstellt wurden, suchen Sie nach **Freigegebene Power Apps** oder **Freigegebene Power Virtual Agent-Apps**, wählen Sie sie aus, und wählen Sie dann **Blockieren** aus.
    * Um Apps zu erlauben, die in Power Apps oder Power Virtual Agents für alle Benutzer in Ihrer Organisation erstellt wurden, suchen Sie nach **Freigegebene Power Apps** oder **Freigegebene Power Virtual Agent-Apps**, wählen Sie sie aus, und wählen Sie dann **Erlauben** aus.

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>Zulassen von Microsoft Power Platform-Apps für bestimmte Benutzer

Um bestimmten Benutzern in Ihrem Unternehmen den Zugriff auf in Power Apps oder Power Virtual Agents erstellte Anwendungen zu erlauben oder zu sperren, erstellen Sie eine oder mehrere benutzerdefinierte [Richtlinien für Anwendungsberechtigungen](teams-app-permission-policies.md) und weisen diese zu.

Um beispielsweise bestimmte Benutzer am Zugriff auf Apps zu hindern, die in Power Apps erstellt wurden, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um **freigegebene Power-Apps** zu blockieren, und weisen Sie die Richtlinie dann diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot eines Beispiels für eine benutzerdefinierte App-Berechtigungsrichtlinie mit blockierten freigegebenen Power-Apps.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Installationsaktivitäten von Microsoft Power Platform

Sie können Audit-Protokolle für Teams verwenden, um Ereignisse zu untersuchen, bei denen Benutzer Microsoft Power Platform-Apps aus dem Abschnitt **Mit Power Platform erstellt** auf der Seite "Apps" in Teams installiert haben. Dazu [suchen sie im Audit-Protokoll](./audit-log-events.md) nach dem Ereignis **Installierte App** Teams (unter dem Vorgang **AppInstalled**) für einen Benutzer oder eine Gruppe von Benutzern. Um Anwendungen zu finden, die von **Mit Power Platform erstellt** installiert wurden, suchen Sie nach dem Wert **TemplatedInstance** in der Eigenschaft **AppDistributionMode** in den Details eines bestimmten Datensatzes.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot des TemplatedInstance-Werts in der AppDistributionMode-Eigenschaft." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Sie können Audit-Datensätze im CSV-Format exportieren, um sie leichter zu filtern.

## <a name="related-articles"></a>Verwandte Artikel

* [Freigeben einer Canvas-App in Power Apps](/powerapps/maker/canvas-apps/share-app)
* [Freigeben Ihres Bots für andere Benutzer](/power-virtual-agents/admin-share-bots)
* [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
* [Eine benutzerdefinierte App veröffentlichen, die über die Teams-App Submission API eingereicht wurde](submit-approve-custom-apps.md)
