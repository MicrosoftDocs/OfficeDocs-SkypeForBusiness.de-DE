---
title: 'Lync Server 2013: Anzeigen von Profilinformationen für die Netzwerkbandbreite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 513bd20e9a1ecd40f061c4873e7da8bff4738f36
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="24fc6-102">Anzeigen von Profilinformationen zu Netzwerkbandbreiten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fc6-102">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24fc6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="24fc6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="24fc6-104">Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="24fc6-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="24fc6-105">In Microsoft lync Server 2013 können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="24fc6-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="24fc6-106">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="24fc6-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="24fc6-107">Sie können die lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="24fc6-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="24fc6-108">Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="24fc6-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="24fc6-109">Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="24fc6-109">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="24fc6-110">Informationen zum Erstellen oder Ändern eines Profils für Bandbreitenrichtlinien finden Sie unter [erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="24fc6-110">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="24fc6-111">So zeigen Sie ein bandbreitenrichtlinienprofil an</span><span class="sxs-lookup"><span data-stu-id="24fc6-111">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="24fc6-112">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="24fc6-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24fc6-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="24fc6-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24fc6-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24fc6-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24fc6-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="24fc6-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="24fc6-116">Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="24fc6-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="24fc6-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="24fc6-117">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="24fc6-118">Anzeigen von Profilinformationen für die Netzwerkbandbreite mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="24fc6-118">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="24fc6-119">Netzwerkbandbreiten Profile können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkBandwidthPolicyProfile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="24fc6-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="24fc6-120">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="24fc6-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24fc6-121">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="24fc6-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="24fc6-122">So zeigen Sie Profilinformationen zu Netzwerkbandbreiten an</span><span class="sxs-lookup"><span data-stu-id="24fc6-122">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="24fc6-123">Wenn Sie Informationen zu allen Richtlinienprofilen für Netzwerkbandbreite anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="24fc6-123">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="24fc6-124">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="24fc6-124">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="24fc6-125">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="24fc6-125">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24fc6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24fc6-126">See Also</span></span>


[<span data-ttu-id="24fc6-127">Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fc6-127">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="24fc6-128">Löschen von Netzwerkbandbreite-Richtlinienprofilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fc6-128">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="24fc6-129">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24fc6-129">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

