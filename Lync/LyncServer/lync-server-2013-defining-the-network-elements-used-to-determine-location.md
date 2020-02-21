---
title: 'Lync Server 2013: Definieren der zum Bestimmen des Standorts verwendeten Netzwerkelemente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6578c0cca54c41f079c682862b9e96a54e3d456
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="56010-102">Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in lync Server 2013 verwendet werden</span><span class="sxs-lookup"><span data-stu-id="56010-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56010-103">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="56010-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="56010-104">Wenn Sie Ihre lync Server-Infrastruktur für die Unterstützung der automatischen Clientstandort Erkennung einrichten, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie verwenden, um Anrufern Standorte zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="56010-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="56010-105">In lync Server 2013 können Sie die folgenden Layer 2-und Layer 3-Netzwerkelemente mit Standorten verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="56010-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="56010-106">Adressen für drahtlosen Zugriffspunk (BSSID, Basic Service Set Identification) (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="56010-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="56010-107">LLDP-Switch-Port (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="56010-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="56010-108">LLDP-Switch-Chassis-IDs (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="56010-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="56010-109">IP-Subnetze (Layer 3)</span><span class="sxs-lookup"><span data-stu-id="56010-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="56010-110">Client-MAC-Adressen (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="56010-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="56010-111">Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="56010-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="56010-112">Wenn ein Client mit mehr als einem Netzwerkelement gefunden werden kann, verwendet lync Server die Rangfolge, um den zu verwendenden Mechanismus zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="56010-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="56010-113">Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.</span><span class="sxs-lookup"><span data-stu-id="56010-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56010-114">Wenn Sie Netzwerkelemente zum Zuordnen von Anrufern zu Standorten verwenden, ist es äußerst wichtig, dass Sie die Standortinformationsdienst-Datenbank auf dem neuesten Stand halten.</span><span class="sxs-lookup"><span data-stu-id="56010-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="56010-115">Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (angenommen Sie fügen z. B. einen drahtlosen Zugriffspunkt hinzu), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56010-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="56010-116">Drahtloser Zugriffspunkt</span><span class="sxs-lookup"><span data-stu-id="56010-116">Wireless Access Point</span></span>

<span data-ttu-id="56010-117">Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die standortanforderung die BSSID-Adresse des WAP, um den Speicherort zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="56010-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="56010-118">Wenn der Client Roaming durchführt, ist der angegebene WAP möglicherweise nicht der nächste, und es ist sogar möglich, einen WAP auf einem anderen Stockwerk des Gebäudes zu holen.</span><span class="sxs-lookup"><span data-stu-id="56010-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="56010-119">Um anzugeben, dass der Speicherort ungefähr ist, können Sie den Location-Wert mit einem near-oder Close-to-Deskriptor voranstellen.</span><span class="sxs-lookup"><span data-stu-id="56010-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="56010-120">Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist.</span><span class="sxs-lookup"><span data-stu-id="56010-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="56010-121">Wenn der Zugriffspunktanbieter jedoch dynamisch zugewiesene BSSIDs verwendet, könnte sich die von einem Zugriffspunkt erhaltene BSSID ändern (dies kann beispielsweise bei einer Konfigurationsänderung für den Zugriffspunkt auftreten) und für die drahtlosen Clients könnte die Situation auftreten, dass sie keinen Standort erhalten.</span><span class="sxs-lookup"><span data-stu-id="56010-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="56010-122">Um diese Möglichkeit zu verhindern, müssen Sie die Standortinformationsdienst Datenbank mit ERLs für alle möglichen BSSID-Adressen auffüllen, die von den einzelnen WAP-Adressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56010-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="56010-123">LLDP-Ports und -Switches</span><span class="sxs-lookup"><span data-stu-id="56010-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="56010-p106">Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="56010-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56010-126">Lync Server 2013 unterstützt die Verwendung von LLDP-MED zur Bestimmung von Speicherorten nur für lync Phone Edition-Geräte und lync 2013, die auf Windows 8 durchführen.</span><span class="sxs-lookup"><span data-stu-id="56010-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="56010-127">Wenn Sie Layer 2-Daten auf switchebene verwenden müssen, um den Speicherort anderer drahtgebundener PC-basierter lync-Clients zu ermitteln, müssen Sie die Client MAC-Adress Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="56010-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="56010-128">Subnetz</span><span class="sxs-lookup"><span data-stu-id="56010-128">Subnet</span></span>

<span data-ttu-id="56010-129">Layer 3-IP-Subnetze bieten einen Mechanismus, der von allen lync Server-Clients unterstützt wird, die zum automatischen Erkennen des Client Standorts verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="56010-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="56010-130">Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="56010-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="56010-131">Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:</span><span class="sxs-lookup"><span data-stu-id="56010-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="56010-132">Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?</span><span class="sxs-lookup"><span data-stu-id="56010-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="56010-133">Umfassen ein oder mehrere Subnetze mehrere Gebäude?</span><span class="sxs-lookup"><span data-stu-id="56010-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="56010-134">Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?</span><span class="sxs-lookup"><span data-stu-id="56010-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="56010-p109">Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, sofern möglich, dass Kunden ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="56010-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="56010-137">Client-MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="56010-137">Client MAC Address</span></span>

<span data-ttu-id="56010-138">Um die Mac-Adresse eines Clientcomputers zum Auffinden eines Anrufers zu verwenden, benötigen Sie Managed Ethernet Switches und müssen eine Drittanbieter-SNMP-Lösung bereitstellen, mit der die Mac-Adressen von lync-Clients ermittelt werden, die mit diesen Switches verbunden sind (oder über diese).</span><span class="sxs-lookup"><span data-stu-id="56010-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="56010-139">Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuellen Zuordnungen der Endpunkt-Mac-Adressen abzurufen, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab.</span><span class="sxs-lookup"><span data-stu-id="56010-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="56010-140">Während der Anforderung eines lync-Clients an den Standortinformationsdienst fragt der Standortinformationsdienst die Drittanbieteranwendung mithilfe der Mac-Adresse des Clients ab und gibt dann alle übereinstimmenden Switch-IP-Adressen und Port-IDs zurück.</span><span class="sxs-lookup"><span data-stu-id="56010-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="56010-141">Der Standortinformationsdienst verwendet diese Informationen zum Abfragen seiner veröffentlichten Schicht 2-Wiremap nach einem übereinstimmenden Datensatz und gibt den Speicherort an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="56010-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="56010-142">Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switch-Port-IDs zwischen der SNMP-Anwendung und den veröffentlichten Datensätzen der Speicherort Datenbank konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="56010-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56010-143">Einige SNMP-Lösungen von Drittanbietern können nicht verwaltete Zugriffs Switches unterstützen. Wenn der Switch, von dem der lync-Client verwaltet wird, aber über einen Uplink an eine verwaltete Verteilungsoption verfügt, kann der verwaltete Switch der SNMP-Anwendung die Mac-Adressen der mit dem Zugriffs Schalter verbundenen Clients zurückerstatten.</span><span class="sxs-lookup"><span data-stu-id="56010-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="56010-144">Mithilfe dieser Informationen kann der Standortinformationsdienst den Speicherort des Benutzers ermitteln.</span><span class="sxs-lookup"><span data-stu-id="56010-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="56010-145">Es ist jedoch möglich, allen Ports auf dem nicht verwalteten Switch nur ein einzelnes Erl zuzuweisen, sodass die Standort Spezifität nur auf der Chassis-Ebene des Zugriffs Switches und nicht auf der Portebene zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="56010-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

