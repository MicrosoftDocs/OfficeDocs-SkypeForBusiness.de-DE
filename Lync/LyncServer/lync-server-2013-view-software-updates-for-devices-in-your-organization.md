---
title: 'Lync Server 2013: Anzeigen von Softwareupdates für Geräte in Ihrer Organisation'
description: 'Lync Server 2013: Anzeigen von Softwareupdates für Geräte in Ihrer Organisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 833ab25315847b760271c63bbfca3ba8357e41c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558831"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="dff33-103">Anzeigen von Softwareupdates für Geräte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff33-103">View software updates for devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dff33-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dff33-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dff33-105">Mit lync Server 2013 verwenden Sie den Geräte Update-Webdienst, um Softwareupdates für die Geräte Ihrer Organisation anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="dff33-105">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="dff33-106">Diese Updates stehen in CAB-Dateien auf der Microsoft-Support Website unter zur Verfügung [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) .</span><span class="sxs-lookup"><span data-stu-id="dff33-106">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="dff33-107">Nachdem Sie die CAB-Datei heruntergeladen haben, führen Sie das Cmdlet **Import-CSDeviceUpdate** aus, um die geräteaktualisierungsregeln aus der CAB-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dff33-107">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="dff33-108">Ausführliche Informationen zum **Import-CSDeviceUpdate** -Cmdlet finden Sie unter [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="dff33-108">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="dff33-109">Bevor Sie ein neues Update in Ihrer Organisation bereitstellen, sollten Sie seine ordnungsgemäße Funktion auf einem Testgerät überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dff33-109">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="dff33-110">So zeigen Sie Softwareupdates für UC-Geräte an</span><span class="sxs-lookup"><span data-stu-id="dff33-110">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="dff33-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dff33-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dff33-112">Laden Sie die CAB-Datei von der Microsoft-Support Website unter an [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) einen Speicherort auf einem lync Server 2013 Computer herunter (beispielsweise C: \\ Updates \\UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="dff33-112">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="dff33-113">Importieren Sie die geräteaktualisierungsregeln aus der Datei C: \\ Updates \\UCUpdates.cab, indem Sie eines der folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="dff33-113">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="dff33-114">Wenn sich die CAB-Datei auf demselben Computer befindet wie der Dienst, der aktualisiert werden soll (service:Redmond-websvc-2), führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="dff33-114">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="dff33-115">Wenn sich die CAB-Datei auf einem anderen Computer befindet als der Dienst, der aktualisiert werden soll (service:Redmond-websvc-3), führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="dff33-115">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="dff33-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dff33-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dff33-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dff33-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="dff33-118">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteaktualisierung**.</span><span class="sxs-lookup"><span data-stu-id="dff33-118">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="dff33-119">Klicken Sie auf der Seite **Geräteaktualisierung** auf ein Update in der Liste, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="dff33-119">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="dff33-p103">**Abbrechen eines ausstehenden Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Ausstehende Updates abbrechen**, um die Bereitstellung des ausgewählten Updates auf den Geräten in Ihrer Organisation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="dff33-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="dff33-p104">**Genehmigen eines Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Genehmigen**, um die Bereitstellung des ausgewählten Updates auf den Geräten in Ihrer Organisation zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="dff33-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="dff33-p105">**Wiederherstellen eines Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Wiederherstellen**, um die Bereitstellung eines zuvor genehmigten Updates auf den Geräten in Ihrer Organisation zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="dff33-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dff33-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dff33-126">See Also</span></span>


[<span data-ttu-id="dff33-127">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff33-127">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

