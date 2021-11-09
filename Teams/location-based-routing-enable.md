---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie sie Location-Based Für Direct-Routing aktivieren, einschließlich der Aktivierung für Benutzer, Netzwerkwebsites, Gatewaykonfigurationen und Anrufrichtlinien.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 750c20367c5710054d2b19d266ff9dc70f46edd9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829619"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Aktivieren des standortbasierten Routings für direktes Routing

Bevor Sie die Schritte in diesem Artikel ausführen, vergewissern Sie sich, dass Sie den Artikel Planen von Location-Based-Routing für [Direct-Routing](location-based-routing-plan.md) gelesen und die Schritte unter Konfigurieren von Netzwerkeinstellungen für das Routing [Location-Based abgeschlossen haben.](location-based-routing-configure-network-settings.md)

In diesem Artikel wird beschrieben, wie Sie Location-Based für Direct-Routing aktivieren. Nachdem Sie Direct Telefonsystem Routing bereitgestellt und Netzwerkregionen, Standorte und Subnetze eingerichtet haben, können Sie das Location-Based aktivieren. Um die Schritte in diesem Artikel ausführen zu können, müssen Sie mit PowerShell-Cmdlets vertraut sein. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

 Sie müssen das Location-Based für Folgendes aktivieren:
- Benutzer
- Netzwerkwebsites
- Gatewaykonfigurationen
- Anrufpläne

