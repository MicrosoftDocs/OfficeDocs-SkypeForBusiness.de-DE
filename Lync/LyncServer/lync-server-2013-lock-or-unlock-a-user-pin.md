---
title: 'Lync Server 2013: Sperren oder Entsperren einer Benutzer-PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61892a19fde4f9584d39557eac2f3ae46c51092
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="74b83-102">Sperren oder Entsperren einer Benutzer-PIN in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74b83-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74b83-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="74b83-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="74b83-104">Sie können die PIN eines Benutzers im Abschnitt **Benutzer** der lync Server 2013 Systemsteuerung sperren oder entsperren.</span><span class="sxs-lookup"><span data-stu-id="74b83-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="74b83-105">So sperren Sie die PIN eines Benutzers in lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="74b83-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="74b83-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="74b83-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74b83-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="74b83-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74b83-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74b83-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74b83-109">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="74b83-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="74b83-110">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="74b83-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="74b83-111">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="74b83-112">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="74b83-113">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="74b83-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="74b83-114">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="74b83-115">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="74b83-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="74b83-116">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="74b83-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="74b83-117">Geben Sie je nach ausgewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="74b83-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="74b83-118">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="74b83-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="74b83-119">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="74b83-120">Klicken Sie auf den Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN sperren**.</span><span class="sxs-lookup"><span data-stu-id="74b83-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="74b83-121">So entsperren Sie die PIN eines Benutzers in lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="74b83-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="74b83-122">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="74b83-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74b83-123">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="74b83-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74b83-124">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74b83-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74b83-125">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="74b83-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="74b83-126">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="74b83-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="74b83-127">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="74b83-128">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="74b83-129">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="74b83-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="74b83-130">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="74b83-131">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="74b83-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="74b83-132">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="74b83-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="74b83-133">Geben Sie je nach ausgewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="74b83-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="74b83-134">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="74b83-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="74b83-135">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="74b83-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="74b83-136">Klicken Sie auf den Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN entsperren**.</span><span class="sxs-lookup"><span data-stu-id="74b83-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74b83-137">Sperren und Entsperren von Benutzer Pins mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="74b83-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74b83-138">Sie können Benutzer Pins mithilfe von Windows PowerShell und den Cmdlets Lock-CsClientPin und Unlock-CsClientPin Sperren und entsperren.</span><span class="sxs-lookup"><span data-stu-id="74b83-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="74b83-139">Sie können diese Cmdlets entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="74b83-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74b83-140">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="74b83-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="74b83-141">So sperren Sie die PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="74b83-141">To lock a user PIN</span></span>

  - <span data-ttu-id="74b83-p104">Verwenden Sie zum Sperren der PIN eines Benutzers das Cmdlet Lock-CsClientPin. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74b83-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="74b83-144">So entsperren Sie die PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="74b83-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="74b83-p105">Verwenden Sie zum Entsperren der PIN eines Benutzers das Cmdlet Unlock-CsClientPin. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74b83-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="74b83-147">Weitere Informationen finden Sie im Hilfethema zu den Cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) und [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="74b83-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

