---
title: 'Lync Server 2013: Exportieren von Testfällen für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d871379f9c9be161aec879b7ca8da16ac40e2b5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="24258-102">Exportieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24258-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24258-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="24258-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="24258-104">Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: Sie definieren beispielsweise die Nummer, die gewählt werden soll, und die Wähleinstellungen und die VoIP-Richtlinie, die verwendet werden sollen, und lync Server können dann anhand dieser Bedingungen überprüfen, ob die angegebene Nummer erfolgreich an das PSTN-Netzwerk weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24258-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="24258-105">Testfälle, die mithilfe von lync Server-Systemsteuerung erstellt werden können, werden normalerweise nur auf dem Server gespeichert, auf dem der Fall ursprünglich erstellt und ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="24258-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="24258-106">Sie können jedoch in Form von XML-Dateien (mit der Erweiterung VTEST) exportiert und dann auf anderen Servern importiert werden.</span><span class="sxs-lookup"><span data-stu-id="24258-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="24258-107">Auf diese Weise können Sie die gleichen Tests auf verschiedenen Computern an unterschiedlichen Standorten in Ihrer Topologie durchführen.</span><span class="sxs-lookup"><span data-stu-id="24258-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="24258-108">So exportieren Sie einen Testfall für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="24258-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="24258-109">Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf VoIP- **Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="24258-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="24258-p102">Wählen Sie auf der Registerkarte **VoIP-Routing testen** den Testfall (oder die Testfälle) aus, die exportiert werden sollen. Sie können mehrere Fälle auswählen, indem Sie auf den ersten Fall klicken, der exportiert werden soll, und beim Klicken auf weitere Fälle die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="24258-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="24258-112">Klicken Sie auf **Aktion** und dann auf **Testfälle exportieren**.</span><span class="sxs-lookup"><span data-stu-id="24258-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="24258-p103">Wählen Sie im Dialogfeld **Speichern unter** einen Ordner aus, in dem die exportierten Testfälle gespeichert werden sollen, und geben Sie einen Namen für die resultierende XML-Datei im Feld **Dateiname** ein. Wenn Sie mehrere Testfälle exportieren, werden alle Testfälle in einer einzelnen XML-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="24258-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="24258-115">Klicken Sie auf **Speichern**, um die Testfälle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="24258-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24258-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24258-116">See Also</span></span>


[<span data-ttu-id="24258-117">Importieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24258-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

