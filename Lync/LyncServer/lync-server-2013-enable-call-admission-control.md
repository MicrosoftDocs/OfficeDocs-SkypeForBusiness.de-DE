---
title: 'Lync Server 2013: Aktivieren der Anrufsteuerung'
description: 'Lync Server 2013: Aktivieren Sie die Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bd352d407c3b14ac90a76fd6d53ccb312cab7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551581"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="73ca3-103">Aktivieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73ca3-103">Enable call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73ca3-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="73ca3-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="73ca3-105">Nachdem Sie die Ihre Netzwerkeinstellungen für die Bereitstellung der Anrufsteuerung konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreitenrichtlinien anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="73ca3-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="73ca3-106">Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation zu den folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="73ca3-106">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="73ca3-107">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="73ca3-107">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="73ca3-108">Gruppe-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="73ca3-108">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="73ca3-109">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="73ca3-109">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="73ca3-110">So aktivieren Sie die Anrufsteuerung mithilfe der Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="73ca3-110">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="73ca3-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="73ca3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="73ca3-p101">Führen Sie das Cmdlet "Set-CsNetworkConfiguration" aus, um die Anrufsteuerung in Ihrem Netzwerk zu aktivieren. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="73ca3-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="73ca3-114">Wenn Sie die Anrufsteuerung in Ihrem Netzwerk deaktivieren möchten, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="73ca3-114">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="73ca3-115">So aktivieren Sie die Anrufsteuerung mithilfe der Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="73ca3-115">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="73ca3-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73ca3-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73ca3-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73ca3-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="73ca3-118">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="73ca3-118">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="73ca3-119">Klicken Sie auf die Navigationsschaltfläche **Global**.</span><span class="sxs-lookup"><span data-stu-id="73ca3-119">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="73ca3-120">Klicken Sie in der Liste auf **Global**, und wählen Sie anschließend im Menü **Bearbeiten** die Option **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="73ca3-120">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="73ca3-121">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="73ca3-121">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73ca3-122">Wenn Sie die Anrufsteuerung innerhalb Ihrer Bereitstellung deaktivieren möchten, deaktivieren Sie dieses Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="73ca3-122">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="73ca3-123">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="73ca3-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

