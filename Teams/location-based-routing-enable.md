---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Location-Based für Direct Routing aktivieren, einschließlich der Aktivierung für Benutzer, Netzwerkwebsites, Gatewaykonfigurationen und Anrufrichtlinien.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822915"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Aktivieren des standortbasierten Routings für direktes Routing

Bevor Sie die Schritte in diesem Artikel ausführen, vergewissern Sie sich, dass Sie ["Plan Location-Based](location-based-routing-plan.md) Routing für direktes Routing" gelesen und die Schritte unter "Konfigurieren von Netzwerkeinstellungen für das Routing Location-Based [abgeschlossen haben.](location-based-routing-configure-network-settings.md)

In diesem Artikel wird beschrieben, wie Sie Location-Based routing für direktes Routing aktivieren. Nachdem Sie das direkte Routing für das Telefonsystem bereitgestellt und Netzwerkbereiche, Standorte und Subnetze eingerichtet haben, können Sie das Location-Based aktivieren. Um die Schritte in diesem Artikel ausführen zu können, benötigen Sie einige Vertrautheit mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

 Sie müssen das Routing Location-Based für Folgendes aktivieren:
- Benutzer
- Netzwerkwebsites
- Gatewaykonfigurationen
- Anrufpläne

Sie können das [Microsoft Team Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShel](#using-powershell)l verwenden, um das Location-Based zu aktivieren.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="enable-location-based-routing-for-users"></a>Aktivieren Location-Based Routing für Benutzer

1. Erstellen Sie eine Voiceroutingrichtlinie, und weisen Sie der Richtlinie PstN-Nutzungen zu. Wenn Sie einer Richtlinie PstN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Schritte tun:

    - Verwenden Sie PSTN-Nutzungen, die Sprachrouten zugeordnet sind, für die ein lokales PSTN-Gateway zum Standort verwendet wird.
    - Verwenden Sie PSTN-Nutzungen, die Sprachrouten zugeordnet sind, die ein PSTN-Gateway verwenden, das sich in einer Region befindetLocation-Based für die keine Routingeinschränkungen erforderlich sind.
2. Weisen Sie die Sprachroutingrichtlinie Benutzern zu, die Routingeinschränkungen erzwingen müssen.

Weitere Informationen zum Erstellen von Voiceroutingrichtlinien und deren Zuweisung zu Benutzern finden Sie unter "Verwalten von [Voiceroutingrichtlinien in Microsoft Teams".](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren Location-Based Routing für Netzwerkwebsites

Aktivieren Location-Based Routing für Ihre Websites, die Routingeinschränkungen erzwingen müssen. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Netzwerktopologie für Speicherorte, wählen Sie eine Netzwerkwebsite aus, klicken Sie auf "Bearbeiten", und aktivieren Sie dann "Standortbasiertes  >   **Routing".**   

Weitere Informationen finden Sie unter ["Verwalten der Netzwerktopologie".](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Location-Based Routing für Gateways

Aktivieren Location-Based routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway located. 

1. Wechseln Sie in der linken Navigationsleiste zu **Voice** Direct Routing, und klicken Sie dann auf die Registerkarte  >   **"SBCs".**
2. Wählen Sie den SBC aus, und klicken Sie dann auf **"Bearbeiten".** 
3. Aktivieren **Sie unter "Standortbasiertes Routing und Medienoptimierung"** die Option **"Standortbasiertes Routing aktivieren".**
4. Geben Sie die Gatewaywebsite-ID an, und legen Sie dann den Umgehungsmodus fest.
5. Klicken Sie auf **Speichern**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Location-Based Routing für Anrufrichtlinien

Um das Location-Based für bestimmte Benutzer zu erzwingen, richten Sie die Anrufrichtlinie des Benutzers ein, um die gebührenpflichtige Umgehung des PSTNs zu verhindern. Aktivieren Sie dazu die Einstellung "Gebührenpflichtige Umgehung **verhindern"** in der Anrufrichtlinie.

Weitere Informationen finden Sie unter [Anrufrichtlinien in Teams.](teams-calling-policy.md)

## <a name="using-powershell"></a>Verwendung von PowerShell

### <a name="enable-location-based-routing-for-users"></a>Aktivieren Location-Based Routing für Benutzer

1. Verwenden Sie [das Cmdlet "Set-CsOnlinePstnUsage"](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) zum Festlegen von PSTN-Verwendungen. Bei mehreren Verwendungen trennen Sie jede Verwendung durch ein Komma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Beispiel:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Verwenden Sie [das Cmdlet "New-CsOnlineVoiceRoutingPolicy",](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) um eine Sprachroutingrichtlinie zu erstellen, um den Benutzer den entsprechenden PstN-Nutzungen zuzuordnen.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Wenn Sie einer Sprachroutingrichtlinie PstN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Schritte tun:
    - Verwenden von PSTN-Nutzungen, die Sprachrouten zugeordnet sind, für die ein lokales PSTN-Gateway zum Standort verwendet wird
    - Verwenden Sie PSTN-Nutzungen, die Sprachrouten zugeordnet sind, die ein PSTN-Gateway verwenden, das sich in einer Region befindetLocation-Based für die keine Routingeinschränkungen erforderlich sind.

    In diesem Beispiel erstellen wir zwei neue Voiceroutingrichtlinien und weisen ihnen PSTN-Nutzungen zu. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    In der folgenden Tabelle sind die in diesem Beispiel definierten Richtlinien für die Sprachrouting aufgeführt. 
    
    ||Voice routing policy 1|Voice routing policy 2|
    |---------|---------|---------|
    |Online-Voicerichtlinien-ID   |Richtlinien für Online-Voice-Routing   |Hyderabad Online Voice Routing Policy    |
    |Online-PSTN-Verwendungen  |Ferndistanz  |Ferndistanz, Lokal, Intern  |

3. Verwenden Sie [das Cmdlet Grant-CsOnlineVoiceRoutingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) um Benutzern, die Routingeinschränkungen erzwingen müssen, Online-Voiceroutingrichtlinien zuzuordnen.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren Location-Based Routing für Netzwerkwebsites

1.  Verwenden Sie [das Cmdlet "Set-CsTenantNetworkSite",](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) um das Routing Location-Based zu aktivieren und Ihren Netzwerkwebsites Voiceroutingrichtlinien zuzuordnen, die Routingeinschränkungen erzwingen müssen.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In diesem Beispiel aktivieren wir Location-Based Routing für die Standortwebsite und die Hyderabad-Website. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Die folgende Tabelle zeigt die Websites, die für das Routing Location-Based in diesem Beispiel aktiviert sind.

    ||Website 1 (Nachen)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
|Standortname    |Website 1 (Nachen)    |Site 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Wahr    |Wahr    |
    |Subnetze     |Subnetz 1 (Subnetz)     |Subnetz 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Location-Based Routing für Gateways

1. Verwenden Sie [das Cmdlet "New-CsOnlinePSTNGateway",](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) um eine Gatewaykonfiguration für jedes Gateway oder jede Netzwerkwebsite zu erstellen. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Wenn einem System mehrere Gateways zugeordnet sind (z. B. Gateway oder PBX), ändern Sie jedes Gateway, um die Verwendung Location-Based zu aktivieren. 

    In diesem Beispiel erstellen wir eine Gatewaykonfiguration für jedes Gateway. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Weitere Informationen finden Sie unter ["Konfigurieren des direkten Routings".](direct-routing-configure.md)
    
2. Verwenden Sie [das Cmdlet "Set-CSOnlinePSTNGateway",](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) um Location-Based für Ihre Gateways zu aktivieren, die Routingeinschränkungen erzwingen müssen. 

    Aktivieren Location-Based routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway located.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In diesem Beispiel aktivieren wir Location-Based Routing für jedes Gateway, das zu den PSTN-Gateways auf den Sites "Routing" und "Hyderabad" zugeordnet ist. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Aktivieren Sie nicht das Location-Based für Gateways, die keine Anrufe an das PSTN weiterleiten. Sie müssen das Gateway jedoch weiterhin der Netzwerkwebsite zuordnen, an der sich das System befindet. Dies liegt daranLocation-Based dass Routingeinschränkungen für Anrufe über das Festnetz erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind. In diesem Beispiel ist Location-Based Routing nicht für jedes Gateway aktiviert, das pbX-Systemen auf den Websites "Routing" und "Hyderabad" zugeordnet ist.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Location-Based Routing für Anrufrichtlinien

Um das Location-Based für bestimmte Benutzer zu erzwingen, richten Sie die Sprachrichtlinie des Benutzer ein, um die gebührenpflichtige Umgehung von PTSN zu verhindern. 

Verwenden Sie das [Cmdlet Grant-CsTeamsCallingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) um das Routing Location-Based, indem Sie die gebührenpflichtige Umgehung des PSTN verhindern.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In diesem Beispiel verhindern wir die gebührenpflichtige Umgehung des PstNs mit den Anrufrichtlinien von Benutzer1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
