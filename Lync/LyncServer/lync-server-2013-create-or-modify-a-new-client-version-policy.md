---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="c06ef-102">Erstellen oder Ändern einer neuen clientversionsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c06ef-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c06ef-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c06ef-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c06ef-104">Sie können clientversionsrichtlinien verwenden, um die Versionen der Clients anzugeben, die in Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c06ef-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="c06ef-105">Die Verwendung der Client Versionsverwaltung kann dazu beitragen, die Kosten für die Unterstützung mehrerer Clientversionen zu senken.</span><span class="sxs-lookup"><span data-stu-id="c06ef-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="c06ef-106">Darüber hinaus kann die Benutzeroberfläche insgesamt verbessert werden, da die verfügbaren Features durch die frühere Version des Clients limitiert werden können, wenn frühere und spätere Versionen von Clients interagieren.</span><span class="sxs-lookup"><span data-stu-id="c06ef-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="c06ef-107">Sie können clientversionsrichtlinien über die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="c06ef-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="c06ef-108">So erstellen oder ändern Sie clientversionsrichtlinien mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="c06ef-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c06ef-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c06ef-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c06ef-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c06ef-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c06ef-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c06ef-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c06ef-112">Klicken Sie in der linken Navigationsleiste auf **Clients**.</span><span class="sxs-lookup"><span data-stu-id="c06ef-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c06ef-113">Die Registerkarte <STRONG>Client Versionsrichtlinie</STRONG> ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c06ef-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="c06ef-114">Führen Sie auf der Seite **Client Versionsrichtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c06ef-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c06ef-115">Wenn Sie eine clientversionsrichtlinie erstellen möchten, klicken Sie auf **neu**, wählen Sie **Website Richtlinie**, **Pool Richtlinie**oder **Benutzerrichtlinie**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c06ef-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="c06ef-116">Wenn Sie die globale Richtlinie oder eine andere vorhandene clientversionsrichtlinie ändern möchten, wählen Sie die Richtlinie aus, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c06ef-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c06ef-117">Erstellen oder ändern Sie auf der Seite **Richtlinie zum Bearbeiten der Client Version** Regeln, wie unter [erstellen oder Ändern einer neuen clientversionsrichtlinien Regel in lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c06ef-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c06ef-118">Erstellen oder Ändern von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c06ef-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c06ef-119">Sie können clientversionsrichtlinien mithilfe des Cmdlets **New-CsClientVersionPolicy** erstellen und mithilfe des Cmdlets " **Satz-CsClientVersionPolicy** " ändern.</span><span class="sxs-lookup"><span data-stu-id="c06ef-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="c06ef-120">Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c06ef-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c06ef-121">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c06ef-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="c06ef-122">So erstellen Sie eine neue Richtlinie für Clientversionen mit Website Bereich</span><span class="sxs-lookup"><span data-stu-id="c06ef-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="c06ef-123">Mit dem folgenden Befehl wird eine neue clientversionsrichtlinie erstellt, die auf die Redmond-Website angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c06ef-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="c06ef-124">Da keine zusätzlichen Parameter angegeben werden, werden in der neuen Richtlinie die Standardeinstellungen für Clientversionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c06ef-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="c06ef-125">So erstellen Sie eine neue Richtlinie für benutzerspezifische Clientversionen</span><span class="sxs-lookup"><span data-stu-id="c06ef-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="c06ef-126">Verwenden Sie zum Erstellen einer benutzerbezogenen Richtlinie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="c06ef-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="c06ef-127">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) und dem Cmdlet " [Satz-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) ".</span><span class="sxs-lookup"><span data-stu-id="c06ef-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

