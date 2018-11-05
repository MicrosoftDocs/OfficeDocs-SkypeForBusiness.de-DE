---
title: Zertifikatzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
TOCTitle: Zertifikatzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49295104
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zertifikatsanforderungen für das Aktivieren und Einrichten von Kommunikationen mit XMPP-Partnern (Extensible Messaging and Presence Protocol) erfordern den zusätzlichen Eintrag in Ihren XMPP-Domänen. Der Eintrag, der auf dem Zertifikat als alternativer Antragstellername (SAN) enthalten ist, ist die Domäne, die an XMPP-Kommunikationen teilnehmen kann. Die Domäne kann die Domäne auf Stammebene sein (beispielsweise contoso.com), wenn Sie XMPP für die gesamte Domäne aktivieren möchten, oder sie kann als untergeordnete Domäne (beispielsweise corp.contoso.com, finance.contoso.com) verwendet werden, wenn Sie XMPP für eine Teilmenge an Benutzern aktivieren.

## Zertifikatzusammenfassung für XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Komponente</th>
<th>Antragstellername</th>
<th>Alternativer Antragstellername (Subject Alternative Name, SAN)/Reihenfolge</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zuweisen zum Zugriffs-Edgedienst des Edgeservers oder des Edgepools</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Die ersten drei SAN-Einträge sind die regulären SAN-Einträge für einen vollständigen Edgeserver. &quot;contoso.com&quot; ist der für den Partnerverbund mit dem XMPP-Partner auf der Stammdomänenebene erforderliche Eintrag. Dieser Eintrag ermöglicht XMPP für alle Domänen mit dem Suffix &quot;contoso.com&quot;.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Aufgaben

[Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Konzepte

[Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  

#### Weitere Ressourcen

[Einrichten von Edgezertifikaten für Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

