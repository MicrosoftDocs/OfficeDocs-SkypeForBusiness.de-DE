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
description: Direkte Routing Protokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: a66213214457648ec0b699d77bdadc96113fba27
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780684"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing – SIP-Protokoll

In diesem Artikel wird beschrieben, wie das direkte Routing das Session Initiation Protocol (SIP) implementiert. Um den Datenverkehr zwischen einem Session Border Controller (SBC) und dem SIP-Proxy ordnungsgemäß weiterzuleiten, müssen einige SIP-Parameter bestimmte Werte aufweisen. Dieser Artikel richtet sich an sprach Administratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst verantwortlich sind.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Verarbeiten der eingehenden Anforderung: Suchen des Mandanten und des Benutzers

Bei einem eingehenden Anruf muss der SIP-Proxy den Mandanten finden, zu dem der Anruf bestimmt ist, und den jeweiligen Nutzer innerhalb dieses Mandanten finden. Der mandantenadministrator kann nicht-DID-Nummern konfigurieren, beispielsweise + 1001, in mehreren Mandanten. Daher ist es wichtig, den jeweiligen Mandanten zu finden, für den die Nummernsuche durchgeführt werden soll, da die nicht-DID-Nummern in mehreren Office 365-Organisationen identisch sein können.  

In diesem Abschnitt wird beschrieben, wie der SIP-Proxy den Mandanten und den Benutzer findet und die Authentifizierung des SBC für die eingehende Verbindung ausführt.

Der folgende Code ist ein Beispiel für die SIP-Einladungsnachricht bei einem eingehenden Anruf:

| Parameter Name | Beispiel für den Wert | 
| :---------------------  |:---------------------- |
| Request-URI | INVITE SIP:+18338006777@SIP.pstnhub.Microsoft.com SIP/2,0 |
| Überschrift | Über: SIP/2.0/TLS sbc1. adatum. biz: 5058; Alias; Branch = z9hG4bKac2121518978 | 
| Max-Forwards-Kopfzeile | Max-Forwards: 68 |
| From-Kopfzeile | From Header from: <SIP: 7168712781@sbc1. adatum. biz; Transport = UDP; Tag = 1c747237679 |
| Kopfzeile | An: SIP:+183338006777@sbc1.adatum.biz | 
| CSeq-Kopfzeile | CSeq: 1 Einladung | 
| Kontakt Kopfzeile | Kontakt: <SIP: 68712781@sbc1. adatum. biz; Transport = TLS> | 

Beim Empfang der Einladung führt der SIP-Proxy die folgenden Schritte aus:

1. Überprüfen Sie das Zertifikat. Bei der ersten Verbindung übernimmt der Direct Routing-Dienst den FQDN-Namen, der in der Kontakt Kopfzeile angezeigt wird, und vergleicht ihn mit dem allgemeinen Namen oder dem alternativen Subjektnamen des vorgestellten Zertifikats. Der SBC-Name muss mit einer der folgenden Optionen übereinstimmen:

   - Option 1. Der vollständige FQDN-Name, der in der Kontakt Kopfzeile angezeigt wird, muss dem allgemeinen Namen/Subjekt alternativen Namen des vorgestellten Zertifikats entsprechen.  

   - Option 2. Der Domänenteil des FQDN-namens, der in der Kontakt Kopfzeile angezeigt wird (beispielsweise adatum.biz des FQDN-namens sbc1.adatum.biz), muss dem Platzhalterwert im allgemeinen Namen/Subjekt alternativen Namen (beispielsweise *. adatum.biz) entsprechen.

2. Versuchen Sie, einen Mandanten mit dem vollständigen FQDN-Namen zu finden, der in der Kontakt Kopfzeile dargestellt wird.  

   Überprüfen Sie, ob der FQDN-Name aus der Kontakt Kopfzeile (sbc1.adatum.biz) in einer beliebigen Office 365-Organisation als DNS-Name registriert ist. Wenn Sie gefunden wird, wird die Suche des Benutzers im Mandanten durchgeführt, auf dem der SBC-FQDN als Domänenname registriert ist. Wenn Sie nicht gefunden wird, gilt Schritt 3.   

