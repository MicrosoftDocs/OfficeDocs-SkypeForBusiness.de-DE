---
title: Aktivieren des standortbasierten Routings für direktes Routing
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie Location-Based Routing für Direct Routing aktivieren, einschließlich der Aktivierung für Benutzer, Netzwerkstandorte, Gatewaykonfigurationen und Anrufrichtlinien.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562194"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Aktivieren des standortbasierten Routings für direktes Routing

In diesem Artikel wird beschrieben, wie Sie Location-Based Routing für Direct Routing aktivieren. Bevor Sie die Schritte in diesem Artikel ausführen, stellen Sie sicher, dass Sie ["Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) " gelesen und die Schritte unter ["Konfigurieren von Netzwerkeinstellungen für Location-Based Routing"](location-based-routing-configure-network-settings.md) ausgeführt haben.

 Nachdem Sie Direct Routing bereitgestellt und Netzwerkregionen, Standorte und Subnetze eingerichtet haben, können Sie Location-Based Routing aktivieren. Um die Schritte in diesem Artikel auszuführen, benötigen Sie einige Kenntnisse mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Teams PowerShell Overview](teams-powershell-overview.md)

 Sie müssen Location-Based Routing für Folgendes aktivieren:

- Benutzer
- Netzwerkstandorte
- Gatewaykonfigurationen
- Anrufpläne

Sie können das [Teams Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShell](#using-powershell) verwenden, um Location-Based Routing zu aktivieren.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="enable-location-based-routing-for-users"></a>Aktivieren Location-Based Routing für Benutzer

1. Erstellen Sie eine VoIP-Routingrichtlinie, und weisen Sie der Richtlinie PSTN-Verwendungen zu. Wenn Sie einer Richtlinie PSTN-Verwendungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:

    - Verwenden Sie PSTN-Verwendungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway zum Standort verwenden.

    - Verwenden Sie PSTN-Verwendungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der Location-Based Routingeinschränkungen nicht erforderlich sind.

2. Weisen Sie die VoIP-Routingrichtlinie Benutzern zu, für die Routingeinschränkungen erzwungen werden müssen.

Weitere Informationen zum Erstellen von VoIP-Routingrichtlinien und zum Zuweisen dieser Richtlinien zu Benutzern finden Sie unter [Verwalten von VoIP-Routingrichtlinien in Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren Location-Based Routing für Netzwerkstandorte

Aktivieren Sie Location-Based Routing für Ihre Websites, die Routingeinschränkungen erzwingen müssen. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "**Standortnetzwerktopologie** > ", wählen Sie einen Netzwerkstandort aus, klicken Sie auf **"Bearbeiten"**, und aktivieren Sie dann das **standortbasierte Routing**.  

Weitere Informationen finden [Sie unter Verwalten Ihrer Netzwerktopologie](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Location-Based Routing für Gateways

Aktivieren Sie Location-Based Routing an Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie den Netzwerkstandort zu, an dem sich das Gateway befindet. 

1. Wechseln Sie im linken Navigationsbereich zu **Voice** > **Direct Routing**, und klicken Sie dann auf die Registerkarte **"SBCs** ".

2. Wählen Sie den SBC aus, und klicken Sie dann auf **"Bearbeiten"**. 

3. Aktivieren Sie unter **"Standortbasiertes Routing und Medienoptimierung**" die Option **"Standortbasiertes Routing aktivieren"**.

4. Geben Sie die Gatewaywebsite-ID an, und legen Sie dann den Umgehungsmodus fest.

5. Klicken Sie auf **Speichern**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Location-Based Routing für Anrufrichtlinien

Um Location-Based Routing für bestimmte Benutzer zu erzwingen, richten Sie die Anrufrichtlinie des Benutzers ein, um die gebührenpflichtige PSTN-Umgehung zu verhindern. Aktivieren Sie dazu die Einstellung " **Gebührenumgehung verhindern** " in der Anrufrichtlinie.

Weitere Informationen finden Sie [unter Anrufrichtlinien in Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Verwendung von PowerShell

### <a name="enable-location-based-routing-for-users"></a>Aktivieren Location-Based Routing für Benutzer

1. Verwenden Sie zum Festlegen von PSTN-Verwendungen das Cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Trennen Sie bei mehreren Verwendungen jede Verwendung durch ein Komma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Zum Beispiel: 

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) , um eine VoIP-Routingrichtlinie zu erstellen, um den Benutzer mit der entsprechenden PSTN-Verwendung zu verknüpfen.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Wenn Sie einer VoIP-Routingrichtlinie PSTN-Verwendungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:

    - Verwenden Sie PSTN-Verwendungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway zum Standort verwenden.

    - Verwenden Sie PSTN-Verwendungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der Location-Based Routingeinschränkungen nicht erforderlich sind.

    Im folgenden Beispiel werden zwei neue VoIP-Routingrichtlinien erstellt und ihnen PSTN-Verwendungen zugewiesen. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    Die folgende Tabelle zeigt die in diesem Beispiel definierten VoIP-Routingrichtlinien. 
    
    |&nbsp;|VoIP-Routingrichtlinie 1|VoIP-Routingrichtlinie 2|
    |---------|---------|---------|
    |Richtlinien-ID für Online-VoIP   |Richtlinie für das Online-VoIP-Routing in Delhi   |Hyderabad Online-VoIP-Routingrichtlinie    |
    |Online-PSTN-Verwendungen  |Fernstrecke  |Ferndistanz, lokal, intern  |

3. Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) , um Online-VoIP-Routingrichtlinien Benutzern zuzuordnen, für die Routingeinschränkungen erzwungen werden müssen.

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren Location-Based Routing für Netzwerkstandorte

1. Verwenden Sie das Cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) , um Location-Based Routing zu aktivieren und Ihren Netzwerkstandorten VoIP-Routingrichtlinien zuzuordnen, die Routingeinschränkungen erzwingen müssen.

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In diesem Beispiel wird Location-Based Routing für den Standort Delhi und den Standort Hyderabad aktiviert. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    In der folgenden Tabelle sind die Websites aufgeführt, die in diesem Beispiel für Location-Based Routing aktiviert sind.

    |&nbsp;|Standort 1 (Delhi)  |Standort 2 (Hyderabad)  |
    |---------|---------|---------|
    |Standortname    |Standort 1 (Delhi)    |Standort 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Wahr    |Wahr    |
    |Subnetze     |Subnetz 1 (Delhi)     |Subnetz 2 (Hyderabad)     |


### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Location-Based Routing für Gateways

1. Verwenden Sie zum Erstellen einer Gatewaykonfiguration für jedes Gateway oder jeden Netzwerkstandort das Cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Wenn einem System mehrere Gateways zugeordnet sind (z. B. Gateway oder Nebenstellenanlage), ändern Sie jedes Gateway, um Location-Based Routingeinschränkungen zu aktivieren. 

    Im folgenden Beispiel wird eine Gatewaykonfiguration für jedes Gateway erstellt. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Weitere Informationen finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md).
    
