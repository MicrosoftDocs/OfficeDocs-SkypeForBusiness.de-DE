---
title: Zertifikatübersicht – AutoErmittlung
TOCTitle: Zertifikatübersicht – AutoErmittlung
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945616(v=OCS.15)
ms:contentKeyID: 52056291
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatübersicht – AutoErmittlung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Lync Server 2013-AutoErmittlungsdienst wird auf dem Director und auf Servern im Front-End-Pool ausgeführt und kann bei Veröffentlichung in DNS von Lync-Clients zum Suchen von Server- und Benutzerdiensten verwendet werden. Wenn Sie ein Upgrade von Lync Server 2010 durchführen und keine Mobilität bereitgestellt haben, müssen Sie bestimmte Listen mit alternativen Antragstellernamen auf allen Directors und Front-End-Servern ändern, auf denen der AutoErmittlungsdienst ausgeführt wird, damit Clients die die automatische Ermittlung verwenden können. Möglicherweise müssen auch die Listen mit alternativen Antragstellernamen auf Zertifikaten geändert werden, für Zertifikate zu ändern, die von Veröffentlichungsregeln für externe Webdienste auf Reverseproxys verwendet werden.

Die Entscheidung, ob auf Reverseproxys alternative Antragstellernamen verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst an Port 80 oder an Port 443 veröffentlichen:

  - **Veröffentlicht an Port 80**   Es sind keine Zertifikatänderungen erforderlich, wenn die anfängliche Abfrage des AutoErmittlungsdiensts über den Port 80 erfolgt. Dies ist darauf zurückzuführen, dass mobile Geräte, auf denen Lync ausgeführt wird, extern auf den Reverseproxy an Port 80 zugreifen und dann intern an einen Director oder Front-End-Server an Port 8080 umgeleitet werden. Ausführliche Informationen finden Sie im Abschnitt "Anfänglicher AutoErmittlungsprozess über Port 80" unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Veröffentlicht an Port 443**   Die Liste der alternativen Antragstellennamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, müssen einen *lyncdiscover.\<sipdomain\>*-Eintrag für jede SIP-Domäne in der Organisation enthalten.
    

    > [!IMPORTANT]
    > Es wird ausdrücklich empfohlen, HTTPS anstatt HTTP zu verwenden. HTTPS verwendet Zertifikate von Verschlüsseln von Datenverkehr. HTTP bietet keine Verschlüsselung; alle Daten werden als Nur-Text gesendet.



Das erneute Ausstellen von Zertifikaten durch eine interne Zertifizierungsstelle ist normalerweise ein einfacher Vorgang. Bei öffentlichen Zertifikaten, die für die Webdienst-Veröffentlichungsregel verwendet werden, kann das Hinzufügen mehrerer alternativer Antragstellernamen jedoch aufwendig sein. Zur Umgehung dieses Problems wird die anfängliche Verbindung der automatischen Ermittlung über Port 80 unterstützt, die dann an Port 8080 für den Director oder den Front-End-Server umgeleitet wird.


> [!NOTE]
> Wenn Sie in der Lync Server 2013-Infrastruktur interne Zertifikate verwenden, die von einer internen Zertifizierungsstelle (ZS) ausgestellt werden, und planen, eine WLAN-Verbindung für mobile Geräte zu unterstützen, muss entweder die Stammzertifikatkette von der internen ZS auf den mobilen Geräten installiert sein, oder Sie müssen für die Lync Server 2013-Infrastruktur ein öffentliches Zertifikat verwenden.



In diesem Thema werden die zusätzlichen alternativen Antragstellernamen beschrieben, die für Director den Front-End-Server und den Reverseproxy erforderlich sind. Es wird nur auf die zusätzlichen alternativen Antragstellernamen (Subject Alternative Names, SAN) verwiesen. Anweisungen zu den anderen Einträgen auf Zertifikaten finden Sie in den Abschnitten zur Planung. Ausführliche Informationen finden Sie unter [Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und [Szenarien für Reverseproxys in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

In den folgenden Tabellen werden die Einträge von zusätzlichen alternativen Antragstellernamen der AutoErmittlung für den Directorpool, den Front-End-Pool und den Reverseproxy beschrieben:

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
<td><p>SAN=lyncdiscoverinternal.<em>&lt;interner domänenname&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;sipdomäne&gt;</em></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Sie weisen das soeben aktualisierte Zertifikat mit dem neuen SAN-Eintrag dem Standardzertifikat zu. Alternativ können Sie auch SAN=*.<EM>&lt;sipdomäne&gt;</EM>verwenden.



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
<td><p>SAN=lyncdiscoverinternal.<em>&lt;interner domänenname&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;sipdomäne&gt;</em></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Sie weisen das soeben aktualisierte Zertifikat mit dem neuen SAN-Eintrag dem Standardzertifikat zu. Alternativ können Sie auch SAN=*.<EM>&lt;sipdomäne&gt;</EM>verwenden.



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
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;sipdomäne&gt;</em></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Sie weisen das soeben aktualisierte Zertifikat mit dem neuen SAN-Eintrag dem SSL-Listener auf dem Reverseproxy zu.


