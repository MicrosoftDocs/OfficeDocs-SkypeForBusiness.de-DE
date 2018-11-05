---
title: Standortbasiertes Routing und Anrufübergaben mit Ankündigung
TOCTitle: Standortbasiertes Routing und Anrufübergaben mit Ankündigung
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56269330
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standortbasiertes Routing und Anrufübergaben mit Ankündigung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zusätzlich zum Erzwingen von standortbasiertem Routing zu Lync-Besprechungen erzwingt die Anwendung für standortbasiertes Routing für Konferenzen Einschränkungen für Anrufdurchstellungen mit Ankündigung, die an Telefonfestnetzendgeräte gerichtet sind. Eine Anrufdurchstellung mit Ankündigung ergibt sich für einen Anruf, der zwischen zwei Parteien aufgebaut ist, wobei eine der Parteien den Anruf an einen neuen Teilnehmer durchstellt. Teilnehmer A (Lync-Angerufener) wird beispielsweise über ein Telefonfestnetzendgerät angerufen. Teilnehmer A entscheidet, dass der Telefonfestnetzteilnehmer an den Teilnehmer B (Lync-Benutzer) weitergeleitet werden soll. Teilnehmer A setzt den Anruf mit dem Telefonfestnetzteilnehmer auf Halten und ruft den Teilnehmer B an. Teilnehmer B willigt ein, mit dem Telefonfestnetzteilnehmer zu sprechen. Teilnehmer A stellt den gehaltenen Anruf an den Teilnehmer B durch.

**Anruffluss bei einer Anrufdurchstellung mit Ankündigung**

![Standortbasiertes Routing für Konferenzen (Diagramm)](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Standortbasiertes Routing für Konferenzen (Diagramm)")

Wenn ein Teilnehmer, für den standortbasiertes Routing aktiviert ist, für ein Telefonfestnetzendgerät eine Anrufdurchstellung mit Ankündigung auslöst (siehe vorherige Abbildung), werden zwei aktive Anrufe veranlasst, einer zwischen dem Telefonfestnetzteilnehmer und dem Lync-Benutzer A und einer zwischen dem Lync-Benutzer A und dem Lync-Benutzer B. Folgendes Verhalten wird von der Anwendung für standortbasiertes Routing für Konferenzen erzwungen:

  - Wenn die SIP-Vermittlungsleitung, die den Telefonfestnetzanruf weiterleitet, berechtigt ist, den Anruf auch an den Netzwerkstandort weiterzuleiten, in dem sich der Lync-Benutzer B (d. h. das Übergabeziel) befindet, wird die Anrufdurchstellung zugelassen. Andernfalls wird die Anrufdurchstellung mit Ankündigung blockiert. Die Berechtigung wird auf Basis des Standorts des weitergeleiteten Teilnehmers erteilt, wobei sich der Standort im selben Netzwerkstandort befindet wie die SIP-Vermittlungsleitung, die den aktiven Anruf an das Telefonfestnetzendgerät weiterleitet.

  - Wenn die SIP-Vermittlungsleitung, die den Telefonfestnetzanruf weiterleitet, nicht berechtigt ist, Anrufe an den Netzwerkstandort weiterzuleiten, in dem sich der weitergeleitete Teilnehmer (Lync-Benutzer B) befindet, oder wenn sich der weitergeleitete Teilnehmer in einem unbekannten Netzwerkstandort befindet, wird die Anrufdurchstellung mit Ankündigung an das Telefonfestnetzendgerät (d. h. das Anrufdurchstellungsziel) blockiert.

In der folgenden Tabelle ist beschrieben, wie Beschränkungen für standortbasiertes Routing von der Anwendung für standortbasiertes Routing für Konferenzen bei Anrufdurchstellungen mit Ankündigung angewendet werden. Zwar sind Nebenstellenanlagenendgeräte nicht direkt einem Netzwerkstandort zugewiesen, aber die SIP-Vermittlungsleitung, an die die jeweilige Nebenstelleanlage angeschlossen ist, kann einem Netzwerkstandort zugewiesen sein. Daher kann ein Nebenstellenanlagenendgerät indirekt einem Netzwerkstandort zugewiesen sein.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Netzwerkstandort des Teilnehmers, dessen Anruf durchgestellt wird</p></td>
<td><p>Netzwerkstandort des Ziels der Anrufdurchstellung</p></td>
<td><p>Verhalten</p></td>
</tr>
<tr class="even">
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Lync-Benutzer im selben Netzwerkstandort (d. h. Standort 1)</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Lync-Benutzer in anderem Netzwerkstandort (d. h. Standort 2)</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird nicht zugelassen</p></td>
</tr>
<tr class="even">
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Lync-Benutzer in einem unbekannten Netzwerkstandort</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird nicht zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Lync-Benutzer im Partnerverbund</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird nicht zugelassen</p></td>
</tr>
<tr class="even">
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Nebenstellenanlagenendgerät im selben Standort (d. h. Standort 1)</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Nebenstellenanlagenendgerät in einem anderen Standort (d. h. Standort 2)</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird nicht zugelassen</p></td>
</tr>
<tr class="even">
<td><p>Nebenstellenanlagenendgerät im selben Standort (d. h. Standort 1)</p></td>
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Nebenstellenanlagenendgerät in einem anderen Standort (d. h. Standort 2)</p></td>
<td><p>Telefonfestnetzendgerät</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird nicht zugelassen</p></td>
</tr>
<tr class="even">
<td><p>Nebenstellenanlagenendgerät in einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer im selben Netzwerkstandort (d. h. Standort 1)</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Nebenstellenanlagenendgerät in einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer in anderem Netzwerkstandort (d. h. Standort 2)</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
<tr class="even">
<td><p>Nebenstellenanlagenendgerät in einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer in einem unbekannten Netzwerkstandort</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Nebenstellenanlagenendgerät in einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer im Partnerverbund</p></td>
<td><p>Anrufdurchstellung mit Ankündigung wird zugelassen</p></td>
</tr>
</tbody>
</table>

