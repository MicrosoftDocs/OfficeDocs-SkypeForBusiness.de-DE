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
ms.openlocfilehash: 620230ca3be07bb54386f54a983539716d07b2e9
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297809"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="68486-103">Trunk Failover auf ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="68486-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="68486-104">In diesem Thema wird beschrieben, wie Trunk Failover auf ausgehende Anrufe--von Teams, Session Border Controller (SBC) vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="68486-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="68486-105">Failover auf Netzwerkfehler</span><span class="sxs-lookup"><span data-stu-id="68486-105">Failover on network errors</span></span>

<span data-ttu-id="68486-106">Wenn Sie ein Trunk aus irgendeinem Grund verbunden werden kann, wird die Verbindung mit dem gleichen Trunk aus einer anderen Microsoft Datacenter versucht.</span><span class="sxs-lookup"><span data-stu-id="68486-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="68486-107">Ein Trunk möglicherweise nicht, beispielsweise verbunden werden, wenn eine Verbindung verweigert wird, wenn ein Timeout TLS vorhanden ist, oder eine beliebige andere Ebene Netzwerkprobleme vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="68486-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="68486-108">Beispielsweise eine Verbindung kann Fehler auftreten, wenn ein Administrator schränkt den Zugriff auf die SBC nur von bekannten IP-Adressen, aber vergisst, platzieren Sie die IP-Adressen aller Microsoft direkten Routing Rechenzentren auf die Zugriffssteuerungsliste (ACL) von den SBC.</span><span class="sxs-lookup"><span data-stu-id="68486-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="68486-109">Failover für bestimmte von Session Border Controller (SBC) der SIP-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="68486-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="68486-110">Direktes Routing alle etwaigen Fehlercodes 4xx oder 6xx SIP als Antwort auf eine ausgehende INVITE-Nachricht empfängt, gilt der Anruf standardmäßig abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="68486-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="68486-111">Ausgehende ein Anrufs von einem Client Teams an den Public Switched Telephone Telefon Netzwerk (PSTN) mit den folgenden Datenverkehr bedeutet: Teams Client -> direkten Routing SBC -> -> Telefonienetzwerk.</span><span class="sxs-lookup"><span data-stu-id="68486-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="68486-112">Die Liste der SIP-Codes kann in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261)gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="68486-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="68486-113">Eine Situation, in dem ein SBC geantwortet, auf eine eingehende Einladung durch den Code hat, angenommen "408 Anforderungstimeout: der Server konnte nicht erzeugen eine Antwort innerhalb einer geeigneten Zeitspanne beispielsweise, wenn der Standort des Benutzers nicht rechtzeitig festgestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="68486-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="68486-114">Der Client kann die Anforderung ohne Änderungen zu einem späteren Zeitpunkt wiederholen."</span><span class="sxs-lookup"><span data-stu-id="68486-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="68486-115">In bestimmten SBC möglicherweise Probleme beim Herstellen einer Verbindung mit der aufgerufene – möglicherweise aufgrund eines Konfigurationsfehlers Netzwerk oder ein anderer Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="68486-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="68486-116">Es ist jedoch eine weitere SBC in der Route möglicherweise angerufenen zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="68486-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="68486-117">In der folgenden Abbildung Wenn ein Benutzer einen Anruf an eine Telefonnummer herstellt stehen zwei SBCs in der Route, die potenziell dieses Anrufs übermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="68486-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="68486-118">Zunächst SBC1.contoso.com für den Anruf ausgewählt ist, aber SBC1.contoso.com kein Netzwerk PTSN aufgrund eines Netzwerkproblems zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="68486-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="68486-119">Standardmäßig wird der Anruf zu diesem Zeitpunkt durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68486-119">By default, the call will be completed at this moment.</span></span> 
 
![Zeigt nicht erreicht PSTN aufgrund Netzwerkproblem SBC](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="68486-121">Es gibt jedoch eine weitere SBC in der Route, die den Anruf potenziell bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="68486-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="68486-122">Wenn Sie den Parameter Set-CSOnlinePSTNGateway konfigurieren-Identität sbc1.contoso.com - ReinviteResponceCode "408", der zweite SBC werden versucht--SBC2.contoso.com in der folgenden Abbildung:</span><span class="sxs-lookup"><span data-stu-id="68486-122">If you configure the parameter Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -ReinviteResponceCode "408", the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Zeigt das Weiterleiten an die zweite SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="68486-124">Das Festlegen des Parameters - FailoverResponceCodes und zum Angeben der Codes können Sie nichts Ihrer routing optimieren und vermeiden Sie potenzielle Probleme beim ein SBC tätigen Sie einen Anruf aufgrund von Netzwerk- oder andere Probleme kann nicht.</span><span class="sxs-lookup"><span data-stu-id="68486-124">Setting the parameter -FailoverResponceCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="68486-125">Standardwerte: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="68486-125">Default values:  408, 503, 504</span></span>

