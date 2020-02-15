---
title: 'Lync Server 2013: deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7ed0572d36a87532c4845df887dc87ccb34eec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="7ace5-102">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ace5-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ace5-103">_**Letztes Änderungsstand des Themas:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="7ace5-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="7ace5-104">Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in lync Server 2013 deaktivieren, ohne die lync Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="7ace5-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="7ace5-105">Da die lync Server Benutzerkontoeinstellungen nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7ace5-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7ace5-106">Durch einfaches Deaktivieren eines Benutzerkontos in Active Directory <STRONG>wird</STRONG> verhindert, dass Benutzer sich anmelden oder lync Server verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7ace5-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="7ace5-107">Dies liegt daran, dass lync die Zertifikatauthentifizierung verwendet, die den Authentifizierungsprozess optimiert, und diese Clientzertifikate sind 180 Tage gültig.</span><span class="sxs-lookup"><span data-stu-id="7ace5-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="7ace5-108">Wenn Sie deaktivierte Active Directory Konten beenden möchten, die für lync mit Zugriff auf lync Server aktiviert wurden, müssen Sie das Cmdlet <STRONG>Disable-CsUser</STRONG> verwenden oder die <STRONG>lync Server-Systemsteuerung</STRONG> wie in diesem Artikel dargelegt verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ace5-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="7ace5-109">Nachdem der Benutzer in lync deaktiviert wurde und der zentrale Verwaltungsspeicher in der Umgebung repliziert wurde, können sich die Benutzer nicht mehr anmelden.</span><span class="sxs-lookup"><span data-stu-id="7ace5-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="7ace5-110">Außerdem werden Benutzer, die angemeldet sind, getrennt.</span><span class="sxs-lookup"><span data-stu-id="7ace5-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="7ace5-111">So deaktivieren oder wieder aktivieren Sie ein zuvor aktiviertes Benutzerkonto für lync Server</span><span class="sxs-lookup"><span data-stu-id="7ace5-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="7ace5-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7ace5-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ace5-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7ace5-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ace5-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7ace5-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ace5-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7ace5-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="7ace5-116">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7ace5-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="7ace5-117">Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ace5-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="7ace5-118">Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7ace5-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="7ace5-119">Wenn Sie das Benutzerkonto für lync Server 2013 vorübergehend deaktivieren möchten, klicken Sie auf **vorübergehend für lync Server deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7ace5-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="7ace5-120">Klicken Sie zum Aktivieren des Benutzerkontos für lync Server 2013 auf **für lync Server erneut aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7ace5-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="7ace5-121">Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="7ace5-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="7ace5-122">Benutzerkonten können vorübergehend deaktiviert und später erneut aktiviert werden, indem das Cmdlet " **CsUser** " verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ace5-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="7ace5-123">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7ace5-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7ace5-124">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="7ace5-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="7ace5-125">So deaktivieren Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="7ace5-125">To disable a user account</span></span>

  - <span data-ttu-id="7ace5-126">Zum vorübergehenden Deaktivieren eines Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "False" ($False).</span><span class="sxs-lookup"><span data-stu-id="7ace5-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="7ace5-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7ace5-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="7ace5-128">So aktivieren Sie ein Benutzerkonto erneut</span><span class="sxs-lookup"><span data-stu-id="7ace5-128">To re-enable a user account</span></span>

  - <span data-ttu-id="7ace5-129">Zum erneuten Aktivieren eines deaktivierten Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "True" ($True).</span><span class="sxs-lookup"><span data-stu-id="7ace5-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="7ace5-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7ace5-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="7ace5-131">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) ".</span><span class="sxs-lookup"><span data-stu-id="7ace5-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ace5-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ace5-132">See Also</span></span>


[<span data-ttu-id="7ace5-133">Hinzufügen und Aktivieren des Benutzerkontos für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ace5-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="7ace5-134">Aktivieren und Deaktivieren von Benutzern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ace5-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

