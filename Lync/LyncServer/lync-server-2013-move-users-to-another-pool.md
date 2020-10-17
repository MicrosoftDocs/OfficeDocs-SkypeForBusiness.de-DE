---
title: 'Lync Server 2013: Benutzer in einen anderen Pool verlegen'
description: 'Lync Server 2013: verschiebt Benutzer in einen anderen Pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21012e0df7567a79bca018d194878c85b8653ae4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566391"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="95a63-103">Migrieren von Benutzern in einen anderen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a63-103">Move users to another pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="95a63-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="95a63-104">

<span> </span></span></span>

<span data-ttu-id="95a63-105">_**Letztes Änderungsstand des Themas:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="95a63-105">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="95a63-106">Sie können lync Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="95a63-106">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="95a63-107">Wenn Sie alle vorhandenen Benutzer aus einem Quell Pool verschieben, der lync Server 2010 oder früher in einem lync Server 2013 Ziel Pool in einer komplexen Active Directory Umgebung ausgeführt wird, kann dies zu einer langsameren Active Directory Replikation führen.</span><span class="sxs-lookup"><span data-stu-id="95a63-107">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="95a63-108">Um dies zu vermeiden, können Sie Suchfilter verwenden, um Benutzer aus Pools zu migrieren, die lync Server 2010 oder früher separat ausführen, oder Sie können lync Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="95a63-108">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="95a63-109">Außerdem kann die Filterfunktionalität mit lync Server 2013-Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95a63-109">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="95a63-110">So migrieren Sie ausgewählte Benutzer zu einem anderen Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="95a63-110">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="95a63-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="95a63-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95a63-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95a63-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95a63-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="95a63-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95a63-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="95a63-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="95a63-115">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="95a63-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="95a63-116">Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="95a63-116">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="95a63-117">Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verlagern**.</span><span class="sxs-lookup"><span data-stu-id="95a63-117">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="95a63-118">Wählen Sie unter **Benutzer migrieren**den Pool aus, in den Sie die Benutzer in den **Ziel registrierungsstellenpool**verlagern möchten.</span><span class="sxs-lookup"><span data-stu-id="95a63-118">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="95a63-119">(Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.</span><span class="sxs-lookup"><span data-stu-id="95a63-119">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="95a63-120">Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.</span><span class="sxs-lookup"><span data-stu-id="95a63-120">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="95a63-121">So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder in einen anderen Pool</span><span class="sxs-lookup"><span data-stu-id="95a63-121">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="95a63-122">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="95a63-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95a63-123">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95a63-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95a63-124">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="95a63-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95a63-125">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="95a63-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="95a63-126">Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="95a63-126">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="95a63-127">Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.</span><span class="sxs-lookup"><span data-stu-id="95a63-127">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="95a63-128">Wählen Sie unter **Zielregistrierungspool** den Pool aus, in den Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="95a63-128">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="95a63-129">(Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.</span><span class="sxs-lookup"><span data-stu-id="95a63-129">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="95a63-130">Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.</span><span class="sxs-lookup"><span data-stu-id="95a63-130">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="95a63-131">So verschieben Sie Benutzer mithilfe eines Filters von einem Pool in einen anderen Pool</span><span class="sxs-lookup"><span data-stu-id="95a63-131">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="95a63-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="95a63-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95a63-133">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95a63-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95a63-134">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="95a63-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95a63-135">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="95a63-135">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="95a63-136">Klicken Sie in der **Benutzersuche**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="95a63-136">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="95a63-137">Wählen Sie in den Suchkriterien **Registrierungspool**, **Gleich** und **FQDN des aktuellen Pools** aus, und klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="95a63-137">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="95a63-138">Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="95a63-138">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95a63-139">Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, ist die Option <STRONG>alle Benutzer zu Pool verlagern</STRONG> im Kontext der gefilterten Teilmenge von Benutzern, nicht <STRONG><EM>aller</EM></STRONG> möglichen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="95a63-139">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="95a63-140">Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.</span><span class="sxs-lookup"><span data-stu-id="95a63-140">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="95a63-141">Wählen Sie im **Ziel registrierungsstellenpool**den Pool aus, in den Sie die Benutzer migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="95a63-141">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="95a63-142">(Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.</span><span class="sxs-lookup"><span data-stu-id="95a63-142">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="95a63-143">Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.</span><span class="sxs-lookup"><span data-stu-id="95a63-143">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="95a63-144">So migrieren Sie Benutzer mithilfe von Windows PowerShell-Cmdlets von einem Pool in einen anderen</span><span class="sxs-lookup"><span data-stu-id="95a63-144">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="95a63-145">Je nachdem, wie Sie Windows PowerShell-Befehle (lokal oder Remote) ausführen, müssen Sie sich wie folgt als Mitglied der korrekten lync Server 2013 Administratorrolle anmelden:</span><span class="sxs-lookup"><span data-stu-id="95a63-145">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="95a63-146">Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95a63-146">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="95a63-147">Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich an Ihrem Computer an, und führen Sie die Befehle Remote auf einem Standard Edition-Front-End-Server) aus: Melden Sie sich über ein Benutzerkonto, das der CsUserAdministrator-Rolle oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="95a63-147">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95a63-148">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="95a63-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="95a63-149">Zum Verschieben einzelner Benutzer verwenden Sie das Move-CsUser-Cmdlet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="95a63-149">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="95a63-150">Der Benutzer, der verschoben werden soll, ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem derzeit zugewiesenen Home-Pool in den Pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="95a63-150">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="95a63-151">Zum Verschieben einer großen Zahl von Benutzern verwenden Sie das **Get-CsUser**-Cmdlet mit Filtern und übergeben Sie den daraus resultierenden Benutzersatz an **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="95a63-151">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="95a63-152">Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** Folgendes ergeben:</span><span class="sxs-lookup"><span data-stu-id="95a63-152">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95a63-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95a63-153">See Also</span></span>


[<span data-ttu-id="95a63-154">Ändern von Benutzerkontoeigenschaften in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a63-154">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="95a63-155"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="95a63-155"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