Sie können das Microsoft Teams [Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShel](#using-powershell)l verwenden, um Ihr Location-Based aktivieren.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="enable-location-based-routing-for-users"></a>Aktivieren Location-Based Routings für Benutzer

1. Erstellen Sie eine Voice Routing-Richtlinie, und weisen Sie der Richtlinie PSTN-Nutzungen zu. Wenn Sie einer Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Optionen verwenden:

    - Verwenden Sie PSTN-Nutzungen, die Sprachrouten zugeordnet sind, für die ein lokales PSTN-Gateway zum Standort verwendet wird.
    - Verwenden Sie PSTN-Nutzungen, die Sprachrouten zugeordnet sind, die ein PSTN-Gateway in einer Region verwenden, Location-Based für die keine Routingeinschränkungen erforderlich sind.
2. Weisen Sie die Voice Routing-Richtlinie Benutzern zu, die Routingeinschränkungen erzwingen müssen.

Weitere Informationen zum Erstellen von Voice Routingrichtlinien und zum Zuweisen dieser Richtlinien zu Benutzern finden Sie unter Verwalten von [Voice Routing-Richtlinien in Microsoft Teams.](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren Location-Based Routings für Netzwerkwebsites

Aktivieren Location-Based Routing für Ihre Websites, für die Routingeinschränkungen erzwungen werden müssen. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Centers zu Locations  >  **Network topology**, wählen Sie eine Netzwerkwebsite aus, klicken Sie auf Bearbeiten , und aktivieren Sie dann **Standortbasiertes Routing**.   

Weitere Informationen finden Sie unter [Verwalten der Netzwerktopologie.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Location-Based Routings für Gateways

Aktivieren Location-Based Routing an Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerkwebsite zu, an der sich das Gateway befindet. 

1. Wechseln Sie in der linken Navigationsleiste zu **Voice**  >  **Direct Routing**, und klicken Sie dann auf die Registerkarte **SBCs.**
2. Wählen Sie SBC aus, und klicken Sie dann auf **Bearbeiten**. 
3. Aktivieren **Sie unter Standortbasiertes Routing und Medienoptimierung** die Option **Standortbasiertes Routing aktivieren.**
4. Geben Sie die Gatewaywebsite-ID an, und legen Sie dann den Umgehungsmodus fest.
5. Klicken Sie auf **Speichern**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Location-Based Routing für Anrufrichtlinien

Zum Erzwingen Location-Based Routings für bestimmte Benutzer richten Sie die Anrufrichtlinie des Benutzers ein, um die gebührenpflichtige PSTN-Umgehung zu verhindern. Aktivieren Sie dazu die Einstellung "Gebührenfreie **Umgehung verhindern"** in der Anrufrichtlinie.

Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Teams.](teams-calling-policy.md)

## <a name="using-powershell"></a>Verwendung von PowerShell

### <a name="enable-location-based-routing-for-users"></a>Aktivieren Location-Based Routings für Benutzer

1. Verwenden Sie [das Cmdlet Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) zum Festlegen von PSTN-Nutzungen. Bei mehreren Verwendungen trennen Sie jede Verwendung durch ein Komma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Zum Beispiel: 
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Verwenden Sie [das Cmdlet New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) zum Erstellen einer Sprachroutingrichtlinie, um den Benutzer den entsprechenden PSTN-Nutzungen zuzuordnen.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Wenn Sie einer Voice Routing-Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Optionen verwenden:
    - Verwenden von PSTN-Nutzungen, die Sprachrouten zugeordnet sind, für die ein lokales PSTN-Gateway zum Standort verwendet wird
    - Verwenden Sie PSTN-Nutzungen, die Sprachrouten zugeordnet sind, die ein PSTN-Gateway in einer Region verwenden, Location-Based für die keine Routingeinschränkungen erforderlich sind.

    In diesem Beispiel erstellen wir zwei neue Voice Routing-Richtlinien und weisen ihnen PSTN-Nutzungen zu. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    Die folgende Tabelle zeigt die in diesem Beispiel definierten Sprachroutingrichtlinien. 
    
    |&nbsp;|Voice routing policy 1|Voice routing policy 2|
    |---------|---------|---------|
    |Online-Sprachrichtlinien-ID   |Online-Voiceroutingrichtlinie   |Hyderabad Online Voice Routing Policy    |
    |Online-PSTN-Nutzungen  |Long Distance  |Fern, Lokal, Intern  |

3. Verwenden Sie [das Grant-CsOnlineVoiceRoutingPolicy-Cmdlet,](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) um Benutzern, die Routingeinschränkungen erzwingen müssen, Online-Voiceroutingrichtlinien zuzuordnen.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren Location-Based Routings für Netzwerkwebsites

1.  Verwenden Sie [das Cmdlet Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) um Location-Based-Routing zu aktivieren und Ihren Netzwerkwebsites Voiceroutingrichtlinien zuzuordnen, die Routingeinschränkungen erzwingen müssen.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In diesem Beispiel aktivieren wir Location-Based Routing für die Standortwebsite und die Hyderabad-Website. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Die folgende Tabelle zeigt die Websites, die für das Routing Location-Based in diesem Beispiel aktiviert sind.

    |&nbsp;|Site 1 (Ing)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
    |Standortname    |Site 1 (Ing)    |Site 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Wahr    |Wahr    |
    |Subnetze     |Subnetz 1 (Subnetz)     |Subnetz 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Location-Based Routings für Gateways

1. Verwenden Sie [das Cmdlet New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) zum Erstellen einer Gatewaykonfiguration für jedes Gateway oder jede Netzwerkwebsite. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Wenn einem System mehrere Gateways zugeordnet sind (z. B. Gateway oder PBX), ändern Sie jedes Gateway, um die Location-Based zu aktivieren. 

    In diesem Beispiel erstellen wir eine Gatewaykonfiguration für jedes Gateway. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md)
    
2. Verwenden Sie [das Cmdlet Set-CSOnlinePSTNGateway,](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) um Location-Based für Ihre Gateways zu aktivieren, die Routingeinschränkungen erzwingen müssen. 

    Aktivieren Location-Based Routing an Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerkwebsite zu, an der sich das Gateway befindet.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In diesem Beispiel wird das Location-Based für jedes Gateway aktiviert, das mit PSTN-Gateways auf den Websites "Weiter" und "Hyderabad" verknüpft ist. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Aktivieren Sie nicht Location-Based Routing für Gateways, die keine Anrufe an das PSTN weiterleiten. Sie müssen das Gateway jedoch weiterhin der Netzwerkwebsite zuordnen, an der sich das System befindet. Der Grund hier Location-Based dass Routingeinschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind. In diesem Beispiel Location-Based Routing nicht für jedes Gateway aktiviert, das PBX-Systemen auf den Websites "Weiter" und "Hyderabad" zugeordnet ist.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Location-Based Routing für Anrufrichtlinien

Zum Erzwingen Location-Based Routings für bestimmte Benutzer richten Sie die Sprachrichtlinie des Benutzer ein, um die gebührenpflichtige Umgehung der PTSN zu verhindern. 

Verwenden Sie das [Grant-CsTeamsCallingPolicy-Cmdlet,](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) um das Routing Location-Based zu aktivieren, indem Sie die gebührenpflichtige Umgehung der PSTN-Datei verhindern.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In diesem Beispiel verhindern wir die gebührenpflichtige PstN-Umgehung der Anrufrichtlinien von Benutzer1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)