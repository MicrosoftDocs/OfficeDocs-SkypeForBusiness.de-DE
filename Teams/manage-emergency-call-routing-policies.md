---
title: Verwalten von Richtlinien für Notfall-Voice Routing für Direct Routing
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien für das Routing von Notrufen in ihrem Microsoft Teams verwenden und verwalten, um Notrufnummern zu erstellen und anzugeben, wie Notrufe weiterleiten werden.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e83b33d7e6b9c13b178a7481f5061615836d0c94c4bfcc7c97ec42a3b8250777
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848900"
---
# <a name="manage-emergency-voice-routing-policies-for-direct-routing"></a>Verwalten von Richtlinien für Notfall-Voice Routing für Direct Routing

Wenn Sie Telefonsystem [Direct Routing](direct-routing-landing-page.md) in Ihrer Organisation bereitgestellt haben, können Sie Notfall-Voice routing-Richtlinien in Microsoft Teams verwenden, um Notrufnummern zu erstellen und anzugeben, wie Notrufe weiterleiten werden. Eine Richtlinie für die Weiterleitung von Notrufen bestimmt, ob erweiterte Notrufdienste für Benutzer aktiviert werden, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notdienste angerufen werden (z. B. 911 in den USA) und wie Notrufe an Notdienste umgerufen werden.

Sie verwalten Richtlinien für Die Weiterleitung von Notrufen über die Richtlinien für den Sprachnotruf im Microsoft Teams Admin Center oder mithilfe der  >   Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für das Routing von Notfall-Voice routing zugewiesen haben und sich der Benutzer an diesem Netzwerkstandort befindet, setzt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="create-a-custom-emergency-voice-routing-policy"></a>Erstellen einer benutzerdefinierten Voice Routing-Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Sprachnotrufe , und klicken Sie dann auf die Registerkarte  >   **Anrufroutingrichtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Um dynamische Notrufe zu ermöglichen, aktivieren Sie **dynamische Notrufe**. Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien- und Standortinformationen vom Dienst ab und enthält diese Informationen als Teil des Notrufs.
5. Definieren Sie eine oder mehrere Notfallnummern. Klicken Sie dazu unter **Notrufnummern** **auf Hinzufügen**, und gehen Sie dann wie folgt vor:
    1. **Notrufzeichenfolge:** Geben Sie die Notrufzeichenfolge ein. Diese Wählzeichenfolge gibt an, dass es sich bei einem Anruf um einen Notruf handelt.
        > [!NOTE]
        > Bei Direct Routing werden die Clients, die Notrufe mit einem "+" vor der Notrufzeichenfolge senden, von den Teams-Clients wegübergangen. Bis zum Abschluss des Übergangs sollte das Sprachroutenmuster, das einer Notrufzeichenfolge entspricht, sicherstellen, dass eine Übereinstimmung für Zeichenfolgen mit und ohne vorheriges "+" wie 911 und +911 durchgeführt wird. Beispiel: ^ \\ +?911 oder .*.
    2. **Notrufmaske:** Für jede Notfallnummer können Sie Null- oder mehr Notrufmasken angeben. Ein Wählformat ist die Nummer, die Sie in den Wert der Notrufzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und die Notrufe bleiben erhalten. <br>So fügen Sie beispielsweise 112 als Notrufnummer, d. h. die Notrufnummer für die meisten Benutzer in Europa, und 911 als Notrufzeichenfolge hinzu. Ein Teams aus Europa, der zu Gast ist, weiß möglicherweise nicht, dass 911 die Notfallnummer in den VEREINIGTEn Staaten ist, und wenn er die 112 wählt, wird die Nummer 911 gewählt. Zum Definieren mehrerer Wählmasken trennen Sie die einzelnen Werte durch ein Semikolon. Beispiel: 112;212.
    3. **PSTN-Nutzungsdatensatz:** Wählen Sie den Nutzungsdatensatz public Switched Telephone Network (PSTN) aus. Der PSTN-Nutzungsdatensatz wird verwendet, um zu bestimmen, welche Route verwendet wird, um Notrufe von Benutzern weiter zu routen, die zur Verwendung autorisiert sind. Die dieser Verwendung zugeordnete Route sollte auf einen SIP-Trunk (Session Initiation Protocol) verweisen, der für Notrufe oder ein ELIN-Gateway (Emergency Location Identification Number) zum Routen von Notrufen an den nächstgelegenen Public Safety Answering Point (PSAP) verwendet wird.

    > [!NOTE]
    > Wählzeichenfolgen und Wählmasken müssen innerhalb einer Richtlinie eindeutig sein. Dies bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren und mehrere Wählmasken für eine Wählzeichenfolge festlegen können, aber jede Wählzeichenfolge und Wählmaske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-voice-routing-policy"></a>Bearbeiten einer Richtlinie für Die Weiterleitung von Notrufen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Sprachnotrufe , und klicken Sie dann auf die Registerkarte  >   **Anrufroutingrichtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-voice-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Voice Routing-Richtlinie für Notrufe zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-voice-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für das Routing von Notrufen zu einem Netzwerkstandort

Verwenden Sie [das Cmdlet Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Routingrichtlinie für Notrufe zuzuordnen.

Dieses Beispiel zeigt, wie Sie der Website "Site1" eine Richtlinie namens "Routingrichtlinie 1 für Notrufe" zuweisen.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für Notrufe in Teams](manage-emergency-calling-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)