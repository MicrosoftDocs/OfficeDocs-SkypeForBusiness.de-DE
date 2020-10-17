---
title: Überprüfen der Office Communications Server 2007 R2 Umgebung
description: Überprüfen Sie Office Communications Server 2007 R2 Umgebung.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb200941b3a35ece2b587bcfc89be743c9960d1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555561"
---
# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="4cb4b-103">Überprüfen der Office Communications Server 2007 R2 Umgebung</span><span class="sxs-lookup"><span data-stu-id="4cb4b-103">Verify Office Communications Server 2007 R2 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cb4b-104">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4cb4b-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4cb4b-105">Vor dem Bereitstellen von lync Server 2013 im Status "Koexistenz" mit Office Communications Server 2007 R2 müssen Sie überprüfen, ob die Office Communications Server 2007 R2 Dienste konfiguriert und gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-105">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="4cb4b-106">**Überprüfen, ob der Pool mit dem Office Communications Server 2007 R2 Verwaltungs Tool gestartet wurde**</span><span class="sxs-lookup"><span data-stu-id="4cb4b-106">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="4cb4b-107">Öffnen Sie das Office Communications Server 2007 R2 Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-107">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="4cb4b-108">Erweitern Sie den Knoten **Gesamtstruktur**, den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-108">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="4cb4b-109">Stellen Sie sicher, dass die Dienste auf dem Standard Edition-Server oder im Enterprise-Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-109">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="4cb4b-110">![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")</span><span class="sxs-lookup"><span data-stu-id="4cb4b-110">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="4cb4b-111">**Überprüfen der für Office Communications Server 2007 R2 konfigurierten Benutzer**</span><span class="sxs-lookup"><span data-stu-id="4cb4b-111">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="4cb4b-112">Öffnen Sie das Office Communications Server 2007 R2 Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-112">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="4cb4b-113">Erweitern Sie den Knoten **Gesamtstruktur**, den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-113">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="4cb4b-114">Klicken Sie auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-114">Click **Users**.</span></span>

4.  <span data-ttu-id="4cb4b-115">Überprüfen Sie die Liste der Office Communications Server 2007 R2 Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-115">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="4cb4b-116">![Auflisten von FO-Benutzern im OCS-Verwaltungstool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Auflisten von FO-Benutzern im OCS-Verwaltungstool")</span><span class="sxs-lookup"><span data-stu-id="4cb4b-116">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="4cb4b-117">**Überprüfen der XMPP-Verbundpartnerkonfiguration der Vorversion**</span><span class="sxs-lookup"><span data-stu-id="4cb4b-117">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="4cb4b-118">Navigieren Sie auf dem vorversions-XMPP-Server zum Applet Dienste für administrative Tools \\ .</span><span class="sxs-lookup"><span data-stu-id="4cb4b-118">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="4cb4b-119">Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist.</span><span class="sxs-lookup"><span data-stu-id="4cb4b-119">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="4cb4b-120">![Office Communications Server XMPP-Gatewaydienst](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP-Gatewaydienst")</span><span class="sxs-lookup"><span data-stu-id="4cb4b-120">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

