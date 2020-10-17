---
title: 'Lync Server 2013: Konfigurieren der VoIP-Dienstqualität für lync Phone Edition'
description: 'Lync Server 2013: Konfigurieren der VoIP-Dienstqualität für lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice Quality of Service for Lync Phone Edition
ms:assetid: 2fbe19f7-7ebf-4f9b-a779-3a91f41d488f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520971(v=OCS.15)
ms:contentKeyID: 48183741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faff535cc10d629f4ff3f2f2c43fe3b3118ae859
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566701"
---
# <a name="configure-voice-quality-of-service-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="41666-103">Konfigurieren der VoIP-Dienstqualität für lync Phone Edition in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41666-103">Configure voice Quality of Service for Lync Phone Edition in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41666-104">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="41666-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="41666-105">Sie können QoS-Anforderungen (Voice Quality of Service) für lync Phone Edition-Geräte in einem Pool konfigurieren, indem Sie die QoS-Stufe für IP-Telefone festlegen, die eine Verbindung mit lync Server 2013 herstellen.</span><span class="sxs-lookup"><span data-stu-id="41666-105">You can configure voice Quality of Service (QoS) requirements for Lync Phone Edition devices in a pool by setting the QoS level for IP phones that connect to Lync Server 2013.</span></span>

<div>

## <a name="to-configure-voice-quality-of-service-for-lync-phone-edition"></a><span data-ttu-id="41666-106">So konfigurieren Sie die VoIP-Dienstqualität für lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="41666-106">To configure voice Quality of Service for Lync Phone Edition</span></span>

1.  <span data-ttu-id="41666-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="41666-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="41666-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="41666-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="41666-109">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Gerätekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="41666-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

3.  <span data-ttu-id="41666-110">Doppelklicken Sie auf der Seite **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren QoS-Einstellungen Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="41666-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change QoS settings.</span></span>

4.  <span data-ttu-id="41666-p102">Geben Sie unter **Gerätekonfiguration bearbeiten** im Feld **VoIP-Dienstqualität** die QoS-Ebene an. Die Standardebene lautet **40**.</span><span class="sxs-lookup"><span data-stu-id="41666-p102">In **Edit Device Configuration**, under **Voice quality of service**, specify the QoS level. The default level is **40**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41666-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41666-113">See Also</span></span>


[<span data-ttu-id="41666-114">Verwalten der lync Server 2013 Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="41666-114">Managing the Lync Server 2013 network infrastructure</span></span>](lync-server-2013-managing-the-lync-server-2013-network-infrastructure.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

