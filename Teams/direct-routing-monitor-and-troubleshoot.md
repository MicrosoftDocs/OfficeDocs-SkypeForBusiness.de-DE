---
title: Überwachung und Problembehandlung von direkten Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: In diesem Artikel wird beschrieben, wie zur Überwachung und Problembehandlung für die direkte Routing-Konfiguration.
ms.openlocfilehash: 46fd5ad046551d30bf3822d11864edc2a5353a26
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014933"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Überwachung und Problembehandlung von direkten Routing

In diesem Artikel wird beschrieben, wie zur Überwachung und Problembehandlung für die direkte Routing-Konfiguration. 

Die Möglichkeit zum tätigen und Entgegennehmen von Anrufen durch direktes Routing umfasst die folgenden Komponenten: 

- Session Border Controller (SBCs) 
- Direkte Routing-Komponenten in der Microsoft-Cloud 
- Telekommunikation trunks 

Wenn Sie Probleme bei der Behandlung von Problemen haben, öffnen Sie eine Supportanfrage mit Ihrer SBC-Anbieter oder Microsoft. 

Microsoft ist funktionsfähig, klicken Sie auf Weitere Tools für die Problembehandlung und Überwachung bereitstellen. Überprüfen Sie die Dokumentation in regelmäßigen Abständen nach Updates. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Überwachen der Verfügbarkeit von Session Border Controller über Session Initiation Protocol (SIP) Optionen Nachrichten

Direktes Routing verwendet SIP-Optionen, die von der Session Border Controller gesendet, um SBC Integrität zu überwachen. Es sind keine Aktionen, die von der mandantenadministrator erforderlich sind, um die Optionen SIP-Überwachung aktivieren. Die gesammelte Informationen wird berücksichtigt, wenn Routingentscheidungen vorgenommen werden. 

Beispielsweise wenn für einen bestimmten Benutzer, mehrere SBCs zum Weiterleiten eines Anrufs verfügbar sind, berücksichtigt direkten Routing von jedem SBC-routing bestimmen erhaltenen Informationen SIP-Optionen. 

Das folgende Diagramm zeigt ein Beispiel für die Konfiguration: 

![Beispiel für die Konfiguration von SIP-Optionen](media/sip-options-config-example.png)

Wenn ein Benutzer einen Anruf an Anzahl +1 425 herstellt \<alle sieben Ziffern >, direkten Routing wertet die Route. Es gibt zwei SBCs in der Route: sbc1.contoso.com und sbc2.contoso.com. Beide SBCs haben die gleiche Priorität in der Route. Vor der Entnahme eines SBC, wertet der routing-Mechanismus die Integrität der SBCs basierend auf, wenn der SBC die Optionen SIP gesendet letzten Zeit. 

Ein SBC gilt fehlerfrei, ob Statistiken zum Zeitpunkt der den Anruf senden angezeigt, dass der SBC Optionen in regelmäßigen Abständen gesendet.  

Direktes Routing berechnet regelmäßige Abständen, indem Sie zwei Mal den Mittelwert nutzen, wenn der SBC Optionen sendet, bevor der Aufruf und Hinzufügen von fünf Minuten. 

Beispielsweise wird Folgendes vorausgesetzt: 

- Ein SBC ist so konfiguriert, zum Senden von "Optionen" jede Minute. 
- Der SBC wurde um 11:00 Uhr kombiniert.  
- Der SBC sendet Optionen auf 11.01 Uhr, 11.02 Uhr.  
- An 11.15 ein Benutzer einen Anruf tätigt, und der routing Mechanismus markiert dieses SBC. 

Die folgende Logik angewendet wird: doppelt das durchschnittliche Intervall der SBC Optionen (1 Minute plus eine Minute = zwei Minuten) plus fünf Minuten = sieben Minuten sendet. Dies ist der Wert der der regelmäßigen Intervall für die SBC.
 
Wenn der SBC in unserem Beispiel gesendete Optionen auf einen beliebigen Zeitraum zwischen 11:08 und 11:15 Uhr (Zeit, die der Anruf getätigt wurde), wird es fehlerfrei betrachtet. Wenn dies nicht der Fall ist, wird der SBC aus der Route herabgestuft werden. 

Herabstufung bedeutet, dass der SBC nicht zuerst getestet werden. Zum Beispiel haben wir sbc1.contoso.com und sbc2.contoso.com mit gleiche Priorität.  

Sbc1.contoso.com wie oben beschrieben keine SIP-Optionen in regelmäßigen Abständen sendet, wird es herabgestuft. Im nächsten Schritt versucht sbc2.contoso.com für den Anruf. Wenn den Aufruf von sbc2.contoso.con nicht zugestellt werden kann, die sbc1.contoso.com (tiefer gestuft) erneut versucht werden soll, bevor ein Fehler generiert wird. 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Überwachen der Qualität Analytics aufrufen Dashboard und SBC-Protokolle 
 
In einigen Fällen vor allem in Zeiten der anfänglichen Paarung möglicherweise Probleme im Zusammenhang mit falsche Konfiguration der der SBCs und/oder direkte Routing Service. 

Die folgenden Tools können Sie Ihre Konfiguration überwachen:  
 
- Anrufqualitäts-Dashboard 
- SBC-Protokolle 

Direktes Routing Service hat sehr beschreibenden Fehlercodes gemeldet Analytics aufrufen oder die SBC-Protokolle. 

Das Aufrufen Qualitätsdashboard bietet Informationen zur Anrufqualität und Zuverlässigkeit. Weitere Informationen zum Beheben von Problemen mit Aufrufen Analytics finden Sie unter [aktivieren, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und [Verwendung aufrufen Analysen für die Qualität der Anrufe schlechter Qualität Problembehandlung bei](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

Im Fall eines WAN-anruffehlern bietet Analytics rufen Sie standard-SIP-Codes, die Sie bei der Problembehandlung zu erleichtern. 

![SIP-Beispielcode für das Fehlschlagen des Anrufs](media/failed-response-code.png)

Analytics aufrufen können jedoch nur bei Anrufen die internen Komponenten des direkten Routing erreichen fehlschlagen. Im Fall eines WAN-Probleme bei der Paarung SBC oder Probleme, auf dem SIP "Einladen" (beispielsweise den Namen des Trunks, den FQDN falsch konfiguriert ist) abgelehnt wurde, trägt Analytics Anruf nicht. In diesem Fall finden Sie die SBC-Protokolle. Direktes Routing sendet eine detaillierte Beschreibung der Probleme an die SBCs. Diese Probleme können aus den Protokollen SBC gelesen werden. 
