---
title: Diagnosebericht in Skype for Business Server
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Zusammenfassung: Erfahren Sie mehr über den Diagnosebericht in Skype for Business Server.'
ms.openlocfilehash: ef930870e918cd11f2525914e6f5716d7d685bfec224480c1eb88b3a280e3fa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297221"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Diagnosebericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Diagnosebericht in Skype for Business Server.
  
Der Diagnosebericht enthält Diagnose- und Problembehandlungsinformationen der fehlerhaften Sitzung. Er enthält sowohl die während einer fehlerhaften Sitzung berichtete Diagnose-ID als auch den Diagnoseheader. Die Diagnose-ID ist ein eindeutiger Bezeichner (in der Form eines Headers vom Typ "ms-diagnostics") der an eine SIP-Nachricht angefügt wird, während der Diagnoseheader eine begleitende Beschreibung für die Diagnose-ID bietet. Der Bericht enthält möglicherweise auch wertvolle Details für die Problembehandlung, die der Reporting-Komponente bekannt sind. Beispielsweise:
  
- Der vom PSTN-Gateway bereitgestellte Ursachencode, der den Fehler generiert hat. Wenn ein ausgehender Anruf im Telefonfestnetz nicht getätigt werden kann, wird automatisch ein ISUP-Ursachencode (ISDN User Part) generiert. Beispielsweise kann ein PSTN-Gateway den Ursachencode 34 senden, um anzuzeigen, dass keine Verbindung bzw. kein Kanal zum Tätigen des Anrufs verfügbar war.
    
- FQDN des Peers, Port und Winsock-Fehler für Verbindungsfehler.
    
- Namen, die für DNS-Auflösungsfehler ermittelt werden. Die DNS-Auflösung findet immer dann statt, wenn ein Client einen Namenserver kontaktiert und die IP-Adresse anfordert, die dem angegebenen Gerätenamen entspricht.
    
## <a name="accessing-the-diagnostic-report"></a>Zugreifen auf den Diagnosebericht

Auf den Diagnosebericht kann zugegriffen werden, indem Sie auf die Metrik "Diagnosebericht (Details)" im Detailbericht über [Peer-to-Peer-Sitzungen in Skype for Business Server](peer-to-peer-session-detail-report.md) oder im Detaillierten Konferenzbericht klicken.
  
## <a name="filters"></a>Filter

Keine. Sie können den Diagnosebericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Diagnosebericht enthaltenen Informationen für jeden Anruf aufgeführt.
  
**Metriken des Diagnoseberichts**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Berichtszeit** <br/> |Nein  <br/> |Datum und Uhrzeit der Aufzeichnung des Berichts.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.  <br/> |
|**Anforderungstyp** <br/> |Nein  <br/> |Typ der fehlerhaften SIP-Anforderung. Beispielsweise: INVITE, BYE oder SERVICE.  <br/> |
|**Source** <br/> |Nein  <br/> |Ursache des Fehlers.  <br/> |
|**Von Benutzer-URI** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**Von Benutzer-Agent** <br/> |Nein  <br/> |Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Inhaltstyp** <br/> |Nein  <br/> |Typ der fehlerhaften Medieninhalte. Ein gebräuchlicher Inhaltstyp ist beispielsweise Application/sdp. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen von Einladungen für Multimediasitzungen verwendet wird.  <br/> |
|**Anwendung** <br/> |Nein  <br/> |Anwendung, die am Fehler beteiligt ist.  <br/> |
|**An Benutzer-URI** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.  <br/> |
|**Zeitpunkt des Beitritts für die Konferenz (ms)** <br/> |Nein  <br/> |Gesamtdauer (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.  <br/> |
|**Diagnoseheader** <br/> |Nein  <br/> |Beschreibung der Diagnose-ID.  <br/> |
   
Eine Liste der Diagnosefehler finden Sie auf der Kopfzeile der [Ms-Diagnostics-Seite.](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)
