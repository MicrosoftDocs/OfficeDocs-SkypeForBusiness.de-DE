---
title: Trunk Failover auf ausgehende Anrufe
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lesen Sie in diesem Thema erfahren, wie behandeln Trunk Failover auf ausgehende Anrufe von Teams, Session Border Controller (SBC).
ms.openlocfilehash: 1f8e7dfd5064b9c3d857165a9a4e2d39565dfeef
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271149"
---
# <a name="trunk-failover-on-outbound-calls"></a>Trunk Failover auf ausgehende Anrufe

In diesem Thema wird beschrieben, wie Trunk Failover auf ausgehende Anrufe--von Teams, Session Border Controller (SBC) vermieden werden.

## <a name="failover-on-network-errors"></a>Failover auf Netzwerkfehler

Wenn Sie ein Trunk aus irgendeinem Grund verbunden werden kann, wird die Verbindung mit dem gleichen Trunk aus einer anderen Microsoft Datacenter versucht. Ein Trunk möglicherweise nicht, beispielsweise verbunden werden, wenn eine Verbindung verweigert wird, wenn ein Timeout TLS vorhanden ist, oder eine beliebige andere Ebene Netzwerkprobleme vorhanden sind.
Beispielsweise eine Verbindung kann Fehler auftreten, wenn ein Administrator schränkt den Zugriff auf die SBC nur von bekannten IP-Adressen, aber vergisst, platzieren Sie die IP-Adressen aller Microsoft direkten Routing Rechenzentren auf die Zugriffssteuerungsliste (ACL) von den SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Failover für bestimmte von Session Border Controller (SBC) der SIP-Fehlercodes

Direktes Routing alle etwaigen Fehlercodes 4xx oder 6xx SIP als Antwort auf eine ausgehende INVITE-Nachricht empfängt, gilt der Anruf standardmäßig abgeschlossen. Ausgehende ein Anrufs von einem Client Teams an den Public Switched Telephone Telefon Netzwerk (PSTN) mit den folgenden Datenverkehr bedeutet: Teams Client -> direkten Routing SBC -> -> Telefonienetzwerk.

Die Liste der SIP-Codes kann in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261)gefunden werden.

Eine Situation, in dem ein SBC geantwortet, auf eine eingehende Einladung durch den Code hat, angenommen "408 Anforderungstimeout: der Server konnte nicht erzeugen eine Antwort innerhalb einer geeigneten Zeitspanne beispielsweise, wenn der Standort des Benutzers nicht rechtzeitig festgestellt werden konnte. Der Client kann die Anforderung ohne Änderungen zu einem späteren Zeitpunkt wiederholen."

In bestimmten SBC möglicherweise Probleme beim Herstellen einer Verbindung mit der aufgerufene – möglicherweise aufgrund eines Konfigurationsfehlers Netzwerk oder ein anderer Fehler auftreten. Es ist jedoch eine weitere SBC in der Route möglicherweise angerufenen zu erreichen.

In der folgenden Abbildung Wenn ein Benutzer einen Anruf an eine Telefonnummer herstellt stehen zwei SBCs in der Route, die potenziell dieses Anrufs übermitteln kann. Zunächst SBC1.contoso.com für den Anruf ausgewählt ist, aber SBC1.contoso.com kein Netzwerk PTSN aufgrund eines Netzwerkproblems zu erreichen.
Standardmäßig wird der Anruf zu diesem Zeitpunkt durchgeführt werden. 
 
![Zeigt nicht erreicht PSTN aufgrund Netzwerkproblem SBC](media/direct-routing-failover-response-codes1.png)

Es gibt jedoch eine weitere SBC in der Route, die den Anruf potenziell bereitstellen kann.
Wenn Sie den Parameter Set-CSOnlinePSTNGateway konfigurieren-Identität sbc1.contoso.com - ReinviteResponceCode "408", der zweite SBC werden versucht--SBC2.contoso.com in der folgenden Abbildung:

![Zeigt das Weiterleiten an die zweite SBC](media/direct-routing-failover-response-codes2.png)

Das Festlegen des Parameters - FailoverResponceCodes und zum Angeben der Codes können Sie nichts Ihrer routing optimieren und vermeiden Sie potenzielle Probleme beim ein SBC tätigen Sie einen Anruf aufgrund von Netzwerk- oder andere Probleme kann nicht.

Standardwerte: 408, 503, 504

