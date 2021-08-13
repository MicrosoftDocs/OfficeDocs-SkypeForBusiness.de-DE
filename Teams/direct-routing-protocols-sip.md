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
description: Direct Routing-Protokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a6bafcc7aade115684bce8621877f6fa6f196435b69c4b8388af731997b5dab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321447"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing – SIP-Protokoll

In diesem Artikel wird beschrieben, wie Direct Routing das Session Initiation Protocol (SIP) implementiert. Für die richtige Route des Datenverkehrs zwischen einem Session Border Controller (SBC) und dem SIP-Proxy müssen einige SIP-Parameter bestimmte Werte haben. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst zuständig sind.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Verarbeiten der eingehenden Anforderung: Suchen des Mandanten und des Benutzers

Bevor ein eingehender oder ausgehender Anruf verarbeitet werden kann, werden OPTIONS-Nachrichten zwischen SIP-Proxy und SBC ausgetauscht. Diese OPTIONS-Meldungen ermöglichen es dem SIP-Proxy, die zulässigen Funktionen für SBC zur Verfügung zu stellen. Es ist wichtig, dass die OPTIONEN-Aushandlung erfolgreich ist (200OK-Antwort), sodass eine weitere Kommunikation zwischen SBC- und SIP-Proxy zum Herstellen von Anrufen möglich ist. Die SIP-Kopfzeilen in einer OPTIONS-Nachricht an DEN SIP-Proxy werden im folgenden Beispiel bereitgestellt:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONEN sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Über Kopfzeile | Über: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max-Forwards:68 |
| Aus Kopfzeile | Aus Kopfzeile von: <sip:sbc1.adatum.biz:5058> |
| In Kopfzeile | An: <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq-Kopfzeile | CSeq: 1 INVITE | 
| Kontaktkopfzeile | Kontakt: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Die SIP-Header enthalten im verwendeten SIP-URI keine UserInfos. Wie in [RFC 3261, Abschnitt 19.1.1, beschrieben,](https://tools.ietf.org/html/rfc3261#section-19.1.1)ist der UserInfo-Teil eines URI optional und KANN ABwesend sein, wenn der Zielhost keine Ahnung von Benutzern hat oder der Hosst selbst die zu identifizierende Ressource ist. Wenn das @-Zeichen in einem SIP-URI vorhanden ist, darf das Benutzerfeld NICHT leer sein.

Bei einem eingehenden Anruf muss der SIP-Proxy den Mandanten suchen, an den der Anruf bestimmt ist, und den bestimmten Benutzer in diesem Mandanten suchen. Der Mandantenadministrator kann Nicht-DID-Nummern, z. B. +1001, in mehreren Mandanten konfigurieren. Daher ist es wichtig, den spezifischen Mandanten zu finden, für den die Zahlen nachschlaget werden soll, da die Nicht-DID-Nummern in mehreren Organisationen Microsoft 365 oder Office 365 sind.  

In diesem Abschnitt wird beschrieben, wie der SIP-Proxy den Mandanten und den Benutzer findet und die Authentifizierung des SBC für die eingehende Verbindung durchführt.

Nachfolgend finden Sie ein Beispiel für die SIP-Einladungsnachricht bei einem eingehenden Anruf:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | EINLADEN sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Über Kopfzeile | Über: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max-Forwards:68 |
| Aus Kopfzeile | Aus Kopfzeile von: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| In Kopfzeile | An: sip:+183338006777@sbc1.adatum.biz | 
| CSeq-Kopfzeile | CSeq: 1 INVITE | 
| Kontaktkopfzeile | Kontakt: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Beim Empfang der Einladung führt der SIP-Proxy die folgenden Schritte aus:

1. Überprüfen Sie das Zertifikat. Bei der ersten Verbindung verwendet der Direct-Routingdienst den im Kontaktheader angezeigten FQDN-Namen und gleicht ihn mit dem allgemeinen Namen oder dem alternativen Namen des dargestellten Zertifikats ab. Der Name des SBC muss einer der folgenden Optionen entsprechen:

   - Option 1. Der vollständige FQDN-Name, der in der Kontaktkopfzeile angezeigt wird, muss mit dem Allgemeinen Namen/Betreff Alternativer Name des präsentierten Zertifikats übereinstimmen.  

   - Option 2. Der Domänenteil des im Kontaktheader angezeigten FQDN-Namens (z. B. adatum.biz des FQDN-Namens sbc1.adatum.biz) muss mit dem Platzhalterwert in Gemeinsamer Name/Subject Alternativer Name (z. B. *.adatum.biz) übereinstimmen.

2. Versuchen Sie, einen Mandanten mit dem vollständigen FQDN-Namen zu finden, der in der Kontaktkopfzeile angezeigt wird.  

   Überprüfen Sie, ob der FQDN-Name aus der Kontaktkopfzeile (sbc1.adatum.biz) in einer organisation Microsoft 365 oder Office 365 als DNS-Name registriert ist. Falls gefunden, wird die Suche des Benutzers in dem Mandanten durchgeführt, bei dem der SBC-FQDN als Domänenname registriert ist. Wenn sie nicht gefunden wird, gilt Schritt 3.   

3. Schritt 3 gilt nur, wenn fehler bei Schritt 2. 

   Entfernen Sie den Hostteil aus dem FQDN, der im Kontaktheader (FQDN: sbc12.adatum.biz, nach dem Entfernen des Hostteils: adatum.biz) angezeigt wird, und überprüfen Sie, ob dieser Name in einer beliebigen Microsoft 365- oder Office 365-Organisation als DNS-Name registriert ist. Wenn gefunden, wird die Benutzer-Suche in diesem Mandanten ausgeführt. Wenn sie nicht gefunden wird, schlägt der Aufruf fehl.

4. Führen Sie mit der im Anforderungs-URI dargestellten Telefonnummer die umgekehrte Nummer-Suche innerhalb des Mandanten durch, die in Schritt 2 oder 3 gefunden wurde. Passen Sie die angezeigte Telefonnummer an einen SIP-URI eines Benutzers innerhalb des Mandanten an, der im vorherigen Schritt gefunden wurde.

5. Übernehmen sie die Einstellungen für den Trunk. Suchen Sie die Parameter, die vom Mandantenadministrator für diese SBC festgelegt wurden.

   Microsoft unterstützt nicht die Verwendung eines SIP-Proxys oder Benutzer-Agent-Servers eines Drittanbieters zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC, wodurch der von dem gekoppelten SBC erstellte Anforderungs-URI geändert werden kann.

   Die Anforderungen für die beiden Nachschlageschritte (Schritte 2 und 3), die für das Szenario erforderlich sind, in dem ein SBC mit vielen Mandanten verbunden ist (Carrier-Szenario), werden weiter unten in diesem Artikel behandelt.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Detaillierte Anforderungen für Kontaktkopfzeile und Anforderungs-URI

#### <a name="contact-header"></a>Kontaktkopfzeile

Für alle eingehenden SIP-Nachrichten (OPTIONEN, EINLADEN) an den Microsoft SIP-Proxy muss der Kontaktheader den gekoppelten SBC-FQDN im URI-Hostnamen wie folgt enthalten:

Syntax: Kontakt: <sip:phone oder sip address@FQDN SBC;transport=tls> 

Wie RFC [3261, Abschnitt 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)ist möglicherweise ein Kontaktkopffeld in einer OPTIONS-Nachricht vorhanden. In Direct Routing ist die Kontaktkopfzeile erforderlich. Bei Nachrichten vom Format EINLADEN im oben angegebenen Format kann für OPTIONS-Nachrichten die UserInfo aus dem SIP-URI und nur der im folgenden Format gesendete FQDN entfernt werden:

Syntax: Kontakt: <sip:FQDN des SBC;transport=tls>

Dieser Name (FQDN) muss auch im Feld "Häufiger Name" oder "Alternativer Betreff" des präsentierten Zertifikats stehen. Microsoft unterstützt die Verwendung von Platzhalterwerten der Namen in den Feldern "Gemeinsamer Name" oder "Alternativer Betreffname" des Zertifikats.   

Die Unterstützung für Platzhalter wird in [RFC 2818, Abschnitt 3.1 beschrieben.](https://tools.ietf.org/html/rfc2818#section-3.1) Insbesondere:

*"Namen können das Platzhalterzeichen enthalten, das als Übereinstimmung mit einer einzelnen Komponente für Domänennamen \* oder einem Komponentenfragment betrachtet wird. Beispiel: ".a.com übereinstimmungen foo.a.com, aber nicht \* bar.foo.a.com. f.com entspricht foo.com, aber \* nicht bar.com."*

Wenn in der in einer SIP-Nachricht angezeigten Kontaktkopfzeile mehrere Werte von SBC gesendet werden, wird nur der FQDN-Teil des ersten Werts der Kontaktkopfzeile verwendet.

Als Faustregel für Direct-Routing ist es wichtig, dass der FQDN zum Auffüllen von SIP-URI anstelle von IP verwendet wird. Eine eingehende EINLADUNG oder OPTIONS-Nachricht an SIP-Proxy mit Kontaktkopfzeile, wobei Hostname durch IP und nicht durch FQDN dargestellt wird, wird die Verbindung mit "403 Forbidden" verweigert.

#### <a name="request-uri"></a>Request-URI 

Für alle eingehenden Anrufe wird der Anforderungs-URI verwendet, um die Telefonnummer einem Benutzer zu entsprechen.   

Derzeit muss die Telefonnummer ein Pluszeichen (+) enthalten, wie im folgenden Beispiel gezeigt. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Überlegungen zu Kontakt- Record-Route Kopfzeilen

Der SIP-Proxy muss den FQDN des nächsten Hops für neue Transaktionen im Dialogfeld (z. B. Bye oder Erneut einladen) und beim Antworten auf SIP-Optionen berechnen. Es werden entweder Record-Route Kontakt oder Kontakt verwendet. 

Gemäß [RFC 3261, Abschnitt 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)ist der Kontaktheader in jeder Anforderung erforderlich, die zu einem neuen Dialogfeld führen kann. Die Record-Route ist nur erforderlich, wenn ein Proxy den Pfad zukünftiger Anforderungen in einem Dialogfeld verwenden möchte. Wenn ein Proxy-SBC mit local media optimization für [Direct-Routing](./direct-routing-media-optimization.md)verwendet wird, muss eine Datensatzroute konfiguriert werden, da der Proxy-SBC in der Route bleiben muss. 

Microsoft empfiehlt, nur Kontaktheader zu verwenden, wenn kein Proxy-SBC verwendet wird:

- Nach [RFC 3261, Abschnitt 20.30,](https://tools.ietf.org/html/rfc3261#section-20.30)wird Record-Route verwendet, wenn ein Proxy in einem Dialogfeld auf dem Pfad zukünftiger Anforderungen bleiben möchte. Dies ist nicht von bedeutung, wenn kein Proxy-SBC konfiguriert ist, da der ganze Datenverkehr zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC fließt. 

- Der Microsoft SIP-Proxy verwendet nur die Kontaktkopfzeile (nicht Record-Route), um den nächsten Hop beim Senden ausgehender Ping-Optionen zu ermitteln. Das Konfigurieren von nur einem Parameter (Kontakt) anstelle von zwei (Kontakt und Record-Route) vereinfacht die Verwaltung, wenn ein Proxy-SBC nicht verwendet wird. 

Zur Berechnung des nächsten Hops verwendet der SIP-Proxy:

- Priorität 1. Record-Route der obersten Ebene. Wenn das Dialogfeld der obersten Record-Route den FQDN-Namen enthält, wird der FQDN-Name verwendet, um die ausgehende In-Dialog-Verbindung herzustellen.

- Priorität 2. Kontaktkopfzeile. Wenn Record-Route vorhanden ist, sucht der SIP-Proxy den Wert des Kontaktkopfs, um die ausgehende Verbindung herzustellen. (Dies ist die empfohlene Konfiguration.)

Wenn sowohl Contact als Record-Route verwendet werden, muss der SBC-Administrator die Werte identisch halten, was zu Verwaltungsaufwand führt. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Verwenden des FQDN-Namens in Kontakt oder Record-Route

Die Verwendung einer IP-Adresse wird weder in Ihrem Record-Route noch in Kontakt unterstützt. Die einzige unterstützte Option ist ein FQDN, der entweder mit dem allgemeinen Namen oder dem alternativen Namen für Betreff des SBC-Zertifikats übereinstimmen muss (Platzhalterwerte im Zertifikat werden unterstützt).

- Wenn unter Record-route oder Contact eine IP-Adresse präsentiert wird, schlägt die Zertifikatüberprüfung fehl, und der Aufruf schlägt fehl.

- Wenn der FQDN nicht mit dem Wert für "Allgemein" oder "Alternativer Betreffname" im angezeigten Zertifikat übereinstimmen, schlägt der Aufruf fehl. 

## <a name="inbound-call-sip-dialog-description"></a>Eingehender Anruf: Beschreibung des SIP-Dialogfelds

In der folgenden Tabelle werden die Unterschiede zwischen dem Anruffluss und die Gemeinsamkeiten zwischen den Nichtumgehungs- und Umgehungsmodi zusammengefasst:

| Parametername | Nichtumgehungsmodus | Umgehungsmodus
| :---------------------  |:---------------------- |:----------------|
| Medienkandidaten in 183 und 200 Nachrichten, die von | Medienprozessoren | Clients | 
| Anzahl von 183 Nachrichten, die SBC empfangen kann | Eins pro Sitzung | Mehrere | 
| Anruf kann provisorisch beantwortet werden (183) | Ja | Ja |
| Anruf kann ohne provisorische Antwort sein (183) | Ja | Ja |

###  <a name="non-media-bypass-flow"></a>Nicht-Medienumgehungsfluss

Ein Teams Benutzer kann mehrere Endpunkte gleichzeitig haben. Beispiel: Teams für Windows-Client, Teams für iPhone-Client und Teams Telefon (Teams Android-Client). Jeder Endpunkt kann eine HTTP-Rest-Signalisierung wie folgt signalisieren:

-   Anruffortschritt – Vom SIP-Proxy in SIP-Nachricht 180 konvertiert. Beim Empfangen von Nachrichten 180 muss der SBC lokales Klingeln generieren.

-   Antwort auf Medien : Vom SIP-Proxy in Nachricht 183 mit Medienkandidaten im Session Description Protocol (SDP) konvertiert. Beim Empfangen der Nachricht 183 erwartet der SBC, dass eine Verbindung mit den in der SDP-Nachricht empfangenen Medienkandidaten hergestellt wird. 

    > [!NOTE]
    > In einigen Fällen wird die Antwort auf Medien möglicherweise nicht generiert, und der Endpunkt wird mit der Nachricht "Anruf angenommen" beantwortet.

-   Akzeptierter Anruf – Vom SIP-Proxy in SIP-Nachricht 200 mit SDP umgewandelt. Beim Empfangen von Nachrichten 200 wird erwartet, dass der SBC Medien an die bereitgestellten SDP-Kandidaten sendet und von ihnen empfängt.

    > [!NOTE]
    > Direct Routing unterstützt die Einladung zu verzögerten Angeboten nicht (Einladung ohne SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Mehrere Endpunkte klingeln mit Antwort auf provisorische Antworten

1.  Beim Empfang der ersten Einladung von der SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 Trying" und benachrichtigt alle Endpunkte der Endbenutzer über den eingehenden Anruf. 

2.  Bei Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und sendet Meldungen vom Status eines Anrufs an den SIP-Proxy. Da ein Teams mehrere Endpunkte haben kann, kann der SIP-Proxy mehrere Statusmeldungen empfangen.

3.  Für jede von den Clients empfangene Anruffortschrittsnachricht konvertiert der SIP-Proxy die Meldung "Anruffortschritt" in die SIP-Nachricht "SIP SIP/2.0 180 Trying". Das Intervall für das Senden solcher Nachrichten wird durch das Intervall der empfangenden Nachrichten vom Anrufcontroller definiert. Im folgenden Diagramm werden vom SIP-Proxy zwei 180 Nachrichten generiert. Diese Nachrichten werden von den beiden Teams Endpunkten des Benutzers gesendet. Die Clients haben jeweils eine eindeutige Tag-ID.  Jede Nachricht, die von einem anderen Endpunkt gesendet wird, wird zu einer separaten Sitzung (der Parameter "tag" im Feld "An" ist anders). Ein Endpunkt generiert aber möglicherweise nicht sofort Nachricht 180 und sendet Nachricht 183, wie in der folgenden Abbildung dargestellt.

4.  Sobald ein Endpunkt eine Media Answer-Nachricht mit den IP-Adressen der Medienkandidaten des Endpunkts generiert hat, konvertiert der SIP-Proxy die empfangene Nachricht in die Nachricht "SIP 183-Sitzungsfortschritt", bei der die SDP vom Client durch die SDP vom Medienprozessor ersetzt wird. Im folgenden Diagramm hat der Endpunkt von Fork 2 den Anruf beantwortet. Wenn der Trunk nicht umgangen wird, wird die 183 SIP-Nachricht nur einmal generiert (entweder "Ring Bot" oder "Clientendpunkt"). Die 183 wird möglicherweise auf einer vorhandenen Verteilergkung bzw. in einer neuen Version gestartet.

5.  Eine Nachricht zur Anrufannahme wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Nachricht zur Anrufannahme wird in SIP Message 200 konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte mit Antwort auf Provisorisch klingeln](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Mehrere Endpunkte klingeln ohne Antwort auf provisorische Antworten

1.  Beim Empfang der ersten Einladung von der SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 Trying" und benachrichtigt alle Endpunkte der Endbenutzer über den eingehenden Anruf. 

2.  Bei Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und sendet die Nachricht "Anruffortschritt" an den SIP-Proxy. Da ein Teams mehrere Endpunkte haben kann, kann der SIP-Proxy mehrere Statusmeldungen empfangen.

3.  Für jede von den Clients empfangene Anruffortschrittsnachricht konvertiert der SIP-Proxy die Meldung "Anruffortschritt" in die SIP-Nachricht "SIP SIP/2.0 180 Trying".  Das Intervall für das Senden der Nachrichten wird durch das Intervall für den Empfang der Nachrichten von der Anrufcontroller definiert. Im Bild unten werden zwei 180 Nachrichten vom SIP-Proxy generiert. Das bedeutet, dass sich der Benutzer bei drei Teams-Clients angemeldet hat und jeder Client den Anruffortschritt sendet. Bei jeder Nachricht handelt es sich um eine separate Sitzung (der Parameter "tag" im Feld "An" ist anders).

4.  Eine Nachricht zur Anrufannahme wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Nachricht zur Anrufannahme wird in SIP Message 200 konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte ohne Antwort provisorisch klingeln](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Medienumgehungsfluss

Im Medienumgehungsszenario werden die gleichen Meldungen (100 Trying, 180, 183) verwendet. 

Das Schema unten zeigt ein Beispiel für den Ablauf der Umgehungsaufrufe. 

> [!NOTE]
> Die Medienkandidaten können von verschiedenen Endpunkten stammen. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte mit Antwort auf Provisorisch klingeln](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Option "Ersetzt"

Der SBC muss "Invite with Replaces" unterstützen.

## <a name="size-of-sdp-considerations"></a>Umfang der SDP-Überlegungen

Die Direct Routing-Schnittstelle sendet möglicherweise eine SIP-Nachricht, die mehr als 1.500 Bytes enthält.  Dies wird in erster Linie durch die Größe von SDP verursacht. Wenn sich hinter dem SBC jedoch ein UDP-Trunk befindet, kann die Nachricht abgelehnt werden, wenn sie unverändert vom Microsoft SIP-Proxy an den Trunk weitergeleitet wird. Microsoft empfiehlt, einige Werte in SDP auf dem SBC zu beschneiden, wenn die Nachricht an die UDP-Trunks gesendet wird. So können beispielsweise die ICE-Kandidaten oder nicht verwendete Codecs entfernt werden.

## <a name="call-transfer"></a>Anrufübertragung

Direct Routing unterstützt zwei Methoden für die Anrufübertragung:

- Option 1. SIP-Proxyprozesse Verweisen sie lokal vom Client und fungiert wie in Abschnitt 7.1 von RFC 3892 beschrieben als "Referee".

  Bei dieser Option beendet der SIP-Proxy die Übertragung und fügt eine neue Einladung hinzu. 


- Option 2. SIP-Proxy sendet den "Refer to the SBC" (Verweisen auf den SBC) und fungiert als Transferor (wie in Abschnitt 6 von RFC 5589 beschrieben).

  Bei dieser Option sendet der SIP-Proxy einen "Refer" an die SBC und erwartet, dass der SBC die Übertragung vollständig verarbeitet.

Der SIP-Proxy wählt die Methode basierend auf den von SBC gemeldeten Funktionen aus. Wenn der SBC angibt, dass die Methode "Refer" unterstützt wird, verwendet der SIP-Proxy Option 2 für Anrufübertragungen.

Es folgt ein Beispiel für ein SBC-Senden der Nachricht, dass die Refer-Methode unterstützt wird:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Wenn der SBC nicht angibt, dass "Verweisen" als unterstützte Methode gilt, verwendet Direct-Routing Option 1 (SIP-Proxy fungiert als "Referee"). Der SBC muss auch signalisieren, dass er die Notify-Methode unterstützt:

Beispiel für SBC, das angibt, dass die Refer-Methode nicht unterstützt wird:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP-Proxyprozesse Verweisen vom Client lokal und fungiert als "Referee"

Wenn der SBC darauf hingewiesen hat, dass die Refer-Methode nicht unterstützt wird, fungiert der SIP-Proxy als Referee. 

Die Vom Client gesendete Refer-Anforderung wird auf dem SIP-Proxy beendet. (Die Refer-Anforderung vom Client wird in der folgenden Abbildung als "Call transfer to Dave" (Anrufübertragung an Dave) angezeigt.  Weitere Informationen finden Sie im Abschnitt 7.1 von [RFC 3892.](https://www.ietf.org/rfc/rfc3892.txt) 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte mit Antwort auf Provisorisch klingeln](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP-Proxy sendet "Verweisen auf SBC" und fungiert als Transferor

Dies ist die bevorzugte Methode für Die Übertragung von Aufrufen, und sie ist für Geräte erforderlich, die eine Medienumgehungszertifizierung suchen. Die Anrufübertragung ohne die Verarbeitung von Refer durch den SBC wird im Medienumgehungsmodus nicht unterstützt. 

Der Standard wird in Abschnitt 6 von RFC 5589 erläutert. Die zugehörigen RFCs sind:

- [Sip-Anrufsteuerung (Session Initiation Protocol) – Übertragung](https://tools.ietf.org/html/rfc5589)

- [Session Initiation Protocol (SIP) "Replaces"-Header](https://tools.ietf.org/html/rfc3891)

- [SIP-Mechanismus (Session Initiation Protocol) (Referred-By)](https://tools.ietf.org/html/rfc3892)

Bei dieser Option wird davon ausgegangen, dass der SIP-Proxy als Transferor fungiert und eine Refer-Nachricht an die SBC sendet. Der SBC fungiert als Transferee und behandelt "Refer" zum Generieren eines neuen Transferangebots. Es gibt zwei mögliche Fälle:

- Der Anruf wird an einen externen PSTN-Teilnehmer übertragen. 
- Der Anruf wird über SBC Teams einen benutzer Teams anderen Benutzer in demselben Mandanten übertragen. 

Wenn der Anruf über SBC von einem Teams-Benutzer an einen anderen übertragen wird, wird erwartet, dass der SBC eine neue Einladung (Ein neues Dialogfeld starten) für das Übertragungsziel (den Teams-Benutzer) aus, indem die in der Nachricht "Refer" empfangenen Informationen verwendet werden. 

Um die To/Transferor-Felder für die interne Transaktion der Anforderung zu füllen, muss der SIP-Proxy diese Informationen in den HEADERN REFER-TO/REFERRED-BY übermitteln. 

Der SIP-Proxy wird das REFER-TO als SIP-URI bilden, der aus einem SIP-Proxy-FQDN im Hostnamen und einer der folgenden Optionen besteht:

- Eine E.164-Telefonnummer im Benutzernamenteil des URI für den Fall, dass es sich bei dem Übertragungsziel um eine Telefonnummer handelt, oder

- x-m- bzw. x-t-Parameter, die die MRI bzw. Mandanten-ID des vollständigen Übertragungsziels codieren 

Der Header "REFERRED-BY" ist ein SIP-URI mit in ihm codierter Transferor-MRI sowie der Mandanten-ID des Transferor und anderen Parametern für den Übertragungskontext, wie in der folgenden Tabelle dargestellt:

| Parameter | Wert | Beschreibung |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | Vollständige MRI des von CC aufgefüllten Transferor-/Übertragungsziels |
| x-t | Mandanten-ID | x-t Tenant ID Optional Tenant ID as populated by CC |
| x-ti | Transferor-Korrelations-ID | Korrelations-ID des Aufrufs an den Transferor |
| x-tt | Übertragungszielaufruf-URI | Codierter Anrufersetzungs-URI |

In diesem Fall kann die Refer-Kopfzeile bis zu 400 Symbole aufweisen. Der SBC muss die Behandlung von Verweisen von Nachrichten mit einer Größe von bis zu 400 Symbolen unterstützen.

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, wie mehrere Endpunkte mit Antwort auf Provisorisch klingeln](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Sitzungstimer

Der SIP-Proxy unterstützt (bietet immer) den Sitzungstimer bei Nicht-Umgehungsanrufen, bietet ihn aber nicht für Umgehungsanrufe an. Die Verwendung des Sitzungstimers durch den SBC ist nicht obligatorisch.

##  <a name="use-of-request-uri-parameter-userphone"></a>Verwendung des Request-URI-Parameters user=phone

Der SIP-Proxy analysiert den Anforderungs-URI, und wenn der Parameter user=phone vorhanden ist, verarbeitet der Dienst den Anforderungs-URI als Telefonnummer und gibt die Nummer an einen Benutzer weiter. Wenn kein Parameter vorhanden ist, wendet der SIP-Proxy Heuristiken zur Ermittlung des Anforderungs-URI-Benutzertyps (Telefonnummer oder SIP-Adresse) an.

Microsoft empfiehlt, zur Vereinfachung des Anrufeinrichtungsprozesses immer den Parameter user=phone zu verwenden.

## <a name="history-info-header"></a>History-Info Kopfzeile

Der History-Info-Header wird zum Neutargetieren von SIP-Anforderungen verwendet und "stellt(en) einen Standardmechanismus zum Erfassen der Informationen zum Anforderungsverlauf zur Verfügung, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen". Weitere Informationen finden Sie unter [RFC 4244 – Abschnitt 1.1.](http://www.ietf.org/rfc/rfc4244.txt) Für Microsoft-Telefon System wird dieser Header in Szenarien für Die Anruf- und Simulring-Weiterleitung verwendet.  

Beim Senden wird History-Info wie folgt aktiviert:

- Der SIP-Proxy fügt einen Parameter, der die zugeordnete Telefonnummer enthält, in einzelne History-Info ein, aus denen der History-Info den PSTN-Controller gesendet wird.  Der PSTN-Controller erstellt einen neuen History-Info-Header neu und über den SIP-Proxy an den SIP-Trunkanbieter, indem er nur Einträge mit dem Telefonnummerparameter verwendet.

- History-Info Kopfzeile wird für gleichzeitige Anrufe und Anruf weiterleitungsfälle hinzugefügt.

- History-Info Kopfzeile wird für Anrufübertragungsfälle nicht hinzugefügt.

- Bei einem individuellen Verlaufseintrag im nachkonstruierten History-Info-Header wird der Telefonnummerparameter bereitgestellt, der in Kombination mit dem Direct Routing-FQDN (sip.pstnhub.microsoft.com) als Hostteil des URI festgelegt ist. Der Parameter "user=phone" wird als Teil des SIP-URI hinzugefügt.  Alle anderen dem ursprünglichen History-Info-Header zugeordneten Parameter, mit Ausnahme von Kontextparametern für Telefon, werden in der neu erstellten History-Info übergeben.  

  > [!NOTE]
  > Einträge, die privat sind (wie durch die in Abschnitt 3.3 von RFC 4244 definierten Mechanismen definiert), werden wie folgt weitergeleitet: Der SIP-Trunkanbieter ist ein vertrauenswürdiger Peer.

- Eingehende History-Info werden ignoriert.

Es folgt das Format des vom SIP-Proxy gesendeten Verlaufs-Info-Headers:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Wenn der Anruf mehrmals umgeleitet wurde, werden Informationen zu jeder Umleitung in chronologischer Reihenfolge aus dem entsprechenden Grund eingeschlossen.


Headerbeispiel:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Die History-Info ist durch einen obligatorischen TLS-Mechanismus geschützt. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC-Verbindung mit Direct-Routing- und Failovermechanismus

Weitere Informationen finden Sie im Abschnitt Failovermechanismus für SIP-Signalisierung unter [Planen des Direct-Routings.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

Wenn ein Direct Routing-Rechenzentrum ausgelastet ist, kann der Dienst eine Retry-After mit einem Intervall von einer Sekunde an den SBC senden. Wenn der SBC als Antwort auf eine EINLADUNG eine 503-Nachricht mit einem Retry-After-Header empfängt, muss der SBC diese Verbindung beenden und das nächste verfügbare Microsoft-Rechenzentrum ausprobieren.

## <a name="handling-retries-603-response"></a>Behandeln von Wiederholungen (603-Antwort)
Wenn ein Endbenutzer nach dem Abnehmen des eingehenden Anrufs mehrere verpasste Anrufe für einen Anruf bemerkt, bedeutet dies, dass der Wiederholungsmechanismus des SBC- oder PSTN-Trunkanbieters falsch konfiguriert ist. Der SBC muss neu konfiguriert werden, um die Wiederholungsversuche für die 603-Antwort zu beenden.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE-Neustart: Übertragung eines Medienumgehungsanrufs an einen Endpunkt, der die Medienumgehung nicht unterstützt

Der SBC muss ICE-Neustarts unterstützen, wie in [RFC 5245, Abschnitt 9.1.1.1 beschrieben.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)

Der Neustart in Direct Routing wird gemäß den folgenden Rfc-Absätzen implementiert:

*Um ICE neu zu starten, MUSS ein Agent sowohl das Eis-Pwd als auch das Eis-Ufrag für den Medienstream in einem Angebot ändern.  Beachten Sie, dass es zulässig ist, in einem Angebot ein Sitzungsattribut zu verwenden, aber das gleiche Eis pwd oder ice-ufrag als Medienebenenattribut in einem nachfolgenden Angebot zu verwenden.  Dies ist keine Kennwortänderung, sondern lediglich eine Änderung an der Darstellung und führt nicht zu einem ICE-Neustart.*

*Ein Agent legt die restlichen Felder in der SDP für diesen Medienstream wie bei einem ersten Angebot dieses Medienstreams fest (siehe Abschnitt 4.3).  Folglich enthält die Gruppe der Kandidaten MÖGLICHERWEISE einige, keine oder alle vorherigen Kandidaten für diesen Datenstrom und KANN eine völlig neue Gruppe von Kandidaten enthalten, wie in Abschnitt 4.1.1 beschrieben.*

Wenn der Aufruf zunächst mit der Medienumgehung eingerichtet wurde und der Aufruf an einen Skype for Business-Client übertragen wird, muss Direct-Routing einen Medienprozessor einfügen. Dies liegt daran, dass direct-Routing nicht mit einem Skype for Business-Client mit Medienumgehung verwendet werden kann. Das direkte Routing startet den ICE-Neustartvorgang, indem das Eis-Pwd und das Ice-ufrag geändert und neue Medienkandidaten in einer erneuten Einwahl angeboten werden.
