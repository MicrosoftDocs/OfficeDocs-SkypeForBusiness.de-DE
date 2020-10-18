---
title: 'Lync Server 2013: Löschen einer Archivierungsrichtlinie'
description: 'Lync Server 2013: Löschen einer Archivierungsrichtlinie.'
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
ms.openlocfilehash: ecf465a62cf8f54777b03a1634d9a95f1b565c9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575801"
---
# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="3988c-103">Löschen einer Archivierungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3988c-103">Deleting an Archiving policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3988c-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3988c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3988c-105">Benutzer- und Standortrichtlinien können gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3988c-105">You can delete a user policy or site policy.</span></span> <span data-ttu-id="3988c-106">Die globale Richtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3988c-106">The global policy cannot be removed.</span></span> <span data-ttu-id="3988c-107">Wenn Sie versuchen, die globale Richtlinie zu löschen, setzt lync Server 2013 die Richtlinie automatisch auf die Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="3988c-107">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3988c-108">Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und lassen ihre Postfächer In-Place halten.</span><span class="sxs-lookup"><span data-stu-id="3988c-108">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3988c-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3988c-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="3988c-110">So löschen Sie eine Benutzer- oder Standortrichtlinie für die Archivierung</span><span class="sxs-lookup"><span data-stu-id="3988c-110">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="3988c-111">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3988c-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3988c-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3988c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3988c-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3988c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3988c-114">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3988c-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="3988c-115">Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3988c-115">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="3988c-116">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3988c-116">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3988c-117">Entfernen von Archivierungsrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3988c-117">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3988c-118">Archivierungsrichtlinien können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3988c-118">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="3988c-119">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3988c-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3988c-120">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3988c-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="3988c-121">So entfernen Sie eine angegebene Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3988c-121">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="3988c-p105">**Remove-CsArchivingPolicy** löscht beispielsweise die Richtlinie mit der Identität "site:Redmond". Wenn Sie eine auf Standortebene konfigurierte Richtlinie löschen, werden Benutzer, die zuvor durch die Standortrichtlinie verwaltet wurden, automatisch durch die globale Archivierungsrichtlinie verwaltet. Mit dem folgenden Befehl wird die Archivierung für den Standort "Redmond" entfernt:</span><span class="sxs-lookup"><span data-stu-id="3988c-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="3988c-125">So entfernen Sie alle auf Benutzerebene angewendeten Archivierungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3988c-125">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="3988c-126">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerbasis festgelegt wurden:</span><span class="sxs-lookup"><span data-stu-id="3988c-126">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="3988c-127">So entfernen Sie alle Archivierungsrichtlinien, die die interne Archivierung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="3988c-127">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="3988c-128">Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="3988c-128">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="3988c-129">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="3988c-129">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3988c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3988c-130">See Also</span></span>


[<span data-ttu-id="3988c-131">Verwalten der Archivierung von interner und externer Kommunikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3988c-131">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

