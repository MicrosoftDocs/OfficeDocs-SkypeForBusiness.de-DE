---
title: 'Lync Server 2013: Testen des VoIP-Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b27fc4f3dfc42e9187ea0aee801b3c2115d83ff0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="f7db3-102">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7db3-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7db3-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f7db3-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f7db3-104">Mit der lync Server-Systemsteuerung können Sie die Registerkarte **VoIP-Routing testen** , um testfallszenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f7db3-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="f7db3-105">Um einen Test Case zu definieren, geben Sie den Wählplan, die VoIP-Richtlinie, die PSTN-Nutzung und die VoIP-Route an, anhand derer eine bestimmte Telefonnummer getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7db3-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="f7db3-106">Bevor Sie Ihre sprach Routingkonfiguration tatsächlich bereitstellen, empfehlen wir, Sie auf verschiedenen Telefonnummern zu testen, um sicherzustellen, dass die Ergebnisse Ihren Erwartungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f7db3-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f7db3-107">Sie können die Befehle Testfälle <STRONG>exportieren</STRONG> und <STRONG>Testfälle importieren</STRONG> verwenden, um sprach Routing Testfälle zu speichern und für die Verwendung auf einem anderen Computer zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f7db3-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="f7db3-108">Wenn Sie einen Teil Ihrer VoIP-Routingkonfiguration löschen, beispielsweise einen Wählplan, eine VoIP-Richtlinie, eine VoIP-Route oder eine Telefonnutzung, sollten Sie Ihre VoIP-Routing Testfälle überprüfen und aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f7db3-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="f7db3-109">In der lync Server-Systemsteuerung werden Sie nicht auf Test Fälle hingewiesen, die aufgrund geänderter Konfigurationen nicht mehr gültig sind.</span><span class="sxs-lookup"><span data-stu-id="f7db3-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7db3-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f7db3-110">In This Section</span></span>

  - [<span data-ttu-id="f7db3-111">Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7db3-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="f7db3-112">Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7db3-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="f7db3-113">Importieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7db3-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="f7db3-114">Ausführen von Tests für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7db3-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

