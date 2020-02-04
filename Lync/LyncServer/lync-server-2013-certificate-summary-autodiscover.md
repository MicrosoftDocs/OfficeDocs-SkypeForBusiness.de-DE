---
title: 'Lync Server 2013: Zertifikatzusammenfassung – AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Zertifikatzusammenfassung – AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

Der lync Server 2013-AutoErmittlungsdienst wird auf den Director-und Front-End-Pool Servern ausgeführt und kann bei Veröffentlichung in DNS von lync-Clients zum Auffinden von Server-und Benutzerdiensten verwendet werden. Wenn Sie ein Upgrade von lync Server 2010 durchführen und keine Mobilität bereitstellen, bevor Clients die automatische Ermittlung verwenden können, müssen Sie die Listen für alternative Namen für Zertifikats Subjekte auf jedem Director-und Front-End-Server ändern, auf dem der AutoErmittlungsdienst ausgeführt wird. Darüber hinaus ist es möglicherweise erforderlich, die Listen Betreff alternativer Name auf Zertifikaten zu ändern, die für externe Webdienst Veröffentlichungsregeln für umgekehrte Proxys verwendet werden.

Die Entscheidung darüber, ob die Listen Betreff alternativer Namen in umgekehrten Proxys verwendet werden, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder auf Port 443 veröffentlichen:

  - **Veröffentlicht auf Port 80**   es sind keine Zertifikat Änderungen erforderlich, wenn die ursprüngliche Abfrage des AutoErmittlungsdiensts über Port 80 erfolgt. Dies liegt daran, dass Mobile Geräte, auf denen lync ausgeführt wird, auf den Reverseproxy auf Port 80 extern zugreifen und dann intern mit einem Director oder Front-End-Server auf Port 8080 überbrückt werden. Ausführliche Informationen finden Sie im Abschnitt "ursprünglicher Auto Ermittlungsprozess mit Port 80" unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Veröffentlicht auf Port 443**   die Liste der alternativen Subjektnamen für Zertifikate, die von der externen Webdienste-Veröffentlichungsregel verwendet werden, muss eine *lyncdiscover enthalten.\< sipdomain\> * -Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation.
    
    <div>
    

    > [!IMPORTANT]  
    > Es wird dringend empfohlen, HTTPS über HTTP zu verwenden. HTTPS verwendet Zertifikate, um den Datenverkehr zu verschlüsseln. HTTP bietet keine Verschlüsselung, und die gesendeten Daten sind nur Text.

    
    </div>

Das erneute ausgeben von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess. Bei öffentlichen Zertifikaten, die für die Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen von Einträgen mit mehreren Alternativen Subjekten teuer werden. Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann auf Port 8080 auf dem Director-oder Front-End-Server umgeleitet wird.

<div>


> [!NOTE]  
> Wenn Ihre lync Server 2013-Infrastruktur interne Zertifikate verwendet, die von einer internen Zertifizierungsstelle (Certification Authority, ca) ausgestellt wurden und Sie beabsichtigen, Mobile Geräte drahtlos zu unterstützen, muss entweder die Stammzertifikatkette von der internen Zertifizierungsstelle installiert werden. auf den mobilen Geräten oder müssen Sie zu einem öffentlichen Zertifikat in ihrer lync Server 2013-Infrastruktur wechseln.



</div>

In diesem Thema werden die für Director, Front-End-Server und Reverse Proxy erforderlichen zusätzlichen alternativen Namen für Subjekte beschrieben. Es werden nur die zusätzlichen alternativen Namen (Subject Alternative Names, San) referenziert. In den Planungs Abschnitten finden Sie Anleitungen zu den anderen Einträgen auf Zertifikaten. Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)und [Szenarien für den Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

In den folgenden Tabellen werden die San-Einträge für die AutoErmittlung für den Director-Pool, den Front-End-Pool und den Reverse-Proxy definiert:

### <a name="director-pool-certificate-requirements"></a>Anforderungen des Director-Pool Zertifikats

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für den alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des internen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscoverinternal. &lt;Interner Domänenname&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen das neu aktualisierte Zertifikat mit dem neuen San-Eintrag dem Standardzertifikat zu. Sie können auch San = * verwenden. &lt;sipdomain&gt;.



</div>

### <a name="front-end-pool-certificate-requirements"></a>Anforderungen für das Front-End-Pool Zertifikat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für den alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des internen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscoverinternal. &lt;Interner Domänenname&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen das neu aktualisierte Zertifikat mit dem neuen San-Eintrag dem Standardzertifikat zu. Sie können auch San = * verwenden. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Zertifikatanforderungen für Reverse Proxy (öffentliche Zertifizierungsstelle)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für den alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen das neu aktualisierte Zertifikat dem SSL-Listener auf dem Reverse-Proxy mit dem neuen San-Eintrag zu.



</div>

</div>

<span> </span>

</div>

</div>

</div>

