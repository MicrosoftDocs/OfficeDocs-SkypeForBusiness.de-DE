---
title: 'Lync Server 2013: Erstellen oder Ändern einer Mobilitätsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a240c55b4478c5cf5f67a4f0774b1979e884b3b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="8aa33-102">Erstellen oder Ändern einer Mobilitätsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa33-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aa33-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8aa33-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8aa33-104">Sie können mobilitätsrichtlinien erstellen oder ändern, um mobilen Benutzern die Verwendung unterstützter mobiler Geräte für lync-Funktionen wie Instant Messaging (Sofortnachrichten), Anwesenheit und Kontakte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8aa33-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="8aa33-105">Sie können mobilitätsrichtlinien in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="8aa33-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="8aa33-106">So erstellen Sie eine Mobilitätsrichtlinie mit lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="8aa33-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8aa33-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8aa33-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8aa33-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8aa33-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8aa33-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8aa33-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8aa33-110">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie** .</span><span class="sxs-lookup"><span data-stu-id="8aa33-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="8aa33-111">Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf **neu**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8aa33-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="8aa33-112">Klicken Sie zum Erstellen einer Website Mobilitätsrichtlinie auf **Website Richtlinie**, klicken Sie auf einen Standort, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="8aa33-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="8aa33-113">Um eine Benutzer Mobilitätsrichtlinie zu erstellen, klicken Sie auf **Benutzerrichtlinie**, geben Sie einen Namen ein, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="8aa33-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="8aa33-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8aa33-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="8aa33-115">So ändern Sie eine Mobilitätsrichtlinie mit lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="8aa33-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8aa33-116">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8aa33-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8aa33-117">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8aa33-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8aa33-118">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8aa33-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8aa33-119">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie** .</span><span class="sxs-lookup"><span data-stu-id="8aa33-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="8aa33-120">Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf eine der vorhandenen mobilitätsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="8aa33-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="8aa33-121">Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="8aa33-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8aa33-122">Bearbeiten Sie eine der Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8aa33-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="8aa33-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8aa33-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8aa33-124">Erstellen von Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8aa33-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8aa33-125">Sie können mobilitätsrichtlinien (auf Standortebene oder auf Benutzerebene) erstellen, indem Sie Windows PowerShell und das Cmdlet **New-CsMobilityPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aa33-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="8aa33-126">Darüber hinaus können Sie mit dem Cmdlet " **CsMobilityPolicy** " alle vorhandenen Richtlinien ändern, einschließlich der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="8aa33-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="8aa33-127">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8aa33-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8aa33-128">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="8aa33-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="8aa33-129">So erstellen Sie eine Mobilitätsrichtlinie auf Standortebene</span><span class="sxs-lookup"><span data-stu-id="8aa33-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="8aa33-130">Mit diesem Befehl wird eine neue Mobilitätsrichtlinie für den Standort "Redmond" erstellt:</span><span class="sxs-lookup"><span data-stu-id="8aa33-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="8aa33-131">Da im vorherigen Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden die Standardwerte für alle Eigenschaften der Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="8aa33-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="8aa33-132">So erstellen Sie eine Mobilitätsrichtlinie auf Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="8aa33-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="8aa33-133">Um eine Mobilitätsrichtlinie auf Benutzerebene zu erstellen, geben Sie eine eindeutige Identität für die Richtlinie an:</span><span class="sxs-lookup"><span data-stu-id="8aa33-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="8aa33-134">So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen einer Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8aa33-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="8aa33-135">Um Richtlinien mit unterschiedlichen Eigenschaftswerten zu erstellen, schließen Sie den entsprechenden Parameter und Parameterwert ein.</span><span class="sxs-lookup"><span data-stu-id="8aa33-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="8aa33-136">Mit diesem Befehl wird beispielsweise eine Mobilitätsrichtlinie erstellt, mit der die Funktion "Anruf über Arbeit" deaktiviert wird:</span><span class="sxs-lookup"><span data-stu-id="8aa33-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="8aa33-137">So ändern Sie beim Erstellen einer Mobilitätsrichtlinie mehrere Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="8aa33-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="8aa33-138">Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8aa33-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="8aa33-139">Mit diesem Befehl wird beispielsweise eine Richtlinie erstellt, die sowohl die Mobilität als auch die Funktion "Anruf über" deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="8aa33-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="8aa33-140">Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) und [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .</span><span class="sxs-lookup"><span data-stu-id="8aa33-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8aa33-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8aa33-141">See Also</span></span>


[<span data-ttu-id="8aa33-142">Konfigurieren von mobilitätsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa33-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

