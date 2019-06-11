---
title: 'Lync Server 2013: aufgerufene ID-Präsentation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="713b1-102">Aufgerufene ID-Präsentation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713b1-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="713b1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="713b1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="713b1-104">Bei lync Server 2010 kann die Telefonnummer des angerufenen (also die Telefonnummer) vom E. 164-Format in das lokale Wählformat übersetzt werden, das für den trunk-Peer erforderlich ist (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder der SIP-Trunk).</span><span class="sxs-lookup"><span data-stu-id="713b1-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="713b1-105">Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="713b1-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="713b1-106">Die Möglichkeit, eine oder mehrere Übersetzungsregeln einer Enterprise Voice trunk-Konfiguration zuzuordnen, dient als <EM>Alternative</EM> zum Konfigurieren von Übersetzungsregeln für den trunk-Peer.</span><span class="sxs-lookup"><span data-stu-id="713b1-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="713b1-107">Ordnen Sie Übersetzungsregeln keiner Enterprise-VoIP-trunk-Konfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="713b1-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="713b1-108">Sie können eine der folgenden Methoden verwenden, um eine Übersetzungsregel zu erstellen oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="713b1-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="713b1-109">Verwenden Sie das Tool zum **Erstellen einer Übersetzungsregel** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie die lync Server Control Panel-Anwendung das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie generieren.</span><span class="sxs-lookup"><span data-stu-id="713b1-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="713b1-110">Schreiben Sie reguläre Ausdrücke manuell, um das übereinstimmende Muster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="713b1-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="713b1-111">Informationen dazu, wie reguläre Ausdrücke geschrieben werden, finden Sie unter ".NET Framework-reguläre <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>Ausdrücke" unter.</span><span class="sxs-lookup"><span data-stu-id="713b1-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="713b1-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="713b1-112">In This Section</span></span>

  - [<span data-ttu-id="713b1-113">Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713b1-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="713b1-114">Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713b1-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="713b1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="713b1-115">See Also</span></span>


[<span data-ttu-id="713b1-116">Präsentation der Rufnummernanzeige in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713b1-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

