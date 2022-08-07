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
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Direct Routing-Protokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a4ba1715ccf7b1ea2f0dbf12b58fd5aa6556b24
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271260"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing – SIP-Protokoll

In diesem Artikel wird beschrieben, wie Direct Routing das Session Initiation Protocol (SIP) implementiert. Um den Datenverkehr zwischen einem Session Border Controller (SBC) und dem SIP-Proxy ordnungsgemäß weiterzuleiten, müssen einige SIP-Parameter bestimmte Werte aufweisen. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst verantwortlich sind.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Verarbeiten der eingehenden Anforderung: Suchen des Mandanten und Benutzers

Bevor ein eingehender oder ausgehender Anruf verarbeitet werden kann, werden OPTIONS-Nachrichten zwischen dem SIP-Proxy und dem SBC ausgetauscht. Diese OPTIONS-Nachrichten ermöglichen dem SIP-Proxy die Bereitstellung der zulässigen Funktionen für SBC. Es ist wichtig, dass die OPTIONS-Aushandlung erfolgreich ist (200OK-Antwort), die eine weitere Kommunikation zwischen SBC und SIP-Proxy zum Einrichten von Anrufen ermöglicht. Die SIP-Header in einer OPTIONS-Nachricht an den SIP-Proxy werden nachfolgend als Beispiel bereitgestellt:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Anforderungs-URI | OPTIONEN sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Über Kopfzeile | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max-Forwards:68 |
| Von Kopfzeile | Von Kopfzeile aus: <sip:sbc1.adatum.biz:5058> |
| An Kopfzeile | An: <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq-Header | CSeq: 1 INVITE | 
| Kontaktkopf | Kontakt: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Die SIP-Header enthalten keine Benutzerinfos im verwendeten SIP-URI. Gemäß [RFC 3261, Abschnitt 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), ist der UserInfo-Teil eines URI optional und KANN nicht vorhanden sein, wenn der Zielhost keine Vorstellung von Benutzern hat oder wenn der Hosst selbst die zu identifizierende Ressource ist. Wenn das @-Zeichen in einem SIP-URI vorhanden ist, DARF das Benutzerfeld NICHT leer sein.
> Bitte beachten Sie, dass der SIPS-URI nicht mit Direct Routing verwendet werden sollte, da er nicht unterstützt wird.
> Überprüfen Sie ihre Session Border Controller-Konfiguration, und stellen Sie sicher, dass Sie keine "Replaces"-Header in SIP-Anforderungen verwenden. Direct Routing lehnt SIP-Anforderungen ab, für die Replaces-Header definiert sind.

Bei einem eingehenden Anruf muss der SIP-Proxy den Mandanten finden, für den der Anruf bestimmt ist, und den bestimmten Benutzer in diesem Mandanten finden. Der Mandantenadministrator kann Nicht-DID-Nummern, z. B. +1001, in mehreren Mandanten konfigurieren. Daher ist es wichtig, den bestimmten Mandanten zu finden, auf dem die Nummernsuche ausgeführt werden soll, da die Nicht-DID-Nummern in mehreren Microsoft 365- oder Office 365-Organisationen möglicherweise identisch sind.  

In diesem Abschnitt wird beschrieben, wie der SIP-Proxy den Mandanten und den Benutzer findet und die Authentifizierung des SBC für die eingehende Verbindung durchführt.

Es folgt ein Beispiel für die SIP-Einladungsnachricht bei einem eingehenden Anruf:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Anforderungs-URI | EINLADEN sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Über Kopfzeile | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max-Forwards:68 |
| Von Kopfzeile | Von Header von: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| An Kopfzeile | An: sip:+183338006777@sbc1.adatum.biz | 
| CSeq-Header | CSeq: 1 INVITE | 
| Kontaktkopf | Kontakt: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Beim Empfangen der Einladung führt der SIP-Proxy die folgenden Schritte aus:

