---
title: 'Lync Server 2013: deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="fb795-102">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb795-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb795-103">_**Letztes Änderungsdatum des Themas:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="fb795-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="fb795-104">Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in lync Server 2013 deaktivieren, ohne die lync-Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="fb795-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="fb795-105">Da die Einstellungen für das lync Server-Benutzerkonto nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="fb795-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fb795-106">Durch einfaches Deaktivieren eines Benutzerkontos in Active Directory wird verhindert, dass ein Benutzer sich <STRONG>nicht</STRONG> anmelden oder lync Server verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="fb795-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="fb795-107">Dies liegt daran, dass lync die Zertifikatauthentifizierung verwendet, die den Authentifizierungsprozess optimiert, und diese Clientzertifikate sind für 180 Tage gültig.</span><span class="sxs-lookup"><span data-stu-id="fb795-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="fb795-108">Wenn Sie die deaktivierten Active Directory-Konten, die für lync aktiviert wurden, nicht mehr auf lync Server zugreifen möchten, müssen Sie das Cmdlet <STRONG>Disable-CsUser</STRONG> verwenden oder die <STRONG>lync Server-System</STRONG> Steuerung verwenden, wie in diesem Artikel dargelegt.</span><span class="sxs-lookup"><span data-stu-id="fb795-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="fb795-109">Nachdem der Benutzer in lync deaktiviert wurde und der zentrale Verwaltungsspeicher in der Umgebung repliziert wurde, können sich die Benutzer nicht mehr anmelden.</span><span class="sxs-lookup"><span data-stu-id="fb795-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="fb795-110">Außerdem werden Benutzer, die angemeldet sind, getrennt.</span><span class="sxs-lookup"><span data-stu-id="fb795-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="fb795-111">So deaktivieren oder erneutes Aktivieren eines zuvor aktivierten Benutzerkontos für lync Server</span><span class="sxs-lookup"><span data-stu-id="fb795-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="fb795-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="fb795-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb795-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fb795-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fb795-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fb795-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fb795-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="fb795-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fb795-116">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten. und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="fb795-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="fb795-117">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder erneut aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fb795-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="fb795-118">Führen Sie im Menü **Aktion** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="fb795-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="fb795-119">Wenn Sie das Benutzerkonto für lync Server 2013 vorübergehend deaktivieren möchten, klicken Sie auf **vorübergehend für lync Server deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="fb795-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="fb795-120">Wenn Sie das Benutzerkonto für lync Server 2013 aktivieren möchten, klicken Sie auf **für lync Server erneut aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="fb795-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="fb795-121">Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="fb795-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="fb795-122">Mithilfe des Cmdlets " **Satz-CsUser** " können Benutzerkonten vorübergehend deaktiviert und später erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fb795-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="fb795-123">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb795-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fb795-124">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="fb795-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="fb795-125">So deaktivieren Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="fb795-125">To disable a user account</span></span>

  - <span data-ttu-id="fb795-126">Wenn Sie ein Benutzerkonto vorübergehend deaktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf false ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="fb795-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="fb795-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb795-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="fb795-128">So aktivieren Sie ein Benutzerkonto erneut</span><span class="sxs-lookup"><span data-stu-id="fb795-128">To re-enable a user account</span></span>

  - <span data-ttu-id="fb795-129">Wenn Sie ein deaktiviertes Benutzerkonto erneut aktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf true ($true) fest.</span><span class="sxs-lookup"><span data-stu-id="fb795-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="fb795-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb795-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="fb795-131">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) ".</span><span class="sxs-lookup"><span data-stu-id="fb795-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb795-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb795-132">See Also</span></span>


[<span data-ttu-id="fb795-133">Hinzufügen und Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb795-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="fb795-134">Aktivieren und Deaktivieren von Benutzern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb795-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

