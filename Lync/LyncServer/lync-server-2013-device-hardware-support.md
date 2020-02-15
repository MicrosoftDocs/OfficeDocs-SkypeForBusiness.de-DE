---
title: Hardwareunterstützung für lync Server 2013 Geräte
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
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="55d74-102">Unterstützung von Gerätehardware in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55d74-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55d74-103">_**Letztes Änderungsstand des Themas:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="55d74-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="55d74-104">Bevor Sie IP-Telefone und analoge Geräte bereitstellen, müssen spezifische Hardwarekonfigurationen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="55d74-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="55d74-105">IP-Telefone, auf denen lync Phone Edition Support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) und Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="55d74-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="55d74-106">Um die Vorteile von LLDP-MED zu nutzen, muss der Switch IEEE802.1AB und ANSI/TIA-1057 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="55d74-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="55d74-107">Um PoE zu nutzen, muss der Switch PoE802.3AF oder 802.3at unterstützen.</span><span class="sxs-lookup"><span data-stu-id="55d74-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="55d74-108">Zur Aktivierung von LLDP-MED muss der Administrator LLDP über das Konsolenfenster für den Switch aktivieren und die LLDP-MED-Netzwerkrichtlinie mit der richtigen VoIP-VLAN-ID konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="55d74-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="55d74-109">Wenn Ihre Bereitstellung analoge Geräte enthält, müssen Sie darüber hinaus das analoge Gateway für die Verwendung von lync Server konfigurieren, und das Gateway muss einer der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="55d74-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="55d74-110">ATA-Gerät (Analog Telephone Adapter)</span><span class="sxs-lookup"><span data-stu-id="55d74-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="55d74-111">Analoges PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="55d74-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="55d74-112">Survivable Branch Appliance mit analogem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="55d74-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="55d74-113">Survivable Branch Appliance mit PSTN-Gateway, das mit einem ATA-Gerät kommuniziert</span><span class="sxs-lookup"><span data-stu-id="55d74-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="55d74-114">Informationen zum Konfigurieren eines analogen Gateways finden Sie unter "Planung der Bereitstellung von analogen [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) Geräten" in der lync Server 2010 TechNet-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="55d74-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="55d74-115">(Analoge Geräte funktionieren in lync Server 2013 genauso wie in lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="55d74-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55d74-116">Sie können den Switch für 9-1-1 (erweitert) (E9-1-1) konfigurieren, wenn der Switch diese Funktion unterstützt.</span><span class="sxs-lookup"><span data-stu-id="55d74-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

