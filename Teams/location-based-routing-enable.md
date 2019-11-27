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
description: Hier erfahren Sie, wie Sie standortbasiertes Routing für direktes Routing aktivieren.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 615848be1f91f80b0afd06c1eaa44a4f9d7b4f63
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615795"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Aktivieren des standortbasierten Routings für direktes Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, dass Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md) gelesen haben, und führen Sie die Schritte unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md)aus.

In diesem Artikel wird beschrieben, wie standortbasiertes Routing für das direkte Routing aktiviert wird. Nachdem Sie das direkte Routing für das Telefon System bereitgestellt und netzwerkregionen,-Standorte und-Subnetze eingerichtet haben, können Sie das standortbasierte Routing aktivieren. Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen. Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

 Sie müssen standortbasiertes Routing für Folgendes aktivieren:
- Benutzer
- Netzwerk Websites
- Gateway-Konfigurationen
- Anruf Richtlinien

## <a name="enable-location-based-routing-for-users"></a>Aktivieren des standortbasierten Routings für Benutzer

1. Verwenden Sie das Cmdlet " [Satz-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) ", um die PSTN-Verwendung festzulegen. Für mehrere Verwendungen trennen Sie jede Verwendung durch ein Komma.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Beispiel:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) , um eine VoIP-Routing Richtlinie zu erstellen, um den Benutzer mit den entsprechenden PSTN-Verwendungen zu verknüpfen.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Wenn Sie einer VoIP-Routing Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:
    - Verwenden von PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden
    - Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.

    In diesem Beispiel erstellen wir zwei neue VoIP-Routing Richtlinien und weisen Ihnen PSTN-Nutzungen zu. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    In der folgenden Tabelle sind die in diesem Beispiel definierten VoIP-Routing Richtlinien aufgeführt. 
    
    ||VoIP-Routing Richtlinie 1|VoIP-Routing Richtlinie 2|
    |---------|---------|---------|
    |Online-VoIP-Richtlinien-ID   |Delhi Online-VoIP-Routing Richtlinie   |Hyderabad Online-VoIP-Routing Richtlinie    |
    |Online PSTN-Nutzungen  |Ferngespräche  |Fern-, Orts-, binnen-und fern-  |

3. Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) , um Benutzern, die Routing Einschränkungen erfordern, das Erzwingen von Online-VoIP-Routing Richtlinien zuzuordnen.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Aktivieren des standortbasierten Routings für Netzwerk Websites
1.  Verwenden Sie das Cmdlet " [festlegen-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) ", um standortbasiertes Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In diesem Beispiel wird standortbasiertes Routing für die Delhi-Website und die Hyderabad-Website aktiviert. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    In der folgenden Tabelle sind die Websites aufgeführt, die in diesem Beispiel für standortbasiertes Routing aktiviert sind.

    ||Website 1 (Delhi)  |Website 2 (Hyderabad)  |
    |---------|---------|---------|
|Standortname    |Website 1 (Delhi)    |Website 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Wahr    |Wahr    |
    |Subnetze     |Subnetz 1 (Delhi)     |Subnetz 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Aktivieren des standortbasierten Routings für Gateways
1. Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) , um eine Gateway-Konfiguration für jede Gateway-oder Netzwerk Website zu erstellen. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Wenn einem System mehrere Gateways zugeordnet sind (beispielsweise Gateway oder Telefonanlage), ändern Sie die einzelnen Gateways, um standortbasierte Routing Einschränkungen zu ermöglichen. 

    In diesem Beispiel erstellen wir für jedes Gateway eine Gateway-Konfiguration. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).
    
2. Verwenden Sie das Cmdlet " [festlegen-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) ", um standortbasiertes Routing für Ihre Gateways zu aktivieren, die Routing Einschränkungen erzwingen müssen. 

    Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In diesem Beispiel aktivieren wir standortbasiertes Routing für jedes Gateway, das PSTN-Gateways in den Websites Delhi und Hyderabad zugeordnet ist. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Aktivieren Sie das standortbasierte Routing nicht für Gateways, die keine Anrufe an das PSTN weiterleiten. Sie müssen das Gateway jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet. Dies liegt daran, dass standortbasierte Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind. In diesem Beispiel ist die standortbasierte Weiterleitung für jedes Gateway, das PBX-Systemen in den Websites Delhi und Hyderabad zugeordnet ist, nicht aktiviert.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (beispielsweise eine Telefonanlage) weiterleiten, weisen ähnliche Einschränkungen wie Endpunkte von Team Benutzern auf, die für standortbasiertes Routing aktiviert sind. Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von Teams-Benutzern tätigen und empfangen können. Sie können auch Anrufe von und zu anderen Systemen tätigen und empfangen, die keine Anrufe an das PSTN-Netzwerk weiterleiten (beispielsweise einen Endpunkt, der mit einer anderen Telefonanlage verbunden ist), und zwar unabhängig von der Netzwerk Website, der das System zugeordnet ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung, die PSTN-Endpunkte einbeziehen, unterliegen standortbasierten Routing-Erzwingungen. Bei diesen anrufen müssen nur PSTN-Gateways verwendet werden, die für solche Systeme als lokal definiert sind. 

    Die folgende Tabelle zeigt die Gateway-Konfiguration von vier Gateways auf zwei verschiedenen Netzwerkstandorten: zwei mit PSTN-Gateways verbunden und zwei mit PBX-Systemen verbunden. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: Gateway 1 del-GW    |    Wahr     |   Website 1 (Delhi)      |
    |PstnGateway: Gateway 2 Hyd-GW     |   Wahr      |      Website 2 (Hyderabad)   |
    |PstnGateway: Gateway 3 del-PBX    |    Falsch     |     Website 1 (Delhi)    |
    |PstnGateway: Gateway 4 Hyd-PBX    |    Falsch     |    Website 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren des standortbasierten Routings für Anruf Richtlinien

Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die VoIP-Richtlinie der Benutzer ein, um PTSN Gebühren Umgehung zu verhindern. 

Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , um standortbasiertes Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In diesem Beispiel verhindern wir die PSTN-Maut Umgehung für von Benutzer1-Anruf Richtlinien. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a>Verwandte Themen

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
