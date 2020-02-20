---
title: 'Lync Server 2013: Löschen einer vorhandenen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d74fa95a92c483d5a37c3f051d6dc372110a00b9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="7f57b-102">Löschen einer vorhandenen clientversionsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f57b-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f57b-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7f57b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7f57b-104">Wenn Sie eine zuvor konfigurierte clientversionsrichtlinie löschen möchten, können Sie Sie aus lync Server 2013 Systemsteuerung oder aus lync Server 2013 Verwaltungsshell löschen.</span><span class="sxs-lookup"><span data-stu-id="7f57b-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="7f57b-105">So löschen Sie clientversionsrichtlinien mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="7f57b-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7f57b-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f57b-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f57b-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f57b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7f57b-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7f57b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7f57b-109">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versionsrichtlinie** .</span><span class="sxs-lookup"><span data-stu-id="7f57b-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="7f57b-110">Wählen Sie auf der Seite **clientversionsrichtlinie** die clientversionsrichtlinie oder Richtlinien aus, die Sie löschen möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="7f57b-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7f57b-111">Löschen von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7f57b-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7f57b-112">Sie können clientversionsrichtlinien mithilfe des Cmdlets **Remove-CsClientVersionPolicy** löschen.</span><span class="sxs-lookup"><span data-stu-id="7f57b-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="7f57b-113">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7f57b-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7f57b-114">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="7f57b-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="7f57b-115">So entfernen Sie eine bestimmte clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7f57b-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="7f57b-116">Mit diesem Befehl wird die clientversionsrichtlinie gelöscht, die auf den Standort "Redmond" angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="7f57b-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="7f57b-117">So entfernen Sie alle auf den Website Bereich angewendeten clientversionsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7f57b-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="7f57b-118">Mit diesem Befehl werden alle clientversionsrichtlinien entfernt, die auf Standortebene konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="7f57b-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="7f57b-119">So entfernen Sie clientversionsrichtlinien, die keinen bestimmten Benutzer-Agent enthalten</span><span class="sxs-lookup"><span data-stu-id="7f57b-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="7f57b-120">Mit diesem Befehl werden alle clientversionsrichtlinien entfernt, die keine Regel für den Windows Phone lync-Benutzer-Agent (WPLync) enthalten:</span><span class="sxs-lookup"><span data-stu-id="7f57b-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="7f57b-121">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="7f57b-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

