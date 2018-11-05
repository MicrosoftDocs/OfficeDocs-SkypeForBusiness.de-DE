---
title: Verschlüsselung für Lync Server 2013
TOCTitle: Verschlüsselung für Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59679137
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschlüsselung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync Server 2013 verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet. TLS ist optional, wird aber zwischen dem Vermittlungsserver und dem Mediengateway dringend empfohlen. Wenn TLS auf dieser Verbindung konfiguriert ist, ist MTLS erforderlich. Daher muss das Gateway mit einem Zertifikat von einer Zertifizierungsstelle konfiguriert sein, die für die Vermittlungsserver vertrauenswürdig ist.

Die Anforderungen für den Client-zu-Client-Datenverkehr hängen davon ab, ob der Datenverkehr die interne Unternehmensfirewall überschreitet. Rein interner Datenverkehr kann entweder TLS verwenden, wobei die Chatnachricht verschlüsselt wird, oder TCP, wobei sie nicht verschlüsselt wird.

In der folgenden Tabelle sind die Protokollanforderungen für jeden Datenverkehrstyp zusammengefasst.

### Datenverkehrsschutz

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
<td><p>TLS (wenn für TLS konfiguriert)</p></td>
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


## Medienverschlüsselung

Mediendatenverkehr wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport Protocol), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt. SRTP verwendet einen Sitzungsschlüssel, der vom Mediarelay-Authentifizierungsdienst in Reaktion auf eine erfolgreiche Authentifizierung der Serveranforderung (im Namen der Medienteilnehmer) generiert wird. Der Sitzungsschlüssel wird von dem ausgehandelten Benutzernamen und Kennwort gesichert, die dem Mediarelay-Authentifizierungsdienst von den Front-End-Server präsentiert werden, und über den mit TLS gesicherten SIP-Kanal an die Teilnehmer gesendet. Die Entschlüsselung des gesicherten Sitzungsschlüssels mit dem Benutzernamen und Kennwort, die der Mediarelaydienst verwendet hat und die auf sichere Weise über das TLS-Zertifikat und den gesicherten SIP-Kanal bereitgestellt werden, ermöglicht den Teilnehmern die Entschlüsselung des SRTP-Streams. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Vermittlungsserver und seinem internen nächsten Hop übertragen werden, ebenfalls über SRTP verschlüsselt. Medien, die in beide Richtungen zwischen dem Vermittlungsserver und einem Gateway übertragen werden, werden nicht verschlüsselt. Der Vermittlungsserver kann die Verschlüsselung an das Mediengateway unterstützen, aber das Gateway muss MTLS und das Speichern eines Zertifikats unterstützen.


> [!NOTE]
> Audio/Video (A/V) wird mit der neuen Version von Windows Live Messenger unterstützt. Wenn Sie einen A/V-Verbund mit Windows Live Messenger implementieren, müssen Sie auch die Lync Server-Verschlüsselungsstufe ändern. Standardmäßig ist die Verschlüsselungsstufe „Erforderlich“. Sie müssen diese Einstellung über die Lync Server-Verwaltungsshell auf „Unterstützt“ ändern. Weitere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013</A>.



Audio- und Videomediendatenverkehr wird nicht zwischen Microsoft Lync 2013- und Windows Live-Clients verschlüsselt.

## FIPS

Lync Server 2013 und Microsoft Exchange Server 2013 unterstützen FIPS 140-2-Algorithmen (Federal Information Processing Standard), wenn die Windows Server-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert wurden. Um FIPS-Unterstützung zu implementieren, müssen Sie jeden Server mit Lync Server 2013 so konfigurieren, dass er FIPS unterstützt. Ausführliche Informationen zu FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, „Auswirkungen der Sicherheitseinstellung 'Systemkryptografie: FIPS-konformen Algorithmus für Verschlüsselung, Hashing und Signatur verwenden' unter Windows XP und neueren Version von Windows“ unter [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Ausführliche Informationen zur Unterstützung von FIPS 140-2 und den dafür geltenden Einschränkungen in Exchange 2010 finden Sie unter Exchange 2010 SP1 und Unterstützung für FIPS-kompatible Algorithmen unter [http://go.microsoft.com/fwlink/p/?LinkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).

