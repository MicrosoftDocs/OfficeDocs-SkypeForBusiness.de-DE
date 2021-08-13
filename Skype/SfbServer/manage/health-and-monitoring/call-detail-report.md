---
title: Anrufdetailbericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Zusammenfassung: Erfahren Sie mehr über den Anrufdetailbericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: 42a0dd40bb32005fcae49464f5ebfc6570055f7078c22b6a8b5be6004793158b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336585"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Anrufdetailbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Anrufdetailbericht, der in Skype for Business Server verwendet wird.
  
Der Anrufdetailbericht bietet einen detaillierten Überblick über einen einzelnen Anruf. Der Bericht enthält fast alle QoE-Metriken und Statistiken, die von Skype for Business Server gesammelt wurden, unterteilt in Berichtsabschnitte, z. B.:
  
- Anrufinformationen 
    
- Gerät und Signalmetrik des Anrufers
    
- Gerät und Signalmetrik des Angerufenen
    
- Clientereignis des Anrufers
    
- Clientereignis des Angerufenen
    
- Audiodatenstrom (Anrufer zum Angerufenen)
    
- Videodatenstrom (Anrufer zum Angerufenen)
    
- Audiodatenstrom (Angerufener zum Anrufer)
    
- Videodatenstrom (Angerufener zum Anrufer)
    
Beachten Sie, dass die Kategorien und Metriken in einem bestimmten Bericht zum einen vom Typ der Sitzung und zum anderen vom Typ der Endpunkte abhängen, die in der Sitzung verwendet werden. Bei einem reinen Audioanruf werden keine Metriken für Videodatenströme gemeldet, da der Anruf keinen Videodatenstrom beinhaltete. Entsprechend werden in einem Bericht ggf. zwar Anruferstatistiken, aber keine Statistiken zum Angerufen angezeigt. Dies liegt normalerweise daran, dass der Angerufene kein SIP-kompatibles Gerät verwendet. Endpunkte sind für das Melden von Statistiken am Ende des Anrufs verantwortlich. Ein Mobiltelefon (das SIP oder SIP-Statistiken nicht unterstützt) kann diese Informationen jedoch nicht melden. Wenn Sie jemanden anrufen und diese Person den Anruf auf einem Mobiltelefon entgegennimmt, erhalten Sie keinen Bericht von diesem Mobiltelefon, wenn der Anruf beendet wird.
  
Der Anrufdetailbericht ist sehr nützlich, wenn Sie genau feststellen möchten, warum bei einem bestimmten Anruf Probleme in Bezug auf die Medienqualität aufgetreten sind.
  
## <a name="accessing-the-call-detail-report"></a>Zugreifen auf den Anrufdetailbericht

Auf den Anrufdetailbericht kann von einem der folgenden Berichte aus zugegriffen werden:
  
