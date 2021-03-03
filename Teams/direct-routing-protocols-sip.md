---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Direct Routing protocols
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fe636029c3a058dc1a8d33cc191d7654888ec5e
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278725"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing – SIP-Protokoll

In diesem Artikel wird beschrieben, wie direct Routing das Session Initiation Protocol (SIP) implementiert. Für die richtige Route des Datenverkehrs zwischen einem Session Border Controller (SBC) und dem SIP-Proxy müssen einige SIP-Parameter bestimmte Werte haben. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst verantwortlich sind.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Verarbeiten der eingehenden Anforderung: Suchen des Mandanten und des Benutzers

Bevor ein eingehender oder ausgehender Anruf verarbeitet werden kann, werden zwischen dem SIP-Proxy und dem SBC Optionsnachrichten ausgetauscht. Diese Optionsmeldungen ermöglichen es dem SIP-Proxy, SBC die zulässigen Funktionen zur Verfügung zu stellen. Es ist wichtig, dass die Aushandlung mit OPTIONEN erfolgreich ist (200OK-Antwort), um eine weitere Kommunikation zwischen SBC- und SIP-Proxy zum Herstellen von Anrufen zu ermöglichen. Die SIP-Header in einer OPTIONS-Nachricht an den SIP-Proxy sind unten aufgeführt:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONEN sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Über Kopfzeile | Über: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max-Forwards:68 |
| Aus Kopfzeile | Aus Kopfzeile von: <sip:sbc1.adatum.biz:5058> |
| Kopfzeile | An: <sip:sip.pstnhub.microsoft.com:5061> |
| #A0 | CSeq: 1 EINLADUNG | 
| Kontaktkopfzeile | Kontakt: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Die SIP-Header enthalten keine Benutzerinfos im verwendeten SIP-URI. Nach [RFC 3261, Abschnitt 19.1.1,](https://tools.ietf.org/html/rfc3261#section-19.1.1)ist der Teil "userinfo" eines URI optional und kann abwesend sein, wenn der Zielhost keine Vorstellung von Benutzern hat oder der Hosst selbst die zu identifizierende Ressource ist. Wenn das @-Zeichen in einem SIP-URI vorhanden ist, darf das Benutzerfeld NICHT leer sein.

Bei einem eingehenden Anruf muss der SIP-Proxy den Mandanten suchen, an den der Anruf bestimmt ist, und den bestimmten Benutzer in diesem Mandanten finden. Der Mandantenadministrator kann Nicht-DID-Nummern, z. B. +1001, in mehreren Mandanten konfigurieren. Daher ist es wichtig, den spezifischen Mandanten zu finden, für den die Zahlen nachgeschaut werden sollen, da die Nicht-DID-Nummern in mehreren Microsoft 365- oder Office 365-Organisationen identisch sein können.  

In diesem Abschnitt wird beschrieben, wie der SIP-Proxy den Mandanten und den Benutzer findet und die Authentifizierung des SBC für die eingehende Verbindung durchführt.

Im Folgenden finden Sie ein Beispiel für die NACHRICHT "SIP-Einladung" bei einem eingehenden Anruf:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | EINLADEN sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Über Kopfzeile | Über: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max-Forwards:68 |
| Aus Kopfzeile | Aus Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| Kopfzeile | So: sip:+183338006777@sbc1.adatum.biz | 
| #A0 | CSeq: 1 EINLADUNG | 
| Kontaktkopfzeile | Kontakt: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Beim Empfang der Einladung führt der SIP-Proxy die folgenden Schritte aus:

1. Überprüfen Sie das Zertifikat. Bei der anfänglichen Verbindung verwendet der Direct Routing-Dienst den im Kopf des Kontakts angezeigten FQDN-Namen und gleicht ihn mit dem allgemeinen Namen oder dem alternativen Namen des präsentierten Zertifikats ab. Der Name des SBC muss einer der folgenden Optionen entsprechen:

   - Option 1. Der vollständige FQDN-Name, der in der Kopfzeile des Kontakts angezeigt wird, muss mit dem alternativen Namen für "Gemeinsamer Name/Betreff" des präsentierten Zertifikats übereinstimmen.  

   - Option 2. Der Domänenteil des #A0 im Kontaktheader (z. B. adatum.biz des FQDN-Namens sbc1.adatum.biz) muss mit dem Platzhalterwert in "Gemeinsamer Name/Betreff Alternativer Name" (z. B. *.adatum.biz) übereinstimmen.

2. Versuchen Sie, einen Mandanten mit dem vollständigen FQDN-Namen zu finden, der im Kopf des Kontakts angezeigt wird.  

   Überprüfen Sie, ob der FQDN-Name aus dem Kontaktheader (sbc1.adatum.biz) in einer beliebigen Microsoft 365- oder Office 365-Organisation als DNS-Name registriert ist. Falls gefunden, wird die Suche des Benutzers in dem Mandanten ausgeführt, bei dem der SBC-FQDN als Domänenname registriert ist. Wenn sie nicht gefunden wird, gilt Schritt 3.   

3. Schritt 3 gilt nur, wenn Schritt 2 fehlgeschlagen ist. 

   Entfernen Sie den Hostteil aus dem FQDN, der im Kontaktheader (FQDN: sbc12.adatum.biz, nach dem Entfernen des Hostteils: adatum.biz) angezeigt wird, und überprüfen Sie, ob dieser Name in einer beliebigen Microsoft 365- oder Office 365-Organisation als DNS-Name registriert ist. Wenn gefunden, wird die Benutzer-Suche in diesem Mandanten ausgeführt. Wenn sie nicht gefunden wird, schlägt der Aufruf fehl.

4. Führen Sie mit der im Anforderungs-URI dargestellten Telefonnummer die in Schritt 2 oder 3 gefundene umgekehrte Nummern-Suche innerhalb des Mandanten durch. Passen Sie die angezeigte Telefonnummer an einen SIP-URI eines Benutzers innerhalb des Mandanten an, der im vorherigen Schritt gefunden wurde.

5. "Trunkeinstellungen anwenden" aus. Suchen Sie die Parameter, die vom Mandantenadministrator für diesen SBC festgelegt wurden.

   Microsoft unterstützt nicht die Verwendung eines Drittanbieter-SIP-Proxys oder Benutzer-Agent-Servers zwischen dem Microsoft -SIP-Proxy und dem gekoppelten SBC, wodurch sich der anforderungs-URI ändern kann, der von dem gekoppelten SBC erstellt wird.

   Die Anforderungen für die beiden Nachschlageschritte (Schritt 2 und 3) für das Szenario, in dem ein SBC mit vielen Mandanten verbunden ist (Carrier-Szenario), werden weiter unten in diesem Artikel behandelt.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Detaillierte Anforderungen für Kontaktkopfzeile und Anforderungs-URI

#### <a name="contact-header"></a>Kontaktkopfzeile

Für alle eingehenden SIP-Nachrichten (OPTIONEN, EINLADUNG) an den Microsoft SIP-Proxy muss der Kontaktheader den gekoppelten SBC-FQDN im Hostnamen des URI wie folgt enthalten:

Syntax: Kontakt: <sip:phone oder sip address@FQDN des SBC;transport=tls> 

Wie rfc [3261, Abschnitt 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)ist möglicherweise ein Kontaktkopffeld in einer OPTIONSmeldung vorhanden. In Direct Routing ist die Kontaktkopfzeile erforderlich. Bei EINLADUNGsnachrichten im oben angegebenen Format können bei OPTIONSmeldungen die Benutzerinfos aus dem SIP-URI und nur der im folgenden Format gesendete FQDN entfernt werden:

Syntax: Kontakt: <sip:FQDN des SBC;transport=tls>

Dieser Name (FQDN) muss auch im Feld (Common Name) oder Subject Alternative Name(n) des präsentierten Zertifikats stehen. Microsoft unterstützt die Verwendung von Platzhalterwerten der Namen in den Feldern "Gemeinsamer Name" oder "Alternativer Betreffname" des Zertifikats.   

Die Unterstützung für Platzhalter wird in [RFC 2818, Abschnitt 3.1 beschrieben.](https://tools.ietf.org/html/rfc2818#section-3.1) Insbesondere:

*"Namen können ein Platzhalterzeichen enthalten, das als übereinstimmungend mit einer einzelnen Komponente für Domänennamen \* oder einem Komponentenfragment betrachtet wird. Beispielsweise entspricht ".a.com" foo.a.com \* nicht bar.foo.a.com. "f.com" entspricht \* foo.com aber nicht bar.com."*

Wenn im in einer SIP-Nachricht dargestellten Kontaktkopf mehr als ein Wert von SBC gesendet wird, wird nur der FQDN-Teil des ersten Werts des Kontaktkopfs verwendet.

Als Faustregel für das direkte Routing ist es wichtig, dass der FQDN zum Auffüllen von SIP-URI anstelle von IP verwendet wird. Eine eingehende EINLADUNGs- oder OPTIONSnachricht an den SIP-Proxy mit Kontaktheader, wobei hostname durch IP und nicht durch FQDN dargestellt wird, wird die Verbindung mit "403 Forbidden" verweigert.

#### <a name="request-uri"></a>Request-URI 

Für alle eingehenden Anrufe wird der Anforderungs-URI verwendet, um die Telefonnummer einem Benutzer zu entsprechen.   

Die Telefonnummer muss derzeit ein Pluszeichen (+) enthalten, wie im folgenden Beispiel gezeigt. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Überlegungen zu Kontakten Record-Route Kopfzeilen

Der SIP-Proxy muss den FQDN des nächsten Hops für neue In-Dialog-Clienttransaktionen (z. B. Bye oder Re-Invite) und beim Antworten auf DIE SIP-Optionen berechnen. Es werden entweder Record-Route Kontakt verwendet. 

Gemäß [RFC 3261, Abschnitt 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)ist der Kontaktheader in jeder Anforderung erforderlich, die zu einem neuen Dialogfeld führen kann. Die Record-Route ist nur erforderlich, wenn ein Proxy in einem Dialogfeld auf dem Pfad zukünftiger Anforderungen bleiben möchte. Wenn ein Proxy-SBC mit der Optimierung der lokalen Medien für [direct-Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)verwendet wird, muss eine Datensatzroute konfiguriert werden, da der Proxy-SBC auf der Route bleiben muss. 

Microsoft empfiehlt, nur kontaktkopfkopf zu verwenden, wenn kein Proxy-SBC verwendet wird:

- Nach [RFC 3261, Abschnitt 20.30,](https://tools.ietf.org/html/rfc3261#section-20.30)Record-Route wird verwendet, wenn ein Proxy den Pfad zukünftiger Anforderungen in einem Dialogfeld einschlagen möchte. Dies ist nicht unbedingt erforderlich, wenn kein Proxy-SBC konfiguriert ist, da der ganze Datenverkehr zwischen dem Microsoft -SIP-Proxy und dem gekoppelten SBC fließt. 

- Der Microsoft -SIP-Proxy verwendet nur den Kontaktheader (nicht Record-Route), um den nächsten Hop beim Senden von ausgehenden Pingoptionen zu ermitteln. Das Konfigurieren von nur einem Parameter (Kontakt) anstelle von zwei (Kontakt und Datensatzroute) vereinfacht die Verwaltung, wenn ein Proxy-SBC nicht verwendet wird. 

Zum Berechnen des nächsten Hops verwendet der SIP-Proxy:

- Priorität 1. Record-Route der obersten Ebene. Wenn der Name der obersten Record-Route den Namen des FQDNs enthält, wird der FQDN-Name verwendet, um die ausgehende In-Dialog-Verbindung herzustellen.

- Priorität 2. Kontaktkopfzeile Wenn Record-Route vorhanden ist, sucht der SIP-Proxy den Wert des Kontaktkopfs, um die ausgehende Verbindung herzustellen. (Dies ist die empfohlene Konfiguration.)

Wenn kontakt- und Record-Route verwendet werden, muss der SBC-Administrator die Werte identisch halten, was zu Verwaltungsaufwand führt. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Verwenden des FQDN-Namens in "Kontakt" oder "Record-Route

Die Verwendung einer E-Mail-Adresse wird in Record-Route Kontakten nicht unterstützt. Die einzige unterstützte Option ist ein FQDN, der entweder mit dem allgemeinen Namen oder dem alternativen Betreffnamen des SBC-Zertifikats übereinstimmen muss (Platzhalterwerte im Zertifikat werden unterstützt).

- Wenn eine IP-Adresse in "Datensatzroute" oder "Kontakt" dargestellt wird, schlägt die Zertifikatüberprüfung fehl, und der Aufruf schlägt fehl.

- Wenn der FQDN nicht mit dem Wert des allgemeinen oder alternativen Betreffnamens im präsentierten Zertifikat übereinstimmen, schlägt der Aufruf fehl. 

## <a name="inbound-call-sip-dialog-description"></a>Eingehender Anruf: Beschreibung des SIP-Dialogfelds

In der folgenden Tabelle sind die Unterschiede zwischen dem Anruffluss und die Ähnlichkeiten zwischen den Nichtumgehungs- und Umgehungsmodi zusammengefasst:

| Parametername | Nichtumgehungsmodus | Umgehungsmodus
| :---------------------  |:---------------------- |:----------------|
| Medienkandidaten in 183 und 200 Nachrichten, die von | Medienprozessoren | Clients | 
| Anzahl von 183 Nachrichten, die SBC empfangen kann | Eins pro Sitzung | Mehrfach | 
| Anruf kann mit provisorischen Antworten beantwortet werden (183) | Ja | Ja |
| Anruf kann ohne hilfelos beantwortet werden (183) | Ja | Ja |

###  <a name="non-media-bypass-flow"></a>Nicht medianumgehungsfluss

Ein Benutzer von Teams kann mehrere Endpunkte gleichzeitig haben. Beispiel: Teams für Windows-Client, Teams für iPhone-Client und Teams Phone (Teams Android-Client). Jeder Endpunkt kann wie folgt auf eine HTTP-Rest-Signalisierungde:

-   Anruffortschritt – vom SIP-Proxy in die SIP-Nachricht 180 konvertiert. Beim Empfangen von Nachricht 180 muss der SBC lokales Klingeln generieren.

-   Antwort auf Medien – konvertiert vom SIP-Proxy in Nachricht 183 mit Medienkandidaten im Sitzungsbeschreibungsprotokoll (Session Description Protocol, SDP). Beim Empfangen von Nachricht 183 erwartet der SBC, dass eine Verbindung mit den Medienkandidaten hergestellt wird, die in der SDP-Nachricht empfangen wurden. 

    > [!NOTE]
    > In einigen Fällen wird die Antwort "Medien" möglicherweise nicht generiert, und der Endpunkt wird möglicherweise mit der Nachricht "Anruf angenommen" beantwortet.

-   Angenommener Anruf – vom SIP-Proxy in SIP-Nachricht 200 mit SDP konvertiert. Beim Empfang von Nachricht 200 wird erwartet, dass der SBC Medien an die bereitgestellten SDP-Kandidaten sendet und von ihnen empfängt.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Mehrere Endpunkte klingeln mit antwortenden Endpunkten

1.  Bei Eingang der ersten Einladung vom SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 Trying" und benachrichtigt alle Endpunkte von Endbenutzern über den eingehenden Anruf. 

2.  Bei jeder Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und sendet die Meldungen "Anruffortschritt" an den SIP-Proxy. Da ein Benutzer von Teams mehrere Endpunkte haben kann, erhält der SIP-Proxy möglicherweise mehrere Statusmeldungen zum Anruf.

3.  Für jede von den Clients empfangene Anruffortschrittsnachricht konvertiert der SIP-Proxy die Anruffortschrittsnachricht in die SIP-Nachricht "SIP SIP/2.0 180 Trying". Das Intervall zum Senden solcher Nachrichten wird durch das Intervall der empfangenden Nachrichten vom Anrufcontroller definiert. Im folgenden Diagramm werden vom SIP-Proxy zwei 180 Nachrichten generiert. Diese Nachrichten stammen von den beiden Teams-Endpunkten des Benutzers. Die Clients haben jeweils eine eindeutige Tag-ID.  Jede Nachricht, die von einem anderen Endpunkt gesendet wird, ist eine separate Sitzung (der Parameter "tag" im Feld "An" ist anders). Ein Endpunkt generiert aber möglicherweise nicht sofort Nachricht 180 und sendet Nachricht 183, wie in der folgenden Abbildung dargestellt.

4.  Sobald ein Endpunkt eine Media Answer-Nachricht mit den IP-Adressen der Medienkandidaten des Endpunkts generiert hat, konvertiert der SIP-Proxy die empfangene Nachricht in eine Nachricht "SIP 183-Sitzungsfortschritt", bei der die SDP vom Client durch die SDP des Medienprozessors ersetzt wird. Im folgenden Diagramm hat der Endpunkt von Fork 2 den Anruf beantwortet. Wenn der Trunk nicht umgangen wird, wird die 183 -SIP-Nachricht nur einmal generiert (entweder "Ring Bot" oder "Clientendpunkt"). Die 183 wird möglicherweise auf einer vorhandenen Fork oder mit einer neuen 183-Version gestartet.

5.  Es wird eine Anrufannahmemeldung mit den endgültigen Kandidaten des Endpunkts gesendet, von dem der Anruf angenommen wurde. Die Nachricht "Anrufannahme" wird in die Nachricht "SIP Message 200" konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte klingeln und eine Antwort auf eine Provisorischen erhalten](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Mehrere Endpunkte klingeln ohne bestätigende Antwort

1.  Bei Eingang der ersten Einladung vom SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 Trying" und benachrichtigt alle Endpunkte von Endbenutzern über den eingehenden Anruf. 

2.  Bei jeder Benachrichtigung klingelt jeder Endpunkt und sendet die Nachricht "Anruffortschritt" an den SIP-Proxy. Da ein Benutzer von Teams mehrere Endpunkte haben kann, erhält der SIP-Proxy möglicherweise mehrere Statusmeldungen zum Anruf.

3.  Für jede von den Clients empfangene Anruffortschrittsnachricht konvertiert der SIP-Proxy die Anruffortschrittsnachricht in die SIP-Nachricht "SIP SIP/2.0 180 Trying".  Das Intervall zum Senden der Nachrichten wird durch das Intervall zum Empfangen der Nachrichten vom Anrufcontroller definiert. Im Bild unten werden zwei 180 Nachrichten vom SIP-Proxy generiert. Das bedeutet, dass sich der Benutzer bei drei Teamclients angemeldet hat und jeder Client den Anruffortschritt sendet. Jede Nachricht ist eine separate Sitzung (der Parameter "tag" im Feld "An" ist anders)

4.  Es wird eine Anrufannahmemeldung mit den endgültigen Kandidaten des Endpunkts gesendet, von dem der Anruf angenommen wurde. Die Nachricht "Anrufannahme" wird in die Nachricht "SIP Message 200" konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte ohne provisorische Antwort klingeln](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Medienumgehungsfluss

Im Szenario der Medienumgehung werden dieselben Meldungen (100 Trying, 180, 183) verwendet. 

Das Schema unten zeigt ein Beispiel für den Anruffluss bei der Umgehung. 

> [!NOTE]
> Die Medienkandidaten können von verschiedenen Endpunkten stammen. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, dass mehrere Endpunkte klingeln und eine Antwort auf eine Provisorische Lösung enthalten](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Option "Ersetzt"

Der SBC muss "Einladen durch Ersetzen" unterstützen.

## <a name="size-of-sdp-considerations"></a>Umfang der SDP-Überlegungen

Die Direct Routing-Schnittstelle sendet möglicherweise eine SIP-Nachricht, die mehr als 1.500 Bytes enthält.  Dies wird hauptsächlich durch die Größe von SDP verursacht. Wenn sich jedoch ein Benutzerdefinierter Trunk hinter dem SBC befindet, wird die Nachricht möglicherweise abgelehnt, wenn sie unverändert vom Microsoft -SIP-Proxy an den Trunk weitergeleitet wird. Microsoft empfiehlt, beim Senden der Nachricht an die UDP-Trunks einige Werte in SDP auf dem SBC zu streifen. So können beispielsweise die ICE-Kandidaten oder nicht verwendete Codecs entfernt werden.

## <a name="call-transfer"></a>Anrufübertragung

Direct Routing unterstützt zwei Methoden für die Anrufübertragung:

- Option 1. Sip proxy processes Refer from the client locally and acts as a Referee as section 7.1 of RFC 3892.

  Bei dieser Option beendet der SIP-Proxy die Übertragung und fügt eine neue Einladung hinzu. 


- Option 2. Der SIP-Proxy sendet den "Refer" an den SBC und fungiert als Transferor, wie in Abschnitt 6 von RFC 5589 beschrieben.

  Bei dieser Option sendet der SIP-Proxy einen "Refer" an den SBC und erwartet, dass der SBC die Übertragung vollständig verarbeitet.

Der SIP-Proxy wählt die Methode basierend auf den vom SBC gemeldeten Funktionen aus. Wenn der SBC angibt, dass er die Methode "Refer" unterstützt, verwendet der SIP-Proxy Option 2 für Anrufübertragungen.

Das folgende Beispiel zeigt, wie ein SBC die Nachricht sendet, dass die "Refer"-Methode unterstützt wird:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Wenn der SBC nicht angibt, dass "Verweisen" als unterstützte Methode gilt, verwendet Direct Routing Option 1 (der SIP-Proxy fungiert als Referee). Der SBC muss auch signalisieren, dass er die Notify-Methode unterstützt:

Beispiel für SBC, das angibt, dass die Methode "Refer" nicht unterstützt wird:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP Proxy processes Refer from the client locally and fungiert as a Referee

Wenn der SBC darauf hingewiesen hat, dass die "Refer"-Methode nicht unterstützt wird, fungiert der SIP-Proxy als Referee. 

Die refer-Anforderung, die vom Client stammt, wird auf dem SIP-Proxy beendet. (Die Refer-Anforderung vom Client wird in der folgenden Abbildung als "Anrufübertragung an Dave" angezeigt.  Weitere Informationen finden Sie im Abschnitt 7.1 von [RFC 3892.](https://www.ietf.org/rfc/rfc3892.txt) 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte klingeln und eine Antwort auf eine Provisorischen erhalten](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>DER SIP-Proxy sendet den "Verweisen auf den SBC" und fungiert als Transferor

Dies ist die bevorzugte Methode für Anrufübertragungen und ist für Geräte erforderlich, die die Medienumgehungszertifizierung suchen. Die Anrufübertragung wird im Medienumgehungsmodus nicht unterstützt, ohne dass der SBC Refer behandeln kann. 

Der Standard wird in Abschnitt 6 von RFC 5589 erläutert. Die zugehörigen RFCs sind:

- [Sip -Anrufsteuerung (Session Initiation Protocol) – Übertragung](https://tools.ietf.org/html/rfc5589)

- [Session Initiation Protocol (SIP) "Replaces" Header](https://tools.ietf.org/html/rfc3891)

- [SIP (Session Initiation Protocol) "Referred-By"-Mechanismus](https://tools.ietf.org/html/rfc3892)

Bei dieser Option wird davon ausgegangen, dass der SIP-Proxy als Transferor fungiert und eine "Refer"-Meldung an den SBC sendet. Der SBC fungiert als Transferee und behandelt den Refer, um ein neues Angebot für die Übertragung zu generieren. Es gibt zwei mögliche Fälle:

- Der Anruf wird an einen externen Teilnehmer im öffentlichen Telefonnetz übertragen. 
- Der Anruf wird über SBC von einem Benutzer in Teams an einen anderen Benutzer in demselben Mandanten übertragen. 

Wenn der Anruf über SBC von einem Benutzer in Teams an einen anderen übertragen wird, wird erwartet, dass der SBC eine neue Einladung (ein neues Dialogfeld starten) für das Übertragungsziel (den Teams-Benutzer) aus, indem die in der Meldung "Verweisen" empfangenen Informationen verwendet werden. 

Um die An/Transferor-Felder für die Transaktion der Anforderung intern zu füllen, muss der SIP-Proxy diese Informationen in den REFER-TO/REFERRED-BY-Headern übermitteln. 

Der SIP-Proxy wird das REFER-TO als SIP-URI bilden, der aus einem SIP-Proxy-FQDN im Hostnamen und einer der folgenden Optionen besteht:

- Eine E.164-Telefonnummer im Benutzernamenteil des URI für den Fall, dass es sich bei dem Übertragungsziel um eine Telefonnummer handelt, oder

- x-m- bzw. x-t-Parameter, die die MRI- bzw. Mandanten-ID des vollständigen Übertragungsziels codieren 

Der REFERRED-BY-Header ist ein SIP-URI, in dem die MRI des Transferors sowie die Mandanten-ID des Transferors und andere Parameter des Übertragungskontexts codiert sind, wie in der folgenden Tabelle dargestellt:

| Parameter | Wert | Beschreibung |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | Vollständige MRI des durch CC aufgefüllten Transferor-/Übertragungsziels |
| x-t | Mandanten-ID | x-t Tenant ID Optional Tenant ID as populated by CC |
| x-ti | Transferor-Korrelations-ID | Korrelations-ID des Aufrufs an den Transferor |
| x-tt | URI für Übertragungszielaufruf | Codierter Anrufersetzungs-URI |

In diesem Fall kann die Referheadergröße bis zu 400 Symbole aufweisen. Der SBC muss die Behandlung von "Verweisen"-Nachrichten mit einer Größe von bis zu 400 Symbolen unterstützen.

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte klingeln und eine Antwort auf eine Provisorischen erhalten](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Sitzungstimer

Der SIP-Proxy unterstützt (bietet immer) den Sitzungszeitgeber für Nicht-Umgehungsanrufe, bietet ihn aber nicht für Umgehungsanrufe an. Die Verwendung des Sitzungszeitgebers durch den SBC ist nicht obligatorisch.

##  <a name="use-of-request-uri-parameter-userphone"></a>Verwendung des Request-URI-Parameters user=phone

Der SIP-Proxy analysiert den Anforderungs-URI, und wenn der Parameter "user=phone" vorhanden ist, verarbeitet der Dienst den Anforderungs-URI als Telefonnummer und gibt die Nummer an einen Benutzer weiter. Wenn der Parameter nicht vorhanden ist, wendet der SIP-Proxy Heuristiken an, um den Anforderungs-URI-Benutzertyp (Telefonnummer oder SIP-Adresse) zu ermitteln.

Microsof empfiehlt immer die Anwendung des Parameters "user=phone", um den Anrufeinrichtungsprozess zu vereinfachen.

## <a name="history-info-header"></a>History-Info Kopfzeile

Der History-Info header wird zum Neuzielen von SIP-Anfragen verwendet und "(en) stellt einen Standardmechanismus zum Erfassen der Informationen zum Anforderungsverlauf zur Verfügung, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen." Weitere Informationen finden Sie unter [RFC 4244 – Abschnitt 1.1.](http://www.ietf.org/rfc/rfc4244.txt) Bei Microsoft Phone System wird dieser Header in Szenarien für Simulring und Anrufanrufe verwendet.  

Beim Senden wird History-Info wie folgt aktiviert:

- Der SIP-Proxy fügt einen Parameter, der die zugeordnete Telefonnummer enthält, in einzelne History-Info ein, aus denen History-Info an den PSTN Controller gesendet werden.  Wenn nur Einträge verwendet werden, die den Parameter "Telefonnummer" enthalten, erstellt der PSTN-Controller einen neuen History-Info-Header neu und über den SIP-Proxy an den SIP-Trunkanbieter weiter.

- History-Info Kopfzeile wird für fälle gleichzeitiges Anrufen und Anruf weiterleiten hinzugefügt.

- History-Info Kopfzeile wird für Anrufübertragungsfälle nicht hinzugefügt.

- Bei einem einzelnen Verlaufseintrag im rekonstruierten History-Info-Header wird der bereitgestellte History-Info in Kombination mit dem #A1 (Direct Routing FQDN, sip.pstnhub.microsoft.com) als Hostteil des URI festgelegt. wird der Parameter "user=phone" als Teil des SIP-URI hinzugefügt.  Alle anderen Parameter, die dem ursprünglichen History-Info-Header zugeordnet sind, mit Ausnahme von Telefonkontextparametern, werden im neu erstellten History-Info übergeben.  

  > [!NOTE]
  > Private Einträge (wie durch die in Abschnitt 3.3 von RFC 4244 definierten Mechanismen definiert) werden so weitergeleitet, wie dies der Grund ist, dass der SIP -Trunkanbieter ein vertrauenswürdiger Peer ist.

- Eingehende History-Info werden ignoriert.

Im Folgenden finden Sie das Format des vom SIP-Proxy gesendeten Verlaufs-Info-Headers:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Wenn der Anruf mehrmals umgeleitet wurde, sind Informationen zu jeder Umleitung in chronologischer Reihenfolge mit dem entsprechenden Grund enthalten.


Headerbeispiel:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Die History-Info ist durch einen obligatorischen TLS-Mechanismus geschützt. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC-Verbindung mit Direct Routing- und Failovermechanismus

Weitere Informationen finden Sie im Abschnitt "Failovermechanismus für die SIP-Signalisierung" in ["Plan für Direct-Routing".](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

Wenn ein Rechenzentrum mit Direct Routing ausgelastet ist, kann der Dienst eine Retry-After mit einem Intervall von einer Sekunde an den SBC senden. Wenn der SBC als Reaktion auf eine EINLADUNG eine 503-Nachricht mit einem Retry-After-Header empfängt, muss der SBC diese Verbindung beenden und das nächste verfügbare Microsoft-Rechenzentrum ausprobieren. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE-Neustart: An einen Endpunkt übertragener Medienumgehungsaufruf, der die Medienumgehung nicht unterstützt

Der SBC muss ICE-Neustarts unterstützen, wie in [RFC 5245, Abschnitt 9.1.1.1, beschrieben.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)

Der Neustart in Direct Routing wird gemäß den folgenden Absätzen der RFC implementiert:

*Damit ICE neu gestartet werden kann, muss ein Agent sowohl das Eis-Pwd- als auch das Eisspiel für den Medienstream in einem Angebot ändern.  Beachten Sie, dass es zulässig ist, in einem Angebot ein Sitzungsattribut zu verwenden, aber die gleiche Ice-Pwd- oder Ice-ufrag-Eigenschaft als Medienattribut in einem nachfolgenden Angebot zur Verfügung zu stellen.  Dies ist keine Kennwortänderung, sondern lediglich eine Änderung in der Darstellung und führt nicht zu einem ICE-Neustart.*

*Ein Agent legt die restlichen Felder in der SDP für diesen Medienstream wie bei einem ersten Angebot dieses Medienstreams fest (siehe Abschnitt 4.3).  Daher kann die Gruppe der Kandidaten einige, keine oder alle der vorherigen Kandidaten für diesen Datenstrom enthalten, und MÖGLICHERWEISE enthält sie eine völlig neue Gruppe von Kandidaten, die, wie in Abschnitt 4.1.1 beschrieben, gesammelt wurden.*

Wenn der Anruf zunächst mit der Medienumgehung eingerichtet wurde und der Anruf an einen Skype for Business-Client übertragen wird, muss direct Routing einen Medienprozessor einfügen. Dies liegt daran, dass das direkte Routing nicht mit einem Skype for Business-Client mit Medienumgehung verwendet werden kann. Das direkte Routing startet den ICE-Neustartprozess, indem die Ice-Pwd- und Ice-Ufrag-Einstellungen geändert werden und neue Medienkandidaten zur erneuten Einwahl angeboten werden. 


