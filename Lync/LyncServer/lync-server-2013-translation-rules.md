---
title: 'Lync Server 2013: Übersetzungsregeln'
TOCTitle: Übersetzungsregeln
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398520(v=OCS.15)
ms:contentKeyID: 49294338
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersetzungsregeln in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Lync Server 2013Enterprise-VoIP erfordert die Normalisierung aller Wählzeichenfolgen in das E.164-Format, um eine umgekehrte Nummernsuche durchführen zu können. In Microsoft Lync Server 2010 werden Übersetzungsregeln nur für gewählte Nummern unterstützt. Als Neuerung in Microsoft Lync Server 2013 werden Übersetzungsregeln auch für anwählende Nummern unterstützt. Der *Trunkpeer* (also das zugeordnete Gateway, die Nebenstellenanlage (Private Branch Exchange (PBX) oder der zugeordnete SIP-Trunk) erfordert möglicherweise, dass die Nummern in einem lokalen Wählformat vorliegen. Um Nummern aus dem E.164-Format in ein lokales Wählformat zu übersetzen, können Sie eine oder mehrere Übersetzungsregeln definieren, mit denen der Anforderungs-URI vor dem Routen an den Trunkpeer geändert wird. Sie können beispielsweise eine Übersetzungsregel erstellen, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Durch die ausgehende Routenübersetzung auf dem Server können Sie die Konfigurationsanforderungen der einzelnen Trunkpeers für das Übersetzen von Rufnummern in ein lokales Wählformat reduzieren. Wenn Sie planen, welche und wie viele Gateways einem bestimmten Vermittlungsservercluster zugeordnet werden sollen, kann es nützlich sein, Trunkpeers mit ähnlichen lokalen Wählanforderungen zu gruppieren. Dies kann die Anzahl von erforderlichen Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln reduzieren.


> [!IMPORTANT]
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, sollte als Alternative zur Konfiguration von Übersetzungsregeln für den Trunkpeer angesehen werden. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten.



## Beispielübersetzungsregeln

Die folgenden Beispiele für Übersetzungsregeln zeigen, wie Sie Regeln auf dem Server erstellen können, um Nummern aus dem E.164-Format in ein lokales Format für den Trunkpeer zu übersetzen.

Ausführliche Informationen zur Implementierung von Übersetzungsregeln finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.


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
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Normales Ferngespräch in den USA</p>
<p>(Entfernen des Pluszeichens &quot;+&quot;)</p></td>
<td><p>+1</p></td>
<td><p>Exakt 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1\d{10})$</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 wird zu 14255551010</p></td>
</tr>
<tr class="even">
<td><p>Internationales Ferngespräch aus den USA</p>
<p>(Entfernen des Pluszeichens &quot;+&quot; und Hinzufügen von 011)</p></td>
<td><p>+</p></td>
<td><p>Mindestens 11</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d+)$</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 wird zu 011441235551010</p></td>
</tr>
</tbody>
</table>

