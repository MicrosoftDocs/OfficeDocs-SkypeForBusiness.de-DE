---
title: Migireren von Telefonen für gemeinsame Bereiche
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138068c73264ded3483d8d9f0902d403833a306d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="5b720-102">Migireren von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="5b720-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b720-103">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5b720-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5b720-104">Telefone in öffentlichen Bereichen sind IP-Telefone, die sich am häufigsten in einem gemeinsamen Arbeitsbereich oder in einem gemeinsamen Bereich befinden, wie beispielsweise eine Lobby, eine Küche oder ein Factory Floor.</span><span class="sxs-lookup"><span data-stu-id="5b720-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="5b720-105">Telefone für gemeinsame Bereiche müssen nicht mit einem Computer verbunden sein, um lync Server UC-Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5b720-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="5b720-106">Nachdem Sie eine lync Server 2010-Bereitstellung in lync Server 2013 migriert haben, müssen Sie auch die Kontaktobjekte migrieren, die dem Legacy-Telefon für gemeinsame Bereiche zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5b720-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="5b720-107">Mit lync Server-Verwaltungsshell werden zunächst alle Contact-Objekte abgerufen, lync Server 2010 die mit den Telefonen für gemeinsame Bereiche verbunden sind, und diese Objekte dann in den lync Server 2013-Pool zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="5b720-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="5b720-108">**Migrieren von Telefonen für gemeinsame Bereiche**</span><span class="sxs-lookup"><span data-stu-id="5b720-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="5b720-109">Öffnen Sie auf dem lync Server 2013-Front-End-Server lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="5b720-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="5b720-110">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5b720-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="5b720-111">Um zu überprüfen, ob alle Kontaktobjekte in den lync Server 2013 Pool verschoben wurden, geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5b720-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="5b720-112">Überprüfen Sie, ob jetzt alle Contact-Objekte dem lync Server 2013-Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5b720-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

