---
title: 'Lync Server 2013: Häufige Sicherheitsbedrohungen in der modernen Datenverarbeitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60197a65bb0362b1bbdcf3fee779ed503af00eb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526132"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Häufige Sicherheitsbedrohungen in der modernen Datenverarbeitung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-09-10_

Da es sich bei lync Server 2013 um ein Kommunikationssystem der Unternehmensklasse handelt, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und die Kommunikation auswirken könnten.

<div>

## <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. Es gibt zwei vertrauliche Schlüssel, die in der Public Key-Infrastruktur (PKI) verwendet werden, die berücksichtigt werden müssen:.

  - Der private Schlüssel, den jeder Zertifikatbesitzer hat

  - Der Sitzungsschlüssel, der nach einer erfolgreichen Identifizierung und einem Sitzungsschlüssel Austausch durch die kommunizierenden Partner verwendet wird.

Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.

Lync Server 2013 verwendet die PKI-Funktionen im Windows Server-Betriebssystem, um die für die Verschlüsselung verwendeten Schlüsseldaten für die TLS-Verbindungen (Transport Layer Security) zu schützen. Die für die Medienverschlüsselung verwendeten Tasten werden über TLS-Verbindungen ausgetauscht.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk

Der *Denial-of-Service-Angriff* tritt auf, wenn der Angreifer eine normale Netzwerknutzung und Funktion durch gültige Benutzer verhindert. Dies geschieht, wenn der Angreifer den Dienst mit legitimen Anforderungen überflutet, die die Verwendung des Diensts durch berechtigte Benutzer überfordern. Durch die Verwendung eines Denial-of-Service-Angriffs kann der Angreifer folgende Aktionen ausführen:

  - Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.

  - Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.

  - Er kann die Spuren seines Angriffs vertuschen.

  - Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Lauschangriffe (schnüffeln, schnüffeln)

*Lauschangriffe* können auftreten, wenn ein Angreifer Zugriff auf den Datenpfad in einem Netzwerk erhält und über die Möglichkeit verfügt, den Datenverkehr zu überwachen und zu lesen. Dies wird auch als *Sniffing* oder *Snooping*bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, kann der Angreifer ihn lesen, sobald er Zugriff auf den Pfad hat. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird.

Die standardmäßige Empfehlung und Einstellung für den Datenverkehr in Microsoft lync Server 2013 besteht darin, MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS von Client zu Server zu verwenden. Diese Schutzmaßnahme würde einen Angriff innerhalb des Zeitraums, in dem eine bestimmte Unterhaltung stattfindet, sehr schwierig oder unmöglich machen. TLS authentifiziert alle Parteien und verschlüsselt den gesamten Datenverkehr. Dies verhindert nicht das Abhören, aber der Angreifer kann den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung ist beschädigt.

Mit dem Relay-NAT-Protokoll (Umkehren) wird der Datenverkehr nicht verschlüsselt, und die gesendeten Informationen werden durch die Nachrichtenintegrität geschützt. Obwohl es zum Abhören geöffnet ist, können die gesendeten Informationen (also die IP-Adressen und der Port) direkt extrahiert werden, indem Sie einfach die Quell-und Zieladressen der Pakete betrachten. Das A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem die Nachrichtenintegrität der Nachricht mithilfe des von einigen wenigen Elementen abgeleiteten Schlüssels überprüft wird, einschließlich eines Umdrehungs Kennworts, das nie in Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, wird der Mediendatenverkehr ebenfalls verschlüsselt.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Identitäts Spoofing (IP-Adress Spoofing)

*Spoofing* tritt auf, wenn der Angreifer die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermittelt und verwendet, ohne hierzu autorisiert zu sein. Ein erfolgreicher Angriff ermöglicht es dem Angreifer, zu funktionieren, als wäre der Angreifer die Entität, die normalerweise durch die IP-Adresse identifiziert wird. Im Kontext von Microsoft lync Server 2013 kommt diese Situation nur dann ins Spiel, wenn ein Administrator die folgenden beiden Schritte ausgeführt hat:

  - Konfigurierte Verbindungen, die nur TCP (Transmission Control Protocol) unterstützen (Dies wird nicht empfohlen, da die TCP-Kommunikation nicht verschlüsselt ist).

  - Die IP-Adressen dieser Verbindungen wurden als vertrauenswürdige Hosts gekennzeichnet.

Dies ist ein kleineres Problem bei TLS-Verbindungen (Transport Layer Security), da TLS alle Beteiligten authentifiziert und den gesamten Datenverkehr verschlüsselt. Durch die Verwendung von TLS wird verhindert, dass ein Angreifer IP-Adress Spoofing für eine bestimmte Verbindung ausführt (beispielsweise gegenseitige TLS-Verbindungen). Ein Angreifer kann jedoch weiterhin die Adresse des DNS-Servers spoofen, der von lync Server 2013 verwendet wird. Da die Authentifizierung in lync jedoch mit Zertifikaten durchgeführt wird, verfügt ein Angreifer nicht über ein gültiges Zertifikat, das für die Spoofing einer der Parteien in der Kommunikation erforderlich ist.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Ein man-in-the-Middle-Angriff tritt auf, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern über den Computer des Angreifers ohne das Wissen der beiden kommunizierenden Benutzer umleitet. Der Angreifer kann den Datenverkehr überwachen und lesen, bevor er ihn an den beabsichtigten Empfänger sendet. Jeder Benutzer in der Kommunikation sendet unwissentlich Datenverkehr an den Angreifer und empfängt ihn, während er denkt, dass er nur mit dem vorgesehenen Benutzer kommuniziert. Dies kann passieren, wenn ein Angreifer Active Directory-Domänendienste ändern kann, um seinen Server als vertrauenswürdigen Server hinzuzufügen oder um Domain Name System (DNS) zu ändern, damit Clients auf dem Weg zum Server über den Angreifer eine Verbindung herstellen können. Ein man-in-the-Middle-Angriff kann auch mit dem Mediendatenverkehr zwischen zwei Clients auftreten. In Microsoft lync Server 2013 die gemeinsame Verwendung von Audio-, Video-und Anwendungsfreigaben mit mehreren Punkten wird jedoch mit SRTP verschlüsselt, wobei kryptografische Schlüssel verwendet werden, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden. Server wie Gruppen Chat verwenden HTTPS, um die Sicherheit des Webdatenverkehrs zu verbessern.