3. Schritt 3 gilt nur, wenn Schritt 2 fehlgeschlagen ist. 

   Entfernen Sie den Host Anteil aus dem FQDN, der in der Kontakt Kopfzeile (FQDN: sbc12.adatum.biz nach dem Entfernen des Host Abschnitts: adatum.biz) angezeigt wird, und überprüfen Sie, ob dieser Name in einer beliebigen Office 365-Organisation als DNS-Name registriert ist. Wenn Sie gefunden wird, wird die Benutzersuche in diesem Mandanten ausgeführt. Wenn nicht gefunden, schlägt der Anruf fehl.

4. Führen Sie mit der im Anforderungs-URI vorgestellten Telefonnummer die umgekehrte Nummernsuche innerhalb des Mandanten durch, der in Schritt 2 oder 3 gefunden wurde. Vergleichen Sie die vorgestellten Telefonnummern mit einem SIP-URI des Benutzers innerhalb des Mandanten, der im vorherigen Schritt gefunden wurde.

5. Übernehmen Sie trunk-Einstellungen. Suchen Sie die vom mandantenadministrator für diesen SBC festgelegten Parameter.

   Microsoft unterstützt nicht die Nutzung eines SIP-Proxys eines Drittanbieters oder eines Benutzer-Agent-Servers zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC, wodurch der vom gekoppelten SBC erstellte Anforderungs-URI geändert werden kann.

   Die Anforderungen für die beiden Nachschlagevorgänge (Schritte 2 und 3), die für das Szenario erforderlich sind, in dem ein SBC mit vielen Mandanten (Carrier-Szenario) verbunden ist, werden später in diesem Artikel behandelt.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Detaillierte Anforderungen für Kontakt Kopf-und Anforderungs-URI

#### <a name="contact-header"></a>Kontakt Kopfzeile

Für alle eingehenden Anrufe an den Microsoft SIP-Proxy muss der Kontakt Kopf den gepaarten SBC-FQDN im URI-Hostname wie folgt aufweisen:

Syntax: Contact: <SIP: Telefon-oder SIP-Address@FQDN des SBC; Transport = TLS> 

Dieser Name muss sich auch im Feld "allgemeiner Name" oder "alternativer Antragstellername" (n) des vorgestellten Zertifikats befinden. Microsoft unterstützt die Verwendung von Platzhalterwerten der Namen in den Feldern allgemeiner Name oder alternativer Antragstellername des Zertifikats.   

