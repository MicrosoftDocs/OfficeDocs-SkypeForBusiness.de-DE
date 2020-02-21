---
title: 'Lync Server 2013: Überprüfen der Normalisierung und des Routings von VoIP-Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f9cd0beea65cfb1718fea3bc1c0235eb7554ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="6241f-102">Überprüfen der Normalisierung und des Routings von sprach Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6241f-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6241f-103">_**Letztes Änderungsstand des Themas:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="6241f-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="6241f-104">Die richtige Normalisierung und Weiterleitung von Nummern ist für eine funktionale Enterprise-VoIP-Umgebung sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="6241f-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="6241f-105">Vor allem bei Migrationen von einer Nebenstellenanlage zur eigenständigen lync Server Umgebung ist einer der Schlüssel für eine erfolgreiche Migration das aufdecken und dokumentieren aller vorhandenen Wählregeln sowie das Erstellen geeigneter Normalisierungsregeln, VoIP-Richtlinien, Telefonverwendungen und-Routen.</span><span class="sxs-lookup"><span data-stu-id="6241f-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="6241f-106">Das Validieren von Nummern Normalisierung und-Routing ist nicht nur bei Migrationen wichtig, sondern auch während eines normalen, stabilen Betriebs des Systems.</span><span class="sxs-lookup"><span data-stu-id="6241f-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="6241f-107">Es wird empfohlen, diese Überprüfung täglich mithilfe der lync Server-Systemsteuerung durchzuführen, beginnend mit der Entwicklung einer robusten Reihe von Testfällen für den aktuellen Satz von Normalisierungsregeln, die in den lync Server globalen Einstellungen veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="6241f-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="6241f-108">Diese Testfälle sollten täglich ausgeführt werden, um unerwünschte Änderungen hervorzuheben, die für die Wähleinstellungen vorgenommen wurden und für die ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6241f-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="6241f-109">Lync Server-Systemsteuerung unterstützt Sie auch beim visualisieren, testen, ändern, archivieren und Freigeben von Konfigurationsinformationen für das VoIP-Routing sowie beim Ändern von Normalisierungsregeln für Enterprise-VoIP,-Wählpläne,-VoIP-Richtlinien und-Routen.</span><span class="sxs-lookup"><span data-stu-id="6241f-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="6241f-110">Es verfügt über zusätzliche Funktionen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6241f-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="6241f-111">Exportieren und importieren oder Sichern von VoIP-Routingdaten zwischen Systemen.</span><span class="sxs-lookup"><span data-stu-id="6241f-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="6241f-112">Testen von Konfigurationsänderungen vor dem Hochladen auf ein Live-System.</span><span class="sxs-lookup"><span data-stu-id="6241f-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="6241f-113">Erstellen und Ausführen von Konfigurations Testfälle, um die Verwendbarkeit von Routingdaten zu gewährleisten, nachdem Sie Änderungen daran vorgenommen haben, aber bevor Sie die Änderungen an einem bereitgestellten System vornehmen.</span><span class="sxs-lookup"><span data-stu-id="6241f-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="6241f-114">Erstellen und Ändern von Nummern Normalisierungsregeln, Standortprofilen, VoIP-Richtlinien und Routingdaten, ohne die erforderlichen regulären Ausdrücke zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="6241f-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="6241f-115">Analysieren eines Standortprofils zur Kompatibilität mit dem lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="6241f-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="6241f-116">Weitere Informationen zu VoIP-Routing Tests finden Sie unter [Test Voice Routing in lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="6241f-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6241f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6241f-117">See Also</span></span>


[<span data-ttu-id="6241f-118">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6241f-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

