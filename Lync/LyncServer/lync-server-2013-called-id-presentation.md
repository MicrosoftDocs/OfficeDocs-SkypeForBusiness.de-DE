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

# <a name="called-id-presentation-in-lync-server-2013"></a>Aufgerufene ID-Präsentation in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bei lync Server 2010 kann die Telefonnummer des angerufenen (also die Telefonnummer) vom E. 164-Format in das lokale Wählformat übersetzt werden, das für den trunk-Peer erforderlich ist (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder der SIP-Trunk). Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.

<div>


> [!IMPORTANT]  
> Die Möglichkeit, eine oder mehrere Übersetzungsregeln einer Enterprise Voice trunk-Konfiguration zuzuordnen, dient als <EM>Alternative</EM> zum Konfigurieren von Übersetzungsregeln für den trunk-Peer. Ordnen Sie Übersetzungsregeln keiner Enterprise-VoIP-trunk-Konfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise in Konflikt stehen.



</div>

Sie können eine der folgenden Methoden verwenden, um eine Übersetzungsregel zu erstellen oder zu ändern:

  - Verwenden Sie das Tool zum **Erstellen einer Übersetzungsregel** , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie die lync Server Control Panel-Anwendung das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie generieren.

  - Schreiben Sie reguläre Ausdrücke manuell, um das übereinstimmende Muster und die Übersetzungsregel zu definieren.

<div>


> [!NOTE]  
> Informationen dazu, wie reguläre Ausdrücke geschrieben werden, finden Sie unter ".NET Framework-reguläre <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>Ausdrücke" unter.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Präsentation der Rufnummernanzeige in lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

