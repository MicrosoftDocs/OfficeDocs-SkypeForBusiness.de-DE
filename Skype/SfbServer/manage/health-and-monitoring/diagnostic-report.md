---
title: Diagnosebericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Zusammenfassung: erfahren Sie mehr über den Diagnosebericht in Skype for Business Server.'
ms.openlocfilehash: e8f89f1f5a013b40f7f5f105f49611542667a477
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817985"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Diagnosebericht in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Diagnosebericht in Skype for Business Server.
  
Der Diagnosebericht enthält Diagnose- und Problembehandlungsinformationen der fehlerhaften Sitzung. Er enthält sowohl die während einer fehlerhaften Sitzung berichtete Diagnose-ID als auch den Diagnoseheader. Die Diagnose-ID ist ein eindeutiger Bezeichner (in der Form eines Headers vom Typ „ms-diagnostics“) der an eine SIP-Nachricht angefügt wird, während der Diagnoseheader eine begleitende Beschreibung für die Diagnose-ID bietet. Der Bericht enthält möglicherweise auch wertvolle Details für die Problembehandlung, die der Reporting-Komponente bekannt sind. Beispielsweise:
  
- Der vom PSTN-Gateway bereitgestellte Ursachencode, der den Fehler generiert hat. Wenn ein ausgehender Anruf im Telefonfestnetz nicht getätigt werden kann, wird automatisch ein ISUP-Ursachencode (ISDN User Part) generiert. Beispielsweise kann ein PSTN-Gateway den Ursachencode 34 senden, um anzuzeigen, dass keine Verbindung bzw. kein Kanal zum Tätigen des Anrufs verfügbar war.
    
- FQDN des Peers, Port und Winsock-Fehler für Verbindungsfehler.
    
- Namen, die für DNS-Auflösungsfehler ermittelt werden. Die DNS-Auflösung findet immer dann statt, wenn ein Client einen Namenserver kontaktiert und die IP-Adresse anfordert, die dem angegebenen Gerätenamen entspricht.
    
## <a name="accessing-the-diagnostic-report"></a>Zugreifen auf den Diagnosebericht

Sie können auf den Diagnosebericht zugreifen, indem Sie entweder im [Bericht Peer-to-Peer-Sitzungs Detail in Skype for Business Server](peer-to-peer-session-detail-report.md) oder im Konferenz Detailbericht auf die Metrik für den Diagnosebericht (Detail) klicken.
  
## <a name="filters"></a>Filter

Keine. Sie können den Diagnosebericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Diagnosebericht enthaltenen Informationen für jeden Anruf aufgeführt.
  
**Metriken des Diagnoseberichts**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
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
   
Eine Liste der Diagnosefehler finden Sie auf der [Header Seite MS-Diagnostics](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).
  

