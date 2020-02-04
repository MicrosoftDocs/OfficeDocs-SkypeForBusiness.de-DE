---
title: 'Phase 10: Legacy Website der decommission'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="81798-102">Phase 10: Legacy Website der decommission</span><span class="sxs-lookup"><span data-stu-id="81798-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81798-103">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="81798-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="81798-104">In den folgenden Themen finden Sie Anleitungen zur Außerbetriebnahme von Pools sowie zum Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung von Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81798-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="81798-105">Nicht alle in diesem Abschnitt aufgelisteten Verfahren sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81798-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="81798-106">Lesen Sie die Informationen in jedem dieser Themen, um zu ermitteln, welches Verfahren für die Außerbetriebnahme verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81798-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="81798-107">Wenn Sie Konferenzverzeichnisse für Einwahlkonferenzen in lync Server 2013 importiert haben, ist es wichtig, den Besitz von Konferenz Verzeichnissen zu lync Server 2013 zu übertragen, bevor Sie mit der Außerbetriebnahme ihrer Pools beginnen.</span><span class="sxs-lookup"><span data-stu-id="81798-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="81798-108">Wenn Sie einen Pool außer Betrieb nehmen, ohne zuerst den Besitzer des Konferenz Verzeichnisses zu übertragen, funktioniert das Einwahlfeature für alle migrierten Besprechungen nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="81798-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="81798-109">Sie müssen den Schritt zum Übergangs Besitz einmal für jedes Konferenzverzeichnis in Ihrem Legacy Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="81798-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="81798-110">Informationen zum Migrieren und Aktualisieren von Microsoft Unified Communications Managed API-Anwendungen (UCMA) vor der Außerbetriebnahme ihrer Legacyumgebung finden Sie unter<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="81798-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81798-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81798-111">In This Section</span></span>

  - [<span data-ttu-id="81798-112">Verschieben von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="81798-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="81798-113">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="81798-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="81798-114">Außerbetriebnahme von Servern und Pools</span><span class="sxs-lookup"><span data-stu-id="81798-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="81798-115">Entfernen von BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="81798-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

