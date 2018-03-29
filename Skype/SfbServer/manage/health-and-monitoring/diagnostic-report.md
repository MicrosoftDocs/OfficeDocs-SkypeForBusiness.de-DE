---
title: Diagnosebericht in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Zusammenfassung: Informationen Sie zu den Diagnosebericht in Skype für Business Server 2015.'
ms.openlocfilehash: 86639f5687cb6d19ff18c9aafb869a74fb777113
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="diagnostic-report-in-skype-for-business-server-2015"></a>Diagnosebericht in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Diagnosebericht in Skype für Business Server 2015.
  
Der Diagnosebericht enthält Diagnose- und Problembehandlungsinformationen der fehlerhaften Sitzung. Er enthält sowohl die während einer fehlerhaften Sitzung berichtete Diagnose-ID als auch den Diagnoseheader. Die Diagnose-ID ist ein eindeutiger Bezeichner (in der Form eines Headers vom Typ „ms-diagnostics“) der an eine SIP-Nachricht angefügt wird, während der Diagnoseheader eine begleitende Beschreibung für die Diagnose-ID bietet. Der Bericht enthält möglicherweise auch wertvolle Details für die Problembehandlung, die der Reporting-Komponente bekannt sind. Beispielsweise:
  
- Der vom PSTN-Gateway bereitgestellte Ursachencode, der den Fehler generiert hat. Wenn ein ausgehender Anruf im Telefonfestnetz nicht getätigt werden kann, wird automatisch ein ISUP-Ursachencode (ISDN User Part) generiert. Beispielsweise kann ein PSTN-Gateway den Ursachencode 34 senden, um anzuzeigen, dass keine Verbindung bzw. kein Kanal zum Tätigen des Anrufs verfügbar war.
    
- FQDN des Peers, Port und Winsock-Fehler für Verbindungsfehler.
    
- Namen, die für DNS-Auflösungsfehler ermittelt werden. Die DNS-Auflösung findet immer dann statt, wenn ein Client einen Namenserver kontaktiert und die IP-Adresse anfordert, die dem angegebenen Gerätenamen entspricht.
    
## <a name="accessing-the-diagnostic-report"></a>Zugreifen auf den Diagnosebericht

Den Diagnosebericht kann durch Klicken auf die Metrik Diagnosebericht (Detail) auf den [Bericht über Peer-zu-Peer-Sitzungsbericht in Skype für Business Server 2015](peer-to-peer-session-detail-report.md) oder den detaillierten Konferenzbericht zugegriffen werden.
  
## <a name="filters"></a>Filter

Keine. Sie können den Diagnosebericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Diagnosebericht enthaltenen Informationen für jeden Anruf aufgeführt.
  
**Metriken des Diagnoseberichts**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Berichtszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit der Aufzeichnung des Berichts.  <br/> |
|**Antwortcode** <br/> |Nein  <br/> |SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.  <br/> |
|**Anforderungstyp** <br/> |Nein  <br/> |Typ der fehlerhaften SIP-Anforderung. Beispielsweise: INVITE, BYE oder SERVICE.  <br/> |
|**Quelle** <br/> |Nein  <br/> |Ursache des Fehlers.  <br/> |
|**Von Benutzer-URI** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**Von Benutzeragent** <br/> |Nein  <br/> |Software, die vom Endpunkt des Benutzers, der die Sitzung initiiert hat, verwendet wird.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Inhaltstyp** <br/> |Nein  <br/> |Typ der fehlerhaften Medieninhalte. Ein gebräuchlicher Inhaltstyp ist beispielsweise Application/sdp. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen von Einladungen für Multimediasitzungen verwendet wird.  <br/> |
|**Anwendung** <br/> |Nein  <br/> |Anwendung, die am Fehler beteiligt ist.  <br/> |
|**An Benutzer-URI** <br/> |Nein  <br/> |SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.  <br/> |
|**Zeitpunkt des Beitritts für die Konferenz (ms)** <br/> |Nein  <br/> |Gesamtdauer (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.  <br/> |
|**Diagnoseheader** <br/> |Nein  <br/> |Beschreibung der Diagnose-ID.  <br/> |
   
Eine Liste der Diagnose von Fehlern finden Sie auf der [Seite Ms-Diagnostics-Header](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).
  

