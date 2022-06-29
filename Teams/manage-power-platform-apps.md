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
description: Erfahren Sie, wie Sie den Zugriff auf benutzerdefinierte Apps verwalten, die mitHilfe von Microsoft Power Platform im Teams Admin Center erstellt wurden.
ms.openlocfilehash: bf75d65f9ebc84ec836dd64839b3e6178d828867
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240524"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Verwalten von Microsoft Power Platform-Apps im Teams Admin Center

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform-Apps in Teams

In diesem Artikel erhalten Sie einen Überblick über die Verwaltung von [Microsoft Power Platform-Apps](https://powerplatform.microsoft.com/) im Microsoft Teams Admin Center.

> [!NOTE]
> Dieser Artikel bezieht sich auf benutzerdefinierte Apps, die von Entwicklern in Ihrer Organisation mitHilfe von Power Apps oder Power Virtual Agents erstellt wurden. Dieser Artikel gilt nicht für die Power Apps-App oder die Power Virtual Agents-App, die auf der Seite "Apps" installiert oder über eine App-Setuprichtlinie an Teams angeheftet sind. Sie können die Store-Apps mithilfe von [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) und [App-Setuprichtlinien](teams-app-setup-policies.md) verwalten.

[Power Apps](https://powerapps.microsoft.com) ist eine Entwicklungsumgebung mit geringem Code oder ohne Code, die App-Ersteller in Ihrer Organisation verwenden können, um benutzerdefinierte Apps zu erstellen, die eine Verbindung mit Ihren Geschäftsdaten herstellen. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) ist eine Codefreie Bot-Erstellungsumgebung für App-Hersteller, um leistungsstarke Bots zu erstellen. Mit der Integration von Microsoft Power Platform-Apps in Teams können Organisationen Geschäftsprozesse optimieren, schneller auf sich ändernde Geschäftsanforderungen reagieren, um eine bessere Zusammenarbeit zu fördern, und benutzerdefinierte Lösungen erstellen und freigeben, um produktiver zu sein.  

Microsoft Power Platform-Apps, die von Entwicklern in Ihrer Organisation erstellt wurden, werden teams automatisch hinzugefügt. Entwickler können steuern, wer auf ihre App zugreifen kann, indem sie das [Freigabefeature in Power Apps](/powerapps/maker/canvas-apps/share-app) und das [Freigabefeature in Power Virtual Agents verwenden](/power-virtual-agents/admin-share-bots).

Wenn eine Microsoft Power Platform-App erstellt oder freigegeben wird, können Benutzer sie auf der Seite "Apps" anzeigen und installieren, indem sie zu **"Mit Power Platform erstellt"** wechseln. (Es kann einige Minuten dauern, nachdem eine App erstellt oder freigegeben wurde, bis die App hier angezeigt wird.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots der Seite &quot;Apps&quot; mit Microsoft Power Platform-Apps, die in &quot;Integriert mit Power Platform&quot; aufgeführt sind":::

Endbenutzer sehen eine app in **Built with Power Platform** , wenn die App eine der folgenden Bedingungen erfüllt.

|Power Apps |Virtuelle Power Agents  |
|---------|---------|
|<ul><li>Der Benutzer hat die App erstellt.</li><li>Die App wurde direkt für den Benutzer freigegeben.</li><li>Der Benutzer hat die App kürzlich verwendet. </li></ul>| <ul><li>Der Benutzer hat den Bot erstellt.</li><li>Der Bot befindet sich im Besitz eines Teams, in dem der Benutzer Mitglied ist. </li></ul>        |

Benutzer installieren Microsoft Power Platform-Apps auf die gleiche Weise wie jede andere Teams-App. Beachten Sie, dass Benutzer Apps nur in dem Kontext installieren können, für den sie über Berechtigungen verfügen. Beispielsweise ein Team, das ein Benutzer besitzt, ein Chat, zu dem der Benutzer gehört, oder sein persönlicher Bereich.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Verwalten des Zugriffs auf Microsoft Power Platform-Apps im Teams Admin Center

Als Administrator können Sie steuern, ob Microsoft Power Platform-Apps auf der Seite "Apps" in Teams unter " **Mit Power Platform erstellt"** aufgeführt sind. Sie können alle in Power Apps erstellten Apps oder alle in Power Virtual Agents erstellten Apps auf Organisationsebene auf der Seite ["Apps verwalten](manage-apps.md) " oder für bestimmte Benutzer, die [App-Berechtigungsrichtlinien verwenden,](teams-app-permission-policies.md) gemeinsam blockieren oder zulassen.

Die **Apps "Shared Power Apps** " und **"Shared Power Virtual Agent Apps"** im App Store Ihrer Organisation stellen alle Apps dar, die auf dieser bestimmten Plattform erstellt wurden. Wenn Sie eine oder beide Apps für die gesamte Organisation oder für bestimmte Benutzer blockieren, können die Benutzer Apps wie blockierte Apps anzeigen, aber nicht in Teams installieren. Die Benutzer können [die Administratorgenehmigung anfordern, um die Blockierung von Apps aufzuheben](manage-apps.md#manage-user-requests-to-unblock-apps).

Denken Sie daran, dass Sie den Zugriff auf alle Apps steuern können, die in Power Apps und Power Virtual Agents erstellt wurden, Aber Sie können einzelne Apps nicht zulassen oder blockieren. Der App-Ersteller entscheidet, wer über das Freigabefeature in Power Apps und Power Virtual Agents auf die von ihnen erstellten Apps zugreifen kann. Wenn ein Hersteller eine App, die er in Power Virtual Agents erstellt hat, für einen Benutzer freigegeben hat und Sie **freigegebene Power Virtual Agents-Apps** für diesen Benutzer blockiert haben, kann der Benutzer keine Apps von dieser Plattform in Teams sehen oder installieren.

Wenn ein Benutzer über Power Apps oder Power Virtual Agents auf Apps zugreifen darf und Sie dann den Zugriff des Benutzers auf Apps von einer oder beiden Plattformen aus blockieren, kann der Benutzer weiterhin auf die installierten Microsoft Power Platforms-Apps zugreifen und diese verwenden, bevor Sie die App oder Apps blockiert haben. Der Benutzer kann jedoch keine Apps mehr von diesen Plattformen in **Built with Power Platform** installieren.

> [!NOTE]
> Die Einstellung " **Interaktion mit benutzerdefinierten Apps** organisationsweit zulassen" auf der Seite ["Apps verwalten](manage-apps.md) " gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie mit benutzerdefinierten Apps interagieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Wenn diese Einstellung deaktiviert ist, können Benutzer in Ihrer Organisation keine benutzerdefinierten Apps installieren, einschließlich Microsoft Power Platform-Apps. Weitere Informationen finden [Sie unter Verwalten organisationsweiter App-Einstellungen](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für Ihre Organisation

Standardmäßig sind **freigegebene Power-Apps** und **freigegebene Power Virtual Agent-Apps** für alle Teams-Benutzer in Ihrer Organisation zulässig. Sie können sie auf Organisationsebene auf der Seite ["Apps verwalten"](manage-apps.md) im Microsoft Teams Admin Center blockieren oder zulassen.  

1. Wechseln Sie im linken Bereich des Microsoft Teams Admin Centers zu **"Teams-Apps** > **verwalten"**. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um auf die Seite zugreifen zu können.
2. Führen Sie in der Liste der Apps eine der folgenden Aktionen aus.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Screenshot der Seite &quot;Apps verwalten&quot; mit freigegebenen Microsoft Power Platform-Apps":::

    - Um Apps zu blockieren, die in Power Apps oder Power Virtual Agents für alle Benutzer in Ihrer Organisation erstellt wurden, suchen Sie nach **freigegebenen Power Apps** oder **freigegebenen Power Virtual Agent-Apps**, wählen Sie sie aus, und klicken Sie dann auf **"Blockieren"**.
    - Um in Power Apps oder Power Virtual Agents erstellte Apps für alle Benutzer in Ihrer Organisation zuzulassen, suchen Sie nach **freigegebenen Power Apps** oder **freigegebenen Power Virtual Agent-Apps**, wählen Sie sie aus, und klicken Sie dann auf **"Zulassen"**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Zulassen oder Blockieren von Microsoft Power Platform-Apps für bestimmte Benutzer

Um bestimmten Benutzern in Ihrer Organisation den Zugriff auf apps zu ermöglichen oder zu blockieren, die in Power Apps oder Power Virtual Agents erstellt wurden, erstellen und weisen Sie eine oder mehrere benutzerdefinierte [App-Berechtigungsrichtlinien](teams-app-permission-policies.md) zu.

Um z. B. bestimmte Benutzer am Zugriff auf in Power Apps erstellte Apps zu hindern, erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie, um **freigegebene Power Apps** zu blockieren, und weisen Sie die Richtlinie dann diesen Benutzern zu.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Screenshot eines Beispiels für eine benutzerdefinierte App-Berechtigungsrichtlinie mit blockierten freigegebenen Power-Apps.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Verwenden von Überwachungsprotokollen zum Untersuchen der Installationsaktivitäten von Microsoft Power Platform

Sie können Überwachungsprotokolle für Teams verwenden, um Ereignisse zu untersuchen, bei denen Benutzer Microsoft Power Platform-Apps über den Abschnitt **"Mit Power Platform erstellt** " der Seite "Apps" in Teams installiert haben. Durchsuchen Sie dazu [das Überwachungsprotokoll](./audit-log-events.md) nach dem Ereignis " **Installierte App-Teams** " (im Rahmen des **AppInstalled-Vorgangs** ) nach einem Benutzer oder einer Gruppe von Benutzern. Um Apps zu finden, die von **"Built with Power Platform"** installiert wurden, suchen Sie in den Details eines bestimmten Datensatzes nach dem **TemplatedInstance-Wert** in der **AppDistributionMode-Eigenschaft** .

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Screenshot des TemplatedInstance-Werts in der AppDistributionMode-Eigenschaft." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Sie können Überwachungsdatensätze im CSV-Format exportieren, um die Filterung zu vereinfachen.

## <a name="related-topics"></a>Verwandte Themen

- [Freigeben einer Canvas-App in Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Freigeben Ihres Bots für andere Benutzer](/power-virtual-agents/admin-share-bots)
- [Verwalten von Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Veröffentlichen einer benutzerdefinierten App, die über die Teams-App-Übermittlungs-API übermittelt wurde](submit-approve-custom-apps.md)
