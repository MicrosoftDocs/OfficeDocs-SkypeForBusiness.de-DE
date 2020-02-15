---
title: 'Lync Server 2013: Übersetzungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16623d863e9ca4a252ad7249ba1933cfa6934b08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="a4b08-102">Übersetzungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b08-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4b08-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a4b08-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a4b08-104">Für lync Server 2013 Enterprise-VoIP müssen alle Wählzeichenfolgen zum E. 164-Format normalisiert werden, um eine rückwärts Nummernsuche (können) durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a4b08-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="a4b08-105">In Microsoft lync Server 2010 werden Übersetzungsregeln nur für benannte Nummern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4b08-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="a4b08-106">Neu in Microsoft lync Server 2013 werden Übersetzungsregeln auch für Rufnummern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4b08-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="a4b08-107">Der *Trunkpeer* (also das zugeordnete Gateway, die Nebenstellenanlage (Private Branch Exchange (PBX) oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a4b08-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="a4b08-108">Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird.</span><span class="sxs-lookup"><span data-stu-id="a4b08-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="a4b08-109">Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="a4b08-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="a4b08-110">Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren.</span><span class="sxs-lookup"><span data-stu-id="a4b08-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="a4b08-111">Wenn Sie planen, welche Gateways und wie viele Gateways einem bestimmten Vermittlungsserver Cluster zugeordnet werden sollen, kann es hilfreich sein, trunk-Peers mit ähnlichen lokalen wählanforderungen zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="a4b08-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="a4b08-112">Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.</span><span class="sxs-lookup"><span data-stu-id="a4b08-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4b08-113">Das Zuordnen einer oder mehrerer Übersetzungsregeln zu einer Enterprise-VoIP-trunk-Konfiguration sollte als Alternative zum Konfigurieren von Übersetzungsregeln für den trunk-Peer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4b08-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="a4b08-114">Ordnen Sie Übersetzungsregeln nicht einer Enterprise-VoIP-trunkkonfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise einen Konflikt verursachen.</span><span class="sxs-lookup"><span data-stu-id="a4b08-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="a4b08-115">Beispielübersetzungsregeln</span><span class="sxs-lookup"><span data-stu-id="a4b08-115">Example Translation Rules</span></span>

<span data-ttu-id="a4b08-116">Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="a4b08-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="a4b08-117">Ausführliche Informationen zur Implementierung von Übersetzungsregeln finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a4b08-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="a4b08-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4b08-118">Description</span></span></th>
<th><span data-ttu-id="a4b08-119">Anfangsziffern</span><span class="sxs-lookup"><span data-stu-id="a4b08-119">Starting Digits</span></span></th>
<th><span data-ttu-id="a4b08-120">Länge</span><span class="sxs-lookup"><span data-stu-id="a4b08-120">Length</span></span></th>
<th><span data-ttu-id="a4b08-121">Zu entfernende Ziffern</span><span class="sxs-lookup"><span data-stu-id="a4b08-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="a4b08-122">Hinzuzufügende Ziffern</span><span class="sxs-lookup"><span data-stu-id="a4b08-122">Digits to Add</span></span></th>
<th><span data-ttu-id="a4b08-123">Vergleichsmuster</span><span class="sxs-lookup"><span data-stu-id="a4b08-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="a4b08-124">Translation</span><span class="sxs-lookup"><span data-stu-id="a4b08-124">Translation</span></span></th>
<th><span data-ttu-id="a4b08-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4b08-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4b08-126">Normales Ferngespräch in den USA</span><span class="sxs-lookup"><span data-stu-id="a4b08-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="a4b08-127">(Entfernen des Pluszeichens "+")</span><span class="sxs-lookup"><span data-stu-id="a4b08-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="a4b08-128">+1</span><span class="sxs-lookup"><span data-stu-id="a4b08-128">+1</span></span></p></td>
<td><p><span data-ttu-id="a4b08-129">Exakt 12</span><span class="sxs-lookup"><span data-stu-id="a4b08-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="a4b08-130">1 </span><span class="sxs-lookup"><span data-stu-id="a4b08-130">1</span></span></p></td>
<td><p><span data-ttu-id="a4b08-131">0</span><span class="sxs-lookup"><span data-stu-id="a4b08-131">0</span></span></p></td>
<td><p><span data-ttu-id="a4b08-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a4b08-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="a4b08-133">$1</span><span class="sxs-lookup"><span data-stu-id="a4b08-133">$1</span></span></p></td>
<td><p><span data-ttu-id="a4b08-134">+14255551010 wird zu 14255551010</span><span class="sxs-lookup"><span data-stu-id="a4b08-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b08-135">Internationales Ferngespräch aus den USA</span><span class="sxs-lookup"><span data-stu-id="a4b08-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="a4b08-136">(Entfernen des Pluszeichens "+" und Hinzufügen von 011)</span><span class="sxs-lookup"><span data-stu-id="a4b08-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="a4b08-137">Mindestens 11</span><span class="sxs-lookup"><span data-stu-id="a4b08-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="a4b08-138">1 </span><span class="sxs-lookup"><span data-stu-id="a4b08-138">1</span></span></p></td>
<td><p><span data-ttu-id="a4b08-139">011</span><span class="sxs-lookup"><span data-stu-id="a4b08-139">011</span></span></p></td>
<td><p><span data-ttu-id="a4b08-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="a4b08-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="a4b08-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="a4b08-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="a4b08-142">+441235551010 wird zu 011441235551010</span><span class="sxs-lookup"><span data-stu-id="a4b08-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

