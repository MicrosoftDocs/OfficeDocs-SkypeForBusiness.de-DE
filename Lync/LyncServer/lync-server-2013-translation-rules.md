---
title: 'Lync Server 2013: Übersetzungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 088657d530224288a9ffabbfa1644d0fea6796e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Übersetzungsregeln in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Für lync Server 2013 Enterprise-VoIP müssen alle Wählzeichenfolgen zum E. 164-Format normalisiert werden, um eine rückwärts Nummernsuche (können) durchführen zu können. In Microsoft lync Server 2010 werden Übersetzungsregeln nur für benannte Nummern unterstützt. Neu in Microsoft lync Server 2013 werden Übersetzungsregeln auch für Rufnummern unterstützt. Der *Trunkpeer* (also das zugeordnete Gateway, die Nebenstellenanlage (Private Branch Exchange (PBX) oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren. Wenn Sie planen, welche Gateways und wie viele Gateways einem bestimmten Vermittlungsserver Cluster zugeordnet werden sollen, kann es hilfreich sein, trunk-Peers mit ähnlichen lokalen wählanforderungen zu gruppieren. Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.

<div>


> [!IMPORTANT]  
> Das Zuordnen einer oder mehrerer Übersetzungsregeln zu einer Enterprise-VoIP-trunk-Konfiguration sollte als Alternative zum Konfigurieren von Übersetzungsregeln für den trunk-Peer verwendet werden. Ordnen Sie Übersetzungsregeln nicht einer Enterprise-VoIP-trunkkonfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise einen Konflikt verursachen.



</div>

<div>

## <a name="example-translation-rules"></a>Beispielübersetzungsregeln

Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.

Ausführliche Informationen zur Implementierung von Übersetzungsregeln finden Sie unter [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Anfangsziffern</th>
<th>Länge</th>
<th>Zu entfernende Ziffern</th>
<th>Hinzuzufügende Ziffern</th>
<th>Vergleichsmuster</th>
<th>Translation</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Normales Ferngespräch in den USA</p>
<p>(Entfernen des Pluszeichens "+")</p></td>
<td><p>+1</p></td>
<td><p>Exakt 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 wird zu 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Internationales Ferngespräch aus den USA</p>
<p>(Entfernen des Pluszeichens "+" und Hinzufügen von 011)</p></td>
<td><p>+</p></td>
<td><p>Mindestens 11</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011 $1</p></td>
<td><p>+441235551010 wird zu 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

