---
title: 'Lync Server 2013: Überprüfen der physikalischen Umgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17905a8cd379e5fe2b97b494a00b37a181541900
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="3cf76-102">Durchführen von physikalischen Umgebungsprüfungen</span><span class="sxs-lookup"><span data-stu-id="3cf76-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf76-103">_**Letztes Änderungsstand des Themas:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="3cf76-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="3cf76-104">Bevor Sie die Leistung, die Verfügbarkeit und die Funktionalität der lync Server 2013-Bereitstellung überprüfen, sollten Sie die physische Umgebung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3cf76-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="3cf76-105">Beispielsweise muss die Serverraum Temperatur möglicherweise gesenkt werden, oder es muss ein Netzwerkkabel ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3cf76-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="3cf76-106">Um optimale Ergebnisse zu erzielen, führen Sie die folgenden physikalischen Umgebungs Inspektionen durch:</span><span class="sxs-lookup"><span data-stu-id="3cf76-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="3cf76-107">**Physikalische Sicherheitsmaßnahmen**   der physische Sicherheitsschutz wie Schleusen, Türen und eingeschränkte Zugriffs Räume müssen gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="3cf76-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="3cf76-108">Überprüfen Sie, ob sich Personen ohne Autorisierung oder gewaltsame Zutritt verschafft haben oder ob Anzeichen für eine Beschädigung der Ausrüstung vorliegen.</span><span class="sxs-lookup"><span data-stu-id="3cf76-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="3cf76-109">**Temperatur und Feuchtigkeit**   hohe Temperaturen, schlechter Luftstrom und Feuchtigkeit können dazu führen, dass Hardwarekomponenten überhitzt werden.</span><span class="sxs-lookup"><span data-stu-id="3cf76-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="3cf76-110">Überprüfen Sie die Temperatur und Luftfeuchtigkeit, um sicherzustellen, dass die Umgebungssysteme wie Heizung und Klimatisierung akzeptable Bedingungen und Funktionen innerhalb der Hardwarehersteller Spezifikationen aufrecht erhalten können.</span><span class="sxs-lookup"><span data-stu-id="3cf76-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="3cf76-111">Wenn neue Geräte kürzlich installiert wurden, überprüfen Sie auch, ob der Luftstrom sowohl von als auch von den Servern ungehindert ist und die Herstellerspezifikation erfüllt.</span><span class="sxs-lookup"><span data-stu-id="3cf76-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="3cf76-112">**Geräte und Komponenten**   die lync Server 2013 Organisation setzt auf ein funktionierendes physisches Netzwerk und zugehörige Hardware.</span><span class="sxs-lookup"><span data-stu-id="3cf76-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="3cf76-113">Stellen Sie sicher, dass Router, Switches, Hubs, physische Kabel und Connectors betriebsbereit sind.</span><span class="sxs-lookup"><span data-stu-id="3cf76-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="3cf76-114">Die Besonderheiten bei der Durchführung dieser Prüfungen hängen stark von Ihrer Installations Website und der ausgewählten Server Hardware ab.</span><span class="sxs-lookup"><span data-stu-id="3cf76-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="3cf76-115">Wenn Sie diese Prüfung zum ersten Mal durchführen, lesen Sie die Hardwaredokumentation, und beachten Sie die gewünschten Parameter für die spätere Verwendung.</span><span class="sxs-lookup"><span data-stu-id="3cf76-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="3cf76-116">Gewünschte Serverraum Umgebung</span><span class="sxs-lookup"><span data-stu-id="3cf76-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cf76-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="3cf76-117">Parameter</span></span></th>
<th><span data-ttu-id="3cf76-118">Gewünschter Wert oder Bereich</span><span class="sxs-lookup"><span data-stu-id="3cf76-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cf76-119">Temperatur</span><span class="sxs-lookup"><span data-stu-id="3cf76-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf76-120">Luftfeuchtigkeits</span><span class="sxs-lookup"><span data-stu-id="3cf76-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cf76-121">Front of Server Faces</span><span class="sxs-lookup"><span data-stu-id="3cf76-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="3cf76-122">Hot Aisle/Cold Aisle</span><span class="sxs-lookup"><span data-stu-id="3cf76-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cf76-123">Ungehinderter Abgas Abstand</span><span class="sxs-lookup"><span data-stu-id="3cf76-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

