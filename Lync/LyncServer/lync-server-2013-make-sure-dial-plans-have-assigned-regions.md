---
title: 'Lync Server 2013: sicherstellen, dass den Wählplänen Regionen zugewiesen wurden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f25ca766ab7292aeeba0d2e621eccff5a0c47fb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="0be40-102">Sicherstellen, dass den Wählplänen lync Server 2013 zugewiesene Regionen zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="0be40-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0be40-103">_**Letztes Änderungsstand des Themas:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="0be40-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="0be40-p101">Wähleinstellungen, die für Einwahlkonferenzen verwendet werden, müssen eine **Region für Einwahlkonferenzen** enthalten, um Zugriffsnummern für Einwahlkonferenzen den entsprechenden Wähleinstellungen zuzuordnen. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0be40-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="0be40-p102">Da es wichtig ist, eine Region für alle Wähleinstellungen anzugeben, wird empfohlen, mit diesem Verfahren das Vorhandensein von Regionen für alle Wähleinstellungen zu überprüfen. Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="0be40-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="0be40-109">Verwenden Sie das Cmdlet **Get-CsDialPlan** um zu überprüfen, ob für alle Wähleinstellungen eine Region festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="0be40-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="0be40-110">Wenn die Region in einem Satz mit Wähleinstellungen fehlt, können Sie die Region mit dem Cmdlet **Set-CsDialPlan** festlegen.</span><span class="sxs-lookup"><span data-stu-id="0be40-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="0be40-111">Sie können auch lync Server-Systemsteuerung verwenden, um die Region in vorhandenen Wählplänen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0be40-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="0be40-112">Ausführliche Informationen zur Verwendung von lync Server-Systemsteuerung finden Sie unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0be40-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="0be40-113">So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde</span><span class="sxs-lookup"><span data-stu-id="0be40-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="0be40-114">Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="0be40-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="0be40-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0be40-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0be40-116">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="0be40-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="0be40-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0be40-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="0be40-118">In diesem Beispiel werden alle für Ihre Organisation konfigurierten Wähleinstellungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0be40-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="0be40-119">Überprüfen Sie die zurückgegebenen Wähleinstellungen, um fehlende Regionen für Einwahlkonferenzen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0be40-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="0be40-120">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="0be40-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="0be40-121">So legen Sie die Region für einen Satz mit Wähleinstellungen fest</span><span class="sxs-lookup"><span data-stu-id="0be40-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="0be40-122">Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="0be40-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="0be40-123">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0be40-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0be40-124">Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0be40-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="0be40-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0be40-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="0be40-126">In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert.</span><span class="sxs-lookup"><span data-stu-id="0be40-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="0be40-127">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="0be40-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