- Der [Standortbericht in Skype for Business Server (location-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz der Anrufe schlechter Qualität")
    
- Der [Zusammenfassende Bericht über Medienqualität in Skype for Business Server (summary.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz der Anrufe schlechter Qualität")
    
- Der [Vergleichsbericht über Medienqualität in Skype for Business Server](comparison.md) (durch Klicken auf den [Anruflistenbericht in Skype for Business Server](call-list-report-0.md) und dann auf die Metrik "Detail").
    
- Der [Serverleistungsbericht in Skype for Business Server](server-performance.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz der Anrufe schlechter Qualität")
    
- Der [Anruflistenbericht in Skype for Business Server](call-list-report-0.md) (durch Klicken auf die Metrik "Detail")
    
Im Anrufdetailbericht können Sie auf den [Gerätebericht in Skype for Business Server](device-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:
  
- Aufnahmegerät
    
- Darstellungsgerät
    
Sie können auch auf den Trendbericht über Medienqualität des Servers zugreifen, indem Sie auf die Metrik A/V-Edgeserver klicken.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Optimale Verwendung des Anrufdetailberichts

Der Anrufdetailbericht umfasst normalerweise 250 verschiedene Metriken. Hierzu gehören Zeitstempelabweichung des Mikrofons, Geringer Rauschabstand, Zeit und Nahes Ende zu Echo, Zeit. Wenn Sie nicht genau wissen, was mit diesen Metriken gemessen wird, können Sie mit der Maus auf die Bezeichnung der Metrik zeigen. In den meisten Fällen erscheint dann eine QuickInfo mit einer Metrikbeschreibung.
  
Wenn Sie Probleme beim Suchen einer Metrik haben, geben Sie einen Teil der Metrikbezeichnung in das Suchfeld ein, und klicken Sie dann auf **"Suchen".** Wenn Sie z. B. die Metrik "Low SNR time" nicht finden können, geben Sie "SNR" in das Suchfeld ein, und klicken Sie dann auf **"Suchen".**
  
Beachten Sie, dass der Bericht nur Informationen zu einem Anruf nachzeichnet. Der Anruf selbst wird nicht aufgezeichnet.
  
## <a name="filters"></a>Filter

Keine. Der Anrufdetailbericht lässt sich nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Anrufdetailbericht für jeden Anruf angegeben werden.
  
**Metriken im Anrufdetailbericht**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**PAI des Anrufers** <br/> |Nein  <br/> |Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der den Anruf initiiert hat. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.  <br/> |
|**URI des Anrufers** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.  <br/> |
|**Endpunkt des Anrufers** <br/> |Nein  <br/> |Das Gerät, mit dem der Anruf ausgeführt wurde.  <br/> |
|**Benutzer-Agent des Anrufers** <br/> |Nein  <br/> |Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf ausgeführt wurde.  <br/> |
|**Startzeit des Anrufs** <br/> |Nein  <br/> |Der Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf ursprünglich getätigt wurde.  <br/> |
|**Vermittlungsserver-Umgehungsanruf** <br/> |Nein  <br/> |Gibt an, ob der Anruf mit einem PSTN-VoIP-Gateway oder einer qualifizierten IP-Nebenstellenanlage verbunden wurde, ohne dass er über den Vermittlungsserver geleitet wurde.  <br/> |
|**Betriebssystem des Anrufers** <br/> |Nein  <br/> |Das Betriebssystem auf dem Computer des Anrufers.  <br/> |
|**CPU des Anrufers** <br/> |Nein  <br/> |Die CPU, die im Computer des Benutzers installiert ist, der den Anruf initiiert hat.  <br/> |
|**Nummer des CPU-Kerns des Anrufers** <br/> |Nein  <br/> |Die Nummer des Prozessors in dem Computer des Benutzers, der den Anruf initiiert hat.  <br/> |
|**CPU-Geschwindigkeit des Anrufers** <br/> |Nein  <br/> |Die Taktfrequenz der CPU des Computers des Benutzers, der den Anruf initiiert hat.  <br/> |
|**Virtualisierung der CPU des Anrufers** <br/> |Nein  <br/> |Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der den Anruf initiiert hat.  <br/> |
|**PAI des Angerufenen** <br/> |Nein  <br/> |Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der zur Teilnahme an dem Anruf eingeladen wurde. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.  <br/> |
|**URI des Angerufenen** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der angerufen wurde.  <br/> |
|**Endpunkt des Angerufenen** <br/> |Nein  <br/> |Das Gerät, mit dem der Anruf angenommen wurde.  <br/> |
|**Benutzer-Agent des Angerufenen** <br/> |Nein  <br/> |Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf angenommen wurde.  <br/> |
|**Duration** <br/> |Nein  <br/> |Die Dauer des Anrufs.  <br/> |
|**Vermittlungsserver-Warnungskennzeichen** <br/> |Nein  <br/> |Eine Warnung, die ausgegeben wird, wenn der Vermittlungsserver umgangen wurde.  <br/> |
|**Betriebssystem des Angerufenen** <br/> |Nein  <br/> |Das Betriebssystem auf dem Computer des Benutzers, der angerufen wurde.  <br/> |
|**CPU des Angerufenen** <br/> |Nein  <br/> |Die CPU, die im Computer des Benutzers installiert ist, der angerufen wurde.  <br/> |
|**Nummer des CPU-Kerns des Angerufenen** <br/> |Nein  <br/> |Die Nummer des Prozessors in dem Computer des Benutzers, der angerufen wurde.  <br/> |
|**CPU-Geschwindigkeit des Angerufenen** <br/> |Nein  <br/> |Die Taktfrequenz der CPU des Computers des Benutzers, der angerufen wurde.  <br/> |
|**Virtualisierung der CPU des Angerufenen** <br/> |Nein  <br/> |Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der angerufen wurde.  <br/> |
   

