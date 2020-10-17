---
title: 'Lync Server 2013: Definieren von Normalisierungsregeln'
description: 'Lync Server 2013: Definieren von Normalisierungsregeln.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542041"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="f5206-103">Definieren von Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5206-103">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5206-104">_**Letztes Änderungsstand des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="f5206-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="f5206-105">Lync Server 2013 Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen; mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und wandeln diese Nummer in das Format um, das von lync Server intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5206-105">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="f5206-106">Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f5206-106">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="f5206-107">Ausführliche Informationen zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f5206-107">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="f5206-108">Ausführliche Informationen zum Schreiben von regulären Ausdrücken finden Sie unter ".NET Framework reguläre Ausdrücke" unter [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="f5206-108">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="f5206-109">Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="f5206-109">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="f5206-110">Verwenden Sie das Tool **Normalisierungsregel erstellen** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann lync Server-Systemsteuerung das entsprechende Muster und die Übersetzungsregel generieren.</span><span class="sxs-lookup"><span data-stu-id="f5206-110">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="f5206-111">Schreiben Sie reguläre Ausdrücke manuell, um das Vergleichsmuster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f5206-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5206-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f5206-112">In This Section</span></span>

  - [<span data-ttu-id="f5206-113">Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5206-113">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="f5206-114">Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5206-114">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5206-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5206-115">See Also</span></span>


[<span data-ttu-id="f5206-116">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5206-116">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="f5206-117">Ändern von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5206-117">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

