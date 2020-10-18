---
title: 'Lync Server 2013: Zertifikatzusammenfassung-AutoErmittlung'
description: 'Lync Server 2013: Zertifikatzusammenfassung-AutoErmittlung.'
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
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574711"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-14_

Der lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann bei Veröffentlichung in DNS von lync-Clients zum Auffinden von Server-und Benutzerdiensten verwendet werden. Wenn Sie ein Upgrade von lync Server 2010 durchführen und keine Mobilität bereitgestellt haben, müssen Sie, bevor Clients die automatische Ermittlung verwenden können, die Listen alternativer Zertifikatsantrags Teller Namen auf allen Directors ändern und Front-End-Server ausführen des AutoErmittlungsdiensts. Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.

Die Entscheidung, ob Listen für alternative Antragstellernamen in umgekehrten Proxys verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder an Port 443 veröffentlichen:

  - **Veröffentlicht am Port 80**     Wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt, sind keine Änderungen am Zertifikat erforderlich. Dies liegt daran, dass Mobile Geräte, auf denen lync betrieben wird, extern auf den Reverseproxy auf Port 80 zugreifen und dann intern mit einem Director oder Front-End-Server an Port 8080 überbrückt werden. Ausführliche Informationen finden Sie im Abschnitt "erste Auto Ermittlungsverfahren mit Port 80" [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Veröffentlicht am Port 443**     Die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein *lyncdiscover enthalten. \<sipdomain\> * Eintrag für jede SIP-Domäne in Ihrer Organisation.
    
    <div>
    

    > [!IMPORTANT]  
    > Es wird dringend empfohlen, HTTPS über HTTP zu verwenden. HTTPS verwendet Zertifikate zum Verschlüsseln des Datenverkehrs. HTTP bietet keine Verschlüsselung, und alle gesendeten Daten sind nur-Text.

    
    </div>

Das neuausgeben von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess. Bei öffentlichen Zertifikaten, die in der Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen mehrerer alternativer Antragstellernamen teuer werden. Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann an Port 8080 auf dem Director oder Front-End-Server umgeleitet wird.

<div>


> [!NOTE]  
> Wenn Ihre lync Server 2013-Infrastruktur interne Zertifikate verwendet, die von einer internen Zertifizierungsstelle ausgestellt werden und Sie mobile Geräte mit Drahtlosverbindung unterstützen möchten, muss entweder die Stammzertifikatkette von der internen Zertifizierungsstelle auf den mobilen Geräten installiert sein, oder Sie müssen zu einem öffentlichen Zertifikat in ihrer lync Server 2013 Infrastruktur wechseln.



</div>

In diesem Thema werden die zusätzlichen alternativen Antragstellernamen beschrieben, die für Director, Front-End-Server und Reverse Proxy erforderlich sind. Es wird nur auf die hinzugefügten alternativen Antragstellernamen (San) verwiesen. In den Planungs Abschnitten erhalten Sie Anleitungen zu den anderen Einträgen in Zertifikaten. Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)und [Szenarien für Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

In den folgenden Tabellen werden die San-Einträge für die AutoErmittlung für die Directorpool, die Front-End-Pool und den Reverseproxy definiert:

### <a name="director-pool-certificate-requirements"></a>Directorpool-Zertifikatanforderungen

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
<td><p>San = "lyncdiscoverinternal". &lt; Interner Domänenname&gt;</p></td>
</tr>
<tr class="even">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt; sipdomain "&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem Standardzertifikat zu. Alternativ können Sie San = * verwenden. &lt; sipdomain " &gt; .



</div>

### <a name="front-end-pool-certificate-requirements"></a>Front-End-Pool-Zertifikatanforderungen

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
<td><p>San = "lyncdiscoverinternal". &lt; Interner Domänenname&gt;</p></td>
</tr>
<tr class="even">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt; sipdomain "&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem Standardzertifikat zu. Alternativ können Sie San = * verwenden. &lt; sipdomain "&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Reverseproxy-Zertifikatanforderungen (öffentliche ZS)

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
<td><p>San = lyncdiscover. &lt; sipdomain "&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem SSL-Listener auf dem Reverseproxy zu.



</div>

</div>

<span> </span>

</div>

</div>

</div>

