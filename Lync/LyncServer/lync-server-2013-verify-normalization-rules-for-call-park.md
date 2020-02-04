---
title: 'Lync Server 2013: Überprüfen von Normalisierungsregeln für den Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Überprüfen von Normalisierungsregeln für den Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Orbits für das Parken von anrufen dürfen nicht normalisiert werden. Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbit-Nummern nicht normalisiert sind. Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass ihre Umlaufbahnen normalisiert werden, führen Sie die Schritte unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) aus, um eine neue Normalisierungsregel zu definieren, damit das **Übereinstimmungsmuster** den Umlaufbahn Bereich identifiziert und das **Übersetzungsmuster** **$1**ist. Wenn beispielsweise der Orbit-Bereich Ihres Anruf Parks 7000 – 7999 ist, ist das **Muster, das übereinstimmen** soll, **\\^ (7 d{3}) $** , und das **Übersetzungsmuster** ist **$1**.

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass die standardmäßige Normalisierungsregel in Ihren Wählplänen nicht den Ausdruck <STRONG>^(\d*)</STRONG> enthält. Andernfalls wird Ihre Normalisierungsregel für den Anruf Park nie ausgeführt.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

