---
title: 'Lync Server 2013: Löschen eines Workflows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70f2dac3aeceb2c8f6c2cbfe2d0967ac9997cd6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="c68ca-102">Löschen eines Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c68ca-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68ca-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c68ca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c68ca-104">Verwenden Sie eines der folgenden Verfahren, um einen Workflow zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="c68ca-105">So verwenden Sie lync Server-Systemsteuerung Löschen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="c68ca-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="c68ca-106">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c68ca-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c68ca-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c68ca-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c68ca-109">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="c68ca-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="c68ca-110">Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c68ca-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="c68ca-111">Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, der den zu löschenden Workflow hostet.</span><span class="sxs-lookup"><span data-stu-id="c68ca-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="c68ca-112">Klicken Sie in der Liste der Dienste auf den gewünschten Dienst, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c68ca-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c68ca-113">Die Seite Konfigurations Tool für Reaktionsgruppen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c68ca-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="c68ca-114">Sie können die Webseite für das Reaktionsgruppen-Konfigurations Tool auch direkt über einen Webbrowser öffnen, indem Sie eine Verbindung mit <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>herstellen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="c68ca-115">Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie löschen möchten, und klicken Sie anschließend unter **Aktion** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="c68ca-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="c68ca-116">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c68ca-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="c68ca-117">So löschen Sie einen Workflow mithilfe Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c68ca-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="c68ca-118">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c68ca-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c68ca-119">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c68ca-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c68ca-120">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c68ca-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="c68ca-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c68ca-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

