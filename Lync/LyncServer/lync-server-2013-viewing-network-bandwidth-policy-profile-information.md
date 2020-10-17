---
title: 'Lync Server 2013: Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite'
description: 'Lync Server 2013: Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c72a3533ae6f49f91db91b2c3b515c0b5153ec27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565401"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="1163e-103">Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1163e-103">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1163e-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1163e-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1163e-105">Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1163e-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="1163e-106">In Microsoft lync Server 2013 können nur Audio-und Video Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1163e-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="1163e-107">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="1163e-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="1163e-108">Sie können das lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1163e-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="1163e-109">Jedes Bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1163e-109">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="1163e-110">Verwenden Sie die folgenden Verfahren, um ein Bandbreitenrichtlinienprofil anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1163e-110">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="1163e-111">Informationen zum Erstellen oder Ändern eines Richtlinienprofils für Bandbreiten finden Sie unter [erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1163e-111">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="1163e-112">So zeigen Sie ein bandbreitenrichtlinienprofil an</span><span class="sxs-lookup"><span data-stu-id="1163e-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="1163e-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1163e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1163e-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1163e-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1163e-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1163e-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1163e-116">Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="1163e-116">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="1163e-117">Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="1163e-117">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="1163e-118">Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="1163e-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1163e-119">Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1163e-119">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1163e-120">Netzwerkbandbreiten-Profile können mithilfe von Windows PowerShell und dem Get-CsNetworkBandwidthPolicyProfile-Cmdlet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1163e-120">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="1163e-121">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1163e-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1163e-122">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1163e-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="1163e-123">So zeigen Sie Informationen zum Netzwerkband breiten Richtlinienprofil an</span><span class="sxs-lookup"><span data-stu-id="1163e-123">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="1163e-124">Wenn Sie Informationen zu allen Richtlinienprofilen für die Netzwerkbandbreite anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1163e-124">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="1163e-125">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="1163e-125">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="1163e-126">Weitere Informationen finden Sie in dem Hilfethema zum [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1163e-126">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1163e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1163e-127">See Also</span></span>


[<span data-ttu-id="1163e-128">Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1163e-128">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="1163e-129">Löschen von Richtlinienprofilen für Netzwerkbandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1163e-129">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="1163e-130">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1163e-130">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

