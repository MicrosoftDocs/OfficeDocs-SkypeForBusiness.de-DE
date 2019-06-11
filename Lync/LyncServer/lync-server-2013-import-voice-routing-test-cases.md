---
title: 'Lync Server 2013: Importieren von Testfällen für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b1aba05447904d4515df7ab6137743edb52ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="a4c0d-102">Importieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c0d-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4c0d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a4c0d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a4c0d-104">Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: Sie definieren solche Dinge wie die Nummer, die gewählt werden soll, und die Richtlinie für Wähleinstellungen und VoIP, die verwendet werden soll, und lync Server 2013 kann dann überprüfen, ob die angegebene Nummer aufgrund dieser Bedingungen Erfolg haben kann. sfully an das PSTN-Netzwerk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="a4c0d-105">Testfälle, die mithilfe der lync Server-Systemsteuerung erstellt werden können, werden in der Regel nur auf dem Server gespeichert, auf dem der Fall ursprünglich erstellt und ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="a4c0d-106">Diese Testfälle können jedoch als XML-Dateien (mit der Erweiterung. vtest) exportiert und dann auf anderen Servern importiert werden.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="a4c0d-107">Auf diese Weise können Sie dieselben Tests auf verschiedenen Computern ausführen, die sich an unterschiedlichen Stellen in Ihrer Topologie befinden.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="a4c0d-108">So importieren Sie einen Test Case für VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="a4c0d-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="a4c0d-109">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a4c0d-110">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a4c0d-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a4c0d-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a4c0d-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a4c0d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a4c0d-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="a4c0d-114">Klicken Sie im Menü **Aktionen** auf **Testfälle importieren**.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="a4c0d-115">Suchen Sie die Testfalldatei (vtest), die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="a4c0d-116">Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4c0d-117">Wenn Sie eine vtest-Datei importieren, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um den Testfall zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="a4c0d-118">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a4c0d-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4c0d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4c0d-119">See Also</span></span>


[<span data-ttu-id="a4c0d-120">Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4c0d-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

