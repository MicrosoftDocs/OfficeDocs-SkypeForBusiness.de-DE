---
title: Verschieben mehrerer Benutzer in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="79ef0-102">Verschieben mehrerer Benutzer in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="79ef0-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79ef0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="79ef0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="79ef0-104">Mithilfe der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell können Sie mehrere Benutzer aus Ihrem lync Server 2010-Pool in ihren lync Server 2013-Pilot Pool verschieben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="79ef0-105">So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="79ef0-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="79ef0-106">Öffnen Sie die **Lync Server-Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="79ef0-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="79ef0-107">Klicken Sie auf **Benutzer** und anschließend auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="79ef0-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="79ef0-108">Wählen Sie zwei Benutzer aus, die Sie in den lync Server 2013-Pool verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="79ef0-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="79ef0-109">In diesem Beispiel werden die Benutzer Chen Yang und Claus Hansen verschoben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="79ef0-110">![Verschieben von Benutzern in einen bestimmten Registrierungspool] (images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Verschieben von Benutzern in einen bestimmten Registrierungspool")</span><span class="sxs-lookup"><span data-stu-id="79ef0-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="79ef0-111">Wählen Sie im Menü **Aktion** die Option **ausgewählte Benutzer in Pool verschieben**aus.</span><span class="sxs-lookup"><span data-stu-id="79ef0-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="79ef0-112">Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="79ef0-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="79ef0-113">Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="79ef0-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="79ef0-114">Klicken Sie anschließend auf OK.</span><span class="sxs-lookup"><span data-stu-id="79ef0-114">Click OK.</span></span>
    
    <span data-ttu-id="79ef0-115">![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '")</span><span class="sxs-lookup"><span data-stu-id="79ef0-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="79ef0-116">Überprüfen Sie, ob die Spalte des **registrierungspools** für die Benutzer jetzt den lync Server 2013-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="79ef0-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="79ef0-117">So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="79ef0-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="79ef0-118">Öffnen Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="79ef0-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="79ef0-119">Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **Benutzer1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie den **FQDN des Pools\_** durch den Namen des Ziel Pools.</span><span class="sxs-lookup"><span data-stu-id="79ef0-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="79ef0-120">In diesem Beispiel werden die Benutzer Hao Chen und Katie Jordan verschoben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="79ef0-121">![Beispiel für ein PowerShell-Cmdlet "Get-CsUser] " (images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Beispiel für ein PowerShell-Cmdlet \"Get-CsUser") "</span><span class="sxs-lookup"><span data-stu-id="79ef0-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="79ef0-122">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="79ef0-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="79ef0-123">Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweisen, den Sie im vorherigen Schritt als **Pool\_-FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="79ef0-124">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="79ef0-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="79ef0-125">Wiederholen Sie den Schritt, um zu überprüfen, ob **User2** verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="79ef0-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="79ef0-126">![Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity")</span><span class="sxs-lookup"><span data-stu-id="79ef0-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="79ef0-127">So verschieben Sie alle Benutzer gleichzeitig mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="79ef0-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="79ef0-128">In diesem Beispiel wurden alle Benutzer an den lync Server 2010 Pool (pool01.contoso.net) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="79ef0-129">Mit der lync Server 2013-Verwaltungsshell werden alle Benutzer gleichzeitig in den lync Server 2013-Pool (pool02.contoso.net) verschoben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="79ef0-130">Öffnen Sie die **lync Server 2013-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="79ef0-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="79ef0-131">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="79ef0-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="79ef0-132">![PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell] (images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell")</span><span class="sxs-lookup"><span data-stu-id="79ef0-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="79ef0-133">Führen Sie als nächstes " **Get-CsUser** " für einen der Pilotbenutzer aus.</span><span class="sxs-lookup"><span data-stu-id="79ef0-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="79ef0-134">Die Identität des **registrierungspools** für jeden Benutzer verweist nun auf den Pool, den Sie im\_vorherigen Schritt als "Pool-FQDN" angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="79ef0-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="79ef0-135">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="79ef0-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="79ef0-136">Darüber hinaus können wir die Liste der Benutzer in der lync Server 2013-Systemsteuerung anzeigen und überprüfen, ob der Wert des registrierungspools nun auf den lync Server 2013-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="79ef0-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="79ef0-137">![Benutzerliste der lync Server 2013-System] Steuerung (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Benutzerliste der lync Server 2013-System") Steuerung</span><span class="sxs-lookup"><span data-stu-id="79ef0-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

