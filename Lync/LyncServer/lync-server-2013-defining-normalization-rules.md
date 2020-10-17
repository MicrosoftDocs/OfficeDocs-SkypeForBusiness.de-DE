---
title: 'Lync Server 2013: Definieren von Normalisierungsregeln'
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
ms.openlocfilehash: 935df08bd1ede124b048427de21594aa6e727e7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504512"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definieren von Normalisierungsregeln in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-22_

Lync Server 2013 Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen; mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und wandeln diese Nummer in das Format um, das von lync Server intern verwendet wird. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Ausführliche Informationen zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.

Ausführliche Informationen zum Schreiben von regulären Ausdrücken finden Sie unter ".NET Framework reguläre Ausdrücke" unter [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:

  - Verwenden Sie das Tool **Normalisierungsregel erstellen** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann lync Server-Systemsteuerung das entsprechende Muster und die Übersetzungsregel generieren.

  - Schreiben Sie reguläre Ausdrücke manuell, um das Vergleichsmuster und die Übersetzungsregel zu definieren.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

