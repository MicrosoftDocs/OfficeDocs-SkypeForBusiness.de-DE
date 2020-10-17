---
title: 'Lync Server 2013: ID-Präsentation aufgerufen'
description: 'Lync Server 2013: ID-Präsentation aufgerufen.'
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
ms.openlocfilehash: 6b438c7c19bc3c4ad641a8b9f8dac319c9fc2b1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565201"
---
# <a name="called-id-presentation-in-lync-server-2013"></a>Aufgerufene ID-Präsentation in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Bei lync Server 2010 kann die Telefonnummer des angerufenen (also die Telefonnummer genannt) aus dem E. 164-Format in das lokale Wählformat übersetzt werden, das für den trunk-Peer erforderlich ist (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder der SIP-Trunk). Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, die die Anforderungs-URI übersetzen, bevor sie zu dem Trunk-Peer geroutet wird.

<div>


> [!IMPORTANT]  
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, bietet eine <EM>Alternative</EM> zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten.



</div>

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel erstellen oder ändern:

  - Verwenden Sie das Tool zum **Erstellen einer Übersetzungsregel** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann lync Server-Systemsteuerung das entsprechende Muster und die Übersetzungsregel generieren.

  - Schreiben Sie reguläre Ausdrücke manuell, um das Vergleichsmuster und die Übersetzungsregel zu definieren.

<div>


> [!NOTE]  
> Informationen zum Schreiben von regulären Ausdrücken finden Sie unter ".NET Framework reguläre Ausdrücke" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> .



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Darstellung der Anrufer-ID in lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

