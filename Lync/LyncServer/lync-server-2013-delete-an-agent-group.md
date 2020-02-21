---
title: 'Lync Server 2013: Löschen einer Agentengruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71d4d2a2ca22ec0852fb09bdfe011c5d934ab3d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="3998f-102">Löschen einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3998f-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3998f-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3998f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3998f-104">Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3998f-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="3998f-105">So löschen Sie eine Agentgruppe mithilfe lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="3998f-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="3998f-106">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3998f-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="3998f-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3998f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3998f-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3998f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3998f-109">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="3998f-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="3998f-110">Geben Sie auf der Seite **Reaktionsgruppen** im Suchfeld einen Teil oder den vollständigen Namen der Agentgruppe ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3998f-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="3998f-111">Klicken Sie in der Ergebnisliste auf die Gruppe, die Sie löschen möchten, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3998f-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="3998f-112">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3998f-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="3998f-113">So löschen Sie eine Agentgruppe mithilfe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3998f-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="3998f-114">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3998f-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="3998f-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="3998f-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3998f-116">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3998f-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="3998f-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3998f-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3998f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3998f-118">See Also</span></span>


[<span data-ttu-id="3998f-119">Erstellen oder Ändern einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3998f-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="3998f-120">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="3998f-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="3998f-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="3998f-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

