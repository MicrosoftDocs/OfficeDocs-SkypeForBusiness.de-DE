---
title: Verwalten von Notruf-Routing-Richtlinien für Direct Routing
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien für das Routing von Notrufen in Microsoft Teams verwenden und verwalten, um Notrufnummern zu erstellen und anzugeben, wie Notrufe weiterleiten werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 582036d6168a235744b092f7f11bfd34442f5221
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634914"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Verwalten von Notruf-Routing-Richtlinien für Direct Routing

Wenn Sie Direct [Routing](direct-routing-landing-page.md) in Ihrer Organisation bereitgestellt haben, können Sie richtlinien für das Routing von Notrufen in Microsoft Teams verwenden, um Notrufnummern zu erstellen und anzugeben, wie Notrufe routing werden. Eine Richtlinie für das Routing von Notrufen bestimmt, ob erweiterte Notrufdienste für Benutzer aktiviert werden, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notdienste angerufen werden (z. B. 911 in den VEREINIGTEn Staaten), und wie Notrufe an Notdienste umgerufen werden. 

> [!Note]
> **Beachten Sie, dass diese Anrufroutingrichtlinien nur für Direct-Routing gelten– sie gelten nicht für Anrufpläne oder Operatoren Verbinden.**

Sie verwalten Richtlinien für die Weiterleitung von Notrufen, indem Sie zu den Richtlinien für den Sprachnotruf im Microsoft Teams Admin Center oder mithilfe von  >   Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für das Routing von Notrufen zugewiesen haben und sich der Benutzer an diesem Netzwerkstandort befindet, setzt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für das Routing von Notrufen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Sprachnotrufe , und klicken Sie dann auf die Registerkarte  >   **Anrufroutingrichtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Um dynamische Notrufe zu ermöglichen, aktivieren Sie **dynamische Notrufe**. Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien- und Standortinformationen vom Dienst ab und enthält diese Informationen als Teil des Notrufs.
5. Definieren Sie eine oder mehrere Notfallnummern. Klicken Sie dazu unter **Notrufnummern** **auf Hinzufügen**, und gehen Sie dann wie folgt vor:
    1. **Notrufzeichenfolge:** Geben Sie die Notrufzeichenfolge ein. Diese Wählzeichenfolge gibt an, dass es sich bei einem Anruf um einen Notruf handelt.
        > [!NOTE]
        > **Bei direct Routing senden Teams-Clients keine Notrufe mehr mit einem "+" vor der Notrufzeichenfolge. Achten Sie darauf, dass das Sprachroutenmuster, das einer Notrufzeichenfolge entspricht, diese Änderung widerspiegelt.**
    2. **Notrufmaske:** Für jede Notfallnummer können Sie Null- oder mehr Notrufmasken angeben. Ein Wählformat ist die Nummer, die Sie in den Wert der Notrufzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und die Notrufe bleiben erhalten. <br>So fügen Sie beispielsweise 112 als Notrufnummer, d. h. die Notrufnummer für die meisten Benutzer in Europa, und 911 als Notrufzeichenfolge hinzu. Ein Teams aus Europa, der zu Gast ist, weiß möglicherweise nicht, dass 911 die Notrufnummer in den USA ist, und wenn er die 112 wählt, wird die Nummer 911 gewählt. Zum Definieren mehrerer Wählmasken trennen Sie die einzelnen Werte durch ein Semikolon. Beispiel: 112;212.
    3. **PSTN-Nutzungsdatensatz:** Wählen Sie den Nutzungsdatensatz public Switched Telephone Network (PSTN) aus. Der PSTN-Nutzungsdatensatz wird verwendet, um zu bestimmen, welche Route verwendet wird, um Notrufe von Benutzern weiter zu routen, die zur Verwendung autorisiert sind. Die dieser Verwendung zugeordnete Route sollte auf einen SIP-Trunk (Session Initiation Protocol) verweisen, der für Notrufe oder ein ELIN-Gateway (Emergency Location Identification Number) zum Routen von Notrufen an den nächstgelegenen Public Safety Answering Point (PSAP) verwendet wird.

    > [!NOTE]
    > Wählzeichenfolgen und Wählmasken müssen innerhalb einer Richtlinie eindeutig sein. Dies bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren und mehrere Wählmasken für eine Wählzeichenfolge festlegen können, aber jede Wählzeichenfolge und Wählmaske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Richtlinie für die Weiterleitung von Notrufen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Sprachnotrufe , und klicken Sie dann auf die Registerkarte  >   **Anrufroutingrichtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für die Weiterleitung von Notrufen zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für das Routing von Notrufen zu einem Netzwerkstandort

Verwenden Sie [das Cmdlet Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Routingrichtlinie für Notrufe zuzuordnen.

Dieses Beispiel zeigt, wie Sie der Website "Site1" eine Richtlinie namens "Routingrichtlinie 1 für Notrufe" zuweisen.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für Notrufe in Teams](manage-emergency-calling-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)