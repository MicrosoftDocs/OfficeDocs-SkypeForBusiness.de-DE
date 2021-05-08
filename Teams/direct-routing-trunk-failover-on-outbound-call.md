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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: In diesem Thema erfahren Sie, wie Sie Trunk-Failover bei ausgehenden Anrufen von Teams zum Session Border Controller (SBC) behandeln.
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836177"
---
# <a name="trunk-failover-on-outbound-calls"></a>Trunkfailover bei ausgehenden Anrufen

In diesem Thema wird beschrieben, wie Sie Trunk-Failover bei ausgehenden Anrufen vermeiden – von Teams zum Session Border Controller (SBC).

## <a name="failover-on-network-errors"></a>Failover bei Netzwerkfehlern

Wenn ein Trunk aus irgendeinem Grund nicht verbunden werden kann, wird die Verbindung mit demselben Trunk von einem anderen Microsoft Datacenter aus versucht. Ein Trunk ist möglicherweise nicht verbunden, z. B. wenn eine Verbindung verweigert wird, wenn ein TLS-Timeout vor liegt oder wenn andere Probleme auf Netzwerkebene auftreten.
Beispielsweise kann eine Verbindung fehlschlagen, wenn ein Administrator den Zugriff auf die SBC nur von bekannten IP-Adressen beschränkt, dabei aber vergessen hat, die IP-Adressen aller Microsoft Direct Routing-Rechenzentren in der Zugriffssteuerungsliste (Access Control List, ACL) der SBC zu speichern. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover bestimmter SIP-Codes, die vom Session Border Controller (SBC) empfangen werden

Wenn Direct Routing als Antwort auf eine ausgehende Einladung SIP-Fehlercodes von 4xx oder 6xx erhält, gilt der Anruf standardmäßig als abgeschlossen. Ausgehend bedeutet einen Anruf von einem Teams-Client an das Public Switched Telephone Network (PSTN) mit folgendem Datenverkehrsfluss: Teams Client -> Direct Routing -> SBC -> Telephony network.

Die Liste der SIP-Codes finden Sie in [SIP RFC (Session Initiation Protocol).](https://tools.ietf.org/html/rfc3261)

Gehen Sie von einer Situation aus, in der ein SBC auf eine eingehende Einladung mit dem Code "408 Request Timeout" antwortet: Der Server konnte nicht innerhalb eines geeigneten Zeitraumes eine Antwort erstellen, z. B. wenn er den Standort des Benutzers nicht innerhalb der Zeit bestimmen konnte. Der Kunde KANN die Anfrage zu einem späteren Zeitpunkt ohne Änderungen wiederholen."

Dieser spezielle SBC hat möglicherweise Schwierigkeiten beim Herstellen einer Verbindung mit dem Anrufer – möglicherweise aufgrund einer falschen Konfiguration des Netzwerks oder eines anderen Fehlers. Es gibt jedoch einen weiteren SBC in der Route, der den Anrufer möglicherweise erreichen kann.

Im folgenden Diagramm sind zwei SBCs in der Route, die diesen Anruf potenziell liefern können, wenn ein Benutzer einen Anruf bei einer Telefonnummer anruft. Zunächst ist SBC1.contoso.com für den Anruf ausgewählt, aber SBC1.contoso.com ist aufgrund eines Netzwerkproblems nicht in der Lage, ein PTSN-Netzwerk zu erreichen.
Der Anruf ist in diesem Moment standardmäßig abgeschlossen. 
 
![Diagramm, das zeigt, dass SBC das PSTN aufgrund eines Netzwerkproblems nicht erreichen kann](media/direct-routing-failover-response-codes1.png)

Es gibt jedoch noch einen weiteren SBC in der Route, der den Anruf potenziell liefern kann.
Wenn Sie den Parameter konfigurieren, wird der zweite SBC ausprobiert– SBC2.contoso.com `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` im folgenden Diagramm dargestellt:

![Diagramm, das das Routing an den zweiten SBC zeigt](media/direct-routing-failover-response-codes2.png)

Durch Festlegen des Parameters -FailoverResponseCodes und Angeben der Codes können Sie das Routing optimieren und potenzielle Probleme vermeiden, wenn ein SBC aufgrund eines Netzwerks oder anderer Probleme keinen Aufruf ausführen kann.

Standardwerte: 408, 503, 504

