---
title: 'Lync Server 2013: Übersetzungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="bf53b-102">Übersetzungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf53b-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf53b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="bf53b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bf53b-104">Für lync Server 2013 Enterprise-VoIP müssen alle Wählzeichenfolgen im E. 164-Format normalisiert werden, um RNL (Reverse Number Lookup) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="bf53b-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="bf53b-105">In Microsoft lync Server 2010 werden Übersetzungsregeln nur für benannte Nummern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bf53b-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="bf53b-106">Neu in Microsoft lync Server 2013 werden Übersetzungsregeln auch für Rufnummern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bf53b-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="bf53b-107">Der *Trunkpeer* (also das zugeordnete Gateway, die Nebenstellenanlage (Private Branch Exchange (PBX) oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen.</span><span class="sxs-lookup"><span data-stu-id="bf53b-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="bf53b-108">Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird.</span><span class="sxs-lookup"><span data-stu-id="bf53b-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="bf53b-109">Sie können beispielsweise eine Übersetzungsregel erstellen, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="bf53b-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="bf53b-110">Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren.</span><span class="sxs-lookup"><span data-stu-id="bf53b-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="bf53b-111">Wenn Sie planen, welche Gateways und wie viele Gateways einem bestimmten Vermittlungs Server Cluster zugeordnet werden sollen, kann es hilfreich sein, trunk-Peers mit ähnlichen lokalen wählanforderungen zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="bf53b-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="bf53b-112">Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.</span><span class="sxs-lookup"><span data-stu-id="bf53b-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bf53b-113">Das Zuordnen einer oder mehrerer Übersetzungsregeln zu einer Enterprise Voice trunk-Konfiguration sollte als Alternative zum Konfigurieren von Übersetzungsregeln für den trunk-Peer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bf53b-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="bf53b-114">Ordnen Sie Übersetzungsregeln keiner Enterprise-VoIP-trunk-Konfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="bf53b-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="bf53b-115">Beispielübersetzungsregeln</span><span class="sxs-lookup"><span data-stu-id="bf53b-115">Example Translation Rules</span></span>

<span data-ttu-id="bf53b-116">Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="bf53b-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="bf53b-117">Ausführliche Informationen zum Implementieren von Übersetzungsregeln finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bf53b-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf53b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf53b-118">Description</span></span></th>
<th><span data-ttu-id="bf53b-119">Anfangsziffern</span><span class="sxs-lookup"><span data-stu-id="bf53b-119">Starting Digits</span></span></th>
<th><span data-ttu-id="bf53b-120">Länge</span><span class="sxs-lookup"><span data-stu-id="bf53b-120">Length</span></span></th>
<th><span data-ttu-id="bf53b-121">Zu entfernende Ziffern</span><span class="sxs-lookup"><span data-stu-id="bf53b-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="bf53b-122">Hinzuzufügende Ziffern</span><span class="sxs-lookup"><span data-stu-id="bf53b-122">Digits to Add</span></span></th>
<th><span data-ttu-id="bf53b-123">Vergleichsmuster</span><span class="sxs-lookup"><span data-stu-id="bf53b-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="bf53b-124">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="bf53b-124">Translation</span></span></th>
<th><span data-ttu-id="bf53b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf53b-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf53b-126">Normales Ferngespräch in den USA</span><span class="sxs-lookup"><span data-stu-id="bf53b-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="bf53b-127">(Entfernen des Pluszeichens „+“)</span><span class="sxs-lookup"><span data-stu-id="bf53b-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="bf53b-128">+1</span><span class="sxs-lookup"><span data-stu-id="bf53b-128">+1</span></span></p></td>
<td><p><span data-ttu-id="bf53b-129">Exakt 12</span><span class="sxs-lookup"><span data-stu-id="bf53b-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="bf53b-130">1</span><span class="sxs-lookup"><span data-stu-id="bf53b-130">1</span></span></p></td>
<td><p><span data-ttu-id="bf53b-131">0</span><span class="sxs-lookup"><span data-stu-id="bf53b-131">0</span></span></p></td>
<td><p><span data-ttu-id="bf53b-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="bf53b-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="bf53b-133">$1</span><span class="sxs-lookup"><span data-stu-id="bf53b-133">$1</span></span></p></td>
<td><p><span data-ttu-id="bf53b-134">+14255551010 wird zu 14255551010</span><span class="sxs-lookup"><span data-stu-id="bf53b-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf53b-135">Internationales Ferngespräch aus den USA</span><span class="sxs-lookup"><span data-stu-id="bf53b-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="bf53b-136">(Entfernen des Pluszeichens „+“ und Hinzufügen von 011)</span><span class="sxs-lookup"><span data-stu-id="bf53b-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="bf53b-137">Mindestens 11</span><span class="sxs-lookup"><span data-stu-id="bf53b-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="bf53b-138">1</span><span class="sxs-lookup"><span data-stu-id="bf53b-138">1</span></span></p></td>
<td><p><span data-ttu-id="bf53b-139">011</span><span class="sxs-lookup"><span data-stu-id="bf53b-139">011</span></span></p></td>
<td><p><span data-ttu-id="bf53b-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="bf53b-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="bf53b-141">011$1</span><span class="sxs-lookup"><span data-stu-id="bf53b-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="bf53b-142">+441235551010 wird zu 011441235551010</span><span class="sxs-lookup"><span data-stu-id="bf53b-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

