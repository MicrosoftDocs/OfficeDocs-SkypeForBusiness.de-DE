---
title: 'Lync Server 2013: Anzeigen von Softwareupdates für Geräte in Ihrer Organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="2b696-102">Anzeigen von Softwareupdates für Geräte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b696-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b696-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2b696-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2b696-104">Mit lync Server 2013 verwenden Sie den Geräte Update-Webdienst, um Softwareupdates für die Geräte Ihrer Organisation anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2b696-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="2b696-105">Diese Updates sind in CAB-Dateien (Cabinet) von der Microsoft [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)-Support Website unter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2b696-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="2b696-106">Führen Sie nach dem Herunterladen der CAB-Datei das Cmdlet " **Import-CSDeviceUpdate** " aus, um die geräteaktualisierungsregeln aus der CAB-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2b696-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="2b696-107">Details zum Cmdlet " **Import-CSDeviceUpdate** " finden Sie unter [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="2b696-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2b696-108">Bevor Sie ein neues Update für Ihre Organisation bereitstellen, stellen Sie sicher, dass es auf einem Testgerät ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2b696-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="2b696-109">So zeigen Sie Softwareupdates für UC-Geräte an</span><span class="sxs-lookup"><span data-stu-id="2b696-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="2b696-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2b696-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b696-111">Laden Sie auf der Microsoft [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)-Support Website unter die CAB-Datei an einen Speicherort auf einem lync Server 2013-Computer herunter (beispielsweise\\C\\: Updates ucupdates. cab).</span><span class="sxs-lookup"><span data-stu-id="2b696-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="2b696-112">Importieren Sie die geräteaktualisierungsregeln aus der Datei\\C\\: Updates ucupdates. cab, indem Sie eines der folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="2b696-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="2b696-113">Wenn sich die CAB-Datei auf demselben Computer befindet wie diejenige, die den zu aktualisierenden Dienst ausführt (Dienst: Redmond-websvc-2), führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="2b696-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="2b696-114">Wenn sich die CAB-Datei auf einem anderen Computer als derjenige befindet, der den zu aktualisierenden Dienst ausführt (Dienst: Redmond-websvc-3), führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="2b696-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="2b696-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2b696-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2b696-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2b696-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="2b696-117">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Geräteaktualisierung**.</span><span class="sxs-lookup"><span data-stu-id="2b696-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="2b696-118">Klicken Sie auf der Seite **Device Update** auf ein Update in der Liste, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2b696-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="2b696-119">**Abbrechen einer ausstehenden Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="2b696-119">**Cancel a pending update.**</span></span> <span data-ttu-id="2b696-120">Wenn Sie verhindern möchten, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird, klicken Sie auf das Menü **Aktion** und dann auf ausstehende **Updates Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="2b696-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="2b696-121">**Genehmigen eines Updates**</span><span class="sxs-lookup"><span data-stu-id="2b696-121">**Approve an update.**</span></span> <span data-ttu-id="2b696-122">Wenn Sie zulassen möchten, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird, klicken Sie auf das Menü **Aktion** und dann auf **genehmigen**.</span><span class="sxs-lookup"><span data-stu-id="2b696-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="2b696-123">**Wiederherstellen eines Updates**</span><span class="sxs-lookup"><span data-stu-id="2b696-123">**Restore an update.**</span></span> <span data-ttu-id="2b696-124">Wenn Sie zulassen möchten, dass ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt wird, klicken Sie auf das Menü **Aktion** und dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="2b696-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b696-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b696-125">See Also</span></span>


[<span data-ttu-id="2b696-126">Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b696-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

