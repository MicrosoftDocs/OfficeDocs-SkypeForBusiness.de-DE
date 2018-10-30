---
title: 'Lync Server 2013: Ermitteln der Anforderungen für externe A/V-Firewalls und Ports'
TOCTitle: Ermitteln der Anforderungen für externe A/V-Firewalls und Ports
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425882(v=OCS.15)
ms:contentKeyID: 49293735
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die A/V-Kommunikation (Audio/Video) kann komplex sein. Aufgrund der Beschaffenheit der bei der A/V-Kommunikation verwendeten Protokolle und der Art, wie diese von Clients und Servern verwendet werden, ist es notwendig, in diesem Abschnitt die Unterschiede zwischen Client- und Serverversionen zu erläutern.

Ermitteln Sie anhand der folgenden Firewall- und Porttabelle für A/V, welche Firewallanforderungen gelten und welche Ports geöffnet werden müssen. Lesen Sie anschließend die Hinweise zur Netzwerkadressenübersetzung (Network Address Translation, NAT), da NAT auf viele verschiedene Arten implementiert werden kann. Ein detailliertes Beispiel zu den Firewallporteinstellungen finden Sie in den Referenzarchitekturen unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### Allgemeine Protokollverwendung für UDP und TCP in Audio-/Video- und Mediendatenverkehr

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Audio/Videotransport</th>
<th>Verwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Bevorzugtes Transportschichtprotokoll für Audio und Video</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Ausweich-Transportschichtprotokoll für Audio und Video</p>
<p>Erforderliches Transportschichtprotokoll für Anwendungsfreigabe für Office Communications Server 2007 R2, Lync Server 2010 und Lync Server 2013</p>
<p>Erforderliches Transportschichtprotokoll für Dateiübertragung an Lync Server 2010 und Lync Server 2013</p></td>
</tr>
</tbody>
</table>


## Portanforderungen für die externe A/V-Firewall für den externen Benutzerzugriff

Die Anforderungen in Bezug auf Firewallports für externe (und interne) SIP- und Konferenzschnittstellen sind gleich, unabhängig von Ihrer oder der vom Verbundpartner ausgeführten Clientversion.

Dies gilt nicht für die externe A/V-Edgeschnittstelle (Audio/Video). Für den Verbund mit Office Communications Server 2007 erfordert der A/V-Edgedienst, dass die externen Firewallregeln RTP/TCP- und RTP/UDP-Datenverkehr im Portbereich 50.000 bis 59.999 in beide Richtungen zulassen. In der obigen Tabelle wird davon ausgegangen, dass Lync Server 2013 den primären Verbundpartner darstellt und für die Kommunikation mit einem der anderen Verbundpartnertypen konfiguriert ist.

Beim Konfigurieren des Audio-/Videoportbereichs von of 50.000 - 59.999 muss berücksichtigt werden, dass der Portbereich die Quellports für die Kommunikation mit Verbundpartnern enthält. Berücksichtigen Sie insbesondere, dass die Kommunikation vom Verbundpartner initiiert wird. Bei der Kommunikation von den A/V-Edgedienst-Ports im Bereich 50.000 - 59.999 wird eine Verbindung mit dem erwarteten Port TCP 443 des A/V-Edgediensts des Partners hergestellt. Dagegen ist für eingehenden Datenverkehr an Ihren A/V-Edgedienst-Port TCP 443 ein Quellport im Bereich 50.000 - 59.999 vorhanden.

Verschiedene Firewalls und Richtlinien für die Firewallverwaltung erfordern entweder nur die Konfiguration von Zielregeln oder die Konfiguration von Quelle und Ziel. Werden nur Zielports erfordert, gelten folgende Audio-/Videovoraussetzungen:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Quell-IP</th>
<th>Ziel-IP</th>
<th>Zielport</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Erfordern Ihre Richtlinien die Definition von Firewallregeln für eingehenden und ausgehenden Datenverkehr, gelten folgende Audio-/Videovoraussetzungen:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Quell-IP</th>
<th>Ziel-IP</th>
<th>Quellport</th>
<th>Zielport</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 50.000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Beliebig</p></td>
<td><p>A/V-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> Microsoft Office Communications Server 2007 erfordert eine leicht abweichende Konfiguration. Der TCP- und UDP-Portbereich von 50.000 - 59.999 muss für eingehenden und ausgehenden Datenverkehr geöffnet sein. Die Anforderung gilt nur für Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 und Lync Server 2013 erfordern nur die Öffnung des TCP-Bereichs 50.000 - 59.999 für ausgehenden Datenverkehr.



