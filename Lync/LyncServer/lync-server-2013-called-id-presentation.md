---
title: 'Lync Server 2013: ID-Präsentation aufgerufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddb1902422cb3efc52f4f0b3271976ab9b9950e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508222"
---
# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="90d68-102">Aufgerufene ID-Präsentation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90d68-102">Called ID presentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90d68-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="90d68-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="90d68-104">Bei lync Server 2010 kann die Telefonnummer des angerufenen (also die Telefonnummer genannt) aus dem E. 164-Format in das lokale Wählformat übersetzt werden, das für den trunk-Peer erforderlich ist (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder der SIP-Trunk).</span><span class="sxs-lookup"><span data-stu-id="90d68-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="90d68-105">Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, die die Anforderungs-URI übersetzen, bevor sie zu dem Trunk-Peer geroutet wird.</span><span class="sxs-lookup"><span data-stu-id="90d68-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="90d68-p102">Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, bietet eine <EM>Alternative</EM> zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="90d68-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="90d68-108">Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel erstellen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="90d68-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="90d68-109">Verwenden Sie das Tool zum **Erstellen einer Übersetzungsregel** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann lync Server-Systemsteuerung das entsprechende Muster und die Übersetzungsregel generieren.</span><span class="sxs-lookup"><span data-stu-id="90d68-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="90d68-110">Schreiben Sie reguläre Ausdrücke manuell, um das Vergleichsmuster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="90d68-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90d68-111">Informationen zum Schreiben von regulären Ausdrücken finden Sie unter ".NET Framework reguläre Ausdrücke" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> .</span><span class="sxs-lookup"><span data-stu-id="90d68-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="90d68-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="90d68-112">In This Section</span></span>

  - [<span data-ttu-id="90d68-113">Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90d68-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="90d68-114">Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90d68-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90d68-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90d68-115">See Also</span></span>


[<span data-ttu-id="90d68-116">Darstellung der Anrufer-ID in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90d68-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

