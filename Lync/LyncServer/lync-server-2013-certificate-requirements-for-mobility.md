---
title: 'Lync Server 2013: Zertifikatanforderungen für die Mobilität'
TOCTitle: Zertifikatanforderungen für die Mobilität
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690044(v=OCS.15)
ms:contentKeyID: 49295223
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatanforderungen für die Mobilität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn Sie das Mobilitätsfeature bereitstellen und die automatische Ermittlung für mobile Clients unterstützten, müssen Sie für Zertifikate bestimmte Einträge für alternative Antragstellernamen einfügen, um sichere Verbindungen von den mobilen Clients aus zu unterstützen.

Zur Unterstützung der automatischen Ermittlung müssen Sie für folgende Zertifikate Einträge für alternative Antragstellernamen einfügen:

  - Directorpool

  - Front-End-Pool

  - Reverseproxy

In diesem Abschnitt werden die Einträge für alternative Antragstellernamen beschrieben, die zur Unterstützung der automatischen Ermittlung für Zertifikate erforderlich sind.


> [!NOTE]
> Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist normalerweise ein einfacher Vorgang. Das Hinzufügen mehrerer Einträge für alternative Antragstellernamen zu öffentlichen Zertifikaten, die vom Reverseproxy verwendet werden, kann jedoch aufwendig sein. Wenn Sie über viele SIP-Domänen verfügen und das Hinzufügen alternativer Antragstellernamen daher sehr zeitaufwendig ist, können Sie Reverseproxy zum Verwenden von HTTP für die anfängliche AutoErmittlungsdienst-Anforderung verwenden, anstatt zum Verwenden von HTTPS (die Standardkonfiguration). Ausführliche Informationen finden Sie unter <A href="lync-server-2013-technical-requirements-for-mobility.md">Technische Anforderungen für die Mobilität in Lync Server 2013</A>.



### Directorpool-Zertifikatanforderungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne URL des AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;sipDomäne&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscover.&lt;sipDömäne&gt;</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Alternativ können Sie SAN=*.&lt;sipDömäne&gt; verwenden.



### Front-End-Pool-Zertifikatanforderungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne URL des AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;sipDomäne&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscover.&lt;sipDömäne&gt;</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Alternativ können Sie SAN=*.&lt;sipDömäne&gt; verwenden.



### Reverseproxy-Zertifikatanforderungen (öffentliche ZS)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscover.&lt;sipDömäne&gt;</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Sie weisen dieses SAN dem Zertifikat zu, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.




> [!NOTE]
> Ihr Reverseproxy-Listener verfügt über alternative Antragstellernamen für die externen Webdienste-URLs (z.&nbsp;B. "SAN=lyncwebextpool01.contoso.com" und "dirwebexternal.contoso.com", wenn Sie den optionalen Director bereitgestellt haben).