</div>

<div>

## <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Ein *Wiedergabeangriff* tritt auf, wenn eine gültige Medienübertragung zwischen zwei Parteien abgefangen und zu böswilligen Zwecken erneut übermittelt wird. SRTP, das in Verbindung mit einem Secure Signaling-Protokoll verwendet wird, schützt Übertragungen vor Replay-Angriffen, indem es dem Empfänger ermöglicht, einen Index der bereits empfangenen RTP-Pakete beizubehalten und jedes neue Paket mit denen zu vergleichen, die bereits im Index aufgeführt sind.

</div>

<div>

## <a name="spim"></a>Spim

*Spim* ist unerbetene kommerzielle Sofortnachrichten oder Anwesenheitsabonnementanforderungen. Zwar selbst keine Kompromisse im Netzwerk, sondern im geringsten stört, kann Ressourcenverfügbarkeit und-Produktion reduzieren und möglicherweise zu einer Gefährdung des Netzwerks führen. Ein Beispiel hierfür sind Benutzer, die sich gegenseitig durch Senden von Anforderungen Spimming. Benutzer können sich gegenseitig blockieren, um dies zu verhindern, aber mit dem Verbund, wenn ein koordinierter spim-Angriff hergestellt wird, kann dies nur schwer zu überwinden sein, wenn Sie den Partnerverbund nicht deaktivieren.

</div>

<div>

## <a name="viruses-and-worms"></a>Viren und Würmer

Ein *Virus* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren. Um zu funktionieren, benötigt ein Virus einen Host, beispielsweise eine Datei, eine e-Mail oder ein Programm. Ein *Wurm* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren, jedoch keinen Host benötigt. Viren und Würmer werden in erster Linie bei Dateiübertragungen zwischen Clients oder beim Senden von URLs von anderen Benutzern angezeigt. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und in Ihrem Namen Sofortnachrichten senden.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen

Microsoft lync Server 2013 hat das Potenzial, Informationen über ein öffentliches Netzwerk offen zu geben, die möglicherweise mit einer Person verknüpft werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:

  - **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer für die Freigabe oder nicht Freigabe über einen Link zu einem Verbundpartner oder mit Kontakten in einer Organisation auswählen kann. Diese Daten werden nicht für Benutzer in einem öffentlichen Chat Netzwerk freigegeben. Clientrichtlinien und andere Clientkonfigurationen können dem System Administrator eine gewisse Kontrolle versetzen. In lync Server 2013 kann ein erweiterter Anwesenheitsdaten Schutzmodus für einen einzelnen Benutzer konfiguriert werden, um zu verhindern, dass lync-Benutzer die Anwesenheitsinformationen des Benutzers nicht in der Kontaktliste des Benutzers sehen. Der Datenschutzmodus für verstärkte Anwesenheit hindert Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 nicht daran, die Anwesenheitsinformationen eines Benutzers zu sehen. Ausführliche Informationen finden Sie unter [What es New for Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in der Dokumentation "erste Schritte" und [Konfigurieren des Datenschutzmodus für erweiterte Anwesenheit in lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in der Bereitstellungsdokumentation.

  - **Obligatorische Daten** Obligatorische Daten sind für den ordnungsgemäßen Betrieb des Servers oder des Clients erforderlich und unterliegen nicht der Kontrolle der Client-oder Systemverwaltung. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.

In den folgenden Tabellen sind die Daten aufgeführt, die über ein öffentliches Netzwerk verfügbar gemacht werden.

### <a name="enhanced-presence-data"></a>Erweiterte Anwesenheitsdaten

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Offen gelegte Daten</th>
<th>Mögliche Einstellungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Persönliche Daten</p></td>
<td><p>Name, Titel, Unternehmen, e-Mail-Adresse, Zeitzone</p></td>
</tr>
<tr class="even">
<td><p>Telefonnummern</p></td>
<td><p>Geschäftlich, mobil, privat</p></td>
</tr>
<tr class="odd">
<td><p>Kalenderdaten</p></td>
<td><p>Frei/gebucht, out-of-Town Notice, Besprechungs Details (für Personen, die Zugriff auf Ihren Kalender haben)</p></td>
</tr>
<tr class="even">
<td><p>Anwesenheitsstatus</p></td>
<td><p>Abwesend, verfügbar, gebucht, nicht stören, offline</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>Pflichtdaten

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Offen gelegte Daten</th>
<th>Beispiel Informationen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IP-Adresse</p></td>
<td><p>Tatsächliche Computer- oder NAT-Adresse</p></td>
</tr>
<tr class="even">
<td><p>SIP-URI</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

