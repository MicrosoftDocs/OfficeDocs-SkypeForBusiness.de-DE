---
title: Verwalten von Notfall-Anrufweiterleitungsrichtlinien
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien für das Routing von Notrufen in Microsoft Teams verwenden und verwalten, um Notrufnummern festzulegen und anzugeben, wie Notrufe routingiert werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096179"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Verwalten von Routingrichtlinien für Notrufe in Microsoft Teams

Wenn Sie das direkte [Telefonsystemrouting](direct-routing-landing-page.md) in Ihrer Organisation bereitgestellt haben, können Sie mithilfe von Richtlinien für das Routing von Notrufen in Microsoft Teams Notfallnummern einrichten und angeben, wie Notrufe weiterleitet werden. Eine Richtlinie für die Weiterleitung von Notrufen bestimmt, ob erweiterte Notfalldienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Telefonnummern, die zum Anrufen von Notdiensten verwendet werden (z. B. 911 in den USA), und wie Anrufe an Notdienste weiterleitiert werden.

Sie verwalten Richtlinien für das Routing von Notrufen, indem Sie im Microsoft Teams Admin Center zu Den Sprachnotrufrichtlinien oder mithilfe von  >   Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten können, sie aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Routingrichtlinie für Notrufe zugewiesen haben und sich dieser Benutzer auf dieser Netzwerkwebsite befindet, setzt die der Netzwerkwebsite zugewiesene Richtlinie die dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für das Routing von Notrufen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Sprachnotrufrichtlinien, und klicken Sie dann auf die Registerkarte  >   **Anrufroutingrichtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Um dynamische Notrufe zu aktivieren, aktivieren Sie **Dynamische Notrufe.** Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien- und Standortinformationen vom Dienst ab und schließt diese Informationen als Teil des Notrufs ein.
5. Definieren Sie eine oder mehrere Notfallnummern. Klicken Sie dazu unter **Notrufnummern** auf **Hinzufügen**, und gehen Sie dann wie folgt vor:
    1. **Wählzeichenfolge für Notrufe:** Geben Sie die Notrufzeichenfolge ein. Diese Wählzeichenfolge gibt an, dass es sich bei einem Anruf um einen Notruf handelt.
        > [!NOTE]
        > Bei Direct Routing werden wir von Teams-Clients, die Notrufe senden, mit einem "+" vor der Wählzeichenfolge für Notrufe umschalten. Bis zum Abschluss des Übergangs sollte das Sprachroutenmuster, das einer Wählzeichenfolge für Notrufe entspricht, sicherstellen, dass eine Übereinstimmung für Zeichenfolgen vorgenommen wird, die über ein vorheriges "+" verfügen, z. B. 911 und +911. Beispiel: ^ \\ +?911 oder .*.
    2. **Notrufmaske:** Für jede Notfallnummer können Sie null oder mehr Notrufmasken angeben. Ein Wählformat ist die Zahl, die Sie in den Wert der Notrufzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und die Anrufer erreichen weiterhin die Notfalldienste. <br>So fügen Sie beispielsweise 112 als Notrufmaske hinzu, die die Notrufnummer für die meisten europäischen Benutzer ist, und 911 als Notrufzeichenfolge. Ein Benutzer von Teams aus Europa, der zu Besuch ist, weiß möglicherweise nicht, dass 911 die Notrufnummer in den USA ist, und wenn er 112 wählt, wird der Anruf an 911 vorgenommen. Um mehrere Wählformaten zu definieren, trennen Sie jeden Wert durch ein Semikolon. Beispiel: 112;212.
    3. **PSTN-Nutzungsdatensatz:** Wählen Sie den Nutzungsdatensatz für das öffentliche Telefonnetz (Public Switched Telephone Network, PSTN) aus. Der PstN-Nutzungsdatensatz wird verwendet, um zu bestimmen, welche Route zum Routen von Notrufen von Benutzern verwendet wird, die berechtigt sind, sie zu verwenden. Die route, die dieser Verwendung zugeordnet ist, sollte auf einen Sip-Trunk (Session Initiation Protocol) verweisen, der für Notrufe oder ein ELIN-Gateway (Emergency Location Identification Number) verwendet wird, das Notrufe an den nächstgelegenen öffentlichen Sicherheitsanrufpunkt (Public Safety Answering Point, PSAP) weiter leitet.

    > [!NOTE]
    > Wählzeichenfolgen und Wählformaten müssen innerhalb einer Richtlinie eindeutig sein. Dies bedeutet, dass Sie für eine Richtlinie mehrere Notrufnummern definieren und mehrere Wählformaten für eine Wählzeichenfolge festlegen können, aber jede Wählzeichenfolge und Wählmaske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Routingrichtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Sprachnotrufrichtlinien, und klicken Sie dann auf die Registerkarte  >   **Anrufroutingrichtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für das Routing von Notrufen zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Routingrichtlinie für Notrufe zu einer Netzwerkwebsite

Verwenden Sie [das Cmdlet Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Routingrichtlinie für Notrufe zuzuordnen.

In diesem Beispiel wird gezeigt, wie Sie der Website "Website1" eine Richtlinie namens "Richtlinie für das Routing von Notrufen 1" zuweisen.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für Notrufe in Teams](manage-emergency-calling-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)