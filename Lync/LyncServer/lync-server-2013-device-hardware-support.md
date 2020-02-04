---
title: 'Lync Server 2013: Unterstützte Gerätehardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="52a8a-102">Unterstützte Gerätehardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52a8a-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52a8a-103">_**Letztes Änderungsdatum des Themas:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="52a8a-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="52a8a-104">Bevor Sie IP-Telefone und analoge Geräte bereitstellen, müssen bestimmte Hardwarekonfigurationen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="52a8a-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="52a8a-105">IP-Telefone mit lync Phone Edition Support Link Layer Discovery Protocol – medienendpunkt Ermittlung (LLDP-MED) und Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="52a8a-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="52a8a-106">Um die Vorteile von LLDP-MED zu nutzen, muss der Switch IEEE 802.1 ab und ANSI/TIA-1057 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52a8a-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="52a8a-107">Um Poe nutzen zu können, muss der Switch Poe 802.3 AF oder 802.3 at unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52a8a-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="52a8a-108">Um LLDP-MED zu aktivieren, muss der Administrator LLDP über das Console-Fenster Switch aktivieren und die LLDP-MED-Netzwerkrichtlinie mit der korrekten sprach-VLAN-ID festlegen.</span><span class="sxs-lookup"><span data-stu-id="52a8a-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="52a8a-109">Wenn Ihre Bereitstellung analoge Geräte umfasst, müssen Sie außerdem das analoge Gateway für die Verwendung von lync Server konfigurieren, und das Gateway muss eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="52a8a-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="52a8a-110">Einen analogen Telefonadapter (ATA)</span><span class="sxs-lookup"><span data-stu-id="52a8a-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="52a8a-111">Ein analoges PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="52a8a-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="52a8a-112">Eine Survivable-Branch-Appliance mit einem analogen PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="52a8a-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="52a8a-113">Eine Survivable-Branch-Appliance, die ein PSTN-Gateway enthält, das mit einem ATA kommuniziert</span><span class="sxs-lookup"><span data-stu-id="52a8a-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="52a8a-114">Informationen zum Konfigurieren eines analogen Gateways finden Sie unter "Planen der Bereitstellung von analogen [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) Geräten" in der lync Server 2010 TechNet-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="52a8a-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="52a8a-115">(Analoge Geräte funktionieren auf die gleiche Weise in lync Server 2013 wie in lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="52a8a-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52a8a-116">Sie können den Schalter für Enhanced 9-1-1 (E9-1-1) konfigurieren, wenn dies vom Switch unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="52a8a-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

