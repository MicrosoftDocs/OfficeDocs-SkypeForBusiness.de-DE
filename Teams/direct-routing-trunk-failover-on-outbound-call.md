---
title: Trunkfailover bei ausgehenden Anrufen
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: In diesem Thema erfahren Sie, wie Sie Trunkfailovers bei ausgehenden Anrufen von Teams an den Session Border Controller (SBC) behandeln.
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457135"
---
# <a name="trunk-failover-on-outbound-calls"></a>Trunkfailover bei ausgehenden Anrufen

In diesem Thema wird beschrieben, wie Trunkfailovers bei ausgehenden Anrufen von Teams an den Session Border Controller (SBC) vermieden werden.

## <a name="failover-on-network-errors"></a>Failover bei Netzwerkfehlern

Wenn ein Trunk aus irgendeinem Grund nicht verbunden werden kann, wird die Verbindung mit demselben Trunk von einem anderen Microsoft Datacenter aus versucht. Das Rechenzentrum befindet sich möglicherweise in einer anderen geografischen Region außerhalb Ihrer aktuellen Region. Ein Trunk ist möglicherweise nicht verbunden, wenn eine Verbindung verweigert wird, wenn ein TLS-Timeout vorliegt oder andere Probleme auf Netzwerkebene auftreten.

Beispielsweise kann eine Verbindung fehlschlagen, wenn ein Administrator den Zugriff auf den SBC nur von bekannten IP-Adressen aus eingrenzt, aber vergisst, die IP-Adressen aller Microsoft Direct Routing-Rechenzentren in die Access Control Liste (ACL) des SBC zu setzen. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover bestimmter SIP-Codes, die vom Session Border Controller (SBC) empfangen wurden

Wenn Direct Routing als Reaktion auf eine ausgehende Einladung 4xx- oder 6xx-SIP-Fehlercodes empfängt, gilt der Anruf standardmäßig als abgeschlossen. Ausgehend bedeutet ein Anruf von einem Teams-Client an das PSTN (Public Switched Telephone Network) mit folgendem Datenverkehrsfluss: Teams-Client -> Direct Routing -> SBC -> Telefonienetzwerk.

Die Liste der SIP-Codes finden Sie in [SESSION Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).

Gehen Sie von einer Situation aus, in der ein SBC auf eine eingehende Einladung mit dem Code "408 Anforderungstimeout" geantwortet hat: Der Server konnte nicht innerhalb einer geeigneten Zeitspanne eine Antwort erzeugen, z. B. wenn der Standort des Benutzers nicht rechtzeitig ermittelt werden konnte. Der Kunde KANN die Anforderung jederzeit ohne Änderungen wiederholen."

Dieser spezielle SBC hat möglicherweise Probleme beim Herstellen einer Verbindung mit dem Angerufenen – möglicherweise aufgrund einer Fehlkonfiguration des Netzwerks oder eines anderen Fehlers. Es gibt jedoch einen weiteren SBC in der Route, der möglicherweise den Angerufenen erreichen kann.

Im folgenden Diagramm befinden sich zwei SBCs in der Route, die diesen Anruf möglicherweise entgegenbringen können, wenn ein Benutzer einen Anruf an eine Telefonnummer sendet. Zunächst ist SBC1.contoso.com für den Anruf ausgewählt, aber SBC1.contoso.com ist aufgrund eines Netzwerkproblems nicht in der Lage, ein PTSN-Netzwerk zu erreichen.
Standardmäßig wird der Anruf zu diesem Zeitpunkt abgeschlossen. 
 
![Diagramm, das zeigt, dass der SBC aufgrund eines Netzwerkproblems das PSTN nicht erreichen kann.](media/direct-routing-failover-response-codes1.png)

Es gibt einen weiteren SBC in der Route, der den Anruf möglicherweise entgegenbringen kann.
Wenn Sie den Parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`konfigurieren, wird der zweite SBC ausprobiert (SBC2.contoso.com im folgenden Diagramm):

![Diagramm, das das Routing an den zweiten SBC zeigt.](media/direct-routing-failover-response-codes2.png)

Wenn Sie den Parameter "-FailoverResponseCodes" festlegen und die Codes angeben, können Sie Ihr Routing optimieren und potenzielle Probleme vermeiden, wenn ein SBC aufgrund von Netzwerk- oder anderen Problemen keinen Anruf tätigen kann.

Standardwerte: 408, 503, 504

