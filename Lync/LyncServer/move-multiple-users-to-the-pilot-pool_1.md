---
title: Verschieben mehrerer Benutzer in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="1ea5a-102">Verschieben mehrerer Benutzer in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="1ea5a-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea5a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1ea5a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1ea5a-104">Sie können mehrere Benutzer aus Ihrem Office Communications Server 2007 R2-Pool in ihren lync Server 2013-Pilot Pool mithilfe der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="1ea5a-105">So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="1ea5a-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="1ea5a-106">Öffnen Sie die **Lync Server-Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="1ea5a-107">Klicken Sie auf der Registerkarte **Benutzersuche** auf die Schaltfläche **Suchen** .</span><span class="sxs-lookup"><span data-stu-id="1ea5a-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="1ea5a-108">Klicken Sie als nächstes auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="1ea5a-109">Erstellen Sie einen Filter, bei dem **Office Communications Server-Benutzer** gleich **true**ist.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="1ea5a-110">Klicken Sie auf **Suchen** , um nach Legacy Office Communications Server 2007 R2-Benutzern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="1ea5a-111">Wählen Sie zwei Benutzer aus, die Sie in den lync Server 2013-Pool verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1ea5a-112">In diesem Beispiel werden die Benutzer Chen Yang und Claus Hansen verschoben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="1ea5a-113">![Von der Suche nach OCS-Benutzern angezeigte Benutzerliste] (images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Von der Suche nach OCS-Benutzern angezeigte Benutzerliste")</span><span class="sxs-lookup"><span data-stu-id="1ea5a-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="1ea5a-114">Wählen Sie im Menü **Aktion** die Option **ausgewählte Benutzer in Pool verschieben**aus.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="1ea5a-115">Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="1ea5a-116">Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="1ea5a-117">Klicken Sie anschließend auf OK.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-117">Click OK.</span></span>
    
    <span data-ttu-id="1ea5a-118">![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '")</span><span class="sxs-lookup"><span data-stu-id="1ea5a-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="1ea5a-119">Überprüfen Sie, ob die Spalte des **registrierungspools** für die Benutzer jetzt den lync Server 2013-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="1ea5a-120">So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="1ea5a-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="1ea5a-121">Öffnen Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="1ea5a-122">Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **Benutzer1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie den **FQDN des Pools\_** durch den Namen des Ziel Pools.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="1ea5a-123">In diesem Beispiel werden die Benutzer Hao Chen und Katie Jordan verschoben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="1ea5a-124">![Beispiel-Cmdlet zum Verschieben eines Legacy Benutzers] (images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Beispiel-Cmdlet zum Verschieben eines Legacy Benutzers")</span><span class="sxs-lookup"><span data-stu-id="1ea5a-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="1ea5a-125">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1ea5a-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="1ea5a-126">Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweisen, den Sie im vorherigen Schritt als **Pool\_-FQDN** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="1ea5a-127">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="1ea5a-128">Wiederholen Sie den Schritt, um zu überprüfen, ob **User2** verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="1ea5a-129">![Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity")</span><span class="sxs-lookup"><span data-stu-id="1ea5a-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="1ea5a-130">So verschieben Sie alle Benutzer gleichzeitig mithilfe der lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="1ea5a-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="1ea5a-131">In diesem Beispiel wurden alle Benutzer an den Office Communications Server 2007 R2-Pool (pool01.contoso.net) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="1ea5a-132">Mit der lync Server 2013-Verwaltungsshell werden alle Benutzer gleichzeitig in den lync Server 2013-Pool (pool02.contoso.net) verschoben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="1ea5a-133">Öffnen Sie die **lync Server 2013-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="1ea5a-134">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1ea5a-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="1ea5a-135">![Beispiel-Cmdlet zum Verschieben aller Legacy Benutzer in einem Pool] (images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Beispiel-Cmdlet zum Verschieben aller Legacy Benutzer in einem Pool")</span><span class="sxs-lookup"><span data-stu-id="1ea5a-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="1ea5a-136">Führen Sie als nächstes " **Get-CsUser** " für einen der Pilotbenutzer aus.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="1ea5a-137">Die Identität des **registrierungspools** für jeden Benutzer verweist nun auf den Pool, den Sie im\_vorherigen Schritt als "Pool-FQDN" angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="1ea5a-138">Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="1ea5a-139">Darüber hinaus können wir die Liste der Benutzer in der lync Server 2013-Systemsteuerung anzeigen und überprüfen, ob der Wert des registrierungspools nun auf den lync Server 2013-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="1ea5a-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="1ea5a-140">![Benutzerliste der lync Server 2013-System] Steuerung (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Benutzerliste der lync Server 2013-System") Steuerung</span><span class="sxs-lookup"><span data-stu-id="1ea5a-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