1. Überprüfen Sie das Zertifikat. Bei der ersten Verbindung verwendet der Direct Routing-Dienst den FQDN-Namen, der im Kontaktkopf angezeigt wird, und stimmt ihn mit dem allgemeinen Namen oder dem Alternativen Antragstellernamen des präsentierten Zertifikats überein. Der SBC-Name muss mit einer der folgenden Optionen übereinstimmen:

   - Option 1. Der vollständige FQDN-Name, der im Kontaktkopf angezeigt wird, muss mit dem Allgemeinen Namen/Alternativen Antragstellernamen des präsentierten Zertifikats übereinstimmen.  

   - Option 2. Der Domänenteil des FQDN-Namens, der im Kontaktheader angezeigt wird (z. B. adatum.biz des FQDN-Namens sbc1.adatum.biz) muss mit dem Platzhalterwert in Common Name/Subject Alternative Name (z. B. *.adatum.biz) übereinstimmen.

2. Versuchen Sie, einen Mandanten mit dem vollständigen FQDN-Namen zu finden, der im Kontaktheader angezeigt wird.  

   Überprüfen Sie, ob der FQDN-Name aus dem Kontaktheader (sbc1.adatum.biz) als DNS-Name in einer beliebigen Microsoft 365- oder Office 365-Organisation registriert ist. Wenn gefunden, wird die Suche des Benutzers in dem Mandanten ausgeführt, in dem der SBC-FQDN als Domänenname registriert ist. Wenn dieser Schritt nicht gefunden wird, wird Schritt 3 angewendet.   

3. Schritt 3 gilt nur, wenn Schritt 2 fehlgeschlagen ist. 

   Entfernen Sie den Hostteil aus dem FQDN, der im Kontaktheader angezeigt wird (FQDN: sbc12.adatum.biz, nachdem Sie den Hostteil entfernt haben: adatum.biz), und überprüfen Sie, ob dieser Name als DNS-Name in einer Beliebigen Microsoft 365- oder Office 365 Organisation registriert ist. Wenn gefunden, wird die Benutzersuche in diesem Mandanten ausgeführt. Wenn der Aufruf nicht gefunden wird, schlägt er fehl.

4. Führen Sie mithilfe der im Anforderungs-URI angegebenen Telefonnummer die umgekehrte Nummernsuche innerhalb des Mandanten aus, der in Schritt 2 oder 3 gefunden wurde. Passen Sie die angezeigte Telefonnummer einem SIP-URI eines Benutzers innerhalb des Mandanten an, der im vorherigen Schritt gefunden wurde.

5. Anwenden von Trunkeinstellungen Suchen Sie die vom Mandantenadministrator für diesen SBC festgelegten Parameter.

   Microsoft unterstützt keinen SIP-Proxy oder Benutzer-Agent-Server eines Drittanbieters zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC, wodurch möglicherweise der vom gekoppelten SBC erstellte Anforderungs-URI geändert wird.

   Die Anforderungen für die beiden Nachschlagevorgänge (Schritte 2 und 3), die für das Szenario erforderlich sind, in dem ein SBC mit vielen Mandanten (Netzbetreiberszenario) verbunden ist, werden weiter unten in diesem Artikel behandelt.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Detaillierte Anforderungen für den Kontaktheader und den Anforderungs-URI

#### <a name="contact-header"></a>Kontaktkopfzeile

Für alle eingehenden SIP-Nachrichten (OPTIONEN, INVITE) an den Microsoft SIP-Proxy muss der Kontaktheader den gekoppelten SBC-FQDN im URI-Hostnamen wie folgt aufweisen:

Syntax: Contact: <sip:phone or sip address@FQDN of the SBC;transport=tls> 

Gemäß [RFC 3261, Abschnitt 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), kann ein Kontaktkopffeld in einer OPTIONS-Nachricht vorhanden sein. Im Direct Routing ist der Kontaktheader erforderlich. Bei INVITE-Nachrichten im obigen Format kann bei OPTIONS-Nachrichten die UserInfo aus dem SIP-URI entfernt und nur FQDN wie folgt gesendet werden:

Syntax: Contact: <sip:FQDN of the SBC;transport=tls>

Dieser Name (FQDN) muss auch im Feld (Common Name) oder Subject Alternative name(s) des dargestellten Zertifikats enthalten sein. Microsoft unterstützt die Verwendung von Platzhalterwerten der Namen in den Feldern "Allgemeiner Name" oder "Alternativer Antragstellername" des Zertifikats.   

