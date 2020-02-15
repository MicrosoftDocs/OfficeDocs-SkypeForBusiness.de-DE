---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8464e64c3de1e85f823bb3e1b5dac4dd1837effd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="688cd-102">Erstellen oder Ändern einer neuen clientversionsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="688cd-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="688cd-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="688cd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="688cd-104">Mithilfe von clientversionsrichtlinien können Sie die Versionen von Clients angeben, die in Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="688cd-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="688cd-105">Die Verwendung der Client Versionsverwaltung kann dazu beitragen, die mit der Unterstützung mehrerer Clientversionen verbundenen Kosten zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="688cd-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="688cd-106">Es kann auch die gesamtbenutzerfreundlichkeit verbessern, da die verfügbaren Features bei einer Interaktion mit früheren und höheren Versionen der Clients durch die frühere Version des Clients limitiert werden können.</span><span class="sxs-lookup"><span data-stu-id="688cd-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="688cd-107">Sie können clientversionsrichtlinien in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="688cd-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="688cd-108">So erstellen oder ändern Sie clientversionsrichtlinien mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="688cd-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="688cd-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="688cd-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="688cd-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="688cd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="688cd-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="688cd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="688cd-112">Klicken Sie in der linken Navigationsleiste auf **Clients**.</span><span class="sxs-lookup"><span data-stu-id="688cd-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="688cd-113">Die Registerkarte <STRONG>Clientversionsrichtlinie</STRONG> ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="688cd-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="688cd-114">Führen Sie auf der Seite **Client Versionsrichtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="688cd-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="688cd-115">Um eine clientversionsrichtlinie zu erstellen, klicken Sie auf **neu**, wählen Sie **Standortrichtlinie**, **Pool Richtlinie**oder **Benutzerrichtlinie**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="688cd-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="688cd-116">Um die globale Richtlinie oder eine andere vorhandene clientversionsrichtlinie zu ändern, wählen Sie die Richtlinie aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="688cd-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="688cd-117">Erstellen oder ändern Sie auf der Seite **clientversionsrichtlinie bearbeiten** in lync Server 2013 die in [erstellen oder Ändern einer neuen clientversionsrichtlinien Regel](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)beschriebenen Regeln.</span><span class="sxs-lookup"><span data-stu-id="688cd-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="688cd-118">Erstellen oder Ändern von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="688cd-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="688cd-119">Sie können clientversionsrichtlinien erstellen, indem Sie das Cmdlet **New-CsClientVersionPolicy** verwenden, und Sie mithilfe des Cmdlets "Cmdlet" **festlegen-CsClientVersionPolicy** ändern.</span><span class="sxs-lookup"><span data-stu-id="688cd-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="688cd-120">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="688cd-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="688cd-121">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="688cd-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="688cd-122">So erstellen Sie eine neue clientversionsrichtlinie für Standort Bereiche</span><span class="sxs-lookup"><span data-stu-id="688cd-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="688cd-123">Mit dem folgenden Befehl wird eine neue clientversionsrichtlinie erstellt, die auf den Standort "Redmond" angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="688cd-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="688cd-124">Da keine zusätzlichen Parameter angegeben werden, verwendet die neue Richtlinie die Standardeinstellungen für Clientversionen.</span><span class="sxs-lookup"><span data-stu-id="688cd-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="688cd-125">So erstellen Sie eine neue clientversionsrichtlinie pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="688cd-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="688cd-126">Verwenden Sie einen Befehl wie den folgenden, um eine benutzerspezifische Richtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="688cd-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="688cd-127">Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsClientVersionPolicy-](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet und das Cmdlet "Set [-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) ".</span><span class="sxs-lookup"><span data-stu-id="688cd-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

