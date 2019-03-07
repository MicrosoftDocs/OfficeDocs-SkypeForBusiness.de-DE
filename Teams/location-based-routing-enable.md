---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie speicherortbasierte Routing für die direkte Weiterleitung zu aktivieren.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 809e48e4a770906b93642356cc5f37fd03c411c4
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460332"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Aktivieren des standortbasierten Routings für direktes Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, Sie [Plan Location-Based Routing für das direkte Routing](location-based-routing-plan.md) gelesen und die Schritte unter [Configure Netzwerkeinstellungen für standortbasierte Routing](location-based-routing-configure-network-settings.md)abgeschlossen haben.

In diesem Artikel wird beschrieben, wie speicherortbasierte Routing für die direkte Weiterleitung zu aktivieren. Nachdem Sie Phone System direkten Routing bereitstellen und von netzwerkregionen, Standorten und Subnetzen einrichten, können Sie standortbasierte Routing zu aktivieren. Um die Schritte in diesem Artikel ausführen zu können, benötigen Sie einige gute Kenntnisse im Umgang mit PowerShell-Cmdlets. Weitere Informationen finden Sie unter [Teams PowerShell (Übersicht)](teams-powershell-overview.md).

 Sie müssen den speicherortbasierte Routing für Folgendes aktivieren:
- Benutzer
- Netzwerkstandorte
- Gateway-Konfigurationen
- Aufrufen von Richtlinien

## <a name="enable-location-based-routing-for-users"></a>Speicherortbasierte Routing für Benutzer aktivieren

1. Verwendung der ``Set-CsOnlinePstnUsages`` -Cmdlet zum Festlegen von PSTN-Verwendungen. Trennen Sie mehrere Verwendungen jeder Verwendung durch ein Komma.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Beispiel:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Verwendung der ``New-CsOnlineVoiceRoutingPolicy`` -Cmdlet zum Erstellen einer VoIP-Routingrichtlinie, um den Benutzer mit den entsprechenden PSTN-Verwendungen verknüpfen.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Wenn Sie eine VoIP-Routingrichtlinie mit PSTN-Verwendungen zuweisen, stellen Sie sicher, dass Sie einen der folgenden Schritte ausführen:
    - Verwenden von PSTN-Verwendungen, die VoIP-Routen, mit denen ein PSTN-Gateway lokalen zu der Website zugeordnet sind
    - Verwenden Sie die PSTN-Verwendungen, VoIP-Routen, die ein PSTN-Gateway befindet sich in einem Bereich, in dem Routing speicherortbasierte Einschränkungen nicht benötigte, verwenden zugeordnet ist.

    In diesem Beispiel werden zwei neue VoIP-Routingrichtlinien erstellen und PSTN-Verwendungen zuweisen. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    In der folgenden Tabelle zeigt die in diesem Beispiel definierten VoIP-Routingrichtlinien zurückgegeben. 
    
    ||VoIP-routing-Richtlinie 1|VoIP-routing-Richtlinie 2|
    |---------|---------|---------|
    |Online VoIP-Richtlinien-ID   |Delhi online VoIP-routing-Richtlinie   |Hyderabad online VoIP-routing-Richtlinie    |
    |Online PSTN-Verwendungen  |Ferngespräche  |Long Distance, lokale, interne  |

    Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).
3. Verwendung der ``Grant-CsOnlineVoiceRoutingPolicy`` -Cmdlet zum Zuordnen online VoIP-routing Richtlinien für Benutzer, die erfordern routing Einschränkungen erzwungen werden.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Speicherortbasierte Routing für Netzwerkstandorte aktivieren
1.  Verwendung der ``Set-CsTenantNetworkSite`` -Cmdlet zum Aktivieren speicherortbasierte Routing- und ordnen Sie VoIP-Routingrichtlinien zu Netzwerkstandorten, die zum Erzwingen von routing Einschränkungen benötigen.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    In diesem Beispiel können wir speicherortbasierte Routing für die Delhi und der Hyderabad-Website. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    Die folgende Tabelle zeigt die Websites für standortbasierte Routing in diesem Beispiel wird aktiviert.

    ||Website 1 (Delhi)  |Standort 2 (Hyderabad)  |
    |---------|---------|---------|