Die Unterstützung für Platzhalter wird in [RFC 2818, Abschnitt 3.1](https://tools.ietf.org/html/rfc2818#section-3.1), beschrieben. Speziell:

*"Namen können das Platzhalterzeichen \* enthalten, das mit einer einzelnen Domänennamenkomponente oder einem Komponentenfragment übereinstimmt. .a.com entspricht z. B \*. foo.a.com, aber nicht bar.foo.a.com. f.com\* entspricht foo.com, aber nicht bar.com."*

Wenn mehr als ein Wert im In einer SIP-Nachricht angezeigten Kontaktheader vom SBC gesendet wird, wird nur der FQDN-Teil des ersten Werts des Kontaktheaders verwendet.

Als Faustregel für Direct Routing ist es wichtig, dass FQDN zum Auffüllen von SIP-URI anstelle von IP verwendet wird. Eine eingehende INVITE- oder OPTIONS-Nachricht an den SIP-Proxy mit Kontaktheader, bei der der Hostname durch IP und nicht durch FQDN dargestellt wird, wird die Verbindung mit 403 Forbidden verweigert.

#### <a name="request-uri"></a>Anforderungs-URI 

Für alle eingehenden Anrufe wird der Anforderungs-URI verwendet, um die Telefonnummer einem Benutzer anzupassen.   

Derzeit muss die Telefonnummer ein Pluszeichen (+) enthalten, wie im folgenden Beispiel gezeigt. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>Von Kopfzeile

Für alle eingehenden Anrufe wird die "Von-Kopfzeile" verwendet, um die Telefonnummer des Anrufers mit der Liste der blockierten Telefonnummern des Anrufers abzugleichen.

Die Telefonnummer muss ein + enthalten, wie im folgenden Beispiel gezeigt.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>Überlegungen zu Kontakt- und Record-Route Kopfzeilen

Der SIP-Proxy muss den nächsten Hop-FQDN für neue dialogbasierte Clienttransaktionen (z. B. Bye oder Re-Invite) und beim Antworten auf SIP-Optionen berechnen. Es werden entweder "Kontakt" oder "Record-Route" verwendet. 

Gemäß [RFC 3261, Abschnitt 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), ist der Kontaktheader in jeder Anforderung erforderlich, die zu einem neuen Dialogfeld führen kann. Die Record-Route ist nur erforderlich, wenn ein Proxy den Pfad zukünftiger Anforderungen in einem Dialogfeld beibehalten möchte. Wenn ein Proxy-SBC mit der [lokalen Medienoptimierung für Direct Routing](./direct-routing-media-optimization.md) verwendet wird, muss eine Datensatzroute konfiguriert werden, da der Proxy-SBC in der Route bleiben muss. 

Microsoft empfiehlt die Verwendung des Kontaktheaders nur, wenn kein Proxy-SBC verwendet wird:

- Gemäß [RFC 3261, Abschnitt 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), wird Record-Route verwendet, wenn ein Proxy den Pfad zukünftiger Anforderungen in einem Dialogfeld beibehalten möchte. Dies ist nicht erforderlich, wenn kein Proxy-SBC konfiguriert ist, da der gesamte Datenverkehr zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC erfolgt. 

- Der Microsoft SIP-Proxy verwendet nur den Kontaktheader (nicht die Datensatzroute), um den nächsten Hop beim Senden ausgehender Pingoptionen zu ermitteln. Das Konfigurieren nur eines Parameters (Contact) anstelle von zwei (Contact und Record-Route) vereinfacht die Verwaltung, wenn kein Proxy-SBC verwendet wird. 

Zum Berechnen des nächsten Hops verwendet der SIP-Proxy Folgendes:

- Priorität 1. Record-Route der obersten Ebene. Wenn die Record-Route der obersten Ebene den FQDN-Namen enthält, wird der FQDN-Name verwendet, um die ausgehende In-Dialog-Verbindung herzustellen.

- Priorität 2. Kontaktkopfzeile. Wenn Record-Route nicht vorhanden ist, sucht der SIP-Proxy den Wert des Kontaktheaders nach, um die ausgehende Verbindung herzustellen. (Dies ist die empfohlene Konfiguration.)

Wenn sowohl Kontakt- als auch Record-Route verwendet werden, muss der SBC-Administrator seine Werte identisch halten, was zu verwaltungstechnischem Aufwand führt. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Verwendung des FQDN-Namens in Kontakt oder Record-Route

Die Verwendung einer IP-Adresse wird weder in Record-Route noch in Kontakten unterstützt. Die einzige unterstützte Option ist ein FQDN, der entweder dem allgemeinen Namen oder dem alternativen Antragstellernamen des SBC-Zertifikats entsprechen muss (Platzhalterwerte im Zertifikat werden unterstützt).

- Wenn eine IP-Adresse in "Datensatzroute" oder "Kontakt" angezeigt wird, schlägt die Zertifikatüberprüfung fehl, und der Anruf schlägt fehl.

- Wenn der FQDN nicht mit dem Wert des allgemeinen oder alternativen Antragstellernamens im dargestellten Zertifikat übereinstimmt, schlägt der Aufruf fehl. 

## <a name="inbound-call-sip-dialog-description"></a>Eingehender Anruf: SIP-Dialogfeldbeschreibung

In der folgenden Tabelle unten sind die Unterschiede und Ähnlichkeiten zwischen Nichtumgehungs- und Umgehungsmodi zusammengefasst:

| Parametername | Modus ohne Umgehung | Umgehungsmodus
| :---------------------  |:---------------------- |:----------------|
| Medienkandidaten in 183 und 200 Nachrichten, die von | Medienprozessoren | Clients | 
| Anzahl von 183 Nachrichten, die SBC empfangen kann | Eins pro Sitzung | Mehrere | 
| Anruf kann vorläufig angenommen werden (183) | Ja | Ja |
| Anruf kann ohne vorläufige Antwort erfolgen (183) | Ja | Ja |

###  <a name="non-media-bypass-flow"></a>Fluss der Nicht-Medienumgehung

Ein Teams-Benutzer kann mehrere Endpunkte gleichzeitig haben. Beispielsweise Teams für Windows-Client, Teams für iPhone-Client und Teams Phone (Teams Android-Client). Jeder Endpunkt signalisiert möglicherweise eine HTTP-Restung wie folgt:

-   Anrufstatus – wird vom SIP-Proxy in die SIP-Nachricht 180 konvertiert. Beim Empfangen von Nachricht 180 muss der SBC lokales Klingeln generieren.

-   Medienantwort – vom SIP-Proxy in Nachricht 183 mit Medienkandidaten im Session Description Protocol (SDP) konvertiert. Beim Empfang der Nachricht 183 erwartet der SBC, eine Verbindung mit den Medienkandidaten herzustellen, die in der SDP-Nachricht empfangen wurden. 

    > [!NOTE]
    > In einigen Fällen wird die Medienantwort möglicherweise nicht generiert, und der Endpunkt kann mit der Nachricht "Anruf angenommen" beantwortet werden.

-   Anruf angenommen – vom SIP-Proxy in SIP-Nachricht 200 mit SDP konvertiert. Beim Empfang von Nachricht 200 wird erwartet, dass der SBC Medien an und von den bereitgestellten SDP-Kandidaten sendet und empfängt.

    > [!NOTE]
    > Direct Routing unterstützt keine verzögerte Angebotsseinladung (Einladung ohne SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Mehrere Endpunkte klingeln mit vorläufiger Antwort

1.  Beim Empfangen der ersten Einladung vom SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 Trying" und benachrichtigt alle Endbenutzerendpunkte über den eingehenden Anruf. 

2.  Nach der Benachrichtigung klingelt jeder Endpunkt und sendet "Anrufstatus"-Nachrichten an den SIP-Proxy. Da ein Teams-Benutzer mehrere Endpunkte haben kann, empfängt der SIP-Proxy möglicherweise mehrere Anrufstatusmeldungen.

3.  Für jede von den Clients empfangene Anrufstatusnachricht konvertiert der SIP-Proxy die Anrufstatusnachricht in die SIP-Nachricht "SIP SIP/2.0 180 Klingeln". Das Intervall für das Senden solcher Nachrichten wird durch das Intervall der empfangenden Nachrichten vom Anrufcontroller definiert. Im folgenden Diagramm werden zwei 180 Nachrichten vom SIP-Proxy generiert. Diese Nachrichten stammen von den beiden Teams-Endpunkten des Benutzers. Die Clients verfügen jeweils über eine eindeutige Tag-ID.  Jede Nachricht, die von einem anderen Endpunkt stammt, ist eine separate Sitzung (der Parameter "tag" im Feld "An" ist anders). Aber ein Endpunkt generiert möglicherweise nicht die Nachricht 180 und sendet die Nachricht 183 sofort, wie im folgenden Diagramm dargestellt.

4.  Sobald ein Endpunkt eine Media Answer-Nachricht mit den IP-Adressen der Medienkandidaten des Endpunkts generiert, konvertiert der SIP-Proxy die empfangene Nachricht in eine "SIP 183 Session Progress"-Nachricht, wobei der SDP vom Client durch den SDP vom Medienprozessor ersetzt wird. Im folgenden Diagramm hat der Endpunkt von Fork 2 den Anruf angenommen. Wenn der Trunk nicht umgangen wird, wird die 183-SIP-Nachricht nur einmal generiert (entweder Ring-Bot oder Clientendpunkt). Die 183 kann auf einer vorhandenen Verzweigung enthalten sein oder eine neue Verzweigung starten.

5.  Eine Anrufannahmenachricht wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Anrufannahmenachricht wird in SIP-Nachricht 200 konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, dass mehrere Endpunkte mit vorläufiger Antwort klingeln.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Mehrere Endpunkte klingeln ohne vorläufige Antwort

1.  Beim Empfangen der ersten Einladung vom SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 Trying" und benachrichtigt alle Endbenutzerendpunkte über den eingehenden Anruf. 

2.  Nach der Benachrichtigung klingelt jeder Endpunkt und sendet die Nachricht "Anrufstatus" an den SIP-Proxy. Da ein Teams-Benutzer mehrere Endpunkte haben kann, empfängt der SIP-Proxy möglicherweise mehrere Anrufstatusmeldungen.

3.  Für jede von den Clients empfangene Anrufstatusnachricht konvertiert der SIP-Proxy die Anrufstatusnachricht in die SIP-Nachricht "SIP SIP/2.0 180 Trying".  Das Intervall für das Senden der Nachrichten wird durch das Intervall für den Empfang der Nachrichten vom Anrufcontroller definiert. Auf der folgenden Abbildung befinden sich zwei 180 Nachrichten, die vom SIP-Proxy generiert werden, was bedeutet, dass sich der Benutzer bei drei Teams-Clients angemeldet hat und jeder Client den Anrufstatus sendet. Jede Nachricht wird eine separate Sitzung sein (Parameter "tag" im Feld "An" ist anders)

4.  Eine Anrufannahmenachricht wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Anrufannahmenachricht wird in SIP-Nachricht 200 konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, dass mehrere Endpunkte ohne vorläufige Antwort klingeln.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Medienumgehungsfluss

Dieselben Nachrichten (100 Trying, 180, 183) werden im Medienumgehungsszenario verwendet. 

Das folgende Schema zeigt ein Beispiel für den Umgehungsaufruffluss. 

> [!NOTE]
> Die Medienkandidaten können von verschiedenen Endpunkten stammen. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, dass mehrere Endpunkte mit vorläufiger Antwort klingeln.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Ersetzungsoption

Der SBC muss "Einladen durch Ersetzen" unterstützen.

## <a name="size-of-sdp-considerations"></a>Größe von SDP-Überlegungen

Die Direct Routing-Schnittstelle sendet möglicherweise eine SIP-Nachricht, die mehr als 1.500 Bytes überschreitet.  Die Größe von SDP verursacht dies in erster Linie. Wenn sich jedoch ein UDP-Trunk hinter dem SBC befindet, wird die Nachricht möglicherweise abgelehnt, wenn sie vom Microsoft SIP-Proxy unverändert an den Trunk weitergeleitet wird. Microsoft empfiehlt, einige Werte in SDP auf dem SBC zu entfernen, wenn die Nachricht an die UDP-Trunks gesendet wird. Beispielsweise können die ICE-Kandidaten oder nicht verwendete Codecs entfernt werden.

## <a name="call-transfer"></a>Anrufweiterleitung

Direct Routing unterstützt zwei Methoden für die Anrufübertragung:

- Option 1. SIP-Proxyprozesse verweisen lokal vom Client und fungieren als Referee, wie in Abschnitt 7.1 von RFC 3892 beschrieben.

  Mit dieser Option beendet der SIP-Proxy die Übertragung und fügt eine neue Einladung hinzu. 


- Option 2. Der SIP-Proxy sendet den Verweis auf den SBC und fungiert als Transferor, wie in Abschnitt 6 von RFC 5589 beschrieben.

  Mit dieser Option sendet der SIP-Proxy einen Verweis auf den SBC und erwartet, dass der SBC die Übertragung vollständig verarbeitet.

Der SIP-Proxy wählt die Methode basierend auf den vom SBC gemeldeten Funktionen aus. Wenn der SBC angibt, dass er die Methode "Refer" unterstützt, verwendet der SIP-Proxy Option 2 für Anrufübertragungen.

Es folgt ein Beispiel für einen SBC, der die Nachricht sendet, dass die Refer-Methode unterstützt wird:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Wenn der SBC nicht angibt, dass Refer als unterstützte Methode bezeichnet wird, verwendet Direct Routing Option 1 (SIP-Proxy fungiert als Referee). Der SBC muss außerdem signalisieren, dass er die Notify-Methode unterstützt:

Beispiel für SBC, der angibt, dass die Refer-Methode nicht unterstützt wird:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP-Proxyprozesse verweisen lokal vom Client und fungieren als Referee

Wenn der SBC angegeben hat, dass die Refer-Methode nicht unterstützt wird, fungiert der SIP-Proxy als Referee. 

Die referenzierte Anforderung, die vom Client stammt, wird auf dem SIP-Proxy beendet. (Die Referenzanforderung des Clients wird im folgenden Diagramm als "Anrufdurchstellung an Dave" angezeigt.  Weitere Informationen finden Sie in Abschnitt 7.1 von [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, dass mehrere Endpunkte mit vorläufiger Antwort klingeln.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP-Proxy sendet den Verweis an den SBC und fungiert als Transferor

Dies ist die bevorzugte Methode für Anrufübertragungen und für Geräte, die eine Medienumgehungszertifizierung suchen, obligatorisch. Die Anrufübertragung, ohne dass der SBC Refer verarbeiten kann, wird im Medienumgehungsmodus nicht unterstützt. 

Der Standard wird in Abschnitt 6 von RFC 5589 erläutert. Die zugehörigen RFCs sind:

- [Sip-Anrufsteuerung (Session Initiation Protocol) – Übertragung](https://tools.ietf.org/html/rfc5589)

- [Session Initiation Protocol (SIP) "Replaces" Header](https://tools.ietf.org/html/rfc3891)

- [Sip-Mechanismus (Session Initiation Protocol) "Referred-By"](https://tools.ietf.org/html/rfc3892)

Bei dieser Option wird davon ausgegangen, dass der SIP-Proxy als Transferor fungiert und eine Referenznachricht an den SBC sendet. Der SBC fungiert als Übertragener und übernimmt die Referenz, um ein neues Angebot für die Übertragung zu generieren. Es gibt zwei mögliche Fälle:

- Der Anruf wird an einen externen PSTN-Teilnehmer weitergeleitet. 
- Der Anruf wird über den SBC von einem Teams-Benutzer an einen anderen Teams-Benutzer im selben Mandanten weitergeleitet. 

Wenn der Anruf über den SBC von einem Teams-Benutzer zu einem anderen weitergeleitet wird, wird erwartet, dass der SBC eine neue Einladung (ein neues Dialogfeld starten) für das Übertragungsziel (den Teams-Benutzer) ausgibt, wobei die in der Referenznachricht empfangenen Informationen verwendet werden. 

Um die An/Transferor-Felder für die Transaktion der Anforderung intern aufzufüllen, muss der SIP-Proxy diese Informationen innerhalb der REFER-TO/REFERRED-BY-Header übermitteln. 

Der SIP-Proxy bildet das REFER-TO als SIP-URI, der aus einem SIP-Proxy-FQDN im Hostnamen und einem der folgenden Komponenten besteht:

- Eine E.164-Telefonnummer im Benutzernamenteil des URI für den Fall, dass das Übertragungsziel eine Telefonnummer ist, oder

- x-m- und x-t-Parameter, die die vollständige Übertragungsziel-MRT bzw. Mandanten-ID codieren 

Der REFERRED-BY-Header ist ein SIP-URI mit darin codierter Übertragungs-MRT sowie einer Transferormandanten-ID und anderen Transferkontextparametern, wie in der folgenden Tabelle dargestellt:

| Parameter | Wert | Beschreibung |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Mri | Vollständige MRT des Transferor-/Übertragungsziels, wie von CC aufgefüllt |
| x-t | Mandanten-ID | Optionale Mandanten-ID für x-t-Mandanten-ID, aufgefüllt durch CC |
| x-ti | Transferorkorrelations-ID | Korrelations-ID des Anrufs an den Transferor |
| x-tt | URI für Übertragungszielaufruf | Codierter Aufrufersetzungs-URI |

Die Größe der Referenzkopfzeile kann in diesem Fall bis zu 400 Symbole sein. Der SBC muss die Behandlung von Referenznachrichten mit einer Größe von bis zu 400 Symbolen unterstützen.

> [!div class="mx-imgBorder"]
> ![Diagramm, das zeigt, dass mehrere Endpunkte mit vorläufiger Antwort klingeln.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Sitzungszeitgeber

Der SIP-Proxy unterstützt (immer) den Sitzungstimer bei Anrufen ohne Umgehung, bietet ihn jedoch nicht bei Umgehungsaufrufen an. Die Verwendung des Sitzungszeitgebers durch den SBC ist nicht obligatorisch.

##  <a name="use-of-request-uri-parameter-userphone"></a>Verwendung des Request-URI-Parameters user=phone

Der SIP-Proxy analysiert den Anforderungs-URI. Wenn der Parameter "user=phone" vorhanden ist, verarbeitet der Dienst den Anforderungs-URI als Telefonnummer, die der Nummer eines Benutzers entspricht. Wenn der Parameter nicht vorhanden ist, wendet der SIP-Proxy Heuristiken an, um den Anforderungs-URI-Benutzertyp (Telefonnummer oder SIP-Adresse) zu bestimmen.

Microsoft empfiehlt, immer den Parameter "user=phone" anzuwenden, um den Anrufeinrichtungsprozess zu vereinfachen.

## <a name="history-info-header"></a>History-Info Kopfzeile

Der History-Info Header wird zum Neuzuordnen von SIP-Anforderungen verwendet und "stellt(n) einen Standardmechanismus zum Erfassen der Anforderungsverlaufsinformationen bereit, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen." Weitere Informationen finden Sie [unter RFC 4244 – Abschnitt 1.1](http://www.ietf.org/rfc/rfc4244.txt). Bei Microsoft-Telefonsystem wird dieser Header in Simulring- und Anrufweiterleitungsszenarien verwendet.  

Beim Senden ist die History-Info wie folgt aktiviert:

- Der SIP-Proxy fügt einen Parameter mit der zugeordneten Telefonnummer in einzelne History-Info Einträge ein, die den History-Info Header enthalten, der an den PSTN-Controller gesendet wird.  Der PSTN-Controller erstellt nur Einträge mit dem Parameter "Telefonnummer" und erstellt einen neuen History-Info Header neu und leitet ihn per SIP-Proxy an den SIP-Trunkanbieter weiter.

- History-Info Kopfzeile wird für Fälle von gleichzeitigem Anrufen und Anrufweiterleitung hinzugefügt.

- History-Info Kopfzeile wird für Anrufdurchstellungsfälle nicht hinzugefügt.

- Bei einem individuellen Verlaufseintrag im rekonstruierten History-Info-Header wird der Telefonnummernparameter in Kombination mit dem Direct Routing FQDN (sip.pstnhub.microsoft.com) als Hostteil des URI festgelegt. ein Parameter von "user=phone" wird als Teil des SIP-URI hinzugefügt.  Alle anderen Parameter, die dem ursprünglichen History-Info Header zugeordnet sind, mit Ausnahme von Parametern des Telefonkontexts, werden im neu erstellten History-Info Header übergeben.  

  > [!NOTE]
  > Einträge, die privat sind (wie durch die in Abschnitt 3.3 von RFC 4244 definierten Mechanismen bestimmt), werden wie folgt weitergeleitet, da der SIP-Trunkanbieter ein vertrauenswürdiger Peer ist.

- Eingehende History-Info wird ignoriert.

Es folgt das Format des Verlaufsinformationen-Headers, der vom SIP-Proxy gesendet wird:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Wenn der Anruf mehrmals umgeleitet wurde, werden Informationen zu jeder Umleitung in chronologischer Reihenfolge mit dem entsprechenden Grund versehen.


Header-Beispiel:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Die History-Info wird durch einen obligatorischen TLS-Mechanismus geschützt. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC-Verbindung mit Direct Routing und Failovermechanismus

Weitere Informationen finden Sie im Abschnitt Failovermechanismus für DIE SIP-Signalisierung in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Wenn ein Direct Routing-Rechenzentrum ausgelastet ist, kann der Dienst eine Retry-After Nachricht mit einem Intervall von einer Sekunde an den SBC senden. Wenn der SBC als Reaktion auf eine EINLADUNG eine 503-Nachricht mit einem Retry-After-Header empfängt, muss der SBC diese Verbindung beenden und das nächste verfügbare Microsoft-Rechenzentrum testen.

## <a name="handling-retries-603-response"></a>Behandeln von Wiederholungsversuchen (603-Antwort)
Wenn ein Endbenutzer nach der Ablehnung des eingehenden Anrufs mehrere verpasste Anrufe für einen Anruf beobachtet, bedeutet dies, dass der Wiederholungsmechanismus des SBC- oder PSTN-Trunkanbieters falsch konfiguriert ist. Der SBC muss neu konfiguriert werden, um die Wiederholungsversuche für die 603-Antwort zu beenden.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE-Neustart: Medienumgehungsaufruf wird an einen Endpunkt übertragen, der die Medienumgehung nicht unterstützt

Der SBC muss ICE-Neustarts wie in [RFC 5245, Abschnitt 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) beschrieben, unterstützen.

Der Neustart in Direct Routing wird gemäß den folgenden Absätzen des RFC implementiert:

*Um ICE neu zu starten, muss ein Agent sowohl den Ice-Pwd als auch den Ice-Ufrag für den Medienstrom in einem Angebot ändern.  Beachten Sie, dass es zulässig ist, ein Attribut auf Sitzungsebene in einem Angebot zu verwenden, aber dasselbe Ice-Pwd- oder Ice-Ufrag-Attribut wie ein Medienattribut in einem nachfolgenden Angebot bereitzustellen.  Dies ist keine Änderung des Kennworts, nur eine Änderung der Darstellung und verursacht keinen ICE-Neustart.*

*Ein Agent legt die restlichen Felder im SDP für diesen Mediendatenstrom wie in einem ersten Angebot dieses Medienstreams fest (siehe Abschnitt 4.3).  Folglich kann die Gruppe der Kandidaten einige, keine oder alle vorherigen Kandidaten für diesen Datenstrom umfassen und KANN eine völlig neue Gruppe von Kandidaten enthalten, die wie in Abschnitt 4.1.1 beschrieben gesammelt werden.*

Wenn der Anruf anfänglich mit medienumgehung eingerichtet wurde und der Anruf an einen Skype for Business-Client weitergeleitet wird, muss Direct Routing einen Medienprozessor einfügen. Dies liegt daran, dass Direct Routing nicht mit einem Skype for Business-Client mit Medienumgehung verwendet werden kann. Direct Routing startet den ICE-Neustartprozess, indem es die ice-pwd und ice-ufrag ändert und neue Medienkandidaten in einer Reinvite anbietet.