Die Unterstützung für Platzhalter wird in [RFC 2818, Abschnitt 3,1,](https://tools.ietf.org/html/rfc2818#section-3.1)beschrieben. Speziell

*"Namen können das Platzhalterzeichen \* enthalten, das als Übereinstimmung mit einer einzelnen domänennamenkomponente oder einem Komponenten Fragment angesehen wird. A.com entspricht Beispiels \*Weise foo.a.com, aber nicht Bar.foo.a.com. f\*. com entspricht foo.com, aber nicht Bar.com. "*

Wenn mehr als ein Wert in der in einer SIP-Nachricht vorgestellten Kontakt Kopfzeile vom SBC gesendet wird, wird nur der FQDN-Teil des ersten Werts des Contact-Headers verwendet.

#### <a name="request-uri"></a>Request-URI 

Für alle eingehenden Anrufe wird der Request-URI verwendet, um die Telefonnummer an einen Benutzer anzupassen.   

Derzeit muss die Telefonnummer ein Pluszeichen (+) enthalten, wie im folgenden Beispiel gezeigt. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Überlegungen zum Kontakt und Aufzeichnen von Routenkopfzeilen

Der SIP-Proxy muss den FQDN des nächsten Hop für neue in-Dialog-Clienttransaktionen berechnen (beispielsweise bye oder Re-invite) und bei der Beantwortung von SIP-Optionen. Es werden entweder Kontakt-oder Daten Satz Routen verwendet. 

Gemäß RFC 3261 ist in jeder Anforderung, die zu einem neuen Dialog führen kann, eine Kontakt Kopfzeile erforderlich. Die Daten Satz Route ist nur erforderlich, wenn ein Proxy den Pfad zukünftiger Anforderungen in einem Dialogfeld beibehalten möchte. 

Microsoft empfiehlt die Verwendung von "nur Kontakt Kopfzeile" aus den folgenden Gründen:

- Pro RFC 3261 wird Record-Route verwendet, wenn ein Proxy den Pfad zukünftiger Anforderungen in einem Dialogfeld beibehalten möchte, was nicht unbedingt erforderlich ist, da der gesamte Datenverkehr zwischen dem Microsoft SIP-Proxy und dem gekoppelten SBC abläuft. Zwischen dem SBC und dem Microsoft SIP-Proxy ist kein zwischen Proxy Server erforderlich.

- Der Microsoft SIP-Proxy verwendet nur Kontakt Kopfzeile (keine Daten Satz Route), um den nächsten Hop beim Senden von ausgehenden Ping-Optionen zu ermitteln. Wenn Sie nur einen Parameter (Kontakt) anstelle von zwei (Kontakt-und Daten Satz-Route) konfigurieren, wird die Verwaltung vereinfacht.

Zur Berechnung des nächsten Hop verwendet der SIP-Proxy Folgendes:

- Priorität 1 Record-Route auf oberster Ebene. Wenn die Daten Satz Route auf oberster Ebene den FQDN-Namen oder die IP-Adresse enthält, wird der FQDN-Name oder die IP-Adresse verwendet, um die ausgehende in-Dialog-Verbindung herzustellen.

- Priorität 2. Kontakt Kopfzeile. Wenn Record-Route nicht vorhanden ist, sucht der SIP-Proxy nach dem Wert der Kontakt Kopfzeile, um die ausgehende Verbindung herzustellen. (Dies ist die empfohlene Konfiguration.)

Wenn sowohl der Kontakt als auch die Daten Satz Route verwendet werden, muss der SBC-Administrator die Werte identisch halten, was zu administrativem Overhead führt. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Verwendung des FQDN-namens in Kontakt oder Daten Satz-Route

Die Verwendung einer IP-Adresse wird weder in der Daten Satz Route noch in einem Kontakt unterstützt. Die einzige unterstützte Option ist ein FQDN, der entweder dem allgemeinen Namen oder dem alternativen Subjektnamen des SBC-Zertifikats entsprechen muss (Platzhalterwerte im Zertifikat werden unterstützt).

- Wenn eine IP-Adresse in Record-Route oder Contact angezeigt wird, schlägt die Zertifikatüberprüfung fehl, und der Anruf schlägt fehl.

- Wenn der FQDN nicht dem Wert des allgemeinen oder Subjekt Alternativen namens im vorgestellten Zertifikat entspricht, schlägt der Aufruf fehl. 

## <a name="inbound-call-sip-dialog-description"></a>Eingehendes Gespräch: Beschreibung des SIP-Dialogs

In der folgenden Tabelle sind die Unterschiede bei den Anruf strömen und die Ähnlichkeiten zwischen nicht-Bypass-und Bypass-Modi zusammengefasst:

| Parameter Name | Nicht-Bypass-Modus | Bypass-Modus
| :---------------------  |:---------------------- |:----------------|
| Medien Kandidaten in 183-und 200-Nachrichten von | Medien Prozessoren | Clients | 
| Anzahl von 183-Nachrichten, die SBC empfangen kann | Eine pro Sitzung | Mehrere | 
| Anruf kann mit provisorischer Antwort erfolgen (183) | Ja | Ja |
| Der Anruf kann ohne provisorische Antwort erfolgen (183) | Ja | Ja |

###  <a name="non-media-bypass-flow"></a>Nicht-Medien-Bypass-Flow

Ein Team Benutzer hat möglicherweise mehrere Endpunkte zur gleichen Zeit. Beispiel: Teams für Windows-Client, Teams für iPhone-Client und Teams (Android-Client). Jeder Endpunkt kann einen HTTP-Ruhezustand wie folgt signalisieren:

-   Anruf Fortschritt – wird vom SIP-Proxy in die SIP-Nachricht 180 konvertiert. Beim Empfangen von Nachrichten 180 muss der SBC lokales Klingeln generieren.

-   Medien Antwort – wird vom SIP-Proxy in Nachricht 183 mit Medien Kandidaten in Session Description Protocol (SDP) konvertiert. Beim Empfangen von Nachrichten 183 erwartet der SBC, dass eine Verbindung mit den in der SDP-Nachricht empfangenen Medien Kandidaten hergestellt wird. Beachten Sie, dass die Medien Antwort in einigen Fällen möglicherweise nicht generiert wird und der Endpunkt mit der Nachricht "Anruf angenommen" beantwortet werden kann.

-   Anruf angenommen – wird vom SIP-Proxy in SIP-Nachricht 200 mit SDP konvertiert. Beim Empfangen von Nachrichten 200 wird von SBC erwartet, dass Sie Medien an und von den bereitgestellten SDP-Kandidaten senden und empfangen.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Mehrere Endpunkte läuten mit provisorischer Antwort

1.  Beim Empfang der ersten Einladung vom SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 trying" und benachrichtigt alle Endbenutzer-Endpunkte über den eingehenden Anruf. 

2.  Nach der Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und dem Senden von "Anruf Fortschritt"-Nachrichten an den SIP-Proxy. Da ein Teams-Benutzer mehrere Endpunkte haben kann, erhält der SIP-Proxy möglicherweise mehrere Statusmeldungen für den Anruf.

3.  Für jede Nachricht, die der Anruf Fortschritt von den Clients erhält, wandelt der SIP-Proxy die Meldung "Anruf Fortschritt" in die SIP-Nachricht "SIP SIP/2.0 180 trying" um. Das Intervall für das Senden solcher Nachrichten wird durch das Intervall der empfangenden Nachrichten vom Anruf Controller definiert. Im folgenden Diagramm sind 2 180-Nachrichten vom SIP-Proxy generiert. Diese Nachrichten stammen von den beiden Endpunkten der Teams des Benutzers. Die Clients verfügen jeweils über eine eindeutige Transponder-ID.  Jede Nachricht, die von einem anderen Endpunkt stammt, ist eine separate Sitzung (der Parameter "Tag" im Feld "an" ist anders). Ein Endpunkt generiert aber möglicherweise keine Nachricht 180 und sendet Sofortnachricht 183, wie in der nachstehenden Abbildung gezeigt.

4.  Nachdem ein Endpunkt eine Medien Antwortnachricht mit den IP-Adressen der Medien Kandidaten des Endpunkts generiert hat, wandelt der SIP-Proxy die empfangene Nachricht in die Meldung "SIP 183-Sitzungs Fortschritt" um, wobei die SDP vom Client durch die SDP vom medienprozessor ersetzt wurde. Im folgenden Diagramm hat der Endpunkt von Fork 2 den Anruf beantwortet. Wenn der trunk nicht umgangen wird, wird die 183-SIP-Nachricht nur einmal generiert (entweder Ring-bot oder Client-Endpunkt). Die 183 kann auf eine vorhandene Verzweigung oder auf eine neue Gabel fallen.

5.  Eine Anrufannahme Nachricht wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Anrufannahme Nachricht wird in SIP-Nachricht 200 konvertiert. 

![Diagramm, das zeigt, dass mehrere Endpunkte mit provisorischer Antwort Klingeln](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Mehrere Endpunkte Klingeln ohne provisorische Antwort

1.  Beim Empfang der ersten Einladung vom SBC sendet der SIP-Proxy die Nachricht "SIP SIP/2.0 100 trying" und benachrichtigt alle Endbenutzer-Endpunkte über den eingehenden Anruf. 

2.  Nach der Benachrichtigung beginnt jeder Endpunkt mit dem Klingeln und dem Senden der Nachricht "Anruf Fortschritt" an den SIP-Proxy. Da ein Teams-Benutzer mehrere Endpunkte haben kann, erhält der SIP-Proxy möglicherweise mehrere Statusmeldungen für den Anruf.

3.  Für jede Nachricht, die der Anruf Fortschritt von den Clients erhält, wandelt der SIP-Proxy die Meldung "Anruf Fortschritt" in die SIP-Nachricht "SIP SIP/2.0 180 trying" um.  Das Intervall für das Senden der Nachrichten wird durch das Intervall definiert, in dem die Nachrichten vom Anruf Controller empfangen werden. Auf dem Bild unten sind 2 180 vom SIP-Proxy generierte Nachrichten, was bedeutet, dass der Benutzer sich bei drei Teams-Clients angemeldet hat und jeder Client den Anruf Fortschritt sendet. Jede Nachricht wird eine separate Sitzung sein (der Parameter "Tag" im Feld "an" ist anders)

4.  Eine Anrufannahme Nachricht wird mit den endgültigen Kandidaten des Endpunkts gesendet, der den Anruf angenommen hat. Die Anrufannahme Nachricht wird in SIP-Nachricht 200 konvertiert. 

![Diagramm mit mehreren Endpunkten, die ohne provisorische Antwort Klingeln](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Medien Umgehungs Fluss

Die gleichen Nachrichten (100 versuchen, 180, 183) werden im Szenario "medienumgehung" verwendet. 

Das folgende Schema zeigt ein Beispiel für den Bypass-Anruffluss. Beachten Sie, dass die Medien Kandidaten von unterschiedlichen Endpunkten stammen können. 

![Diagramm, das zeigt, dass mehrere Endpunkte mit provisorischer Antwort Klingeln](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Option ersetzt

Der SBC muss invite mit ersetzt unterstützen.

## <a name="size-of-sdp-considerations"></a>Größe von SDP-Überlegungen

Die direkte Routing Schnittstelle kann eine SIP-Nachricht senden, die 1.500 Bytes überschreitet.  Die Größe von SDP führt in erster Linie dazu. Wenn jedoch ein UDP-Stamm hinter dem SBC vorhanden ist, wird die Nachricht möglicherweise zurückgewiesen, wenn Sie vom Microsoft SIP-Proxy an den Stamm unverändert weitergeleitet wird. Microsoft empfiehlt, beim Senden der Nachricht an die UDP-Stämme einige Werte in SDP auf dem SBC zu entfernen. Beispielsweise können die Ice-Kandidaten oder nicht verwendete Codecs entfernt werden.

## <a name="call-transfer"></a>Anrufübertragung

Direct Routing unterstützt zwei Methoden für die Anrufweiterleitung:

- Option 1. SIP-Proxy Prozesse verweisen vom Client lokal und fungieren als Schiedsrichter, wie in Abschnitt 7,1 von RFC 3892 beschrieben.

  Mit dieser Option beendet der SIP-Proxy die Übertragung und fügt eine neue Einladung hinzu. 


- Option 2. Der SIP-Proxy sendet den Verweis an den SBC und fungiert als Übertragung, wie er in Abschnitt 6 von RFC 5589 beschrieben wird.

  Mit dieser Option sendet der SIP-Proxy einen Verweis auf den SBC und erwartet, dass der SBC die Übertragung vollständig übernimmt.

Der SIP-Proxy wählt die Methode basierend auf den vom SBC gemeldeten Funktionen aus. Wenn der SBC angibt, dass die Methode "Refer" unterstützt wird, verwendet der SIP-Proxy Option 2 für Anruf Übertragungen.

Der folgende Code ist ein Beispiel für einen SBC, der die Nachricht sendet, dass die Refer-Methode unterstützt wird:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Wenn der SBC nicht angibt, dass es sich um eine unterstützte Methode handelt, verwendet das direkte Routing die Option 1 (SIP-Proxy fungiert als Schiedsrichter). Der SBC muss auch signalisieren, dass er die Notify-Methode unterstützt:

Beispiel für SBC, der angibt, dass die Refer-Methode nicht unterstützt wird:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP-Proxy Prozesse verweisen vom Client lokal und fungieren als Schiedsrichter

Wenn der SBC angegeben hat, dass die Refer-Methode nicht unterstützt wird, fungiert der SIP-Proxy als Schiedsrichter. 

Die Refer-Anfrage, die vom Client stammt, wird auf dem SIP-Proxy beendet. (Die Refer-Anfrage des Clients wird im folgenden Diagramm als "Anrufübertragung an Dave" angezeigt.  Weitere Informationen finden Sie in Abschnitt 7,1 von [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

![Diagramm, das zeigt, dass mehrere Endpunkte mit provisorischer Antwort Klingeln](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP-Proxy senden Sie den Verweis an den SBC und fungiert als übertragender.

Dies ist die bevorzugte Methode für Anruf Übertragungen und für Geräte, die eine Medien Umgehungs Zertifizierung suchen, obligatorisch. Die Anrufübertragung, ohne dass der SBC-Verweis verarbeitet werden kann, wird im Medien Umgehungsmodus nicht unterstützt. 

Der Standard wird in Abschnitt 6 von RFC 5589 erläutert. Die zugehörigen RFCs sind:

- [SIP-Anrufsteuerung (Session Initiation Protocol) – Übertragung](https://tools.ietf.org/html/rfc5589)

- [SIP-Header (Session Initiation Protocol) "ersetzt"](https://tools.ietf.org/html/rfc3891)

- [SIP-Mechanismus (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3892)

Bei dieser Option wird davon ausgegangen, dass der SIP-Proxy als Übertragung fungiert und eine Refer-Meldung an den SBC sendet. Der SBC fungiert als übertragender und behandelt das Verweis auf ein neues Angebot für die Übertragung zu generieren. Es gibt zwei mögliche Fälle:

- Der Anruf wird an einen externen PSTN-Teilnehmer übertragen. 
- Der Anruf wird von einem Teams-Benutzer an einen anderen Teams-Benutzer im gleichen Mandanten über den SBC übertragen. 

Wenn der Anruf über den SBC von einem Teams-Benutzer zu einem anderen übertragen wird, wird erwartet, dass der SBC eine neue Einladung (ein neues Dialogfeld) für das Übergabeziel (den Teams-Benutzer) mit den in der Refer-Nachricht erhaltenen Informationen ausgibt. 

Um die Felder an/übertragen für die Transaktion der Anforderung intern zu füllen, muss der SIP-Proxy diese Informationen innerhalb der Verweis-zu/Verweis-Überschriften übermitteln. 

Der SIP-Proxy stellt den Verweis als SIP-URI dar, der aus einem SIP-Proxy-FQDN im Hostname und einer der folgenden besteht:

- Eine E. 164-Telefonnummer im username-Teil des URIs, falls es sich bei dem Übertragungsziel um eine Telefonnummer handelt, oder

- x-m-und x-t-Parameter, die das vollständige Übertragungsziel-MRI und die Mandanten-ID codieren 

Der verweisende Header ist ein SIP-URI, in dem das in ihm codierte MRI-MRT sowie die Mandanten-ID des Verweisers und andere Parameter des Übertragungs Kontexts, wie in der folgenden Tabelle dargestellt, aufgeführt sind:

| Parameter | Wert | Beschreibung |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | Vollständiges MRI des übertragenden/übertragenden Ziels als von CC ausgefüllt |
| x-t | Mandanten-ID | x-t-Mandanten-ID optionale Mandanten-ID, wie von CC ausgefüllt |
| x-TI | Übertragungs Korrelations-ID | Korrelations-ID des Anrufs an den übertragenden |
| x-TT | Übertragen des Ziel Anruf-URIs | Codierter Anruf Ersetzungs-URI |

In diesem Fall kann die Größe des Refer-Headers bis zu 400-Symbole sein. Der SBC muss die Behandlung von Refer-Nachrichten mit einer Größe von bis zu 400-Symbolen unterstützen.

![Diagramm, das zeigt, dass mehrere Endpunkte mit provisorischer Antwort Klingeln](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Sitzungszeitgeber

Der SIP-Proxy unterstützt (immer) den Session-Timer bei nicht-Bypass-anrufen, bietet ihn aber nicht bei Bypass-Anrufen an. Die Verwendung des Session-Timers durch den SBC ist nicht zwingend erforderlich.

##  <a name="use-of-request-uri-parameter-userphone"></a>Verwendung des Request-URI-Parameters User = Phone

Der SIP-Proxy analysiert den Anforderungs-URI, und wenn der Parameter User = Phone vorhanden ist, behandelt der Dienst den Anforderungs-URI als eine Telefonnummer, die der Nummer eines Benutzers entspricht. Wenn Parameter nicht vorhanden ist, wendet der SIP-Proxy Heuristiken an, um den Benutzertyp Request-URI (Telefonnummer oder SIP-Adresse) zu ermitteln.

Microsof empfiehlt immer die Anwendung des User = Phone-Parameters, um den Anruf-Setupvorgang zu vereinfachen.

## <a name="history-info-header"></a>Verlaufsinformationen-Kopfzeile

Der Header "History-Info" wird für die Neuausrichtung von SIP-Anforderungen und "bereitstellen (s) eines Standardmechanismus zum Erfassen der Informationen zum Anforderungsverlauf verwendet, um eine Vielzahl von Diensten für Netzwerke und Endbenutzer zu ermöglichen." Weitere Informationen finden Sie in [RFC 4244 – Abschnitt 1,1](http://www.ietf.org/rfc/rfc4244.txt). Für Microsoft Phone System wird dieser Header in Simulring-und Anruf Weiterleitungs Szenarien verwendet.  

Beim Senden werden die Verlaufsinformationen wie folgt aktiviert:

- Der SIP-Proxy fügt einen Parameter mit der zugehörigen Rufnummer in einzelne Verlaufs-Info-Einträge ein, die den an den PSTN-Controller gesendeten History-Info-Header enthalten.  Wenn nur Einträge mit dem Parameter "Telefonnummer" verwendet werden, wird vom PSTN-Controller eine neue Verlaufsinformationen-Kopfzeile neu erstellt und über den SIP-Proxy an den SIP-Trunk-Anbieter weitergeleitet.

- History-Info-Kopfzeile wird für simultane Klingel-und Anruf Weiterleitungs Fälle hinzugefügt.

- Die Kopfzeile der Verlaufsinformationen wird nicht für Anruf Übertragungs Fälle hinzugefügt.

- Bei einem individuellen Verlaufseintrag im rekonstruierten Verlaufs-Info-Header wird der Parameter für die Telefonnummer in Kombination mit dem Direct Routing-FQDN (SIP.pstnhub.Microsoft.com), der als Host-Teil des URIs festgelegt ist, bereitgestellt. ein Parameter von "User = Phone" wird als Teil des SIP-URIs hinzugefügt.  Alle anderen Parameter, die mit dem ursprünglichen History-Info-Header verknüpft sind, mit Ausnahme von Telefonkontext Parametern, werden im neu konstruierten History-Info-Header durchlaufen.  Beachten Sie, dass private Einträge (entsprechend den in Abschnitt 3,3 von RFC 4244 definierten Mechanismen) weitergeleitet werden, weil der SIP Trunk-Anbieter ein vertrauenswürdiger Peer ist.

- Eingehende Verlaufsinformationen werden ignoriert.

Im folgenden wird das Format der vom SIP-Proxy gesendeten History-Info-Kopfzeile angezeigt:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Wenn der Anruf mehrmals umgeleitet wurde, sind Informationen zu jeder Umleitung in chronologischer Reihenfolge in den entsprechenden Grund eingeschlossen.


Header Beispiel:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Die Verlaufsinformationen sind durch einen obligatorischen TLS-Mechanismus geschützt. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC-Verbindung mit Direct Routing und Failover-Mechanismus

Lesen Sie den Abschnitt Failover-Mechanismus für SIP-Signalisierungen in [Plan für das direkte Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Wiederholen-nachher

Wenn ein direktes Routing-Rechenzentrum ausgelastet ist, kann der Dienst eine Retry-after-Nachricht mit einem Sekunden Intervall an den SBC senden. Wenn der SBC eine 503-Nachricht mit einem Retry-after-Header als Antwort auf eine Einladung erhält, muss der SBC diese Verbindung kündigen und das nächste verfügbare Microsoft Datacenter testen. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Ice-Neustart: Medien Umgehungs Anruf wird an einen Endpunkt übertragen, der keine medienumgehung unterstützt

Der SBC muss Ice-Neustarts unterstützen, wie in [RFC 5245, Abschnitt 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)beschrieben.

Der Neustart beim direkten Routing wird gemäß den folgenden Absätzen der RFC implementiert:

*Um Ice neu zu starten, muss ein Agent sowohl das Ice-pwd als auch das Ice-ufrag für den Mediendatenstrom in einem Angebot ändern.  Beachten Sie, dass es zulässig ist, in einem Angebot ein Attribut auf Sitzungsebene zu verwenden, aber das gleiche Ice-pwd-oder Ice-ufrag-Attribut in einem nachfolgenden Angebot als Attribut auf Medienebene bereitzustellen.  Hierbei handelt es sich nicht um eine Änderung des Kennworts, sondern nur um eine Änderung der Darstellung, und es wird kein Ice-Neustart verursacht.*

*Ein Agent legt die restlichen Felder im SDP für diesen Mediendatenstrom so fest, wie dies bei einem anfänglichen Angebot dieses Mediendatenstroms der Fall wäre (siehe Abschnitt 4,3).  Infolgedessen kann die Gruppe von Kandidaten einige, keine oder alle vorherigen Kandidaten für diesen Datenstrom enthalten und eine völlig neue Gruppe von Kandidaten enthalten, wie in Abschnitt 4.1.1 beschrieben.*

Wenn der Anruf zunächst mit Media Bypass eingerichtet wurde und der Anruf an einen Skype for Business-Client übertragen wird, muss das direkte Routing einen medienprozessor einfügen – Dies liegt daran, dass die direkte Weiterleitung nicht mit einem Skype for Business-Client mit medienumgehung verwendet werden kann. Das direkte Routing startet den ICE-Neustart Prozess, indem die Ice-pwd-und Ice-ufrag geändert und neue Medien Kandidaten in einer erneuten Einladung angeboten werden. 


