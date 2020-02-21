---
title: 'Lync Server 2013: Überprüfen der Normalisierungsregeln für das Parken von Anrufen'
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
ms.openlocfilehash: 1fcde0adac292b8773a81c759c72765f832ce745
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Überprüfen der Normalisierungsregeln für das Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Orbits für das Parken von anrufen dürfen nicht normalisiert werden. Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbit-Nummern nicht normalisiert sind. Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass ihre Umlaufbahnen normalisiert werden, führen Sie das Verfahren unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) aus, um eine neue Normalisierungsregel zu definieren, sodass das **übereinstimmende Muster** den orbitbereich und das **Übersetzungsmuster** **$1**angibt. Wenn Ihr orbitbereich für das Parken von Anrufen z. b. 7000 – 7999 ist, lautet das **übereinstimmende Muster** **^ (\\7 d{3}) $** und das **Übersetzungsmuster** ist **$1**.

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass die Standard Normalisierungsregel in ihren Wählplänen nicht <STRONG>^ (\d *)</STRONG>enthält. Andernfalls wird die Normalisierungsregel für das Parken von Anrufen nie ausgeführt.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

