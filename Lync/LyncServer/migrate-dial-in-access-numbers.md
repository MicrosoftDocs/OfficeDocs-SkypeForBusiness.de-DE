---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaef027180304fca2a64294177faffcc0811e565
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="ebbe1-102">Migrieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="ebbe1-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebbe1-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ebbe1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ebbe1-104">Das Migrieren der Kontaktobjekte erfordert das Ausführen des Cmdlets " **CsApplicationEndpoint** ", um die Zugriffsnummern für die Einwahl von lync Server 2010 auf lync Server 2013 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="ebbe1-105">Während des Zeitraums für lync Server 2010 und lync Server 2013 Koexistenz Verhalten sich Einwahlnummern, die Sie in lync Server 2013 erstellt haben, entsprechend den in diesem Abschnitt beschriebenen Zugriffsnummern für Einwahlen, die Sie in lync Server 2010 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="ebbe1-106">Einwahlnummern, die Sie in lync Server 2010 erstellt, aber in lync Server 2013 verschoben haben oder die Sie in lync Server 2013 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="ebbe1-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="ebbe1-107">Sie werden nicht in Office Communications Server 2007 R2-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="ebbe1-108">Sie werden in Lync Server 2010-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="ebbe1-109">Sie werden in Lync Server 2013-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="ebbe1-110">Sie können nicht im Verwaltungstool von Office Communications Server 2007 R2 angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="ebbe1-111">Sie können in der Lync Server 2010-Systemsteuerung und in der Lync Server 2010-Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="ebbe1-112">Sie können in der Lync Server 2013-Systemsteuerung und in der Lync Server 2013-Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="ebbe1-113">Sie können innerhalb des Bereichs durch Verwendung des Set-CsDialinConferencingAccessNumber-Cmdlets mit dem Priority-Parameter neu sequenziert werden.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="ebbe1-p102">Sie müssen die Migration von Einwahlnummern abschließen, die auf einen Lync Server 2010-Pool verweisen, bevor Sie den Lync Server 2010-Pool außer Betrieb nehmen. Wenn Sie die Migration von Einwahlnummern nicht wie im folgenden Verfahren beschrieben abschließen, schlagen eingehende Anrufe an die Einwahlnummern fehl.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-p102">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool. If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ebbe1-116">Sie müssen dieses Verfahren vor der Außerbetriebnahme des lync Server 2010 Pools ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ebbe1-117">Wir empfehlen, das Verschieben von Einwahlen zu einem Zeitpunkt vorzunehmen, zu dem die Netzwerkauslastung möglichst gering ist, für den Fall, dass es zu einem kurzen Dienstausfall kommt.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="ebbe1-118">**So identifizieren und verschieben Sie Einwahlnummern**</span><span class="sxs-lookup"><span data-stu-id="ebbe1-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="ebbe1-119">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ebbe1-120">Um jede Zugriffsnummer für die Einwahl in einen Pool zu migrieren, der auf lync Server 2013 gehostet wird, führen Sie über die Befehlszeile Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ebbe1-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="ebbe1-121">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="ebbe1-122">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="ebbe1-123">Klicken Sie auf die Registerkarte **Einwahlnummer**.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="ebbe1-124">Stellen Sie sicher, dass keine Einwahlnummern für den lync Server 2010 Pool verbleiben, von dem Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebbe1-125">Wenn alle Zugriffsnummern für Einwahlen auf den lync Server 2013 Pool deuten, können Sie den lync Server 2010-Pool außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="ebbe1-126">**Überprüfen der Migration der Einwahlnummern mithilfe der Lync Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="ebbe1-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="ebbe1-127">Melden Sie sich mit einem Benutzerkonto, dem die Rolle **CsUserAdministrator** oder **CsAdministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ebbe1-128">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="ebbe1-129">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="ebbe1-130">Klicken Sie auf die Registerkarte **Einwahlnummer**.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="ebbe1-131">Vergewissern Sie sich, dass alle Einwahlnummern zu dem auf lync Server 2013 gehosteten Pool migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="ebbe1-132">**Überprüfen der Migration der Einwahlnummern mithilfe der Lync Server-Verwaltungsshell**</span><span class="sxs-lookup"><span data-stu-id="ebbe1-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="ebbe1-133">Öffnen Sie lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ebbe1-134">Um alle migrierten Einwahlnummern für Konferenzen zurückzugeben, führen Sie an der Befehlszeile folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ebbe1-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="ebbe1-135">Überprüfen Sie, ob alle Einwahlnummern zu dem auf lync Server 2013 gehosteten Pool migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ebbe1-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

