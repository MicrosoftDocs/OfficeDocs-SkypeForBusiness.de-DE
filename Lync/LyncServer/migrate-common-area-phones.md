---
title: Migrieren von Telefonen für gemeinsame Bereiche
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="e7dbc-102">Migrieren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="e7dbc-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7dbc-103">_**Letztes Änderungsdatum des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="e7dbc-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="e7dbc-104">Telefone im öffentlichen Bereich sind IP-Telefone, die sich am häufigsten in einem freigegebenen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, beispielsweise in einer Lobby, einer Küche oder einem Factory-Stockwerk.</span><span class="sxs-lookup"><span data-stu-id="e7dbc-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="e7dbc-105">Telefone im öffentlichen Bereich müssen nicht mit einem Computer verbunden sein, um die lync Server UC-Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7dbc-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="e7dbc-106">Nachdem Sie eine lync Server 2010-Bereitstellung zu lync Server 2013 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die mit dem Legacy-Telefon des öffentlichen Bereichs verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="e7dbc-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="e7dbc-107">Mithilfe der lync Server-Verwaltungsshell rufen Sie zunächst alle Kontaktobjekte ab, die mit den Telefonen des lync Server 2010-common areas verknüpft sind, und verschieben diese Objekte dann in den lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="e7dbc-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="e7dbc-108">**Migrieren von Telefonen für gemeinsame Bereiche**</span><span class="sxs-lookup"><span data-stu-id="e7dbc-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="e7dbc-109">Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e7dbc-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e7dbc-110">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7dbc-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="e7dbc-111">Um zu überprüfen, ob alle Kontaktobjekte in den lync Server 2013-Pool verschoben wurden, geben Sie aus der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7dbc-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="e7dbc-112">Überprüfen Sie, ob alle Kontaktobjekte jetzt dem lync Server 2013-Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e7dbc-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

