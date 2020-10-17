---
title: 'Phase 10: decommission Legacy Site'
description: 'Phase 10: decommission Legacy Site.'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9692301a1da38cfd69780ce2524f00dd428454e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571201"
---
# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="1444c-103">Phase 10: decommission Legacy Site</span><span class="sxs-lookup"><span data-stu-id="1444c-103">Phase 10: Decommission legacy site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1444c-104">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="1444c-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="1444c-105">Die folgenden Themen bieten Anleitungen für Außerbetriebnahme-Pools und das Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung von Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1444c-105">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1444c-106">Es sind nicht alle der in diesem Abschnitt aufgeführten Verfahren notwendig.</span><span class="sxs-lookup"><span data-stu-id="1444c-106">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="1444c-107">Lesen Sie die Informationen in den einzelnen Themen, um das Verfahren zu bestimmen, das Sie für die Außerbetriebsetzung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1444c-107">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1444c-108">Wenn Sie Konferenzverzeichnisse für Einwahlkonferenzen in lync Server 2013 importiert haben, ist es wichtig, den Besitz des Konferenz Verzeichnisses auf lync Server 2013 zu übertragen, bevor Sie mit der Außerbetriebnahme ihrer Pools beginnen.</span><span class="sxs-lookup"><span data-stu-id="1444c-108">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="1444c-109">Wenn Sie einen Pool außer Betrieb setzen, ohne zuerst den Besitz für Konferenzverzeichnisse zu übergeben, wird die Einwahlfunktion für alle migrierten Besprechungen nicht weiter ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1444c-109">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="1444c-110">Der Übergang des Besitzes muss für jedes Konferenzverzeichnis in Ihrem Pool der Vorversion durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1444c-110">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1444c-111">Informationen zum Migrieren und aktualisieren verwaltete API von Microsoft Unified Communications (UCMA) Anwendungen vor dem Stillsetzen ihrer Vorgänger Umgebung finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="1444c-111">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1444c-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1444c-112">In This Section</span></span>

  - [<span data-ttu-id="1444c-113">Migrieren von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="1444c-113">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="1444c-114">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="1444c-114">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - [<span data-ttu-id="1444c-115">Außerbetriebnahme von Servern und Pools</span><span class="sxs-lookup"><span data-stu-id="1444c-115">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="1444c-116">Entfernen von "BackCompatSite"</span><span class="sxs-lookup"><span data-stu-id="1444c-116">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

