---
title: DNS-Anforderungen für die automatische Clientanmeldung
TOCTitle: DNS-Anforderungen für die automatische Clientanmeldung
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425884(v=OCS.15)
ms:contentKeyID: 49293739
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für die automatische Clientanmeldung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt wird erläutert, welche DNS-Einträge (Domain Name System) für die automatische Clientanmeldung erforderlich sind. Wenn Sie Standard Edition-Server oder Front-End-Pools bereitstellen, können Sie Ihre Clients zur automatischen Ermittlung von und Anmeldung am geeigneten Standard Edition-Server oder Front-End-Pool konfigurieren. Sie können dieses Thema überspringen, wenn die Verbindung zwischen Ihren Clients und Lync Server 2013 manuell hergestellt werden soll.

Zur Unterstützung der automatischen Clientanmeldung müssen Sie folgende Aufgaben ausführen:

  - Legen Sie einen einzelnen Server oder Pool für die Verteilung und Authentifizierung von Clientanmeldeanforderungen fest. Hierbei kann es sich um einen vorhandenen Server oder Pool handeln, der Benutzer hostet, oder Sie können zu diesem Zweck einen dedizierten Server oder Pool zuweisen, der keine Benutzer hostet. Um eine hohe Verfügbarkeit sicherzustellen, wird empfohlen, einen Front-End-Pool für diese Funktion zuzuweisen.

  - Erstellen Sie einen internen DNS-SRV-Eintrag zur Unterstützung der automatischen Clientanmeldung für diesen Server oder Pool.
    

    > [!NOTE]
    > In den folgenden Eintragsanforderungen bezieht sich die SIP-Domäne auf den Hostabschnitt der SIP-URIs, die Benutzern zugewiesen sind. Wenn die SIP-URIs beispielsweise das Format "*@contoso.com" aufweisen, bezeichnet "contoso.com" die SIP-Domäne. Die SIP-Domäne unterscheidet sich häufig von der internen Active Directory-Domäne. In einer Organisation können auch mehrere SIP-Domänen unterstützt werden.



Um die automatische Konfiguration der Clients zu ermöglichen, müssen Sie einen internen DNS-SRV-Eintrag erstellen, der einen der folgenden Einträge dem vollqualifizierten Domänennamen (FQDN) des Front-End-Pools oder Standard Edition-Servers zuordnet, von dem Anmeldeanforderungen von Lync-Clients verteilt werden:

  - \_sipinternaltls.\_tcp.*\<Domäne\>* – für interne TLS-Verbindungen

Sie müssen für den Front-End-Pool oder Standard Edition-Server, der die Anmeldeanforderungen verteilt, nur einen einzigen SRV-Eintrag erstellen.

Die folgende Tabelle enthält einige der erforderlichen Beispieleinträge für das fiktive Unternehmen Contoso, das die SIP-Domänen "contoso.com" und "retail.contoso.com" unterstützt.

### Beispiele für erforderliche DNS-Einträge für die automatische Clientanmeldung bei mehreren SIP-Domänen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN des Front-End-Pools für die Verteilung von Anmeldeanforderungen</th>
<th>SIP-Domäne</th>
<th>DNS-SRV-Eintrag</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Ein SRV-Eintrag für die Domäne &quot;_sipinternaltls._tcp.contoso.com&quot; über Port 5061, der &quot;pool01.contoso.com&quot; zugeordnet ist</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Ein SRV-Eintrag für die Domäne &quot;_sipinternaltls._tcp.retail.contoso.com&quot; über Port 5061, der &quot;pool01.contoso.com&quot; zugeordnet ist</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> In der Standardeinstellung müssen bei Abfragen für DNS-Einträge die Domänennamen im Benutzernamen und im SRV-Eintrag genau übereinstimmen. Wenn bei DNS-Abfragen des Clients stattdessen die Suffixe verglichen werden sollen, können Sie die Gruppenrichtlinie "DisableStrictDNSNaming" konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planen von Clients und Geräten in Lync Server 2013</A> in der Planungsdokumentation.



## Beispiele für erforderliche Zertifikate und DNS-Einträge für die automatische Clientanmeldung

In diesem Beispiel werden dieselben Beispiele wie in der oben gezeigten Tabelle verwendet. Das Unternehmen Contoso unterstützt die SIP-Domänen "contoso.com" und "retail.contoso.com", und alle Benutzer des Unternehmens verfügen über einen SIP-URI in einem der folgenden Formate:

  - *\<Benutzer\>*@retail.contoso.com

  - *\<Benutzer\>*@contoso.com

