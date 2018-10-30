---
title: Übersicht über das standortbasierte Routing für Konferenzen
TOCTitle: Übersicht über das standortbasierte Routing für Konferenzen
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56269311
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über das standortbasierte Routing für Konferenzen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Anwendung für das standortbasierte Routing von Konferenzen stellt in Lync-Konferenzen einen Mechanismus für das Verhindern von PSTN-Gebührenumgehung bereit. Die Anwendung überwacht aktive Konferenzen und erzwingt basierend auf dem Standort der teilnehmenden Lync-Benutzer Einschränkungen für das standortbasierte Routing.

Die Anwendung für das standortbasierte Routing ermittelt, ob das standortbasierte Routing für eine Lync-Besprechung erzwungen werden muss, wenn die folgenden Kriterien zutreffen:

  - Der Besprechungsorganisator ist für das standortbasierte Routing aktiviert. Die Einschränkungen für das standortbasierte Routing gelten nur für Konferenzen, die von Benutzern organisiert werden, die für das standortbasierte Routing aktiviert sind.

  - Mindestens ein Besprechungsteilnehmer befindet sich an einem Endpunkt im öffentlichen Telefonnetz (PSTN). Die Einschränkungen für das standortbasierte Routing sind nur auf Konferenzen anwendbar, die PSTN-Endpunkte einbeziehen.

  - Der Netzwerkstandort, an dem sich das PSTN-Gateway zum Überbrücken der Konferenz in das PSTN wurde ebenso lokalisiert wie die Netzwerkstandorte, von denen aus die Organisatoren und Teilnehmer die Verbindung herstellen.

Die Anwendung für das standortbasierte Routing von Konferenzen verhindert die Teilnahme von Lync-Benutzern und PSTN-Endpunkten von unterschiedlichen Netzwerkstandorten an der gleichen Konferenz. Wenn der Organisator einer Besprechung für das standortbasierte Routing aktiviert ist, erzwingt die Konferenzanwendung die folgenden Einschränkungen:

  - Die Endpunkte, die an einer Lync-Besprechung teilnehmen können, sind von den Endpunkten abhängig, die bereits an der Konferenz teilnehmen, und diese Einschränkung wird angepasst, wenn verbundene Endpunkte die Konferenz verlassen und neue Endpunkt zur Konferenz hinzukommen. Wenn Organisatoren und Teilnehmer vom gleichen Netzwerkstandort aus an einer Lync-Besprechung teilnehmen, sind auch ein PSTN-Endpunkt, ein anderer Teilnehmer am gleichen Netzwerkstandort, ein anderer Teilnehmer von einer anderen Netzwerkstandort oder ein Teilnehmer von einem unbekannten Netzwerkstandort zulässig.

  - Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten an der Besprechung teilnehmen, darf ein Teilnehmer an einem PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem SIP-Trunk eingeht, der für das standortbasierte Routing aktiviert ist.

  - Wenn Organisatoren und Teilnehmer vom gleichen Netzwerkstandort an der Besprechung teilnehmen und es Teilnehmer gibt, die über das PSTN an der gleichen Besprechung teilnehmen, darf ein Teilnehmer von einem Lync-Endpunkt an einem anderen Netzwerkstandort nicht an der Besprechung teilnehmen.

Diese Einschränkungen für das standortbasierte Routing von Konferenzen werden in der folgenden Tabelle zusammengefasst.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Benutzer in einer Konferenz an einem beliebigen Standort</p></td>
<td><p>Benutzer, die an der Konferenz teilnehmen dürfen</p></td>
<td><p>Benutzer, die nicht an der Konferenz teilnehmen dürfen</p></td>
</tr>
<tr class="even">
<td><p>Lync-VoIP-Clientbenutzer von einem einzelnen Netzwerkstandort</p></td>
<td><p>Lync-VoIP-Clientbenutzer vom gleichen Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer von einem anderen Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer aus dem Partnerverbund</p>
<p>Benutzer, die von einem PSTN-Endpunkt teilnehmen</p></td>
<td><p>–</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Lync-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p></td>
<td><p>Lync-VoIP-Clientbenutzer von einem beliebigen Standort</p>
<p>Lync-VoIP-Clientbenutzer von einem unbekannten Standort</p>
<p>Lync-VoIP-Clientbenutzer aus dem Partnerverbund</p></td>
<td><p>Benutzer, die über einen PSTN-Endpunkt teilnehmen</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Lync-VoIP-Clientbenutzer von anderen Netzwerkstandorten</p></td>
<td><p>Lync-VoIP-Clientbenutzer aus einem beliebigen Netzwerk</p>
<p>Lync-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer aus dem Partnerverbund</p></td>
<td><p>Benutzer, die über einen PSTN-Endpunkt teilnehmen</p></td>
</tr>
<tr class="odd">
<td><p>Lync-VoIP-Clientbenutzer von einem beliebigen Netzwerkstandort und Benutzer, die von einem PSTN-Endpunkt teilnehmen</p></td>
<td><p>Lync-VoIP-Clientbenutzer vom gleichen Netzwerkstandort</p>
<p></p></td>
<td><p>Lync-VoIP-Clientbenutzer von einem anderen Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer aus dem Partnerverbund</p></td>
</tr>
</tbody>
</table>


Im Folgenden Funktionen werden weitere Eigenschaften der Anwendung für das standortbasierte Routing von Konferenzen aufgeführt:

  - Wenn ein Benutzer aufgrund der Einschränkungen des standortbasierten Routings nicht zu einer Konferenz zugelassen wird, werden die Anrufe des Benutzers bei der Konferenz zurückgewiesen, und im Lync-Client wird gemeldet, dass der Anruf nicht durchgestellt werden konnte oder beendet wurde.

  - Ein Teilnehmer der über einen PSTN-Endpunkt an einer Konferenz teilnimmt, für die Einschränkungen des standortbasierten Routings gelten, wird ungeachtet seines Status nicht an der Teilnahme gehindert, wenn der Endpunkt über einen Trunk teilnimmt, der nicht für das standortbasierte Routing aktiviert ist.

  - Für eine Nebenstellenanlage, die mit einem Vermittlungsserver über einen SIP-Trunk verbunden ist, der ausgehende Anrufe nicht über das PSTN leitet, gelten die gleichen Einschränkungen wie für Lync-Benutzer, die sich am gleichen Netzwerkstandort wie der SIP-Trunk befinden. So ist ein Teilnehmer an einem PSTN-Endpunkt beispielsweise in der Lage, an einer Konferenz mit dem Benutzer einer Nebenstellenanlage und einem Lync-Benutzer teilzunehmen, wenn sich alle am gleichen Netzwerkstandort befinden. Der Teilnehmer am PSTN-Endpunkt wird jedoch nicht zur Konferenz zugelassen, wenn sich der Benutzer der Nebenstellenanlage an einem anderen Netzwerkstandort als der Lync-Benutzer befindet.