2. Verwenden Sie das Cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) , um Location-Based Routing für Ihre Gateways zu aktivieren, die Routingeinschränkungen erzwingen müssen. 

    Aktivieren Sie Location-Based Routing an Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie den Netzwerkstandort zu, an dem sich das Gateway befindet.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   Im folgenden Beispiel wird Location-Based Routing für jedes Gateway aktiviert, das PSTN-Gateways in den Standorten Delhi und Hyderabad zugeordnet ist. 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    Aktivieren Sie Location-Based Routing nicht für Gateways, die keine Anrufe an das PSTN weiterleiten. Sie müssen das Gateway jedoch weiterhin dem Netzwerkstandort zuordnen, an dem sich das System befindet. Dies liegt daran, dass Location-Based Routingeinschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind. In diesem Beispiel ist Location-Based Routing nicht für jedes Gateway aktiviert, das pbx-Systemen in den Standorten Delhi und Hyderabad zugeordnet ist.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Location-Based Routing für Anrufrichtlinien

Um Location-Based Routing für bestimmte Benutzer zu erzwingen, richten Sie die VoIP-Richtlinie der Benutzer ein, um die gebührenpflichtige PTSN-Umgehung zu verhindern. 

Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , um Location-Based Routing zu aktivieren, indem Sie die gebührenpflichtige PSTN-Umgehung verhindern.


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

In diesem Beispiel verhindern wir die gebührenpflichtige PSTN-Umgehung der Anrufrichtlinien von User1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud Voice-Features in Teams](cloud-voice-network-settings.md)