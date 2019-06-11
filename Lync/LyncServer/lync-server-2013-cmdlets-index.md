---
title: 'Lync Server 2013: Cmdlets-Index'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d18b599792d2599d96b4775aa37a4178f99d1e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a><span data-ttu-id="7abc2-102">Lync Server 2013-Cmdlets-Index</span><span class="sxs-lookup"><span data-stu-id="7abc2-102">Lync Server 2013 cmdlets index</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7abc2-103">_**Letztes Änderungsdatum des Themas:** 2016-04-12_</span><span class="sxs-lookup"><span data-stu-id="7abc2-103">_**Topic Last Modified:** 2016-04-12_</span></span>

<span data-ttu-id="7abc2-104">Microsoft lync Server 2013 ist mit mehr als 700 Cmdlets ausgeliefert, mit denen Administratoren lync Server 2013 über die Befehlszeile verwalten können.</span><span class="sxs-lookup"><span data-stu-id="7abc2-104">Microsoft Lync Server 2013 ships with more than 700 cmdlets that enable administrators to manage Lync Server 2013 from the command line.</span></span> <span data-ttu-id="7abc2-105">Die lync Server-Cmdlets werden in der Regel mit der lync Server-Verwaltungsshell verwendet.</span><span class="sxs-lookup"><span data-stu-id="7abc2-105">The Lync Server cmdlets are typically used with the Lync Server Management Shell.</span></span> <span data-ttu-id="7abc2-106">Eine Möglichkeit, die lync Server-Verwaltungsshell zu verwenden, ist die Anmeldung an einem Computer, auf dem ein lync Server-Dienst oder eine Serverrolle ausgeführt wird, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf \*\*lync Server-Verwaltungsshell. \*\*.</span><span class="sxs-lookup"><span data-stu-id="7abc2-106">One way to use the Lync Server Management Shell is to log on to a computer running a Lync Server service or server role, click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="7abc2-107">Nach dem Öffnen der Verwaltungsshell können Sie Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen Befehl ähnlich der folgenden eingeben:</span><span class="sxs-lookup"><span data-stu-id="7abc2-107">After the Management Shell is open you can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="7abc2-108">Mit dem oben genannten Befehl rufen Sie alle verfügbaren Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** ab.</span><span class="sxs-lookup"><span data-stu-id="7abc2-108">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="7abc2-109">Wenn Sie Hilfeinformationen zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, zu dem Sie Hilfeinformationen abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="7abc2-109">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="7abc2-110">Wenn Sie eine vollständige Liste der für die Verwaltung von lync Server verfügbaren Cmdlets abrufen möchten, geben Sie Folgendes an der Eingabeaufforderung der lync Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="7abc2-110">To retrieve a full list of cmdlets available for managing Lync Server, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="7abc2-111">Ausführliche Informationen zur Verwendung der lync Server-Verwaltungsshell finden Sie im Windows PowerShell-Blog von [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150)lync Server unter.</span><span class="sxs-lookup"><span data-stu-id="7abc2-111">For details about using the Lync Server Management Shell, see the Lync Server Windows PowerShell blog at [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

<div>

## <a name="lync-server-2013-cmdlets"></a><span data-ttu-id="7abc2-112">Lync Server 2013-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7abc2-112">Lync Server 2013 Cmdlets</span></span>

<span data-ttu-id="7abc2-113">Es folgt eine Liste der Cmdlets, die im Lieferumfang von lync Server 2013 enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="7abc2-113">Following is a list of the cmdlets that ship with Lync Server 2013:</span></span>

  - <span data-ttu-id="7abc2-114">[Add-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-114">[Add-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-115">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-115">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-116">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-116">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-117">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-117">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-118">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-118">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-119">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-119">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-120">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-120">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-121">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-121">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-122">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-122">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-123">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-123">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-124">[Deaktivieren-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-124">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-125">[Deaktivieren-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-125">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-126">[Deaktivieren-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-126">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-127">[Deaktivieren-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-128">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-128">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-129">[Deaktivieren-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-129">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-130">[Deaktivieren-CsUser](https://technet.microsoft.com/en-us/library/Gg398747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-130">[Disable-CsUser](https://technet.microsoft.com/en-us/library/Gg398747(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-131">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-131">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-132">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-132">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-133">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-133">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-134">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-134">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-135">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-135">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-136">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-136">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-137">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-137">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-138">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-138">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-139">[Enable-CsUser](https://technet.microsoft.com/en-us/library/Gg398711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-139">[Enable-CsUser](https://technet.microsoft.com/en-us/library/Gg398711(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-140">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-140">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-141">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-141">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-142">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-142">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-143">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-143">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-144">[Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-144">[Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-145">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-145">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-146">[Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-146">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-147">[Get-CsAdContact](https://technet.microsoft.com/en-us/library/Gg412776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-147">[Get-CsAdContact](https://technet.microsoft.com/en-us/library/Gg412776(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-148">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-148">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-149">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-149">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-150">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-150">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-151">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-151">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-152">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-152">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-153">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-153">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-154">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-154">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-155">[Get-CsAdUser](https://technet.microsoft.com/en-us/library/Gg398592(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-155">[Get-CsAdUser](https://technet.microsoft.com/en-us/library/Gg398592(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-156">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-156">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-157">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-157">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-158">[Get-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-158">[Get-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-159">[Get-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398655(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-159">[Get-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398655(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-160">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-160">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-161">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-161">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-162">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-162">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-163">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-163">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-164">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-164">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-165">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-165">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-166">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-166">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-167">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-167">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-168">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-168">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-169">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-169">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-170">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-170">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-171">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-171">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-172">[Get-CsClientAccessLicense](https://technet.microsoft.com/en-us/library/JJ204853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-172">[Get-CsClientAccessLicense](https://technet.microsoft.com/en-us/library/JJ204853(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-173">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-173">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-174">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-174">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-175">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-175">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-176">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-176">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-177">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-177">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-178">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-178">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-179">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-179">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-180">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-180">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-181">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-181">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-182">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-182">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-183">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-183">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-184">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-184">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-185">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-185">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-186">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-186">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-187">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-187">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-188">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-188">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-189">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-189">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-190">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-190">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-191">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-191">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-192">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-192">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-193">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-193">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-194">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-194">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-195">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-195">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-196">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-196">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-197">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-197">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-198">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-198">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-199">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-199">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-200">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-200">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-201">[Get-CsEffectivePolicy](https://technet.microsoft.com/en-us/library/JJ204636(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-201">[Get-CsEffectivePolicy](https://technet.microsoft.com/en-us/library/JJ204636(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-202">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-202">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-203">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-203">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-204">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-204">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-205">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-205">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-206">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-206">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-207">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-207">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-208">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-208">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-209">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-209">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-210">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-210">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-211">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-211">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-212">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-212">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-213">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-213">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-214">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-214">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-215">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-215">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-216">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-216">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-217">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-217">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-218">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-218">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-219">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-219">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-220">[Get-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg412849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-220">[Get-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg412849(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-221">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-221">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-222">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-222">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-223">[Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-223">[Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-224">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-224">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-225">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-225">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-226">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-226">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-227">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-227">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-228">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-228">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-229">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-229">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-230">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-230">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-231">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-231">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-232">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-232">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-233">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-233">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-234">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-234">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-235">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-235">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-236">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-236">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-237">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-237">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-238">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-238">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-239">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-239">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-240">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-240">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-241">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-241">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-242">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-242">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-243">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-243">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-244">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-244">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-245">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-245">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-246">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-246">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-247">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-247">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-248">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-248">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-249">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-249">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-250">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-250">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-251">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-251">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-252">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-252">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-253">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-253">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-254">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-254">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-255">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-255">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-256">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-256">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-257">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-257">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-258">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-258">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-259">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-259">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-260">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-260">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-261">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-261">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-262">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-262">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-263">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-263">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-264">[Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-264">[Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-265">[Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-265">[Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-266">[Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-266">[Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-267">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-267">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-268">[Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-268">[Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-269">[Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-269">[Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-270">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-270">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-271">[Get-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg425948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-271">[Get-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg425948(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-272">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-272">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-273">[Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-273">[Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-274">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-274">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-275">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-275">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-276">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-276">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-277">[Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-277">[Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-278">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-278">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-279">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-279">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-280">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-280">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-281">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-281">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-282">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-282">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-283">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-283">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-284">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-284">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-285">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-285">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-286">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-286">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-287">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-287">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-288">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-288">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-289">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-289">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-290">[Get-CsUICulture](https://technet.microsoft.com/en-us/library/Gg412900(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-290">[Get-CsUICulture](https://technet.microsoft.com/en-us/library/Gg412900(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-291">[Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-291">[Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-292">[Get-CsUser](https://technet.microsoft.com/en-us/library/Gg398125(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-292">[Get-CsUser](https://technet.microsoft.com/en-us/library/Gg398125(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-293">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-293">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-294">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-294">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-295">[Get-CsUserPoolInfo](https://technet.microsoft.com/en-us/library/Gg398615(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-295">[Get-CsUserPoolInfo](https://technet.microsoft.com/en-us/library/Gg398615(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-296">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-296">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-297">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-297">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-298">[Get-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-298">[Get-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204838(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-299">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-299">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-300">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-300">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-301">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-301">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-302">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-302">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-303">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-303">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-304">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-304">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-305">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-305">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-306">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-306">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-307">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-307">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-308">[Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-308">[Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-309">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-309">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-310">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-310">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-311">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-311">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-312">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-312">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-313">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-313">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-314">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-314">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-315">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-315">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-316">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-316">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-317">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-317">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-318">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-318">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-319">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-319">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-320">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-320">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-321">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-321">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-322">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-322">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-323">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-323">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-324">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-324">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-325">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205388(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-325">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205388(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-326">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-326">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-327">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-327">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-328">[Import-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-328">[Import-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-329">[Importieren-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-329">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-330">[Importieren-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-330">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-331">[Importieren-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-331">[Import-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-332">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-332">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-333">[Importieren-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-333">[Import-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-334">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-334">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-335">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-335">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-336">[Importieren-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-336">[Import-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-337">[Import-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-337">[Import-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-338">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-338">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-339">[Installieren-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-339">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-340">[Installieren-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-340">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-341">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-341">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-342">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-342">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-343">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-343">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-344">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-344">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-345">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-345">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-346">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-346">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-347">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-347">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-348">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-348">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-349">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-349">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-350">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-350">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-351">[Invoke-CsUcsRollback](https://technet.microsoft.com/en-us/library/JJ204661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-351">[Invoke-CsUcsRollback](https://technet.microsoft.com/en-us/library/JJ204661(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-352">[Sperren-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-352">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-353">[Zusammenführen – CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-353">[Merge-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-354">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-354">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-355">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-355">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-356">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-356">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-357">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-357">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-358">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-358">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-359">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-359">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-360">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-360">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-361">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-361">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-362">[Verschieben-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-362">[Move-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-363">[Verschieben-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-363">[Move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-364">[Neu – CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-364">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-365">[Neu – CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-365">[New-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-366">[Neu – CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-366">[New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-367">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-367">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-368">[Neu – CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-368">[New-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-369">[Neu – CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-369">[New-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-370">[Neu – CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-370">[New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-371">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-371">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-372">[Neu – CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-372">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-373">[Neu – CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-373">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-374">[Neu – CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-374">[New-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-375">[Neu – CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-375">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-376">[Neu – CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-376">[New-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-377">[Neu – CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-377">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-378">[Neu – CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-378">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-379">[Neu – CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-379">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-380">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-380">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-381">[Neu – CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-381">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-382">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-382">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-383">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-383">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-384">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-384">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-385">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-385">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-386">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-386">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-387">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-387">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-388">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-388">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-389">[Neu – CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-389">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-390">[Neu – CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-390">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-391">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-391">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-392">[Neu – CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-392">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-393">[Neu – CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-393">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-394">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-394">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-395">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-395">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-396">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-396">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-397">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-397">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-398">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-398">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-399">[Neu – CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-399">[New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-400">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-400">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-401">[Neu – CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-401">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-402">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-402">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-403">[Neu – CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-403">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-404">[Neu – CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-404">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-405">[Neu – CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-405">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-406">[Neu – CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-406">[New-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-407">[Neu – CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-407">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-408">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-408">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-409">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-409">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-410">[Neu – CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-410">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-411">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-411">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-412">[Neu – CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-412">[New-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-413">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-413">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-414">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-414">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-415">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-415">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-416">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-416">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-417">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-417">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-418">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-418">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-419">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-419">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-420">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-420">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-421">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-421">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-422">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-422">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-423">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-423">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-424">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-424">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-425">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-425">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-426">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-426">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-427">[Neu – CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-427">[New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-428">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-428">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-429">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-429">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-430">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-430">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-431">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-431">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-432">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-432">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-433">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-433">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-434">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-434">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-435">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-435">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-436">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-436">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-437">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-437">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-438">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-438">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-439">[Neu – CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-439">[New-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-440">[Neu – CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-440">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-441">[Neu – CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-441">[New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-442">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-442">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-443">[Neu – CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-443">[New-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-444">[Neu – CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-444">[New-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-445">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-445">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-446">[Neu – CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-446">[New-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-447">[Neu – CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-447">[New-CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-448">[Neu – CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-448">[New-CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-449">[Neu – CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-449">[New-CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-450">[Neu – CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-450">[New-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-451">[Neu – CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-451">[New-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-452">[New-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-452">[New-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-453">[Neu – CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-453">[New-CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-454">[Neu – CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-454">[New-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-455">[Neu – CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-455">[New-CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-456">[Neu – CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-456">[New-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-457">[Neu – CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-457">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-458">[Neu – CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398096(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-458">[New-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398096(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-459">[Neu – CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-459">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-460">[Neu – CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-460">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-461">[Neu – CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-461">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-462">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-462">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-463">[Neu – CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-463">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-464">[Neu – CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-464">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-465">[Neu – CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-465">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-466">[Neu – CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-466">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-467">[Neu – CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-467">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-468">[Neu – CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-468">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-469">[Neu – CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-469">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-470">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-470">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-471">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-471">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-472">[Neu – CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-472">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-473">[Neu – CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-473">[New-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-474">[Neu – CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-474">[New-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-475">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-475">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-476">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-476">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-477">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-477">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-478">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-478">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-479">[Neu – CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-479">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-480">[New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-480">[New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-481">[Neu – CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-481">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-482">[Neu – CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-482">[New-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-483">[New-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-483">[New-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205072(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-484">[Neu – CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-484">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-485">[Neu – CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-485">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-486">[Neu – CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-486">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-487">[Neu – CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-487">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-488">[Neu – CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-488">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-489">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-489">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-490">[Neu – CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-490">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-491">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-491">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-492">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-492">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-493">[Neu – CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-493">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-494">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-494">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-495">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-495">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-496">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-496">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-497">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-497">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-498">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-498">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-499">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-499">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-500">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-500">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-501">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-501">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-502">[Remove-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-502">[Remove-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-503">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-503">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-504">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-504">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-505">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-505">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-506">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-506">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-507">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-507">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-508">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-508">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-509">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-509">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-510">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-510">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-511">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-511">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-512">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-512">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-513">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-513">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-514">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-514">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-515">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-515">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-516">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-516">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-517">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-517">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-518">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-518">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-519">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-519">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-520">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-520">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-521">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-521">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-522">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-522">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-523">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-523">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-524">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-524">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-525">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-525">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-526">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-526">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-527">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-527">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-528">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-528">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-529">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-529">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-530">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-530">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-531">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-531">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-532">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-532">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-533">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-533">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-534">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-534">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-535">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-535">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-536">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-536">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-537">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-537">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-538">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-538">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-539">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-539">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-540">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-540">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-541">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-541">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-542">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-542">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-543">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-543">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-544">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-544">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-545">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-545">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-546">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-546">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-547">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-547">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-548">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-548">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-549">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-549">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-550">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-550">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-551">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-551">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-552">[Remove-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg425803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-552">[Remove-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg425803(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-553">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-553">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-554">[Remove-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-554">[Remove-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-555">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-555">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-556">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-556">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-557">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-557">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-558">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-558">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-559">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-559">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-560">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-560">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-561">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-561">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-562">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-562">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-563">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-563">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-564">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-564">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-565">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-565">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-566">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-566">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-567">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-567">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-568">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-568">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-569">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-569">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-570">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-570">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-571">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-571">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-572">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-572">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-573">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-573">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-574">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-574">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-575">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-575">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-576">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-576">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-577">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-577">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-578">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-578">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-579">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-579">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-580">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-580">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-581">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-581">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-582">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-582">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-583">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-583">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-584">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-584">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-585">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-585">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-586">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-586">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-587">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-587">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-588">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-588">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-589">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-589">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-590">[Remove-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-590">[Remove-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-591">[Remove-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-591">[Remove-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-592">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-592">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-593">[Remove-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398366(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-593">[Remove-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398366(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-594">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-594">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-595">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-595">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-596">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-596">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-597">[Remove-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-597">[Remove-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-598">[Remove-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-598">[Remove-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-599">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-599">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-600">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-600">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-601">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-601">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-602">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-602">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-603">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-603">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-604">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-604">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-605">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-605">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-606">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-606">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-607">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-607">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-608">[Remove-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-608">[Remove-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-609">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-609">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-610">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-610">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-611">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-611">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-612">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-612">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204629(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-613">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-613">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-614">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-614">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-615">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-615">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-616">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-616">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-617">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-617">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-618">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-618">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-619">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-619">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-620">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-620">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-621">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-621">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-622">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-622">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-623">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-623">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-624">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-624">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-625">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-625">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-626">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-626">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-627">[REVOKE-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-627">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-628">[REVOKE-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-628">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-629">[REVOKE-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-629">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-630">[Satz-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-630">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-631">[Satz-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-631">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-632">[Satz-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-632">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-633">[Satz-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-633">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-634">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-634">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-635">[Satz-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-635">[Set-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-636">[Satz-CsApplicationServer](https://technet.microsoft.com/en-us/library/Gg398562(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-636">[Set-CsApplicationServer](https://technet.microsoft.com/en-us/library/Gg398562(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-637">[Satz-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-637">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-638">[Satz-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-638">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-639">[Satz-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-639">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-640">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-640">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-641">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-641">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-642">[Satz-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-642">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-643">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-643">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-644">[Satz-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-644">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-645">[Satz-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-645">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-646">[Satz-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-646">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-647">[Satz-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-647">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-648">[Satz-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-648">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-649">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-649">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-650">[Satz-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-650">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-651">[Satz-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-651">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-652">[Satz-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-652">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-653">[Satz-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-653">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-654">[Satz-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-654">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-655">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-655">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-656">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-656">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-657">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-657">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-658">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-658">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-659">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-659">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-660">[Satz-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-660">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-661">[Satz-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-661">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-662">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-662">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-663">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-663">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-664">[Satz-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-664">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-665">[Satz-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-665">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-666">[Satz-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-666">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-667">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-667">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-668">[Satz-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-668">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-669">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-669">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-670">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-670">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-671">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-671">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-672">[Satz-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15)) Satz-CsDialPlan</span><span class="sxs-lookup"><span data-stu-id="7abc2-672">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))Set-CsDialPlan</span></span>

  - <span data-ttu-id="7abc2-673">[Satz-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-673">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-674">[Satz-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-674">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-675">[Satz-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-675">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-676">[Satz-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-676">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-677">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-677">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-678">[Satz-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-678">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-679">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-679">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-680">[Satz-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-680">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-681">[Satz-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-681">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-682">[Satz-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-682">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-683">[Satz-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-683">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-684">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-684">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-685">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-685">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-686">[Satz-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-686">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-687">[Satz-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-687">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-688">[Satz-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-688">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-689">[Satz-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-689">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-690">[Satz-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-690">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-691">[Satz-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-691">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-692">[Satz-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-692">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-693">[Satz-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg413045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-693">[Set-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg413045(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-694">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-694">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-695">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-695">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-696">[Satz-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-696">[Set-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-697">[Satz-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-697">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-698">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-698">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-699">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-699">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-700">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-700">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-701">[Satz-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-701">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-702">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-702">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-703">[Satz-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-703">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-704">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-704">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-705">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-705">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-706">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-706">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-707">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-707">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-708">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-708">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-709">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-709">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-710">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-710">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-711">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-711">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-712">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-712">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-713">[Satz-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-713">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-714">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-714">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-715">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-715">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-716">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-716">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-717">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-717">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-718">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-718">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-719">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-719">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-720">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-720">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-721">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-721">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-722">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-722">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-723">[Satz-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-723">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-724">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-724">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-725">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-725">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-726">[Satz-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-726">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-727">[Satz-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-727">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-728">[Satz-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-728">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-729">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-729">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-730">[Satz-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-730">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-731">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-731">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-732">[Satz-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-732">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-733">[Satz-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-733">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-734">[Satz-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-734">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-735">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-735">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-736">[Satz-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-736">[Set-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-737">[Satz-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-737">[Set-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-738">[Satz-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-738">[Set-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-739">[Satz-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-739">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-740">[Satz-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-740">[Set-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-741">[Satz-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-741">[Set-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-742">[Satz-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-742">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-743">[Satz-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg412850(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-743">[Set-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg412850(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-744">[Satz-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-744">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-745">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-745">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-746">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-746">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-747">[Satz-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-747">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-748">[Satz-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-748">[Set-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-749">[Satz-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-749">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-750">[Satz-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-750">[Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-751">[Satz-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-751">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-752">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-752">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-753">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-753">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-754">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-754">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-755">[Satz-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-755">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-756">[Set-CsUICulture](https://technet.microsoft.com/en-us/library/Gg398354(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-756">[Set-CsUICulture](https://technet.microsoft.com/en-us/library/Gg398354(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-757">[Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-757">[Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-758">[Satz-CsUser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-758">[Set-CsUser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-759">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-759">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-760">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-760">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-761">[Satz-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-761">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-762">[Satz-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-762">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-763">[Satz-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-763">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-764">[Set-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205414(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-764">[Set-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205414(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-765">[Satz-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-765">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-766">[Satz-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-766">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-767">[Satz-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-767">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-768">[Satz-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-768">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-769">[Satz-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-769">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-770">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-770">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-771">[Satz-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-771">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-772">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-772">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-773">[Satz-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-773">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-774">[Satz-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-774">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-775">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-775">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-776">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-776">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-777">[Anfang-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-777">[Start-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-778">[Stopp-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-778">[Stop-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-779">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-779">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-780">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-780">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-781">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-781">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-782">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-782">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-783">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ205117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-783">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ205117(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-784">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-784">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-785">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-785">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-786">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-786">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-787">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-787">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-788">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-788">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-789">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-789">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-790">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-790">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-791">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-791">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-792">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-792">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-793">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-793">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-794">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-794">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-795">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-795">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-796">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-796">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-797">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-797">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-798">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-798">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-799">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-799">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-800">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-800">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-801">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-801">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-802">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-802">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-803">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-803">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-804">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-804">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-805">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-805">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-806">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-806">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-807">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-807">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-808">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-808">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-809">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-809">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-810">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-810">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-811">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-811">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-812">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-812">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-813">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-813">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-814">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-814">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-815">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-815">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-816">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-816">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-817">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-817">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-818">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-818">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-819">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-819">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-820">[Test-CsUnifiedContactStore](https://technet.microsoft.com/en-us/library/JJ204662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-820">[Test-CsUnifiedContactStore](https://technet.microsoft.com/en-us/library/JJ204662(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-821">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-821">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-822">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-822">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-823">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-823">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-824">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-824">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-825">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-825">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-826">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-826">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-827">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-827">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-828">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-828">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-829">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-829">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-830">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-830">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-831">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-831">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-832">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-832">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-833">[Entsperren-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-833">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-834">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-834">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-835">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-835">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-836">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-836">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-837">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-837">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-838">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-838">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span></span>

  - <span data-ttu-id="7abc2-839">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7abc2-839">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

