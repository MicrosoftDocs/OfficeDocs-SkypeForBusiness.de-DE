---
title: Trunkfailover bei ausgehenden Anrufen
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: In diesem Thema erfahren Sie, wie Sie trunk-Failovers bei ausgehenden Anrufen von Teams an den Session Border Controller (SBC) behandeln.
ms.openlocfilehash: e9efcfba696886c0fc4885778b79832956ccb893
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290363"
---
# <a name="trunk-failover-on-outbound-calls"></a>Trunkfailover bei ausgehenden Anrufen

In diesem Thema wird beschrieben, wie Sie trunk-Failovers bei ausgehenden Anrufen vermeiden – von Teams bis zum Session Border Controller (SBC).

## <a name="failover-on-network-errors"></a>Failover bei Netzwerkfehlern

Wenn ein trunk aus irgendeinem Grund nicht verbunden werden kann, wird die Verbindung mit dem gleichen Stamm aus einem anderen Microsoft-Rechenzentrum getestet. Ein trunk ist möglicherweise nicht verbunden, beispielsweise, wenn eine Verbindung verweigert wird, wenn ein TLS-Timeout vorliegt oder wenn es andere Probleme auf Netzwerkebene gibt.
So kann beispielsweise eine Verbindung fehlschlagen, wenn ein Administrator den Zugriff auf den SBC nur von bekannten IP-Adressen einschränkt, aber vergisst, die IP-Adressen aller Microsoft Direct-Routing-Rechenzentren in der Zugriffssteuerungsliste (ACL) des SBC abzulegen. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover spezifischer SIP-Codes, die vom Session Border Controller (SBC) empfangen wurden

Wenn Direktes Routing als Antwort auf eine ausgehende Einladung 4xx-oder 6xx-SIP-Fehlercodes erhält, gilt der Anruf standardmäßig als abgeschlossen. Outgoing bedeutet einen Anruf von einem Teams-Client an das öffentlich geschaltete Telefonnetz (PSTN) mit folgendem Verkehrsfluss: Teams-Client – > Direct Routing – > SBC->-Telefonie-Netzwerk.

Die Liste der SIP-Codes befindet sich im [SIP-RFC (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3261).

Nehmen Sie eine Situation an, in der ein SBC auf eine eingehende Einladung mit dem Code "408-Anforderungs Timeout: der Server konnte keine Antwort innerhalb einer angemessenen Zeitspanne erstellen, beispielsweise antwortete, wenn er den Standort des Benutzers nicht rechtzeitig ermitteln konnte. Der Client kann die Anfrage zu einem späteren Zeitpunkt ohne Änderungen wiederholen. "

Dieser besondere SBC hat möglicherweise Probleme beim Herstellen einer Verbindung mit dem aufgerufenen--möglicherweise aufgrund einer fehlerhafte Netzwerkkonfiguration oder eines anderen Fehlers. Es gibt jedoch noch einen SBC auf der Route, der möglicherweise in der Lage ist, den aufgerufenen zu erreichen.

Wenn ein Benutzer einen Anruf an eine Telefonnummer tätigt, gibt es im folgenden Diagramm zwei SBCS in der Route, die diesen Anruf potenziell übermitteln können. Anfangs ist SBC1.contoso.com für den Anruf ausgewählt, aber SBC1.contoso.com kann aufgrund eines Netzwerkproblems kein PTSN-Netzwerk erreichen.
Standardmäßig wird der Anruf zurzeit abgeschlossen. 
 
![Zeigt, dass SBC aufgrund des Netzwerkproblems nicht erreichbar ist.](media/direct-routing-failover-response-codes1.png)

Es gibt jedoch noch einen SBC auf der Route, der den Anruf potenziell abliefern kann.
Wenn Sie den Parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`konfigurieren, wird der zweite SBC ausprobiert--SBC2.contoso.com im folgenden Diagramm:

![Zeigt Routing an zweiten SBC an](media/direct-routing-failover-response-codes2.png)

Durch das Festlegen der Parameter-FailoverResponseCodes und die Angabe der Codes können Sie Ihr Routing optimieren und potenzielle Probleme vermeiden, wenn ein SBC aufgrund von Netzwerk-oder anderen Problemen keinen Anruf führen kann.

Standardwerte: 408, 503, 504

