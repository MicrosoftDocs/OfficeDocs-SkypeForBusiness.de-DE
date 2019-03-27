---
title: Aufrufdetailbericht in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Zusammenfassung: Informationen Sie zu den Call Detail Report in Skype für Business Server verwendet wird.'
ms.openlocfilehash: a0b0836099e1181a25b95bf7adbbe603ef7d5e5f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887652"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Aufrufdetailbericht in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Call Detail Report in Skype für Business Server verwendet wird.
  
Call Detail Report bietet einen umfassenden Überblick über ein einzelner Anruf. der Bericht enthält fast alle der Quality of Experience Metriken und von Skype für Business Server erfassten Statistiken in Berichtsabschnitte unterteilt wie etwa:
  
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
  
- [Standortbericht in Skype für Business Server (Speicherort report.md) (durch Klicken auf das Anrufvolumen oder Metrik Prozentsatz Anrufe schlechter Qualität)
    
- Die [Media Quality Summary Report in Skype für Business Server (summary.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz-Metrik Anrufe schlechter Qualität)
    
- Vom [Media Quality Comparison Report in Skype für Business Server](comparison.md) (durch Klicken auf den [Call List Report in Skype für Business Server](call-list-report-0.md) und anschließend auf die Metrik Detail).
    
- [Server Performance Report in Skype für Business Server](server-performance.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz-Metrik Anrufe schlechter Qualität)
    
- [Call List Report in Skype für Business Server](call-list-report-0.md) (durch Klicken auf die Metrik Detail)
    
Aus in den Call Detail Report möglich der [Gerätebericht in Skype für Business Server](device-report.md) durch Klicken auf eine der folgenden Metriken:
  
- Aufnahmegerät
    
- Darstellungsgerät
    
Sie können auch auf den Trendbericht über Medienqualität des Servers zugreifen, indem Sie auf die Metrik „A/V-Edgeserver“ klicken.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Optimale Verwendung des Anrufdetailberichts

Der Anrufdetailbericht umfasst normalerweise 250 verschiedene Metriken. Hierzu gehören „Zeitstempelabweichung des Mikrofons“, „Geringer Rauschabstand, Zeit“ und „Nahes Ende zu Echo, Zeit“. Wenn Sie nicht genau wissen, was mit diesen Metriken gemessen wird, können Sie mit der Maus auf die Bezeichnung der Metrik zeigen. In den meisten Fällen erscheint dann eine QuickInfo mit einer Metrikbeschreibung.
  
Wenn Sie eine Metrik nicht finden können, geben Sie einen Teil der Metrikbezeichnung in das Suchfeld ein und klicken Sie anschließend auf **Suchen**. Wenn Sie beispielsweise die Metrik „Geringer Rauschabstand, Zeit“ nicht finden können, geben Sie „SNR“ in das Suchfeld ein und klicken Sie anschließend auf **Suchen**.
  
Beachten Sie, dass im Bericht nur Informationen zu einem Anruf verfolgt werden. Der Anruf selbst wird nicht aufgezeichnet.
  
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
|**CPU-Kernnummer des Anrufers** <br/> |Nein  <br/> |Die Nummer des Prozessors in dem Computer des Benutzers, der den Anruf initiiert hat.  <br/> |
|**CPU-Geschwindigkeit des Anrufers** <br/> |Nein  <br/> |Die Taktfrequenz der CPU des Computers des Benutzers, der den Anruf initiiert hat.  <br/> |
|**CPU-Virtualisierung des Anrufers** <br/> |Nein  <br/> |Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der den Anruf initiiert hat.  <br/> |
|**PAI des Angerufenen** <br/> |Nein  <br/> |Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der zur Teilnahme an dem Anruf eingeladen wurde. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.  <br/> |
|**URI des Angerufenen** <br/> |Nein  <br/> |Die SIP-Adresse des Benutzers, der angerufen wurde.  <br/> |
|**Endpunkt des Angerufenen** <br/> |Nein  <br/> |Das Gerät, mit dem der Anruf angenommen wurde.  <br/> |
|**Benutzer-Agent des Angerufenen** <br/> |Nein  <br/> |Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf angenommen wurde.  <br/> |
|**Dauer** <br/> |Nein  <br/> |Die Dauer des Anrufs.  <br/> |
|**Vermittlungsserver-Umgehungswarnung** <br/> |Nein  <br/> |Eine Warnung, die ausgegeben wird, wenn der Vermittlungsserver umgangen wurde.  <br/> |
|**Betriebssystem des Angerufenen** <br/> |Nein  <br/> |Das Betriebssystem auf dem Computer des Benutzers, der angerufen wurde.  <br/> |
|**CPU des Angerufenen** <br/> |Nein  <br/> |Die CPU, die im Computer des Benutzers installiert ist, der angerufen wurde.  <br/> |
|**CPU-Kernnummer des Angerufenen** <br/> |Nein  <br/> |Die Nummer des Prozessors in dem Computer des Benutzers, der angerufen wurde.  <br/> |
|**CPU-Geschwindigkeit des Angerufenen** <br/> |Nein  <br/> |Die Taktfrequenz der CPU des Computers des Benutzers, der angerufen wurde.  <br/> |
|**CPU-Virtualisierung des Angerufenen** <br/> |Nein  <br/> |Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der angerufen wurde.  <br/> |
   

