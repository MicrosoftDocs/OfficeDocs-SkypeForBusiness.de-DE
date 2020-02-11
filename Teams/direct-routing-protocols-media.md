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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888574"
---
# <a name="overview"></a>Übersicht

In diesem Artikel wird beschrieben, wie das direkte Routing die medienumgehung mit einem für Ice lite aktivierten Session Border Controller (SBC) unterstützt, wie in [RFC 5245](https://tools.ietf.org/html/rfc5245)beschrieben. Dieser Artikel richtet sich an sprach Administratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst verantwortlich sind.

Dieser Artikel enthält eine Übersicht über die Ice lite-Szenarien und die Anforderungen für die Interoperabilität. In diesem Artikel werden die Nachrichtenformate und die erforderlichen Zustandsautomaten Übergänge beschrieben, um eine zuverlässige Anruf-und Medien Übermittlung zu gewährleisten.

## <a name="terminology"></a>Terminologie

- Erster Gruß – die ersten Worte, die vom Anrufer und angerufenen gesprochen werden. Es ist wichtig, dass alle Anstrengungen unternommen werden, um sicherzustellen, dass die ersten Pakete von den Endpunkten für die meisten Anwendungsfälle zuverlässig bereitgestellt werden.

- Forking – das Angebot des Anrufers wird möglicherweise an mehrere Endpunkte übermittelt, wenn der aufgerufene auf mehreren Geräten zur Verfügung steht (beispielsweise kann ein Team Benutzer in Teams für Windows und Teams für Android oder iPhone angemeldet sein).

- Provisorische Antwort (183) – die Endpunkte für Anrufer für eine schnellere Anrufeinrichtung senden Sie eine Antwort mit den Kandidaten und Schlüsseln, die zum Einrichten des Medienflusses erforderlich sind. Dies erfolgt in Erwartung des Benutzers, der den Anruf (200OK) möglicherweise von dieser bestimmten aufgerufenen Instanz aus beantwortet. Mit Forking sollte der Anrufer bereit sein, mehrere provisorische Antworten zu erhalten.

- Re-invite – Angebot mit endgültigen Kandidaten, die vom ICE-Controlling-Endpunkt ausgewählt wurden. Dies hat das a = Remote-Candidate-Attribut, um alle Racebedingungen von der Behandlung mehrerer Gabeln zu lösen.

- Teams-Endpunkt – Dies kann entweder ein Server (medienprozessor, Transport Relay) oder der Client für Teams sein.

## <a name="message-format"></a>Nachrichtenformat

Die Teams-Infrastruktur folgt RFC 5245 für Ice-lite. Dies impliziert, dass alle Stun-Nachrichten mit [RFC 5389](https://tools.ietf.org/html/rfc5389)kompatibel sind.

Das SBCS, wie es in RFC 5389 erforderlich ist, muss alle Betäubungs Attribute ignorieren, die Sie nicht erkennen, und die Nachrichten mit den bekannten Attributen weiterverarbeiten. 

Wenn fehlerhafte Pakete empfangen werden, müssen die Pakete verworfen werden, ohne dass dies Auswirkungen auf die Einrichtung der Mediensitzung hat.

## <a name="ice-lite-requirements"></a>Ice lite-Anforderungen

In diesem Abschnitt werden die Anforderungen für Ice lite kurz erfasst.

### <a name="candidate-gathering"></a>Kandidaten Sammlung

Der SBC muss nur einen Kandidaten anbieten, der öffentlich erreichbar ist. Derzeit werden nur IPv4-Kandidaten unterstützt.


#### <a name="connectivity-checks"></a>Verbindungs Überprüfungen

Die Ice lite-Implementierung muss auf alle empfangenen Verbindungs Überprüfungen Antworten. Der Ice lite-Endpunkt darf keine Verbindungs Prüfanforderungen senden. (Wenn Verbindungs Überprüfungen verstoßen werden, wird die vollständige Implementierung beantwortet, was dazu führen kann, dass unerwartete Peer-abgeleitete Kandidaten erkannt werden und möglicherweise zu Anruf Fehlern führen.)

#### <a name="nominations"></a>Nominierungen

Der vollständige Implementierungs Endpunkt für ICE ist immer der steuernde Endpunkt und folgt "normalen" Nominierungen für die Auswahl der endgültigen Kandidaten, die für den Medienfluss verwendet werden sollen. Der Ice lite-Endpunkt kann die Nominierungen verwenden, um den für Medien und die komplette Anrufeinrichtung zu verwendenden Pfad abzuschließen.

Hinweis: bei der Verzweigung mit Peer Endpunkten, die 183 provisorische Antworten senden, muss der SBC bereit sein, auf Prüfungen von mehreren Endpunkten und auch Nominierungen von mehreren Endpunkten zu reagieren, wenn die Nominierungen vor 200OK erfolgen. Je nach Konvergenz des ICE State Machine auf dem endgültigen Pfad und dem Zeitpunkt der Antwort des Benutzers können die Nominierungen vor oder nach dem 200OK erfolgen. Der SBC muss in der Lage sein, beide Fälle zu verarbeiten.

#### <a name="converging-for-forking"></a>Konvergierende für Verzweigung

Wenn das Angebot des SBC an mehrere Endpunkte für Teams abzweigt, können die Endpunkte der Teams mit einer provisorischen Antwort Antworten und Verbindungs Prüfungen starten. Der SBC muss bereit sein, Verbindungs Überprüfungen zu empfangen und auf Verbindungs Überprüfungen von mehreren Peer Endpunkten zu reagieren. So kann beispielsweise der Benutzer von Teams sowohl auf einem Desktop-Computer als auch auf einem Mobiltelefon angemeldet sein. Beide Geräte werden über den eingehenden Anruf benachrichtigt und versuchen, Verbindungs Prüfungen mit dem SBC durchführen zu lassen.

Schließlich wird nur einer der Endpunkte den Anruf annehmen (200OK). Beim Empfang des 200OK kann der SBC den richtigen Kontext für die Verarbeitung der Medienpakete einrichten.

## <a name="scenarios"></a>Szenarien

###  <a name="inbound-call-from-sbc"></a>Eingehender Anruf von SBC

Für dieses Szenario gibt es mehrere mögliche Peer Endpunkte, die vom SBC behandelt werden müssen:

- Server Endpunkte werden in der Regel direkt mit 200OK beantwortet. Hierbei handelt es sich um vollständige Ice-Endpunkte, die normalerweise in Szenarien für Voicemail, Anrufwarteschlange und automatische Telefonzentrale involviert sind.

- Client Endpunkte können mehrere provisorische Antworten mit unterschiedlichen from/to-Tags (183) senden, gefolgt von einem 200OK vom Endpunkt, der den Anruf annimmt. Hierbei handelt es sich um vollständige Ice-Endpunkte, die Endbenutzer Clients darstellen.

- Andere SBC-Endpunkte. Hierbei handelt es sich um Ice lite-Endpunkte, die normalerweise in das Szenario der gleichzeitigen Klingeln von Clientendpunkten und anderen Telefonnummern involviert sind.

Der SBC muss auf alle gültigen Verbindungs Prüfungsanforderungen Antworten, die von den vollständigen Ice-Endpunkten empfangen werden. Pro RFC werden die vollständigen Ice-Endpunkte zu steuernden Endpunkten. Die Endpunkte der Teams (Client/Server) führen "reguläre" Nominierungen aus, um Verbindungs Prüfungen abzuschließen. Die endgültige 200Ok kann entweder von einem Endpunkt sein, der ein früheres Medium gesendet hat, oder von einem anderen Endpunkt. Beim Empfang des 200Ok muss der SBC den richtigen Kontext für den Medienfluss einrichten. 

###  <a name="early-media"></a>Frühe Medien

Wenn ein früher Medienfluss vorliegt, muss sich der SBC an den ersten Endpunkt verriegeln, der Streaming-Medien startet. der Medienfluss kann beginnen, bevor Kandidaten nominiert werden. Der SBC sollte in dieser Phase Unterstützung für das Senden von DTMF haben, um IVR/Voicemail-Szenarien zu ermöglichen. Der SBC sollte den Pfad mit der höchsten Priorität verwenden, auf dem er überprüft hat, ob die Nominierungen nicht abgeschlossen wurden.

### <a name="outbound-call-to-sbc"></a>Outbound-Anruf an SBC

Die Endpunkte der Teams sind der Aufrufer für dieses Szenario und der steuernde Endpunkt. Beim Empfang einer provisorischen Antwort (183) oder einer endgültigen Antwort (200OK) startet der Team-Endpunkt Verbindungs Prüfungen und führt zu "normalen" Nominierungen, um die Verbindungs Prüfungen abzuschließen.

Hinweis: Wenn der SBC eine provisorische Antwort (183) sendet, muss der SBC bereit sein, Verbindungs Prüfanforderungen zu empfangen und die Nominierungen möglicherweise abzuschließen, bevor der 200OK vom SBC gesendet wird. Wenn Schecks und/oder Nominierungen abgeschlossen werden, bevor die 200OK eingehen, werden die Überprüfungen und/oder Nominierungen nach Eingang von 200OK nicht mehr durchgeführt. Der SBC darf die Ice-Kandidaten, das Kennwort und den ufrag (username-Fragment) nicht zwischen 183 und 200 ändern.

Um frühe Medien zu unterstützen, kann der SBC mit dem Streaming der Medien an den Peer Ice-Kandidaten beginnen, wobei die höchste Priorität auf der Grundlage empfangener Verbindungs Überprüfungen liegt, noch bevor die Nominierungen vom Teams-Endpunkt abgeschlossen werden. Der SBC sollte erwarten, dass Medien aus Teams an einem beliebigen Kandidaten, bis die Nominierungen abgeschlossen sind. Sobald ein Kandidat nominiert wurde, muss der SBC auf den richtigen Kontext zurückgesetzt werden, um Medienpakete zu senden und zu empfangen.

## <a name="srtp-support-requirements"></a>Anforderungen für die SRTP-Unterstützung

Der SBC muss die SRTP-Verschlüsselungs Verschlüsselungs AES_CM_128_HMAC_SHA1_80 für Angebot und Antwort im folgenden Format unterstützen:

```console
"inline:" <key||salt> ["|" lifetime]
```

Der folgende Code ist ein Beispiel für das Crypto-Attribut im SDP-Angebot aus dem SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Die Parameter MkII und length sind nicht erforderlich.

Weitere Informationen finden Sie in [RFC 4568, Abschnitt 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>SDES-Supportanforderungen

Das Gerät muss SDES in dem Format anbieten können, wie nachstehend beschrieben. Microsoft Media Processors bevorzugen immer SDES.

- Auch wenn ein Client nur DTLS unterstützt, werden die Medien Prozessoren in SDES konvertiert, wenn keine medienumgehung erfolgt.

- Wenn ein Client nur DTLS (zukünftiger Google Chrome-Status) ist, wird mit der medienumgehung ein MP-Element in den Pfad eingefügt, und der Anruf wird von der medienumgehung in die nicht-medienumgehung konvertiert. Zwischen der SBC-und der medienprozessor Komponente des direkten Routings wird immer SDES verwendet.

Derzeit gibt es keinen Team-Client, der nur DTLS bietet; Google hat jedoch angekündigt, dass Sie zu einem bestimmten Zeitpunkt die Unterstützung von SDES beenden werden.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format für das Angebot von SBC im Bypass-Modus 

Das Angebot muss SDES enthalten und kann DTLS optional im folgenden Format enthalten:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Format für Antwort mit SDES in SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Format für Angebot von Teams in SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format für SDES-Angebot nur für SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

