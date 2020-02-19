---
title: 'Lync Server 2013: Verschlüsselung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac24736d55b59396e9c04041b4356c0983154c71
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Verschlüsselung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-09-14_

Microsoft lync Server 2013 verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Der gesamte Datenverkehr zwischen den Servern erfordert MTLS, und zwar unabhängig davon, ob die Daten innerhalb des internen Netzwerks verbleiben oder den internen Netzwerkumkreis verlassen. TLS ist optional, wird jedoch dringend zwischen dem Vermittlungsserver und dem Mediengateway empfohlen. Wenn TLS für diesen Link konfiguriert ist, ist MTLS erforderlich. Aus diesem Grund muss das Gateway mit einem Zertifikat von einer für den Vermittlungsserver vertrauenswürdigen Zertifizierungsstelle konfiguriert werden.

<div>


> [!NOTE]  
> Eine Sicherheitsempfehlung zu SSL 3,0 wurde in 2014 veröffentlicht. Das Deaktivieren von SSL 3,0 in lync Server 2013 ist eine unterstützte Option. Weitere Informationen zur Sicherheitsempfehlung finden Sie unter <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet lync Server 2013 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge für Clients an: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. TLS ist ein wichtiger Aspekt von lync Server 2013 und ist daher erforderlich, um eine unterstützte Umgebung beizubehalten.</td>
</tr>
</tbody>
</table>


</div>

Die Anforderungen für den Datenverkehr zwischen Clients sind davon abhängig, ob dieser Datenverkehr die interne Unternehmensfirewall durchquert. Für komplett internen Datenverkehr kann TLS oder TCP verwendet werden. (Lediglich bei TLS wird die Sofortnachricht verschlüsselt.)

In der folgenden Tabelle werden die Protokollanforderungen für die einzelnen Datenverkehrstypen dargestellt.

### <a name="traffic-protection"></a>Schutz des Datenverkehrs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Datenverkehrstyp</th>
<th>Geschützt durch</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server-zu-Server</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Client-zu-Server</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Sofortnachrichten und Anwesenheit</p></td>
<td><p>TLS (wenn für TLS konfiguriert)</p></td>
</tr>
<tr class="even">
<td><p>Audio-, Video- und Desktopfreigabe von Medien</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Desktopfreigabe (Signaldaten)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Webkonferenzen</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Herunterladen von Besprechungsinhalten und Adressbüchern, Erweiterung der Verteilergruppe</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Medienverschlüsselung

Der Mediendatenverkehr wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport Protocol), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Vermittlungsserver und dem internen nächsten Hop fließen, ebenfalls mithilfe von SRTP verschlüsselt. Medien, die in beide Richtungen zwischen dem Vermittlungsserver und einem Mediengateway fließen, werden standardmäßig nicht verschlüsselt. Das Vermittlungsserver kann die Verschlüsselung für das Mediengateway unterstützen, das Gateway muss jedoch MTLS und das Speichern eines Zertifikats unterstützen.

<div>


> [!NOTE]  
> Audio/Video (A/V) wird mit der neuen Version von Windows Live Messenger unterstützt. Wenn Sie einen A/V-Partnerverbund mit Windows Live Messenger implementieren, müssen Sie auch die Microsoft Lync Server 2010-Verschlüsselungsstufe ändern. Standardmäßig lautet die Verschlüsselungsstufe "Erforderlich". Sie müssen diese Einstellung in unterstützt ändern, indem Sie die lync Server-Verwaltungsshell verwenden. Weitere Informationen finden Sie unter <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

Der Datenverkehr für Audio-und Video Medien wird nicht zwischen Microsoft lync 2013 und Windows Live-Clients verschlüsselt.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 und Microsoft Exchange Server 2013 arbeiten mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert sind. Um die FIPS-Unterstützung zu implementieren, müssen Sie jeden Server konfigurieren, der lync Server 2013 ausführt, um ihn zu unterstützen. Ausführliche Informationen zur Verwendung von FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, die Auswirkungen der Aktivierung der Sicherheitseinstellung "System Kryptografie: FIPS-konforme Algorithmen für Verschlüsselung, Hashing und Signierung verwenden" unter Windows XP und in höheren Windows [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)-Versionen unter. Ausführliche Informationen zur Unterstützung von FIPS 140-2 und zu Einschränkungen in Exchange 2010 finden Sie unter Exchange 2010 SP1 und Unterstützung [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)für FIPS-konforme Algorithmen unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

