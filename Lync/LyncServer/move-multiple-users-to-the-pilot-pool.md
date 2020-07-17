---
title: Mehrere Benutzer in den Pilot Pool migrieren
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a5a92b0438e72be0ecb5acaa1b8e1886768ad59
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="165a8-102">Mehrere Benutzer in den Pilot Pool migrieren</span><span class="sxs-lookup"><span data-stu-id="165a8-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="165a8-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="165a8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="165a8-104">Sie können mehrere Benutzer aus dem lync Server 2010 Pool mithilfe lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell in den lync Server 2013-Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="165a8-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="165a8-105">So können Sie mehrere Benutzer mithilfe der lync Server 2013-Systemsteuerung migrieren</span><span class="sxs-lookup"><span data-stu-id="165a8-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="165a8-106">Öffnen Sie die **Lync Server-Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="165a8-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="165a8-107">Klicken Sie auf **Benutzer**, dann auf die Suche und auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="165a8-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="165a8-108">Wählen Sie zwei Benutzer aus, die Sie in den lync Server 2013 Pool umlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="165a8-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="165a8-109">In diesem Beispiel werden wir die Benutzer Chen Yang und Claus Hansen verschieben.</span><span class="sxs-lookup"><span data-stu-id="165a8-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="165a8-110">![Migrieren von Benutzern zu einem bestimmten Register Pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Migrieren von Benutzern zu einem bestimmten Register Pool")</span><span class="sxs-lookup"><span data-stu-id="165a8-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="165a8-111">Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.</span><span class="sxs-lookup"><span data-stu-id="165a8-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="165a8-112">Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="165a8-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="165a8-113">Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="165a8-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="165a8-114">Klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="165a8-114">Click OK.</span></span>
    
    <span data-ttu-id="165a8-115">![Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool")</span><span class="sxs-lookup"><span data-stu-id="165a8-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="165a8-116">Stellen Sie sicher, dass die Spalte **Registrierungspool** für die Benutzer jetzt den lync Server 2013 Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="165a8-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="165a8-117">So migrieren Sie mehrere Benutzer mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="165a8-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="165a8-118">Öffnen Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="165a8-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="165a8-119">Geben Sie an der Befehlszeile Folgendes ein, und ersetzen Sie **User1** und **Benutzer2** durch bestimmte Benutzernamen, die Sie migrieren möchten, und ersetzen Sie den **Pool- \_ FQDN** durch den Namen des Ziel Pools.</span><span class="sxs-lookup"><span data-stu-id="165a8-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="165a8-120">In diesem Beispiel verschieben wir die Benutzer Hao Chen und Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="165a8-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="165a8-121">![Beispiel für das PowerShell Get-CsUser-Cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Beispiel für das PowerShell Get-CsUser-Cmdlet")</span><span class="sxs-lookup"><span data-stu-id="165a8-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="165a8-122">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="165a8-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="165a8-123">Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweist, den Sie im vorherigen Schritt als **Pool- \_ FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="165a8-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="165a8-124">Das Vorhandensein dieser Identität bestätigt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="165a8-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="165a8-125">Wiederholen Sie den Schritt, um zu prüfen, ob **User2** verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="165a8-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="165a8-126">![Ausgabe des PowerShell Get-UsUser-Identity-Cmdlets](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe des PowerShell Get-UsUser-Identity-Cmdlets")</span><span class="sxs-lookup"><span data-stu-id="165a8-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="165a8-127">So führen Sie eine gleichzeitige Verlagerung aller Benutzer mithilfe der lync Server 2013 Management-Shell aus</span><span class="sxs-lookup"><span data-stu-id="165a8-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="165a8-128">In diesem Beispiel wurden alle Benutzer an den lync Server 2010 Pool (pool01.contoso.net) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="165a8-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="165a8-129">Mithilfe der lync Server 2013-Verwaltungsshell werden alle Benutzer gleichzeitig in den lync Server 2013 Pool (pool02.contoso.net) verlagert.</span><span class="sxs-lookup"><span data-stu-id="165a8-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="165a8-130">Öffnen Sie die **lync Server 2013 Management-Shell**.</span><span class="sxs-lookup"><span data-stu-id="165a8-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="165a8-131">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="165a8-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="165a8-132">![PowerShell-Cmdlet und Ergebnisse in der Verwaltungskonsole](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell-Cmdlet und Ergebnisse in der Verwaltungskonsole")</span><span class="sxs-lookup"><span data-stu-id="165a8-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="165a8-133">Führen Sie dann für einen der Pilotbenutzer **Get-CsUser** aus.</span><span class="sxs-lookup"><span data-stu-id="165a8-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="165a8-134">Die Identität des **Registrierungsstellen Pools** für jeden Benutzer verweist nun auf den Pool, den Sie \_ im vorherigen Schritt als Pool-FQDN angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="165a8-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="165a8-135">Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="165a8-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="165a8-136">Darüber hinaus können wir die Liste der Benutzer in der lync Server 2013-Systemsteuerung anzeigen und überprüfen, ob der Wert des Registrierungsstellen Pools nun auf den lync Server 2013-Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="165a8-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="165a8-137">![Benutzerliste für lync Server 2013 Systemsteuerung](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Benutzerliste für lync Server 2013 Systemsteuerung")</span><span class="sxs-lookup"><span data-stu-id="165a8-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

