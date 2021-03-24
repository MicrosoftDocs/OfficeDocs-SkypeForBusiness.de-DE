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
ms.openlocfilehash: 00cdb644efe9fb2c3e49973d7a539718252a7df9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098471"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing – SIP-Protokoll

In diesem Artikel wird beschrieben, wie Direct Routing das Session Initiation Protocol (SIP) implementiert. Um den Datenverkehr zwischen einem Session Border Controller (SBC) und dem SIP-Proxy ordnungsgemäß zu routen, müssen einige SIP-Parameter bestimmte Werte enthalten. Dieser Artikel richtet sich an Sprachadministratoren, die für das Konfigurieren der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst zuständig sind.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Verarbeiten der eingehenden Anforderung: Suchen nach dem Mandanten und dem Benutzer

Bevor ein eingehender oder ausgehender Anruf verarbeitet werden kann, werden OPTIONS-Nachrichten zwischen SIP-Proxy und SBC ausgetauscht. Diese OPTIONS-Meldungen ermöglichen es dem SIP-Proxy, SBC die zulässigen Funktionen zur Verfügung zu stellen. Es ist wichtig, dass die OPTIONEN-Aushandlung erfolgreich ist (200OK-Antwort), wodurch eine weitere Kommunikation zwischen SBC und SIP-Proxy ermöglicht wird, um Anrufe zu erstellen. Die SIP-Header in einer OPTIONS-Nachricht an den SIP-Proxy werden als Beispiel unten bereitgestellt:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONEN sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Über Kopfzeile | Über: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max.-Weiterleitungen:68 |
| Aus Kopfzeile | Von Header From: <sip:sbc1.adatum.biz:5058> |
| An Kopfzeile | An: <sip:sip.pstnhub.microsoft.com:5061> |
| #A0 | CSeq: 1 EINLADUNG | 
| Kontaktkopf | Kontakt: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Die SIP-Header enthalten keine Benutzerinfo im verwendeten SIP-URI. Wie rfc [3261, Abschnitt 19.1.1,](https://tools.ietf.org/html/rfc3261#section-19.1.1)ist der Userinfo-Teil eines URI optional und KANN nicht vorhanden sein, wenn der Zielhost kein Benutzerbegriff hat oder wenn der Hosst selbst die zu identifizierende Ressource ist. Wenn das @-Zeichen in einem SIP-URI vorhanden ist, darf das Benutzerfeld NICHT leer sein.

Bei einem eingehenden Anruf muss der SIP-Proxy den Mandanten suchen, für den der Anruf bestimmt ist, und den bestimmten Benutzer innerhalb dieses Mandanten finden. Der Mandantenadministrator kann Nicht-DID-Nummern, z. B. +1001, in mehreren Mandanten konfigurieren. Daher ist es wichtig, den bestimmten Mandanten zu finden, für den die Nachschlagenummer durchzuführen ist, da die Nicht-DID-Zahlen in mehreren Microsoft 365- oder Office 365-Organisationen gleich sein können.  

In diesem Abschnitt wird beschrieben, wie der SIP-Proxy den Mandanten und den Benutzer findet und die Authentifizierung des SBC für die eingehende Verbindung durchführt.

Im Folgenden ist ein Beispiel für die SIP-Einladungsnachricht bei einem eingehenden Anruf zu finden:

| Parametername | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | EINLADEN sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Über Kopfzeile | Über: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards Kopfzeile | Max.-Weiterleitungen:68 |
| Aus Kopfzeile | From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| An Kopfzeile | An: sip:+183338006777@sbc1.adatum.biz | 
| #A0 | CSeq: 1 EINLADUNG | 
| Kontaktkopf | Kontakt: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Beim Empfangen der Einladung führt der SIP-Proxy die folgenden Schritte aus:

1. Überprüfen Sie das Zertifikat. Bei der anfänglichen Verbindung übernimmt der Direct Routing-Dienst den FQDN-Namen, der in der Kopfzeile "Kontakt" angezeigt wird, und passt ihn mit dem Namen "Common Name" oder "Subject Alternative" des präsentierten Zertifikats an. Der Name des SBC muss mit einer der folgenden Optionen übereinstimmen:

   - Option 1. Der vollständige FQDN-Name, der in der Kopfzeile "Kontakt" angezeigt wird, muss mit dem Namen "Gemeinsamer Name/Betreffalternative" des präsentierten Zertifikats übereinstimmen.  

   - Option 2. Der Domänenbereich des #A0 im Kontaktkopf (z. B. adatum.biz des FQDN-Namens sbc1.adatum.biz) muss mit dem Platzhalterwert in Common Name/Subject Alternative Name (z. B. *.adatum.biz) übereinstimmen.

2. Versuchen Sie, einen Mandanten mit dem vollständigen FQDN-Namen zu finden, der in der Kopfzeile "Kontakt" angezeigt wird.  

   Überprüfen Sie, ob der FQDN-Name aus dem Kontaktkopf (sbc1.adatum.biz) in einer beliebigen Microsoft 365- oder Office 365-Organisation als DNS-Name registriert ist. Wenn gefunden, wird die Suche des Benutzers in dem Mandanten ausgeführt, für den der SBC-FQDN als Domänenname registriert ist. Wenn sie nicht gefunden wird, gilt Schritt 3.   

3. Schritt 3 gilt nur, wenn Schritt 2 fehlgeschlagen ist. 

   Entfernen Sie den Hostbereich aus dem FQDN, der im Kontaktkopf (FQDN: sbc12.adatum.biz, nach dem Entfernen des Hostteils: adatum.biz) angezeigt wird, und überprüfen Sie, ob dieser Name als DNS-Name in einer beliebigen Microsoft 365- oder Office 365-Organisation registriert ist. Wenn gefunden, wird die Benutzer-Suche in diesem Mandanten ausgeführt. Wenn sie nicht gefunden wird, schlägt der Anruf fehl.

4. Führen Sie unter Verwendung der telefonnummer, die im Anforderungs-URI dargestellt wird, den Reverse-Number-Nachschlageschritt innerhalb des Mandanten durch, der in Schritt 2 oder 3 gefunden wurde. Passen Sie die angezeigte Telefonnummer einem SIP-URI des Benutzers innerhalb des Mandanten an, der im vorherigen Schritt gefunden wurde.

5. Anwenden von Trunkeinstellungen Suchen Sie die Parameter, die vom Mandantenadministrator für diesen SBC festgelegt wurden.

   Microsoft unterstützt nicht die Verwendung eines SIP-Proxys oder User Agent Servers eines Drittanbieters zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC, wodurch der vom gekoppelten SBC erstellte Anforderungs-URI geändert werden kann.

   Die Anforderungen für die beiden Nachschlageschritte (Schritte 2 und 3), die für das Szenario erforderlich sind, in dem ein SBC mit vielen Mandanten (Netzbetreiberszenario) verbunden ist, werden weiter unten in diesem Artikel behandelt.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Detaillierte Anforderungen für Kontaktkopf und Anforderungs-URI

#### <a name="contact-header"></a>Kontaktkopf

Für alle eingehenden SIP-Nachrichten (OPTIONEN, EINLADEN) an den Microsoft SIP-Proxy muss der Kontaktkopf den gekoppelten SBC-FQDN im URI-Hostnamen wie folgt enthalten:

Syntax: Kontakt: <sip:phone oder sip address@FQDN des SBC;transport=tls> 

Nach [RFC 3261, Abschnitt 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)ist möglicherweise ein Kontaktkopffeld in einer OPTIONS-Nachricht vorhanden. In Direct Routing ist der Kontaktkopf erforderlich. Bei EINLADUNGsnachrichten im oben angegebenen Format kann bei OPTIONS-Nachrichten die Benutzerinfo aus dem SIP-URI entfernt und nur FQDN im folgenden Format gesendet werden:

Syntax: Kontakt: <sip:FQDN des SBC;transport=tls>

Dieser Name (FQDN) muss sich auch im Feld "Gemeinsamer Name" oder "Betreffalternativer Name"(n) des präsentierten Zertifikats finden. Microsoft unterstützt die Verwendung von Platzhalterwerten der Namen(n) in den Feldern "Gemeinsamer Name" oder "Alternativer Betreffname" des Zertifikats.   

Die Unterstützung von Platzhaltern wird in [RFC 2818, Abschnitt 3.1 beschrieben.](https://tools.ietf.org/html/rfc2818#section-3.1) Im Einzelnen:

*"Namen können das Platzhalterzeichen enthalten, das als mit einer einzelnen Domänennamenkomponente oder einem Komponentenfragment \* übereinstimmend betrachtet wird. Z. B. a.com entspricht foo.a.com nicht bar.foo.a.com. f .com entspricht foo.com \* \* aber nicht bar.com."*

Wenn mehr als ein Wert im In einer SIP-Nachricht angezeigten Kontaktkopf vom SBC gesendet wird, wird nur der FQDN-Teil des ersten Werts des Kontaktkopfs verwendet.

Als Faustregel für Direct Routing ist es wichtig, dass FQDN zum Auffüllen von SIP-URI anstelle von IP verwendet wird. Eine eingehende EINLADUNG oder OPTIONS-Nachricht an den SIP-Proxy mit Kontaktkopf, wobei Hostname durch IP und nicht durch FQDN dargestellt wird, wird die Verbindung mit 403 Forbidden abgelehnt.

#### <a name="request-uri"></a>Request-URI 

Für alle eingehenden Anrufe wird der Anforderungs-URI verwendet, um die Telefonnummer einem Benutzer zu entsprechen.   

Derzeit muss die Telefonnummer ein Pluszeichen (+) enthalten, wie im folgenden Beispiel gezeigt. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Überlegungen zu Record-Route und Kopfzeilen

Der SIP-Proxy muss den nächsten Hop-FQDN für neue in-Dialog-Clienttransaktionen (z. B. Bye oder Erneut einladen) und beim Antworten auf SIP-Optionen berechnen. Entweder Kontakt oder Record-Route werden verwendet. 

Gemäß [RFC 3261, Abschnitt 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)ist der Kontaktkopf in jeder Anforderung erforderlich, die zu einem neuen Dialogfeld führen kann. Die Record-Route ist nur erforderlich, wenn ein Proxy in einem Dialogfeld auf dem Pfad zukünftiger Anforderungen bleiben möchte. Wenn ein Proxy-SBC mit local media optimization für [Direct Routing](./direct-routing-media-optimization.md)verwendet wird, muss eine Datensatzroute konfiguriert werden, da der Proxy-SBC in der Route bleiben muss. 

Microsoft empfiehlt, nur kontaktkopf zu verwenden, wenn kein Proxy-SBC verwendet wird:

- Pro [RFC 3261, Abschnitt 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), wird Record-Route verwendet, wenn ein Proxy auf dem Pfad zukünftiger Anforderungen in einem Dialogfeld bleiben möchte. Dies ist nicht unbedingt erforderlich, wenn kein ProxySBC konfiguriert ist, da der datenverkehr zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC fließt. 

- Der Microsoft SIP-Proxy verwendet nur den Kontaktkopf (nicht Record-Route), um den nächsten Hop beim Senden von ausgehenden Pingoptionen zu ermitteln. Das Konfigurieren von nur einem Parameter (Kontakt) anstelle von zwei (Kontakt und Datensatzroute) vereinfacht die Verwaltung, wenn kein Proxy-SBC verwendet wird. 

Zum Berechnen des nächsten Hops verwendet der SIP-Proxy:

- Priorität 1. Record-Route der obersten Ebene. Wenn der Name der obersten Record-Route den FQDN-Namen enthält, wird der FQDN-Name verwendet, um die ausgehende Indialogfeldverbindung herzustellen.

- Priorität 2. Kontaktkopf. Wenn Record-Route vorhanden ist, sucht der SIP-Proxy den Wert des Kontaktkopfs, um die ausgehende Verbindung herzustellen. (Dies ist die empfohlene Konfiguration.)

Wenn sowohl Kontakt als auch Record-Route verwendet werden, muss der SBC-Administrator seine Werte identisch halten, was zu verwaltungstechnischem Aufwand führt. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Verwenden des FQDN-Namens in Kontakt oder Record-Route

Die Verwendung einer IP-Adresse wird weder in der Record-Route noch in Kontakt unterstützt. Die einzige unterstützte Option ist ein FQDN, der entweder mit dem allgemeinen Namen oder dem alternativen Betreffnamen des SBC-Zertifikats übereinstimmen muss (Platzhalterwerte im Zertifikat werden unterstützt).

- Wenn eine IP-Adresse in Datensatzroute oder Kontakt dargestellt wird, schlägt die Zertifikatüberprüfung fehl, und der Anruf schlägt fehl.

- Wenn der FQDN nicht mit dem Wert des alternativen Namens "Common" oder "Subject Alternative Name" im präsentierten Zertifikat übereinstimmen, schlägt der Aufruf fehl. 

## <a name="inbound-call-sip-dialog-description"></a>Eingehender Anruf: Beschreibung des SIP-Dialogfelds

In der folgenden Tabelle sind die Unterschiede und Ähnlichkeiten zwischen den Modi "Nichtumgehung" und "Umgehung" zusammengefasst:

| Parametername | Nichtumgehungsmodus | Umgehungsmodus
| :---------------------  |:---------------------- |:----------------|
| Medienkandidaten in 183 und 200 Nachrichten, die von | Medienprozessoren | Clients | 
| Anzahl von 183 Nachrichten, die SBC empfangen kann | Eine pro Sitzung | Mehrere | 
| Anruf kann mit vorläufiger Antwort sein (183) | Ja | Ja |
| Anruf kann ohne vorläufige Antwort sein (183) | Ja | Ja |

###  <a name="non-media-bypass-flow"></a>Nicht mediale Umgehungsfluss

Ein Teams-Benutzer kann mehrere Endpunkte gleichzeitig haben. Beispiel: Teams für Windows-Client, Teams für iPhone-Client und Teams Phone (Teams Android-Client). Jeder Endpunkt signalisiert möglicherweise eine HTTP-Pause wie folgt:

-   Anruffortschritt – vom SIP-Proxy in die SIP-Nachricht 180 konvertiert. Beim Empfangen der Nachricht 180 muss der SBC lokales Klingeln generieren.

-   Medienantwort – vom SIP-Proxy in Nachricht 183 mit Medienkandidaten im Sitzungsbeschreibungsprotokoll (Session Description Protocol, SDP) konvertiert. Beim Empfang der Nachricht 183 erwartet der SBC, dass eine Verbindung mit den Medienkandidaten hergestellt wird, die in der SDP-Nachricht empfangen wurden. 

    > [!NOTE]
    > In einigen Fällen wird die Medienantwort möglicherweise nicht generiert, und der Endpunkt antwortet möglicherweise mit der Meldung "Angenommener Anruf".

-   Anruf angenommen – vom SIP-Proxy in SIP-Nachricht 200 mit SDP konvertiert. Beim Empfang der Nachricht 200 wird erwartet, dass der SBC Medien an und von den bereitgestellten SDP-Kandidaten sendet und empfängt.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Mehrere Endpunkte klingeln mit vorläufiger Antwort

1.  Beim Empfang der ersten Einladung vom SBC sendet der SIP-Proxy die Meldung "SIP SIP/2.0 100 Versuchen" und benachrichtigt alle Endpunkte des Endbenutzers über den eingehenden Anruf. 

2.  Nach der Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und sendet Nachrichten zum Status "Anruf" an den SIP-Proxy. Da ein Teams-Benutzer mehrere Endpunkte haben kann, erhält der SIP-Proxy möglicherweise mehrere Nachrichten zum Anruffortschritt.

3.  Für jede von den Clients empfangene Anruffortschrittsnachricht konvertiert der SIP-Proxy die Meldung Anruffortschritt in die SIP-Nachricht "SIP SIP/2.0 180 Versuchen". Das Intervall für das Senden solcher Nachrichten wird durch das Intervall der empfangenden Nachrichten vom Anrufcontroller definiert. Im folgenden Diagramm werden zwei 180 Nachrichten vom SIP-Proxy generiert. Diese Nachrichten stammen von den beiden Teams-Endpunkten des Benutzers. Die Clients verfügen jeweils über eine eindeutige Tag-ID.  Jede Nachricht, die von einem anderen Endpunkt kommt, ist eine separate Sitzung (der Parameter "Tag" im Feld "An" ist anders). Ein Endpunkt generiert jedoch möglicherweise nicht sofort die Nachricht 180 und sendet die Nachricht 183, wie in der folgenden Abbildung dargestellt.

4.  Nachdem ein Endpunkt eine Medienantwortnachricht mit den IP-Adressen der Medienkandidaten des Endpunkts generiert hat, konvertiert der SIP-Proxy die empfangene Nachricht in eine Meldung "SIP 183-Sitzungsfortschritt", bei der die SDP vom Client durch die SDP des Medienprozessors ersetzt wird. In der folgenden Abbildung hat der Endpunkt von Fork 2 den Anruf beantwortet. Wenn der Trunk nicht umgangen wird, wird die 183-SIP-Nachricht nur einmal generiert (entweder Ring Bot oder Client-EndPunkt). Die 183 kann auf einer vorhandenen Gabel vorhanden sein oder eine neue beginnen.

5.  Eine Anrufannahmenachricht wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Anrufannahmenachricht wird in SIP-Nachricht 200 konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm mit mehreren Endpunkten, die mit einer vorläufigen Antwort klingeln](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Mehrere Endpunkte klingeln ohne vorläufige Antwort

1.  Beim Empfang der ersten Einladung vom SBC sendet der SIP-Proxy die Meldung "SIP SIP/2.0 100 Versuchen" und benachrichtigt alle Endpunkte des Endbenutzers über den eingehenden Anruf. 

2.  Nach der Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und sendet die Nachricht "Anruffortschritt" an den SIP-Proxy. Da ein Teams-Benutzer mehrere Endpunkte haben kann, erhält der SIP-Proxy möglicherweise mehrere Nachrichten zum Anruffortschritt.

3.  Für jede von den Clients empfangene Anruffortschrittsnachricht konvertiert der SIP-Proxy die Meldung Anruffortschritt in die SIP-Nachricht "SIP SIP/2.0 180 Versuchen".  Das Intervall für das Senden der Nachrichten wird durch das Intervall definiert, in dem die Nachrichten vom Anrufcontroller empfangen werden. Im Bild unten werden zwei 180 Nachrichten vom SIP-Proxy generiert, d. h., dass sich der Benutzer bei drei Teams-Clients angemeldet hat und jeder Client den Anruffortschritt sendet. Jede Nachricht ist eine separate Sitzung (der Parameter "Tag" im Feld "An" ist anders)

4.  Eine Anrufannahmenachricht wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Anrufannahmenachricht wird in SIP-Nachricht 200 konvertiert. 

> [!div class="mx-imgBorder"]
> ![Diagramm, in dem mehrere Endpunkte ohne vorläufige Antwort klingeln](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Medienumgehungsfluss

Dieselben Nachrichten (100 Versuchen, 180, 183) werden im Szenario der Medienumgehung verwendet. 

Das folgende Schema zeigt ein Beispiel für den Umgehungsaufruffluss. 

> [!NOTE]
> Die Medienkandidaten können von verschiedenen Endpunkten stammen. 

> [!div class="mx-imgBorder"]
> ![Diagramm mit mehreren Endpunkten, die mit einer vorläufigen Antwort klingeln](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Option "Ersetzen"

Der SBC muss Einladen durch Ersetzen unterstützen.

## <a name="size-of-sdp-considerations"></a>Größe von SDP-Überlegungen

Die Direct Routing-Schnittstelle sendet möglicherweise eine SIP-Nachricht, die mehr als 1.500 Bytes überschreitet.  Die Größe von SDP führt in erster Linie dazu. Wenn sich jedoch ein UDP-Trunk hinter dem SBC befindet, wird die Nachricht möglicherweise abgelehnt, wenn sie vom Microsoft SIP-Proxy unverändert an den Trunk weitergeleitet wird. Microsoft empfiehlt, beim Senden der Nachricht an die UDP-Trunks einige Werte in SDP auf dem SBC zu beschneiden. So können beispielsweise die ICE-Kandidaten oder nicht verwendete Codecs entfernt werden.

## <a name="call-transfer"></a>Anrufübertragung

Direct Routing unterstützt zwei Methoden für die Anrufübertragung:

- Option 1. SIP-Proxyprozesse Beziehen Sie sich lokal vom Client und fungiert als Referee, wie in Abschnitt 7.1 von RFC 3892 beschrieben.

  Mit dieser Option beendet der SIP-Proxy die Übertragung und fügt eine neue Einladung hinzu. 


- Option 2. Der SIP-Proxy sendet den Refer an den SBC und fungiert als Transferor, wie in Abschnitt 6 von RFC 5589 beschrieben.

  Bei dieser Option sendet der SIP-Proxy einen Bezug auf den SBC und erwartet, dass der SBC die Übertragung vollständig verarbeitet.

Der SIP-Proxy wählt die -Methode basierend auf den vom SBC gemeldeten Funktionen aus. Wenn der SBC angibt, dass er die Methode "Refer" unterstützt, verwendet der SIP-Proxy Option 2 für Anrufübertragungen.

Im Folgenden sehen Sie ein Beispiel für einen SBC, der die Meldung sendet, dass die Refer-Methode unterstützt wird:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Wenn der SBC nicht angibt, dass Refer als unterstützte Methode gilt, verwendet Direct Routing Option 1 (SIP-Proxy fungiert als Referee). Der SBC muss auch signalisieren, dass er die Notify-Methode unterstützt:

Beispiel für SBC, das angibt, dass die Refer-Methode nicht unterstützt wird:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP-Proxyprozesse Beziehen Sie sich lokal vom Client und fungiert als Referee

Wenn der SBC angegeben hat, dass die Refer-Methode nicht unterstützt wird, fungiert der SIP-Proxy als Referee. 

Die Refer-Anforderung, die vom Client stammt, wird im SIP-Proxy beendet. (Die Referenzanforderung vom Client wird in der folgenden Abbildung als "Anrufübertragung an Dave" angezeigt.  Weitere Informationen finden Sie unter Abschnitt 7.1 von [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagramm mit mehreren Endpunkten, die mit einer vorläufigen Antwort klingeln](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP-Proxy senden den Verweisen auf den SBC und fungiert als Transferor

Dies ist die bevorzugte Methode für Anrufübertragungen, und sie ist für Geräte, die eine Medienumgehungszertifizierung suchen, obligatorisch. Die Anrufübertragung ohne die Verarbeitung von Refer durch den SBC wird im Medienumgehungsmodus nicht unterstützt. 

Der Standard wird in Abschnitt 6 von RFC 5589 erläutert. Die zugehörigen RFCs sind:

- [Sip-Anrufsteuerung (Session Initiation Protocol) – Übertragung](https://tools.ietf.org/html/rfc5589)

- [Session Initiation Protocol (SIP) "Replaces" Header](https://tools.ietf.org/html/rfc3891)

- [Session Initiation Protocol (SIP) "Referred-By"-Mechanismus](https://tools.ietf.org/html/rfc3892)

Bei dieser Option wird davon ausgegangen, dass der SIP-Proxy als Transferor fungiert und eine Refer-Nachricht an den SBC sendet. Der SBC fungiert als Transferee und übernimmt den Refer, um ein neues Angebot für die Übertragung zu generieren. Es gibt zwei mögliche Fälle:

- Der Anruf wird an einen externen PSTN-Teilnehmer übertragen. 
- Der Anruf wird über den SBC von einem Teams-Benutzer an einen anderen Teams-Benutzer im gleichen Mandanten übertragen. 

Wenn der Anruf von einem Teams-Benutzer über den SBC an einen anderen übertragen wird, wird vom SBC erwartet, dass er eine neue Einladung für das Übertragungsziel (den Teams-Benutzer) mit den in der Meldung Refer erhaltenen Informationen aussent(Start eines neuen Dialogfelds). 

Um die Felder an/Transferor für die Transaktion der Anforderung intern auffüllen zu können, muss der SIP-Proxy diese Informationen in den REFER-TO/REFERRED-BY-Headern übermitteln. 

Der SIP-Proxy formt den REFER-TO als SIP-URI, der aus einem SIP-Proxy-FQDN im Hostnamen und einer der folgenden URI besteht:

- Eine E.164-Telefonnummer im Benutzernamenteil des URI für den Fall, dass es sich bei dem Übertragungsziel um eine Telefonnummer handelt, oder

- x-m- und x-t-Parameter, die die vollständige MRT- bzw. Mandanten-ID des Übertragungsziels codieren 

Der REFERRED-BY-Header ist ein SIP-URI mit in ihm codiertem Transferor-MRI sowie der Transferor-Mandanten-ID und anderen Übertragungskontextparametern, wie in der folgenden Tabelle dargestellt:

| Parameter | Wert | Beschreibung |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | Vollständige MRI des Übertragungs-/Übertragungsziels, wie von CC ausgefüllt |
| x-t | Mandanten-ID | x-t Tenant ID Optional Tenant ID as populated by CC |
| x-ti | Transferor Correlation Id | Korrelations-ID des Aufrufs des Übertragungsgebers |
| x-tt | URI für Transferzielanrufe | Codierter Anrufersetzungs-URI |

Die Größe der Refer-Kopfzeile kann in diesem Fall bis zu 400 Symbole aufweisen. Der SBC muss die Behandlung von Refer-Nachrichten mit einer Größe von bis zu 400 Symbolen unterstützen.

> [!div class="mx-imgBorder"]
> ![Diagramm mit mehreren Endpunkten, die mit einer vorläufigen Antwort klingeln](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Sitzungstimer

Der SIP-Proxy unterstützt (immer) den Sitzungstimer bei Nichtumgehungsanrufen, bietet ihn aber nicht bei Umgehungsanrufen an. Die Verwendung des Sitzungszeitgebers durch den SBC ist nicht obligatorisch.

##  <a name="use-of-request-uri-parameter-userphone"></a>Verwendung des Request-URI-Parameters user=phone

Der SIP-Proxy analysiert den Request-URI, und wenn der Parameter user=phone vorhanden ist, verarbeitet der Dienst den Request-URI als Telefonnummer, die der Nummer eines Benutzers folgt. Ist kein Parameter vorhanden, wendet der SIP-Proxy Heuristiken an, um den Benutzertyp Request-URI (Telefonnummer oder SIP-Adresse) zu ermitteln.

Microsoft empfiehlt, immer den Parameter user=phone zu verwenden, um den Anrufeinrichtungsvorgang zu vereinfachen.

## <a name="history-info-header"></a>History-Info Kopfzeile

Der History-Info wird zum Neutargetieren von SIP-Anforderungen verwendet und "stellt(en) einen Standardmechanismus zum Erfassen der Anforderungsverlaufsinformationen zur Verfügung, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen." Weitere Informationen finden Sie unter [RFC 4244 – Abschnitt 1.1](http://www.ietf.org/rfc/rfc4244.txt). Für Microsoft Phone System wird dieser Header in Szenarien für Simulring und Anruf weiterleitung verwendet.  

Beim Senden ist die History-Info wie folgt aktiviert:

- Der SIP-Proxy fügt einen Parameter ein, der die zugeordnete Telefonnummer in einzelne History-Info enthält, die den History-Info an den PSTN-Controller gesendeten Header enthalten.  Wenn nur Einträge verwendet werden, die über den Parameter "Telefonnummer" verfügen, erstellt der PSTN-Controller einen neuen History-Info-Header neu und über den SIP-Proxy an den SIP-Trunkanbieter weiter.

- History-Info Kopfzeile wird für die gleichzeitige Anruf- und Anruf weiterleitenden Fälle hinzugefügt.

- History-Info Kopfzeile wird für Anrufübertragungsfälle nicht hinzugefügt.

- Für einen einzelnen Verlaufseintrag in der rekonstruierten History-Info-Kopfzeile wird der parameter für telefonnummern in Kombination mit dem FQDN für direktes Routing (sip.pstnhub.microsoft.com) als Hostteil des URI festgelegt. Ein Parameter von "user=phone" wird als Teil des SIP-URI hinzugefügt.  Alle anderen Parameter, die dem ursprünglichen History-Info zugeordnet sind, mit Ausnahme von Telefonkontextparametern, werden in der neu erstellten History-Info übergeben.  

  > [!NOTE]
  > Einträge, die privat sind (gemäß den in Abschnitt 3.3 von RFC 4244 definierten Mechanismen), werden wie folgt weitergeleitet, da der SIP-Trunkanbieter ein vertrauenswürdiger Peer ist.

- Eingehende History-Info wird ignoriert.

Im Folgenden wird das Format des Vom SIP-Proxy gesendeten History-Info-Headers angezeigt:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Wenn der Anruf mehrmals umgeleitet wurde, sind Informationen zu jeder Umleitung in chronologischer Reihenfolge mit dem entsprechenden Grund enthalten.


Kopfzeilenbeispiel:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Die History-Info ist durch einen obligatorischen TLS-Mechanismus geschützt. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC-Verbindung mit Direct Routing und Failovermechanismus

Weitere Informationen finden Sie im Abschnitt Failovermechanismus für SIP-Signalisierung in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Wenn ein Direct Routing-Rechenzentrum ausgelastet ist, kann der Dienst eine Retry-After mit einem Intervall von einer Sekunde an den SBC senden. Wenn der SBC als Reaktion auf eine EINLADUNG eine 503-Nachricht mit einem Retry-After-Header empfängt, muss der SBC diese Verbindung beenden und das nächste verfügbare Microsoft-Rechenzentrum ausprobieren. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE-Neustart: Medienumgehungsaufruf, der an einen Endpunkt übertragen wird, der die Medienumgehung nicht unterstützt

Der SBC muss ICE-Neustarts unterstützen, wie in [RFC 5245, Abschnitt 9.1.1.1 beschrieben.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)

Der Neustart in Direct Routing wird gemäß den folgenden Absätzen der RFC implementiert:

*Um ICE neu zu starten, muss ein Agent sowohl den Eis-Pwd als auch den Eislauf für den Medienstrom in einem Angebot ändern.  Beachten Sie, dass es zulässig ist, ein Sitzungsattribut in einem Angebot zu verwenden, aber dasselbe Ice-Pwd- oder Ice-ufrag-Attribut als Attribut auf Medienebene in einem nachfolgenden Angebot zur Verfügung zu stellen.  Dies ist keine Änderung des Kennworts, sondern lediglich eine Änderung der Darstellung und führt nicht zu einem ICE-Neustart.*

*Ein Agent legt die restlichen Felder in der SDP für diesen Medienstream wie in einem ersten Angebot dieses Medienstreams fest (siehe Abschnitt 4.3).  Folglich enthält die Gruppe der Kandidaten MÖGLICHERWEISE einige, keine oder alle vorherigen Kandidaten für diesen Stream und MAY eine völlig neue Gruppe von Kandidaten, die wie in Abschnitt 4.1.1 beschrieben gesammelt wurden.*

Wenn der Anruf ursprünglich mit der Medienumgehung eingerichtet wurde und der Anruf an einen Skype for Business-Client übertragen wird, muss Direct Routing einen Medienprozessor einfügen. Dies liegt daran, dass Direct Routing nicht mit einem Skype for Business-Client mit Medienumgehung verwendet werden kann. Direct Routing startet den ICE-Neustartprozess, indem die Ice-Pwd- und Ice-Ufrag-Version geändert und neue Medienkandidaten in einer Erneuteinleitung angeboten werden.