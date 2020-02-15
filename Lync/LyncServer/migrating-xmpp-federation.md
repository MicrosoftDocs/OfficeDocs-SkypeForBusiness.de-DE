---
title: Migrieren des XMPP-Verbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a88712d68418b6c4144c67b6583f2451fb7e10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="c40e7-102">Migrieren des XMPP-Verbunds</span><span class="sxs-lookup"><span data-stu-id="c40e7-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c40e7-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c40e7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c40e7-104">In früheren Versionen von lync Server und Office Communications Server wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Server Rolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c40e7-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="c40e7-105">In lync Server 2013 kann die XMPP-Funktionalität als Feature bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c40e7-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="c40e7-106">Die XMPP-Funktionalität wird in zwei Teilen installiert: als XMPP-Proxy, der auf dem lync Server 2013 Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem lync Server 2013 Front-End-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c40e7-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="c40e7-107">Aus Migrations Sicht kann ein lync Server-Benutzerkonto in einen lync Server 2013 Pool verschoben werden und weiterhin das Legacy-XMPP-Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="c40e7-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="c40e7-108">Dies ist nur möglich, wenn der XMPP-Verbundpartner nicht in lync Server 2013 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c40e7-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="c40e7-109">Zusammenfassend lässt sich feststellen, ob lync Server 2010 mit dem Office Communications Server 2007 R2 XMPP-Gateway und dem XMPP-Verbund bereitgestellt wurde, für ältere lync Server 2010-Benutzer aktiviert wurde, um den XMPP-Verbund zu lync Server 2013 zu migrieren:</span><span class="sxs-lookup"><span data-stu-id="c40e7-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="c40e7-110">Bereitstellen eines lync Server 2013 Pools.</span><span class="sxs-lookup"><span data-stu-id="c40e7-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="c40e7-111">Bereitstellen eines lync Server 2013-Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="c40e7-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="c40e7-112">Alle Benutzer in den lync Server 2013 Pool verlagern</span><span class="sxs-lookup"><span data-stu-id="c40e7-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="c40e7-113">Erstellen Sie XMPP-Zugriffsrichtlinien und -Zertifikate für den Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="c40e7-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="c40e7-114">Aktivieren Sie XMPP-Verbund in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c40e7-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="c40e7-115">Aktualisieren Sie die DNS-Einträge so, dass Sie auf das lync Server 2013 XMPP-Gateway verweist.</span><span class="sxs-lookup"><span data-stu-id="c40e7-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

