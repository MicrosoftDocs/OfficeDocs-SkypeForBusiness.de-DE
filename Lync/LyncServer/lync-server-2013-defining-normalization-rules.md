---
title: 'Lync Server 2013: Definieren von Normalisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9406e4fa7445242ae3f112ebfb772713d9d2219c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="8c0a9-102">Definieren von Normalisierungsregeln in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0a9-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c0a9-103">_**Letztes Änderungsdatum des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="8c0a9-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="8c0a9-104">Lync Server 2013-Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen. mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und wandeln diese Zahl in das von lync Server intern verwendete Format um.</span><span class="sxs-lookup"><span data-stu-id="8c0a9-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="8c0a9-105">Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8c0a9-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="8c0a9-106">Details zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8c0a9-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="8c0a9-107">Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter ".NET Framework-reguläre Ausdrücke" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)unter.</span><span class="sxs-lookup"><span data-stu-id="8c0a9-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="8c0a9-108">Mithilfe einer der folgenden Methoden können Sie eine Normalisierungsregel definieren oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="8c0a9-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="8c0a9-109">Verwenden Sie das Tool **Normalisierungsregel erstellen** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die zu addierenden Ziffern anzugeben, und lassen Sie dann die lync Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel generieren.</span><span class="sxs-lookup"><span data-stu-id="8c0a9-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="8c0a9-110">Schreiben Sie reguläre Ausdrücke manuell, um das übereinstimmende Muster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8c0a9-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8c0a9-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8c0a9-111">In This Section</span></span>

  - [<span data-ttu-id="8c0a9-112">Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0a9-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="8c0a9-113">Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0a9-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c0a9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c0a9-114">See Also</span></span>


[<span data-ttu-id="8c0a9-115">Erstellen eines Wählplans in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0a9-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="8c0a9-116">Ändern eines Wählplans in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0a9-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

