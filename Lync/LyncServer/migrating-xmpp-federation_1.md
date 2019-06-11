---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="b37f4-102">Migrieren eines XMPP-Partnerverbunds</span><span class="sxs-lookup"><span data-stu-id="b37f4-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b37f4-103">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="b37f4-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="b37f4-104">In früheren Versionen von Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b37f4-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="b37f4-105">In lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b37f4-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="b37f4-106">Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem lync Server 2013-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem lync Server 2013-Front-End-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b37f4-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="b37f4-107">Aus Sicht der Migration kann ein Office Communications Server 2007 R2-Benutzerkonto in einen lync Server 2013-Pool verschoben und weiterhin das Office Communications Server 2007 R2 XMPP-Gateway verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b37f4-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="b37f4-108">Dies ist nur möglich, wenn der XMPP-Verbundpartner nicht in lync Server 2013 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b37f4-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="b37f4-109">Zusammenfassung: Wenn Office Communications Server mit dem Office Communications Server 2007 R2 XMPP-Gateway bereitgestellt wurde und die XMPP-Föderation für Legacy Office Communications Server 2007 R2-Benutzer aktiviert wurde, können Sie die XMPP-Föderation zu lync Server 2013 migrieren:</span><span class="sxs-lookup"><span data-stu-id="b37f4-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="b37f4-110">Bereitstellen eines lync Server 2013-Pools</span><span class="sxs-lookup"><span data-stu-id="b37f4-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="b37f4-111">Bereitstellen eines lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b37f4-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="b37f4-112">Verschieben Sie alle Benutzer in den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="b37f4-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="b37f4-113">Erstellen Sie XMPP-Zugriffsrichtlinien und-Zertifikate für den Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="b37f4-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="b37f4-114">Aktivieren Sie die XMPP-Föderation in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b37f4-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="b37f4-115">Aktualisieren Sie die DNS-Einträge so, dass Sie auf das lync Server 2013 XMPP-Gateway verweisen.</span><span class="sxs-lookup"><span data-stu-id="b37f4-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

