---
title: 'Lync Server 2013: Verschlüsselung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Verschlüsselung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-09-14_

Microsoft lync Server 2013 verwendet TLS und MTLS zum Verschlüsseln von Sofortnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet. TLS ist optional, wird aber dringend zwischen dem Vermittlungs Server und dem Mediengateway empfohlen. Wenn TLS auf dieser Verbindung konfiguriert ist, ist MTLS erforderlich. Daher muss das Gateway mit einem Zertifikat von einer Zertifizierungsstelle konfiguriert werden, die vom Vermittlungs Server als vertrauenswürdig eingestuft wird.

<div>


> [!NOTE]  
> Im Jahr 2014 wurde eine Sicherheitsempfehlung zu SSL 3.0 veröffentlicht. Das Deaktivieren von SSL 3,0 in lync Server 2013 ist eine unterstützte Option. Weitere Informationen zur Sicherheitsempfehlung finden Sie unter <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.



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
<td>Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet lync Server 2013 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge für Clients an: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. TLS ist ein wichtiger Aspekt von lync Server 2013 und daher erforderlich, um eine unterstützte Umgebung zu erhalten.</td>
</tr>
</tbody>
</table>


</div>

Die Anforderungen für Client-zu-Client-Datenverkehr hängen davon ab, ob der Datenverkehr die interne Unternehmensfirewall überschreitet. Rein interner Datenverkehr kann entweder TLS verwenden, in diesem Fall wird die Sofortnachricht verschlüsselt, oder TCP, in diesem Fall nicht.

In der folgenden Tabelle sind die Protokollanforderungen für jeden Datenverkehrstyp zusammengefasst.

### <a name="traffic-protection"></a>Datenverkehrsschutz

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
<td><p>Chat und Anwesenheit</p></td>
<td><p>TLS (falls für TLS konfiguriert)</p></td>
</tr>
<tr class="even">
<td><p>Audio und Video und Desktopfreigaben von Medien</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Desktopfreigabe (Signal)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Webkonferenzen</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Herunterladen von Besprechungsinhalten, Herunterladen des Adressbuchs, Erweiterung der Verteilergruppe</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Medienverschlüsselung

Mediendatenverkehr wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport-Protokoll), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Vermittlungsserver und seinem internen nächsten Hop übertragen werden, ebenfalls über SRTP verschlüsselt. Medien, die in beide Richtungen zwischen dem Vermittlungs Server und einem Mediengateway fließen, werden standardmäßig nicht verschlüsselt. Der Vermittlungsserver kann die Verschlüsselung an das Mediengateway unterstützen, aber das Gateway muss MTLS und das Speichern eines Zertifikats unterstützen.

<div>


> [!NOTE]  
> Audio/Video (A/V) wird mit der neuen Version von Windows Live Messenger unterstützt. Wenn Sie einen/V-Verbund mit Windows Live Messenger implementieren, müssen Sie auch die lync Server-Verschlüsselungsstufe ändern. Standardmäßig ist die Verschlüsselungsstufe auf „Erforderlich“ eingestellt. Sie müssen diese Einstellung mithilfe der lync Server-Verwaltungsshell in unterstützt ändern. Weitere Informationen finden Sie unter <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

Der Datenverkehr für Audio-und Video Medien wird zwischen Microsoft lync 2013 und Windows Live-Clients nicht verschlüsselt.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 und Microsoft Exchange Server 2013 arbeiten mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server-Betriebssysteme so konfiguriert sind, dass Sie die FIPS 140-2-Algorithmen für die Systemkryptografie verwenden. Zum Implementieren der FIPS-Unterstützung müssen Sie jeden Server mit lync Server 2013 so konfigurieren, dass er unterstützt wird. Details zur Verwendung von FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, die Auswirkungen der Aktivierung von "System Kryptographie: Verwenden von FIPS-kompatiblen Algorithmen für Verschlüsselung, Hashing und Signierung"-Sicherheit. Einstellung in Windows XP und späteren Versionen von Windows unter [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Ausführliche Informationen zu FIPS 140-2-Unterstützung und Einschränkungen in Exchange 2010 finden Sie unter Exchange 2010 SP1 und Unterstützung für [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)FIPS-konforme Algorithmen unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

