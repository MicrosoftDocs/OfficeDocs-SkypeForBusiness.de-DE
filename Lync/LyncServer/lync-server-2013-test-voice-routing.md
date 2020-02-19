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
ms.openlocfilehash: eff0d59de7822f738cc7e2253cf728690dd45b50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="e4d59-102">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d59-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d59-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e4d59-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e4d59-104">Sie können die Registerkarte **VoIP-Routing testen** lync Server-Systemsteuerung verwenden, um testfallszenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e4d59-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="e4d59-105">Zum Definieren eines Testfalls geben Sie den Wählplan, die VoIP-Richtlinie, PSTN-Verwendung und VoIP-Route an, die anhand einer angegebenen Telefonnummer getestet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e4d59-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="e4d59-106">Bevor Sie Ihre VoIP-Routingkonfiguration tatsächlich bereitstellen, wird empfohlen, dass Sie Sie auf verschiedenen Telefonnummern testen, um sicherzustellen, dass die Ergebnisse Ihren Erwartungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e4d59-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e4d59-107">Mithilfe der Befehle <STRONG>Testfälle exportieren</STRONG> und <STRONG>Testfälle importieren</STRONG> können Sie Testfälle für das VoIP-Routing speichern und zur Verwendung auf einem anderen Computer importieren.</span><span class="sxs-lookup"><span data-stu-id="e4d59-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="e4d59-108">Wenn Sie einen Teil Ihrer VoIP-Routingkonfiguration löschen, beispielsweise einen Wählplan, eine VoIP-Richtlinie, VoIP-Route oder Telefonverwendung, sollten Sie Ihre Testfälle für das VoIP-Routing überprüfen und aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e4d59-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="e4d59-109">In der lync Server-Systemsteuerung werden Sie nicht auf Test Fälle hingewiesen, die aufgrund von geänderten Konfigurationen nicht mehr gültig sind.</span><span class="sxs-lookup"><span data-stu-id="e4d59-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4d59-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e4d59-110">In This Section</span></span>

  - [<span data-ttu-id="e4d59-111">Erstellen eines Testfalls für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d59-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="e4d59-112">Exportieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d59-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="e4d59-113">Importieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d59-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="e4d59-114">Durchführen von Tests für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d59-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

