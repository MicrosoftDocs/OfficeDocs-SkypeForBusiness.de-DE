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
ms.openlocfilehash: 0638ae76a9aa1108b11c1d1ff98fdd3eef08c938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="a3882-102">Migrieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="a3882-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3882-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a3882-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a3882-104">Zum Migrieren der Kontaktobjekte muss das Cmdlet **Move-CsApplicationEndpoint** ausgeführt werden, um die Einwahl Zugriffsnummern von lync Server 2010 auf lync Server 2013 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="a3882-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="a3882-105">Während des koexistenzbereichs lync Server 2010 und lync Server 2013 Verhalten sich die in lync Server 2013 erstellten Einwahl Zugriffsnummern ähnlich wie die Einwahl Zugriffsnummern, die Sie in lync Server 2010 erstellen, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3882-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="a3882-106">Einwahl Zugriffsnummern, die Sie in lync Server 2010 erstellt, aber nach lync Server 2013 verschoben haben oder die Sie in lync Server 2013 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="a3882-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="a3882-107">Sie werden nicht auf Office Communications Server 2007 R2-Besprechungseinladungen und auf der Seite Einwahl Zugriffsnummer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3882-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a3882-108">In lync Server 2010-Besprechungseinladungen und auf der Seite "Einwahl Zugriffsnummer" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3882-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a3882-109">In lync Server 2013-Besprechungseinladungen und auf der Seite "Einwahl Zugriffsnummer" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3882-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a3882-110">Kann im Office Communications Server 2007 R2-Verwaltungstool nicht angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a3882-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="a3882-111">Kann in der lync Server 2010-Systemsteuerung und in der lync Server 2010-Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a3882-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="a3882-112">Kann in der lync Server 2013-Systemsteuerung und in der lync Server 2013-Verwaltungsshell angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a3882-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="a3882-113">Kann innerhalb des Bereichs mithilfe des Cmdlets "CsDialinConferencingAccessNumber" mit dem Priority-Parameter neu sequenziert werden.</span><span class="sxs-lookup"><span data-stu-id="a3882-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="a3882-114">Sie müssen die Migration von Einwahl Zugriffsnummern beenden, die auf einen lync Server 2010-Pool verweisen, bevor Sie den lync Server 2010-Pool außer Betrieb bringen.</span><span class="sxs-lookup"><span data-stu-id="a3882-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="a3882-115">Wenn Sie die Migration von Einwahlnummern wie im folgenden Verfahren beschrieben nicht abschließen, treten bei eingehenden Anrufen an die Zugriffsnummern keine Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="a3882-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3882-116">Sie müssen dieses Verfahren vor der Außerbetriebnahme des lync Server 2010-Pools ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3882-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a3882-117">Es wird empfohlen, Einwahlnummern zu verschieben, wenn die Netzwerkauslastung gering ist, falls es einen kurzen Zeitraum für einen Ausfall des Diensts gibt.</span><span class="sxs-lookup"><span data-stu-id="a3882-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="a3882-118">**So identifizieren und verschieben Sie Einwahl Zugriffsnummern**</span><span class="sxs-lookup"><span data-stu-id="a3882-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="a3882-119">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a3882-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a3882-120">Wenn Sie jede Einwahl Zugriffsnummer in einen Pool verschieben möchten, der auf lync Server 2013 gehostet wird, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a3882-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="a3882-121">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a3882-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="a3882-122">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="a3882-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="a3882-123">Klicken Sie auf die Registerkarte **Einwahlnummer** .</span><span class="sxs-lookup"><span data-stu-id="a3882-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="a3882-124">Stellen Sie sicher, dass keine Einwahl Zugriffsnummern für den lync Server 2010-Pool verbleiben, von dem aus Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="a3882-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3882-125">Wenn alle Einwahl Zugriffsnummern auf den lync Server 2013-Pool verweisen, können Sie den lync Server 2010-Pool außer Betrieb stellen.</span><span class="sxs-lookup"><span data-stu-id="a3882-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="a3882-126">**Überprüfen der Migration von Einwahl Zugriffsnummern mithilfe der lync Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="a3882-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="a3882-127">Melden Sie sich bei einem Benutzerkonto, das der **CsUserAdministrator** -Rolle oder der **CsAdministrator** -Rolle zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a3882-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3882-128">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a3882-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a3882-129">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="a3882-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="a3882-130">Klicken Sie auf die Registerkarte **Einwahlnummer** .</span><span class="sxs-lookup"><span data-stu-id="a3882-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="a3882-131">Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der auf lync Server 2013 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="a3882-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="a3882-132">**Überprüfen der Migration von Einwahl Zugriffsnummern mithilfe der lync Server-Verwaltungsshell**</span><span class="sxs-lookup"><span data-stu-id="a3882-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="a3882-133">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="a3882-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a3882-134">Um alle migrierten Zugriffsnummern für Einwahlkonferenzen zurückzugeben, führen Sie über die Befehlszeile Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a3882-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="a3882-135">Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der auf lync Server 2013 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="a3882-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

