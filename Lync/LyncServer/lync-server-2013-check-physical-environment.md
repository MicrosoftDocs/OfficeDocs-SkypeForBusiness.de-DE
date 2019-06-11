---
title: 'Lync Server 2013: Überprüfen der physikalischen Umgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07335046dc4b37d0e5327ded0a12293657f5fe43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="51e1a-102">Durchführen physischer Umgebungsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="51e1a-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e1a-103">_**Letztes Änderungsdatum des Themas:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="51e1a-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="51e1a-104">Bevor Sie die Leistung, Verfügbarkeit und Funktionalität der lync Server 2013-Bereitstellung überprüfen, sollten Sie die physikalische Umgebung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="51e1a-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="51e1a-105">Beispielsweise muss die Temperatur des Serverraums gesenkt werden, oder es muss ein Netzwerkkabel ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="51e1a-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="51e1a-106">Um optimale Ergebnisse zu erzielen, führen Sie die folgenden physikalischen Umweltinspektionen durch:</span><span class="sxs-lookup"><span data-stu-id="51e1a-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="51e1a-107">**Physische Sicherheit misst**   physischer Sicherheitsschutz wie Sperren, Türen und eingeschränkte Zugriffs Räume müssen gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="51e1a-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="51e1a-108">Überprüfen Sie, ob unbefugte und erzwungene Einträge und Anzeichen von Geräteschäden auftreten.</span><span class="sxs-lookup"><span data-stu-id="51e1a-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="51e1a-109">**Temperatur und Feuchtigkeit**   hohe Temperaturen, schlechte Luftzirkulation und Feuchtigkeit können dazu führen, dass Hardwarekomponenten überhitzt werden.</span><span class="sxs-lookup"><span data-stu-id="51e1a-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="51e1a-110">Überprüfen Sie Temperatur und Luftfeuchtigkeit, um sicherzustellen, dass die Umweltsysteme wie Heizung und Klimatisierung akzeptable Bedingungen und Funktionen in den Spezifikationen des Hardwareherstellers aufrecht erhalten können.</span><span class="sxs-lookup"><span data-stu-id="51e1a-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="51e1a-111">Wenn neue Geräte vor kurzem installiert wurden, prüfen Sie auch, ob der Luftstrom sowohl von als auch von den Servern ungehindert ist und die Herstellerspezifikation erfüllt.</span><span class="sxs-lookup"><span data-stu-id="51e1a-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="51e1a-112">**Geräte und Komponenten**   die lync Server 2013-Organisation setzt auf ein funktionierendes physisches Netzwerk und die zugehörige Hardware.</span><span class="sxs-lookup"><span data-stu-id="51e1a-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="51e1a-113">Stellen Sie sicher, dass Router, Switches, Hubs, physikalische Kabel und Verbinder funktionsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="51e1a-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="51e1a-114">Die Einzelheiten zur Durchführung dieser Prüfungen hängen stark von Ihrer Installations Website und der ausgewählten Server Hardware ab.</span><span class="sxs-lookup"><span data-stu-id="51e1a-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="51e1a-115">Wenn Sie diese Prüfung zum ersten Mal durchführen, lesen Sie die Hardwaredokumentation, und notieren Sie sich die gewünschten Parameter für die spätere Verwendung.</span><span class="sxs-lookup"><span data-stu-id="51e1a-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="51e1a-116">Gewünschte Serverraum Umgebung</span><span class="sxs-lookup"><span data-stu-id="51e1a-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51e1a-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="51e1a-117">Parameter</span></span></th>
<th><span data-ttu-id="51e1a-118">Gewünschter Wert oder Bereich</span><span class="sxs-lookup"><span data-stu-id="51e1a-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51e1a-119">Temperatur</span><span class="sxs-lookup"><span data-stu-id="51e1a-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e1a-120">Feuchtigkeit</span><span class="sxs-lookup"><span data-stu-id="51e1a-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e1a-121">Front of Server Faces</span><span class="sxs-lookup"><span data-stu-id="51e1a-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="51e1a-122">Hot-Aisle/Cold-Aisle</span><span class="sxs-lookup"><span data-stu-id="51e1a-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e1a-123">Ungehinderte Abgas Freigabe</span><span class="sxs-lookup"><span data-stu-id="51e1a-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

