---
title: 'Lync Server 2013: Löschen einer Archivierungsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="85ff2-102">Löschen einer Archivierungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ff2-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ff2-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="85ff2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="85ff2-104">Sie können eine Benutzerrichtlinie oder eine Website Richtlinie löschen.</span><span class="sxs-lookup"><span data-stu-id="85ff2-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="85ff2-105">Die globale Richtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="85ff2-105">The global policy cannot be removed.</span></span> <span data-ttu-id="85ff2-106">Wenn Sie versuchen, die globale Richtlinie zu löschen, setzt lync Server 2013 die Richtlinie automatisch auf die Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="85ff2-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85ff2-107">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="85ff2-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="85ff2-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="85ff2-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="85ff2-109">So löschen Sie einen Benutzer oder eine Website Richtlinie für die Archivierung</span><span class="sxs-lookup"><span data-stu-id="85ff2-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="85ff2-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="85ff2-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85ff2-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="85ff2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="85ff2-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85ff2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="85ff2-113">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="85ff2-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="85ff2-114">Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="85ff2-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="85ff2-115">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="85ff2-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85ff2-116">Entfernen von Archivierungsrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="85ff2-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="85ff2-117">Archivierungsrichtlinien können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="85ff2-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="85ff2-118">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85ff2-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="85ff2-119">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="85ff2-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="85ff2-120">So entfernen Sie eine bestimmte Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="85ff2-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="85ff2-121">Als Beispiel löscht **Remove-CsArchivingPolicy** die Richtlinie mit der Identitäts Website: Redmond.</span><span class="sxs-lookup"><span data-stu-id="85ff2-121">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="85ff2-122">Beachten Sie, dass Benutzer, die zuvor von der Website Richtlinie verwaltet werden, automatisch durch die globale Archivierungsrichtlinie gesteuert werden, wenn eine auf dem Website Bereich konfigurierte Richtlinie gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="85ff2-122">Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.</span></span> <span data-ttu-id="85ff2-123">Mit dem folgenden Befehl wird die auf die Redmond-Website angewendete Archivierung entfernt:</span><span class="sxs-lookup"><span data-stu-id="85ff2-123">The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="85ff2-124">So entfernen Sie alle auf den Benutzerbereich angewendeten Archivierungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="85ff2-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="85ff2-125">Mit diesem Befehl werden alle auf den Benutzerbereich angewendeten Archivierungsrichtlinien entfernt:</span><span class="sxs-lookup"><span data-stu-id="85ff2-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="85ff2-126">So entfernen Sie alle Archivierungsrichtlinien, die die interne Archivierung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="85ff2-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="85ff2-127">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="85ff2-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="85ff2-128">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="85ff2-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85ff2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85ff2-129">See Also</span></span>


[<span data-ttu-id="85ff2-130">Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ff2-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

