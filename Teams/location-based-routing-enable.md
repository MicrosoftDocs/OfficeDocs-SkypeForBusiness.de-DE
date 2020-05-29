---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie standortbasiertes Routing für das direkte Routing aktivieren können, einschließlich der Aktivierung für Benutzer, Netzwerk Websites, Gateway-Konfigurationen und Anruf Richtlinien.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daf270dcd67dc732bba5e5fe134d5a0994dcd75
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412642"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Aktivieren des standortbasierten Routings für direktes Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, dass Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md) gelesen haben, und führen Sie die Schritte unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md)aus.

In diesem Artikel wird beschrieben, wie standortbasiertes Routing für das direkte Routing aktiviert wird. Nachdem Sie das direkte Routing für das Telefon System bereitgestellt und netzwerkregionen,-Standorte und-Subnetze eingerichtet haben, können Sie das standortbasierte Routing aktivieren. Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen. Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).

 Sie müssen standortbasiertes Routing für Folgendes aktivieren:
- Benutzer
- Netzwerk Websites
- Gateway-Konfigurationen
- Anrufpläne

Sie können das [Microsoft Team Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShel](#using-powershell)l verwenden, um standortbasiertes Routing zu aktivieren.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="enable-location-based-routing-for-users"></a>Aktivieren des standortbasierten Routings für Benutzer

1. Erstellen Sie eine VoIP-Routing Richtlinie, und weisen Sie der Richtlinie PSTN-Nutzungen zu. Wenn Sie einer Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:

    - Verwenden Sie PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden.
    - Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.
2. Weisen Sie die VoIP-Routing Richtlinie Benutzern zu, für die Routing Einschränkungen erzwungen werden müssen.

Weitere Informationen zum Erstellen von VoIP-Routing Richtlinien und zum Zuweisen der Richtlinien zu Benutzern finden Sie unter [Verwalten von VoIP-Routing Richtlinien in Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren des standortbasierten Routings für Netzwerk Websites

Aktivieren Sie standortbasiertes Routing für Ihre Websites, die Routing Einschränkungen erzwingen müssen. Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**  >  **Netzwerktopologie**, wählen Sie eine Netzwerk Website aus, klicken Sie auf **Bearbeiten**, und aktivieren Sie dann **standortbasiertes Routing**.  

Weitere Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren des standortbasierten Routings für Gateways

Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet. 

1. Wechseln Sie in der linken Navigationsleiste zu **VoIP**  >  **Direct Routing**, und klicken Sie dann auf die Registerkarte **SBCS** .
2. Wählen Sie den SBC aus, und klicken Sie dann auf **Bearbeiten**. 
3. Aktivieren Sie unter **standortbasiertes Routing und Medienoptimierung**die **Option standortbasiertes Routing aktivieren**.
4. Geben Sie die Gateway-Standort-ID an, und legen Sie dann den Bypass-Modus fest.
5. Klicken Sie auf **Speichern**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren des standortbasierten Routings für Anruf Richtlinien

Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die Anrufrichtlinie des Benutzers ein, um die PSTN-Maut Umgehung zu verhindern. Aktivieren Sie dazu die Einstellung **Gebühren Umgehung** in der Anrufrichtlinie verhindern.

Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Verwendung von PowerShell

### <a name="enable-location-based-routing-for-users"></a>Aktivieren des standortbasierten Routings für Benutzer

1. Verwenden Sie das Cmdlet " [Satz-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) ", um die PSTN-Verwendung festzulegen. Für mehrere Verwendungen trennen Sie jede Verwendung durch ein Komma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Beispiel:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) , um eine VoIP-Routing Richtlinie zu erstellen, um den Benutzer mit den entsprechenden PSTN-Verwendungen zu verknüpfen.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Wenn Sie einer VoIP-Routing Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:
    - Verwenden von PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden
    - Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.

    In diesem Beispiel erstellen wir zwei neue VoIP-Routing Richtlinien und weisen Ihnen PSTN-Nutzungen zu. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    In der folgenden Tabelle sind die in diesem Beispiel definierten VoIP-Routing Richtlinien aufgeführt. 
    
    ||VoIP-Routing Richtlinie 1|VoIP-Routing Richtlinie 2|
    |---------|---------|---------|
    |Online-VoIP-Richtlinien-ID   |Delhi Online-VoIP-Routing Richtlinie   |Hyderabad Online-VoIP-Routing Richtlinie    |
    |Online PSTN-Nutzungen  |Ferngespräche  |Fern-, Orts-, binnen-und fern-  |

3. Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) , um Benutzern, die Routing Einschränkungen erfordern, das Erzwingen von Online-VoIP-Routing Richtlinien zuzuordnen.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren des standortbasierten Routings für Netzwerk Websites

1.  Verwenden Sie das Cmdlet " [festlegen-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) ", um standortbasiertes Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In diesem Beispiel wird standortbasiertes Routing für die Delhi-Website und die Hyderabad-Website aktiviert. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    In der folgenden Tabelle sind die Websites aufgeführt, die in diesem Beispiel für standortbasiertes Routing aktiviert sind.

    ||Website 1 (Delhi)  |Website 2 (Hyderabad)  |
    |---------|---------|---------|
|Standortname    |Website 1 (Delhi)    |Website 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Wahr    |Wahr    |
    |Subnetze     |Subnetz 1 (Delhi)     |Subnetz 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Aktivieren des standortbasierten Routings für Gateways

1. Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) , um eine Gateway-Konfiguration für jede Gateway-oder Netzwerk Website zu erstellen. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Wenn einem System mehrere Gateways zugeordnet sind (beispielsweise Gateway oder Telefonanlage), ändern Sie die einzelnen Gateways, um standortbasierte Routing Einschränkungen zu ermöglichen. 

    In diesem Beispiel erstellen wir für jedes Gateway eine Gateway-Konfiguration. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).
    
2. Verwenden Sie das Cmdlet " [festlegen-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) ", um standortbasiertes Routing für Ihre Gateways zu aktivieren, die Routing Einschränkungen erzwingen müssen. 

    Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In diesem Beispiel aktivieren wir standortbasiertes Routing für jedes Gateway, das PSTN-Gateways in den Websites Delhi und Hyderabad zugeordnet ist. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Aktivieren Sie das standortbasierte Routing nicht für Gateways, die keine Anrufe an das PSTN weiterleiten. Sie müssen das Gateway jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet. Dies liegt daran, dass standortbasierte Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind. In diesem Beispiel ist die standortbasierte Weiterleitung für jedes Gateway, das PBX-Systemen in den Websites Delhi und Hyderabad zugeordnet ist, nicht aktiviert.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren des standortbasierten Routings für Anruf Richtlinien

Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die VoIP-Richtlinie der Benutzer ein, um PTSN Gebühren Umgehung zu verhindern. 

Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , um standortbasiertes Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In diesem Beispiel verhindern wir die PSTN-Maut Umgehung für von Benutzer1-Anruf Richtlinien. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
