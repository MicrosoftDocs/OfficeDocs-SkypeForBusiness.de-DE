---
title: 'Lync Server 2013: (optional) Überprüfen der Reaktionsgruppen Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00373df840e46e6a0c849f2974b83b858c9fed70
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="7e7fd-102">Optional Überprüfen der Bereitstellung von Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e7fd-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e7fd-103">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="7e7fd-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="7e7fd-104">Nachdem Sie die Reaktionsgruppe konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass Ihre Reaktionsgruppen wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7e7fd-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="7e7fd-105">Führen Sie mindestens eine Überprüfung der folgenden Szenarien mit den folgenden Benutzertypen durch:</span><span class="sxs-lookup"><span data-stu-id="7e7fd-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="7e7fd-106">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="7e7fd-106">**Users**</span></span>

  - <span data-ttu-id="7e7fd-107">Ein Benutzer, der in lync Server 2013 verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="7e7fd-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="7e7fd-108">Ein externer Benutzer, der das Telefonfestnetz (Public Switched Telephone Network, PSTN) verwendet</span><span class="sxs-lookup"><span data-stu-id="7e7fd-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="7e7fd-109">Ein Agent, der in lync Server 2013 verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="7e7fd-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="7e7fd-110">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="7e7fd-110">**Scenarios**</span></span>

  - <span data-ttu-id="7e7fd-111">Der lync Server 2013 Benutzer ruft die Reaktionsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="7e7fd-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="7e7fd-112">Der externe Benutzer ruft die Reaktionsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="7e7fd-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="7e7fd-113">Ein Benutzer ruft die Reaktionsgruppe an, während der Agent sich in einem Gespräch befindet; der Benutzer wird in der Warteschleife platziert.</span><span class="sxs-lookup"><span data-stu-id="7e7fd-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