## NAT-Anforderungen für den externen Benutzerzugriff

NAT war typischerweise eine Routingfunktion, aber neuere Geräte - beispielsweise Firewalls und sogar Hardwaregeräte zum Lastenausgleich - können für NAT konfiguriert werden. Statt einer Beschreibung, welches Gerät die Netzwerkadressenübersetzung durchführt, wird in diesem Thema das erwartete NAT-Verhalten erläutert.

Die Lync Server 2013- Kommunikationssoftware bietet keine NAT-Unterstützung für Datenverkehr von der oder zur internen Edgeschnittstelle, für die externe Edgeschnittstelle ist jedoch das folgende NAT-Verhalten erforderlich.


> [!IMPORTANT]
> Sie müssen ein symmetrisches NAT-Gerät für eingehenden und ausgehenden Datenverkehr konfigurieren. In diesem Thema wird die symmetrische NAT als NAT-Technologie beschrieben.



In dieser Dokumentation werden die Akronyme "ChangeDST" und "ChangeSRC" in Tabellen und Abbildungen zum Definieren des folgenden erforderlichen Verhaltens verwendet:

  - **ChangeDST**   Der Vorgang der Änderung der Ziel-IP-Adresse für Pakete an das Netzwerk mit NAT-Verwendung. Auch bekannt als Transparenz, Portweiterleitung, Ziel-NAT-Modus oder Halb-NAT-Modus.

  - **ChangeSRC**   Der Vorgang der Änderung der Quell-IP-Adresse für Pakete an das Netzwerk mit NAT-Verwendung. Auch bekannt als Proxy, sichere Netzwerkadressenübersetzung, NAT mit Statusinformationen, Quell-NAT oder Voll-NAT-Modus.

Unabhängig von der verwendeten Namenskonvention lautet das für die externe Schnittstelle des Edgeservers erforderliche NAT-Verhalten wie folgt:

  - Für Datenverkehr vom Internet zur externen Edgeschnittstelle:
    
      - Änderung der Ziel-IP-Adresse des eingehenden Pakets von der öffentlichen IP-Adresse der externen Edgeschnittstelle in die übersetzte IP-Adresse der externen Edgeschnittstelle.
    
      - Beibehaltung der Quell-IP-Adresse, sodass eine Rückroute für den Datenverkehr vorhanden ist.

  - Für Datenverkehr von der externen Edgeschnittstelle zum Internet:
    
      - Änderung der Quell-IP-Adresse des von der externen Edgeschnittstelle ausgehenden Pakets von der übersetzten IP-Adresse in die öffentliche IP-Adresse der externen Edgeschnittstelle, sodass die interne (nicht routingfähige) IP-Adresse der Edgeschnittstelle nicht offengelegt wird.
    
      - Beibehaltung der Ziel-IP-Adresse für die ausgehenden Pakete.

Die folgende Abbildung zeigt den Unterschied zwischen der Änderung der Ziel-IP-Adresse (ChangeDST) für eingehenden Datenverkehr und der Änderung der Quell-IP-Adresse (ChangeSRC) für ausgehenden Datenverkehr am Beispiel der A/V-Edgeschnittstelle.

**Änderung der Ziel-IP-Adresse (ChangeDST) für eingehenden Datenverkehr und Änderung der Quell-IP-Adresse (ChangeSRC)**

![Ändern der Ziel-/Quell-IP-Adressen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Ändern der Ziel-/Quell-IP-Adressen")

Die wichtigsten Punkte hierbei sind:

  - Für eingehenden Datenverkehr auf dem Server, auf dem der A/V-Edgedienst ausgeführt wird, wird die Quell-IP-Adresse nicht geändert, die Ziel-IP-Adresse ändert sich jedoch von 131.107.155.30 in die übersetzte IP-Adresse 10.45.16.10.

  - Für Datenverkehr, der vom Server, auf dem der A/V-Edgedienst ausgeführt wird, zurück zur Arbeitsstation ausgeht, ändert sich die Quell-IP-Adresse von der öffentlichen IP-Adresse des Servers in die öffentliche Adresse des Servers, auf dem der A/V-Edgedienst ausgeführt wird. Als Ziel-IP-Adresse wird die öffentliche IP-Adresse der Arbeitsstation beibehalten. Nachdem das Paket das erste NAT-Gerät ausgehend passiert hat, ändert die Regel auf dem NAT-Gerät die Quell-IP-Adresse des Servers, auf dem der A/V-Edgedienst ausgeführt wird, von der IP-Adresse der externen Schnittstelle (10.45.16.10) in die zugehörige öffentliche IP-Adresse (131.107.155.30).

