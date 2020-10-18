---
title: 'Lync Server 2013: Konfigurieren von Netzwerkstandort Links'
description: 'Lync Server 2013: Konfigurieren von Netzwerkstandort Links.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68b4ecce15b8f3ba5a5717c73a8f97f8a0633b58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572931"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="ad653-103">Konfigurieren von Netzwerkstandort Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad653-103">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad653-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ad653-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ad653-105">Innerhalb einer Anrufsteuerung (Call Admission Control, CAC) können Sie standortübergreifende Netzwerkrichtlinien erstellen, die Bandbreiteneinschränkungen zwischen Websites definieren, die direkt verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ad653-105">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="ad653-106">Wenn Netzwerkstandorte eine direkte Verbindung teilen, können Bandbreiteneinschränkungen für Audio- und Videoverbindungen zwischen diesen zwei Standorten definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad653-106">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="ad653-107">Sie können die lync Server-Systemsteuerung nicht zum Konfigurieren von Netzwerkstandort Richtlinien verwenden, dies kann nur mithilfe von Cmdlets aus dem lync Server-Verwaltungsshell erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ad653-107">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="ad653-108">Sie können eine netzwerkstandortverknüpfung (auch als standortübergreifende Netzwerkrichtlinie bezeichnet) aus dem lync Server-Verwaltungsshell erstellen, ändern und entfernen.</span><span class="sxs-lookup"><span data-stu-id="ad653-108">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="ad653-109">So erstellen Sie eine Netzwerkstandortverknüpfung</span><span class="sxs-lookup"><span data-stu-id="ad653-109">To create a network site link</span></span>

1.  <span data-ttu-id="ad653-110">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad653-110">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ad653-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ad653-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ad653-112">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und verwenden Sie dabei die für Ihre Konfiguration gültigen Werte:</span><span class="sxs-lookup"><span data-stu-id="ad653-112">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="ad653-113">In diesem Beispiel wird eine neue netzwerkstandortverknüpfung namens Reno \_ Portland erstellt, die Bandbreiteneinschränkungen zwischen den Netzwerkstandorten "Reno" und "Portland" festlegt.</span><span class="sxs-lookup"><span data-stu-id="ad653-113">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="ad653-114">Die Netzwerkstandorte und das Bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="ad653-114">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="ad653-115">Ausführliche Parameterbeschreibungen finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad653-115">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="ad653-116">Zum Abrufen einer Liste der Bandbreitenrichtlinienprofile, die auf die Netzwerkstandortverknüpfung angewendet werden können, verwenden Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="ad653-116">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="ad653-117">Ausführliche Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad653-117">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="ad653-118">So ändern Sie eine Netzwerkstandortverknüpfung</span><span class="sxs-lookup"><span data-stu-id="ad653-118">To modify a network site link</span></span>

1.  <span data-ttu-id="ad653-119">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad653-119">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ad653-120">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ad653-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ad653-121">Verwenden Sie das Cmdlet **Set-CsNetworkInterSitePolicy**, um die Eigenschaften einer Netzwerkstandortverknüpfung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ad653-121">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="ad653-122">Sie können entweder einen oder beide verbundenen Standorte ändern, und Sie können das der Verknüpfung zugeordnete Bandbreitenrichtlinienprofil bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad653-122">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="ad653-123">Hier ist ein Beispiel für das Ändern des bandbreitenrichtlinienprofils einer Website Verknüpfung namens Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="ad653-123">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="ad653-124">Ausführliche Parameterbeschreibungen finden Sie unter " [CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) " in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad653-124">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="ad653-125">So löschen Sie eine Netzwerkstandortverknüpfung</span><span class="sxs-lookup"><span data-stu-id="ad653-125">To delete a network site link</span></span>

1.  <span data-ttu-id="ad653-126">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad653-126">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ad653-127">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ad653-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ad653-128">Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy**, um eine Netzwerkstandortverknüpfung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ad653-128">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="ad653-129">Im folgenden Beispiel wird der Link für die Portland-Netzwerk Site von Reno gelöscht \_ :</span><span class="sxs-lookup"><span data-stu-id="ad653-129">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="ad653-130">Ausführliche Parameterbeschreibungen finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad653-130">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad653-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad653-131">See Also</span></span>


[<span data-ttu-id="ad653-132">Cmdlets für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad653-132">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="ad653-133">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ad653-133">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ad653-134">Gruppe-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ad653-134">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ad653-135">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ad653-135">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ad653-136">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ad653-136">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="ad653-137">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ad653-137">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

