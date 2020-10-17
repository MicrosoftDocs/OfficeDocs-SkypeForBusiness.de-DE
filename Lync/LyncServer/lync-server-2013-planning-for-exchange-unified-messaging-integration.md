---
title: 'Lync Server 2013: Planen der Integration von Exchange Unified Messaging'
description: 'Lync Server 2013: Planen der Integration von Exchange Unified Messaging.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31296444d21a86a7837da3e29fc2152f3ca96ccc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571881"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="2dee1-103">Planen der Integration von Exchange Unified Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dee1-103">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dee1-104">_**Letztes Änderungsstand des Themas:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="2dee1-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="2dee1-105">Lync Server 2013 unterstützt die Integration in Exchange Unified Messaging (um) für die Kombination von Sprachnachrichten und e-Mail-Messaging in einer einzelnen Messaging Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="2dee1-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="2dee1-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) und Microsoft Exchange Server 2010 ist Exchange Unified Messaging (um) eine von mehreren Exchange-Server Rollen, die Sie installieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="2dee1-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="2dee1-107">In Microsoft Exchange Server 2013 wird Exchange um als Dienst auf einem Exchange-Post Fach Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2dee1-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="2dee1-108">Für lync Server 2013 Enterprise-VoIP-Bereitstellungen kombiniert Unified Messaging Sprachnachrichten und e-Mail-Nachrichten in einem einzigen Speicher, der über ein Telefon (Outlook Voice Access) oder einen Computer zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="2dee1-108">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="2dee1-109">Unified Messaging und lync Server 2013 arbeiten zusammen, um Mailboxansage, Outlook Voice Access und automatische Telefonzentralendienste für Benutzer von Enterprise-VoIP bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2dee1-109">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="2dee1-110">Weitere Informationen zu den Architekturänderungen in Microsoft Exchange Server 2013 finden Sie unter "Änderungen an der Spracharchitektur" in der Microsoft Exchange Server 2013-Dokumentation unter [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="2dee1-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="2dee1-111">Damit diese Features in einer lokalen Exchange um-Bereitstellung unterstützt werden, müssen Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="2dee1-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="2dee1-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="2dee1-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="2dee1-113">Microsoft Exchange Server 2010 oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="2dee1-113">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="2dee1-114">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dee1-114">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2dee1-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2dee1-115">In This Section</span></span>

  - [<span data-ttu-id="2dee1-116">Features integrierter Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dee1-116">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="2dee1-117">Komponenten und Topologien für lokale Unified Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dee1-117">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="2dee1-118">Richtlinien für die Integration von lokalen Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dee1-118">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="2dee1-119">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dee1-119">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

