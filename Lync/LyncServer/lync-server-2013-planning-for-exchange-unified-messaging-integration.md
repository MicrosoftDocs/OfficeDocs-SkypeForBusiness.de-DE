---
title: 'Lync Server 2013: Planen der Integration von Exchange Unified Messaging'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de7f3bc9a3e8a1330fc1a142c491e22a4407f104
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="0489e-102">Planen der Integration von Exchange Unified Messaging in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0489e-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0489e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="0489e-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="0489e-104">Lync Server 2013 unterstützt die Integration in Exchange Unified Messaging (um) zum Kombinieren von Voicemail und e-Mail-Messaging in einer einzelnen Messaginginfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="0489e-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="0489e-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) und Microsoft Exchange Server 2010 ist Exchange Unified Messaging (um) eine von mehreren Exchange-Serverfunktionen, die Sie installieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="0489e-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="0489e-106">In Microsoft Exchange Server 2013 wird Exchange um als Dienst auf einem Exchange-Post Fach Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0489e-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="0489e-107">Bei lync Server 2013 Enterprise-VoIP-Bereitstellungen kombiniert Unified Messaging Voicemail und e-Mail-Nachrichten in einem einzigen Speicher, der über ein Telefon (Outlook Voice Access) oder einen Computer zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="0489e-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="0489e-108">Unified Messaging und lync Server 2013 arbeiten gemeinsam an der Bereitstellung von Anrufbeantwortung, Outlook Voice Access und automatischen Telefonzentralen Diensten für Benutzer von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="0489e-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="0489e-109">Weitere Informationen zu den Architekturänderungen in Microsoft Exchange Server 2013 finden Sie unter "Änderungen der Spracharchitektur" in der Microsoft Exchange Server 2013- [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730)Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="0489e-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="0489e-110">Damit diese Features in einer lokalen Exchange um-Bereitstellung unterstützt werden, müssen Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="0489e-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="0489e-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="0489e-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="0489e-112">Microsoft Exchange Server 2010 oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="0489e-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="0489e-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0489e-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0489e-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0489e-114">In This Section</span></span>

  - [<span data-ttu-id="0489e-115">Features von integriertem Unified Messaging und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0489e-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="0489e-116">Komponenten und Topologien für lokales Unified Messaging in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0489e-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="0489e-117">Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0489e-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="0489e-118">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0489e-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

