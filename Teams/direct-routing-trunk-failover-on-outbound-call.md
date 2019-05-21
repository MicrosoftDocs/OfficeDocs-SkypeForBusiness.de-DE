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
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="59723-103">Trunkfailover bei ausgehenden Anrufen</span><span class="sxs-lookup"><span data-stu-id="59723-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="59723-104">In diesem Thema wird beschrieben, wie Sie trunk-Failovers bei ausgehenden Anrufen vermeiden – von Teams bis zum Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="59723-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="59723-105">Failover bei Netzwerkfehlern</span><span class="sxs-lookup"><span data-stu-id="59723-105">Failover on network errors</span></span>

<span data-ttu-id="59723-106">Wenn ein trunk aus irgendeinem Grund nicht verbunden werden kann, wird die Verbindung mit dem gleichen Stamm aus einem anderen Microsoft-Rechenzentrum getestet.</span><span class="sxs-lookup"><span data-stu-id="59723-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="59723-107">Ein trunk ist möglicherweise nicht verbunden, beispielsweise, wenn eine Verbindung verweigert wird, wenn ein TLS-Timeout vorliegt oder wenn es andere Probleme auf Netzwerkebene gibt.</span><span class="sxs-lookup"><span data-stu-id="59723-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="59723-108">So kann beispielsweise eine Verbindung fehlschlagen, wenn ein Administrator den Zugriff auf den SBC nur von bekannten IP-Adressen einschränkt, aber vergisst, die IP-Adressen aller Microsoft Direct-Routing-Rechenzentren in der Zugriffssteuerungsliste (ACL) des SBC abzulegen.</span><span class="sxs-lookup"><span data-stu-id="59723-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="59723-109">Failover spezifischer SIP-Codes, die vom Session Border Controller (SBC) empfangen wurden</span><span class="sxs-lookup"><span data-stu-id="59723-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="59723-110">Wenn Direktes Routing als Antwort auf eine ausgehende Einladung 4xx-oder 6xx-SIP-Fehlercodes erhält, gilt der Anruf standardmäßig als abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="59723-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="59723-111">Outgoing bedeutet einen Anruf von einem Teams-Client an das öffentlich geschaltete Telefonnetz (PSTN) mit folgendem Verkehrsfluss: Teams-Client – > Direct Routing – > SBC->-Telefonie-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="59723-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="59723-112">Die Liste der SIP-Codes befindet sich im [SIP-RFC (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="59723-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="59723-113">Nehmen Sie eine Situation an, in der ein SBC auf eine eingehende Einladung mit dem Code "408-Anforderungs Timeout: der Server konnte keine Antwort innerhalb einer angemessenen Zeitspanne erstellen, beispielsweise antwortete, wenn er den Standort des Benutzers nicht rechtzeitig ermitteln konnte.</span><span class="sxs-lookup"><span data-stu-id="59723-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="59723-114">Der Client kann die Anfrage zu einem späteren Zeitpunkt ohne Änderungen wiederholen. "</span><span class="sxs-lookup"><span data-stu-id="59723-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="59723-115">Dieser besondere SBC hat möglicherweise Probleme beim Herstellen einer Verbindung mit dem aufgerufenen--möglicherweise aufgrund einer fehlerhafte Netzwerkkonfiguration oder eines anderen Fehlers.</span><span class="sxs-lookup"><span data-stu-id="59723-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="59723-116">Es gibt jedoch noch einen SBC auf der Route, der möglicherweise in der Lage ist, den aufgerufenen zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="59723-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="59723-117">Wenn ein Benutzer einen Anruf an eine Telefonnummer tätigt, gibt es im folgenden Diagramm zwei SBCS in der Route, die diesen Anruf potenziell übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="59723-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="59723-118">Anfangs ist SBC1.contoso.com für den Anruf ausgewählt, aber SBC1.contoso.com kann aufgrund eines Netzwerkproblems kein PTSN-Netzwerk erreichen.</span><span class="sxs-lookup"><span data-stu-id="59723-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="59723-119">Standardmäßig wird der Anruf zurzeit abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="59723-119">By default, the call will be completed at this moment.</span></span> 
 
![Zeigt, dass SBC aufgrund des Netzwerkproblems nicht erreichbar ist.](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="59723-121">Es gibt jedoch noch einen SBC auf der Route, der den Anruf potenziell abliefern kann.</span><span class="sxs-lookup"><span data-stu-id="59723-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="59723-122">Wenn Sie den Parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`konfigurieren, wird der zweite SBC ausprobiert--SBC2.contoso.com im folgenden Diagramm:</span><span class="sxs-lookup"><span data-stu-id="59723-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Zeigt Routing an zweiten SBC an](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="59723-124">Durch das Festlegen der Parameter-FailoverResponseCodes und die Angabe der Codes können Sie Ihr Routing optimieren und potenzielle Probleme vermeiden, wenn ein SBC aufgrund von Netzwerk-oder anderen Problemen keinen Anruf führen kann.</span><span class="sxs-lookup"><span data-stu-id="59723-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="59723-125">Standardwerte: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="59723-125">Default values:  408, 503, 504</span></span>

