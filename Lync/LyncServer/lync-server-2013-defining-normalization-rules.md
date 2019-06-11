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

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definieren von Normalisierungsregeln in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

Lync Server 2013-Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen. mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und wandeln diese Zahl in das von lync Server intern verwendete Format um. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Details zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.

Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter ".NET Framework-reguläre Ausdrücke" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)unter.

Mithilfe einer der folgenden Methoden können Sie eine Normalisierungsregel definieren oder bearbeiten:

  - Verwenden Sie das Tool **Normalisierungsregel erstellen** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die zu addierenden Ziffern anzugeben, und lassen Sie dann die lync Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel generieren.

  - Schreiben Sie reguläre Ausdrücke manuell, um das übereinstimmende Muster und die Übersetzungsregel zu definieren.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