|Standortname    |Website 1 (Delhi)    |Standort 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Subnetze     |Subnetz 1 (Delhi)     |Subnetz 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Aktivieren Sie standortbasierte Routing für gateways
1. Verwendung der ``New-CsOnlinePstnGateway`` -Cmdlet zum Erstellen einer Gatewaykonfiguration für die einzelnen Standorte Gateway oder Netzwerk. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Wenn mehrere Gateways mit einem System (beispielsweise Gateway oder PBX) verbunden sind, ändern Sie jedes Gateway, um Einschränkungen speicherortbasierte Routing zu aktivieren. 

    In diesem Beispiel erstellen wir eine Gatewaykonfiguration für jedes Gateway. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Weitere Informationen finden Sie unter [Konfigurieren von direkten Routing](direct-routing-configure.md).
    
2. Verwendung der ``Set-CSOnlinePSTNGateway`` -Cmdlet zum speicherortbasierte Routing für Ihre Gateways zu aktivieren, die zum Erzwingen von routing Einschränkungen benötigen. 

    Aktivieren speicherortbasierte Routing zu Gateways, die Anrufe weiterleiten an PSTN-Gateways, die Anrufe an das Telefonfestnetz weiterleiten, und ordnen Sie den Netzwerkstandort das Gateway gespeichert ist.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    In diesem Beispiel können wir speicherortbasierte Routing für jedes Gateway, das zum PSTN-Gateways an den Standorten Delhi und Hyderabad zugeordnet ist. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Aktivieren Sie nicht speicherortbasierte Routing für Gateways, die Anrufe an das Telefonfestnetz weiterleiten nicht. Sie haben jedoch weiterhin das Gateway auf den Netzwerkstandort zuzuordnen, in das System gespeichert ist. Dies ist, da Routing speicherortbasierte Einschränkungen müssen erzwungen werden, die für PSTN-Anrufe erreichen von Endpunkten, die über dieses Gateway verbunden sind. In diesem Beispiel wird nicht speicherortbasierte Routing für jedes Gateway aktiviert, die mit PBX-Systemen auf den Websites Delhi und Hyderabad zugeordnet ist.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Endpunkte mit Systemen, die Anrufe an das Telefonfestnetz (beispielsweise eine Nebenstellenanlage (PBX) weitergeleitet werden nicht verbunden werden als Endpunkte des Teams für standortbasierte Routing aktivierten Benutzern ähnliche Einschränkungen haben. Dies bedeutet, dass diese Benutzer tätigen und Entgegennehmen von Anrufen zu und von Teams Benutzer unabhängig vom Standort des Benutzers können. Sie können auch Anrufe tätigen und empfangen zu und von anderen Systemen, die Aufrufe an das PSTN-Netzwerk (beispielsweise einen Endpunkt zu einer anderen Nebenstellenanlage verbunden) unabhängig von den Netzwerkstandort weiterleiten nicht, die das System zugeordnet ist. Speicherortbasierte Routing Bescheide werden alle eingehenden Anrufe, ausgehende Anrufe, Call gehandelt und die anrufweiterleitung, die PSTN-Endgeräten betreffen erhoben. Bei diesen anrufen müssen nur PSTN-Gateways verwenden, die als lokale Systeme dieser definiert sind. 

    Die folgende Tabelle enthält die Gateway-Konfiguration der vier Gateways in zwei verschiedenen Netzwerkstandorten: zwei mit PSTN-Gateways und zwei verbunden mit PBX-Systemen verbunden ist. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway:Gateway 1 DEL-GW    |    True     |   Website 1 (Delhi)      |
    |PstnGateway:Gateway 2 HYD-GW     |   True      |      Standort 2 (Hyderabad)   |
    |DEL PstnGateway:Gateway 3-PBX-Ressource    |    Falsch     |     Website 1 (Delhi)    |
    |PstnGateway:Gateway 4 HYD-PBX-Ressource    |    Falsch     |    Standort 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Aktivieren Sie standortbasierte Routing für den Aufruf von Richtlinien

Zum Erzwingen der speicherortbasierte Routing für bestimmte Benutzer einrichten der Benutzer VoIP-Richtlinie verhindert PTSN gebührenpflichtige umgehen. 

Verwendung der ``Grant-CsTeamsCallingPolicy`` -Cmdlet zum Aktivieren der speicherortbasierte routing, indem Sie verhindern, dass PSTN Gebühren zu umgehen.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
In diesem Beispiel wird verhindert, dass wir PSTN gebührenpflichtige umgangen Benutzer1 Richtlinien aufrufen. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Verwandte Themen
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Terminologie für das standortbasierte Routing](location-based-routing-terminology.md)
