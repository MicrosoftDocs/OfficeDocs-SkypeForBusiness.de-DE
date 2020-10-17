---
title: 'Lync Server 2013: Erstellen eines Geräts zum Testen der Update Funktionalität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf4d45edce186819241ce6244e1ea1cd6677bfa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501972"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="c84b8-102">Erstellen eines Geräts zum Testen der Update Funktionalität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c84b8-102">Create a device to test update functionality in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c84b8-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c84b8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c84b8-104">Sie können ein Gerät zur Seite **Testgerät** hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c84b8-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="c84b8-105">Sie können ein Gerät auf globaler Ebene (in der gesamten lync Server Umgebung) oder an einem einzelnen Standort testen.</span><span class="sxs-lookup"><span data-stu-id="c84b8-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="c84b8-106">Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer.</span><span class="sxs-lookup"><span data-stu-id="c84b8-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="c84b8-107">Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Test Gerät** des lync Server-Systemsteuerung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c84b8-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="c84b8-108">So fügen Sie ein Testgerät hinzu</span><span class="sxs-lookup"><span data-stu-id="c84b8-108">To add a test device</span></span>

1.  <span data-ttu-id="c84b8-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c84b8-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c84b8-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c84b8-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c84b8-111">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Testgerät**.</span><span class="sxs-lookup"><span data-stu-id="c84b8-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="c84b8-112">Klicken Sie auf **Neu** und anschließend entweder auf **Globales Testgerät** oder **Standorttestgerät**.</span><span class="sxs-lookup"><span data-stu-id="c84b8-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="c84b8-113">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c84b8-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="c84b8-114">Wenn Sie auf **Globales Testgerät** geklickt haben, fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="c84b8-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="c84b8-115">Wenn Sie auf **Standorttestgerät** geklickt haben, wählen Sie einen Standort aus der Liste der verfügbaren Standorte aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c84b8-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="c84b8-116">Geben Sie unter **Neues Testgerät** im Feld **Gerätename** einen Namen für das Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="c84b8-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="c84b8-117">Klicken Sie unterhalb von **ID-Typ** entweder auf **MAC-Adresse** oder **Seriennummer**.</span><span class="sxs-lookup"><span data-stu-id="c84b8-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="c84b8-118">Geben Sie im Feld **Eindeutige ID** die MAC-Adresse oder die Seriennummer des Geräts ein.</span><span class="sxs-lookup"><span data-stu-id="c84b8-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="c84b8-119">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c84b8-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c84b8-120">Erstellen von Test Geräten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c84b8-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c84b8-121">Test Geräte können mithilfe von Windows PowerShell und dem New-CsTestDevice-Cmdlet erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c84b8-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="c84b8-122">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c84b8-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c84b8-123">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="c84b8-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="c84b8-124">Beim Erstellen von Testgeräten mithilfe dieses Cmdlets müssen Sie die folgenden beiden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c84b8-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="c84b8-125">Geben Sie MACAddress oder SerialNumber als IdentifierType an.</span><span class="sxs-lookup"><span data-stu-id="c84b8-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="c84b8-p104">Fügen Sie beim Angeben der Geräteidentität die Ebene hinzu. Verwenden Sie zum Erstellen eines neuen Geräts auf globaler Ebene Syntax, die so oder ähnlich aussieht:</span><span class="sxs-lookup"><span data-stu-id="c84b8-p104">Include the scope when specifying the device Identity. To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="c84b8-128">Verwenden Sie zum Erstellen eines neuen Geräts auf Standortebene Syntax, die so oder ähnlich aussieht:</span><span class="sxs-lookup"><span data-stu-id="c84b8-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="c84b8-129">So erstellen Sie ein Test Gerät mithilfe der Mac-Adresse</span><span class="sxs-lookup"><span data-stu-id="c84b8-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="c84b8-130">Mit diesem Befehl wird ein Testgerät auf globaler Ebene und mit der MAC-Adresse als IdentifierType erstellt:</span><span class="sxs-lookup"><span data-stu-id="c84b8-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="c84b8-131">So erstellen Sie mithilfe der Seriennummer ein Test Gerät</span><span class="sxs-lookup"><span data-stu-id="c84b8-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="c84b8-132">Mit diesem Befehl wird ein neues Testgerät auf Standortebene (für den Standort "Redmond") und mit der Seriennummer als IdentifierType erstellt:</span><span class="sxs-lookup"><span data-stu-id="c84b8-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="c84b8-133">Weitere Informationen finden Sie im Hilfethema zum [New-CsTestDevice-](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c84b8-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

