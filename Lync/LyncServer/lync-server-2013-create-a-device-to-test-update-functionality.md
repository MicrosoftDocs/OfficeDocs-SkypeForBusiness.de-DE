---
title: 'Lync Server 2013: Erstellen eines Geräts zum Testen der Update Funktionalität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="fec97-102">Erstellen eines Geräts zum Testen der Update Funktionalität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec97-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fec97-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fec97-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fec97-104">Sie können der Seite **Testgerät** ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fec97-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="fec97-105">Sie können ein Gerät auf globaler Ebene (in der gesamten lync Server-Umgebung) oder auf einer einzigen Website testen.</span><span class="sxs-lookup"><span data-stu-id="fec97-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="fec97-106">Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer.</span><span class="sxs-lookup"><span data-stu-id="fec97-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="fec97-107">Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf \*\*\*\* der Seite Testgerät der lync Server-Systemsteuerung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fec97-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="fec97-108">So fügen Sie ein Testgerät hinzu</span><span class="sxs-lookup"><span data-stu-id="fec97-108">To add a test device</span></span>

1.  <span data-ttu-id="fec97-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fec97-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fec97-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fec97-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="fec97-111">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Gerät testen**.</span><span class="sxs-lookup"><span data-stu-id="fec97-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="fec97-112">Klicken Sie auf **neu**, und klicken Sie dann entweder auf **globales Test Gerät** oder auf **Website Test Gerät**.</span><span class="sxs-lookup"><span data-stu-id="fec97-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="fec97-113">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="fec97-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="fec97-114">Wenn Sie auf **globales Test Gerät**geklickt haben, fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="fec97-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="fec97-115">Wenn Sie auf **Website Test Gerät**geklickt haben, wählen Sie in der Liste der verfügbaren Websites eine Website aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fec97-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="fec97-116">Geben Sie in **Neues Testgerät**einen Namen für das Gerät in **Device Name**ein.</span><span class="sxs-lookup"><span data-stu-id="fec97-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="fec97-117">Klicken \*\*\*\* Sie unter Bezeichnertyp entweder auf **MAC-Adresse** oder auf **Seriennummer**.</span><span class="sxs-lookup"><span data-stu-id="fec97-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="fec97-118">Geben Sie im Feld **eindeutige Kennung** die Mac-Adresse oder die Seriennummer des Geräts ein.</span><span class="sxs-lookup"><span data-stu-id="fec97-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="fec97-119">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fec97-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fec97-120">Erstellen von Test Geräten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="fec97-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fec97-121">Test Geräte können mithilfe von Windows PowerShell und dem Cmdlet New-CsTestDevice erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fec97-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="fec97-122">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fec97-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fec97-123">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="fec97-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="fec97-124">Beim Erstellen von Testgeräten mit diesem Cmdlet müssen Sie zwei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fec97-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="fec97-125">Geben Sie entweder MACAddress oder Seriennummer als IdentifierType an.</span><span class="sxs-lookup"><span data-stu-id="fec97-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="fec97-126">Schließen Sie den Bereich ein, wenn Sie die Geräte Identität angeben.</span><span class="sxs-lookup"><span data-stu-id="fec97-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="fec97-127">Verwenden Sie zum Erstellen eines neuen Geräts im globalen Bereich eine Syntax ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="fec97-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="fec97-128">Verwenden Sie zum Erstellen eines Testgeräts im Website Bereich die Syntax wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fec97-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="fec97-129">So erstellen Sie ein Testgerät mithilfe der Mac-Adresse</span><span class="sxs-lookup"><span data-stu-id="fec97-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="fec97-130">Mit diesem Befehl wird ein Testgerät im globalen Bereich erstellt und die Mac-Adresse als IdentifierType verwendet:</span><span class="sxs-lookup"><span data-stu-id="fec97-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="fec97-131">So erstellen Sie ein Testgerät mithilfe der Seriennummer</span><span class="sxs-lookup"><span data-stu-id="fec97-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="fec97-132">Dieser Befehl erstellt ein neues Testgerät im Website Bereich (für die Website "Redmond") und verwendet die fortlaufende Zahl als IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="fec97-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="fec97-133">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="fec97-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

