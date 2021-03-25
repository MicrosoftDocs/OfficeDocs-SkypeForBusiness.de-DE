---
title: Überwachung und Problembehandlung von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Direct Routing-Konfiguration überwachen und behandeln, einschließlich Session Border Controller, Direct Routing-Komponenten und Telekommunikations-Trunks.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121403"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Überwachung und Problembehandlung von direktem Routing

In diesem Artikel wird beschrieben, wie Sie Ihre Direct Routing-Konfiguration überwachen und problembehebungen. 

Die Möglichkeit zum Anrufen und Empfangen von Anrufen mithilfe von Direct Routing umfasst die folgenden Komponenten: 

- Session Border Controller (SBCs) 
- Direct Routing-Komponenten in der Microsoft Cloud 
- Telekommunikationsstämme 

Wenn Sie Probleme bei der Problembehandlung haben, können Sie einen Supportfall bei Ihrem SBC-Anbieter oder Microsoft öffnen. 

Microsoft arbeitet an der Bereitstellung von weiteren Tools für die Problembehandlung und Überwachung. Überprüfen Sie die Dokumentation in regelmäßigen Abständen auf Updates. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Überwachen der Verfügbarkeit von Sitzungsgrenzcontrollern mithilfe von Sip-Optionsmeldungen (Session Initiation Protocol)

Direct Routing verwendet SIP-Optionen, die von den Session Border Controllern gesendet wurden, um den SBC-Status zu überwachen. Es sind keine Aktionen vom Mandantenadministrator erforderlich, um die Überwachung der SIP-Optionen zu aktivieren. Die gesammelten Informationen werden berücksichtigt, wenn Routingentscheidungen getroffen werden. 

Wenn beispielsweise für einen bestimmten Benutzer mehrere SBCs zum Weiterleiten eines Anrufs verfügbar sind, berücksichtigt Direct Routing die von jedem SBC empfangenen INFORMATIONEN zu den SIP-Optionen, um das Routing zu ermitteln. 

Das folgende Diagramm zeigt ein Beispiel für die Konfiguration: 

![Beispiel für die Konfiguration von SIP-Optionen](media/sip-options-config-example.png)

Wenn ein Benutzer die Nummer +1 425 \<any seven digits> anruft, wertet Direct Routing die Route aus. Die Route besteht aus zwei SBCs: sbc1.contoso.com und sbc2.contoso.com. Beide SBCs haben in der Route die gleiche Priorität. Vor dem Auswählen eines SBC wertet der Routingmechanismus den Zustand der SBCs basierend darauf aus, wann der SBC die SIP-Optionen beim letzten Mal gesendet hat. 

Ein SBC wird als fehlerfrei betrachtet, wenn die Statistik zum Zeitpunkt des Sendens des Anrufs zeigt, dass der SBC optionen im Minutentakt sendet.  

Wenn ein Aufruf erfolgt, gilt die folgende Logik:

- Der SBC wurde um 11:00 Gekoppelt.  
- Der SBC sendet Optionen um 11:01, 11:02 und so weiter.  
- Um 11:15 nimmt ein Benutzer einen Anruf vor, und der Routingmechanismus wählt diesen SBC aus. 

Beim direkten Routing werden die regulären Intervalloptionen dreimal verwendet (das normale Intervall beträgt eine Minute). Wenn optionen während der letzten drei Minuten gesendet wurden, gilt der SBC als fehlerfrei.

Wenn der SBC im Beispiel Optionen zu einem beliebigen Zeitraum zwischen 11:12 und 11:15 Uhr gesendet hat (der Zeitpunkt, zu dem der Anruf erfolgt ist), wird er als fehlerfrei betrachtet. Andern falls nicht, wird der SBC von der Route herabgestuft. 

Demotion bedeutet, dass der SBC nicht zuerst ausprobiert wird. Wir haben z. B. sbc1.contoso.com und sbc2.contoso.com mit gleicher Priorität.  

Wenn sbc1.contoso.com SIP-Optionen nicht wie zuvor beschrieben in einem normalen Intervall sendet, wird sie herabgestuft. Als Nächstes sbc2.contoso.com nach dem Aufruf. Wenn "sbc2.contoso.con" den Anruf nicht liefern kann, wird sbc1.contoso.com (degradiert) erneut versucht, bevor ein Fehler generiert wird. 

Wenn zwei (oder mehr) SBCs in einer Route als fehlerfrei und gleich angesehen werden, wird Fisher-Yates-Shuffle angewendet, um die Anrufe zwischen den SBCs zu verteilen.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Überwachen von Anrufqualitätsanalysedashboards und SBC-Protokollen 
 
In einigen Fällen, insbesondere während der ersten Kopplung, können Probleme im Zusammenhang mit der falschen Konfiguration der SBCs oder des Direct Routing-Diensts auftreten. 

Sie können die folgenden Tools verwenden, um Ihre Konfiguration zu überwachen:  
 
- Anrufqualitäts-Dashboard 
- SBC-Protokolle 

Der Direct Routing-Dienst verfügt über sehr beschreibende Fehlercodes, die entweder der Anrufanalyse oder den SBC-Protokollen gemeldet werden. 

Das Anrufqualitätsdashboard enthält Informationen zur Anrufqualität und -zuverlässigkeit. Weitere Informationen zum Behandeln von Problemen mithilfe der Anrufanalyse finden Sie unter Aktivieren und Verwenden des Anrufqualitätsdashboards für Microsoft Teams und [Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und Verwenden der Anrufanalyse zur Problembehandlung bei schlechter [Anrufqualität.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

Im Fall von Anruffehlern stellt die Anrufanalyse standardmäßige SIP-Codes zur Unterstützung bei der Problembehandlung zur Veranschlagung zur Lösung von Problemen bei. 

![Beispiel-SIP-Code für Anruffehler](media/failed-response-code.png)

Die Anrufanalyse kann jedoch nur hilfreich sein, wenn Anrufe die internen Komponenten von Direct Routing erreichen und fehlschlagen. Bei Problemen mit der SBC-Kopplung oder Bei Problemen, bei denen SIP "Invite" abgelehnt wurde (z. B. der Name des Stamm-FQDNs ist falsch konfiguriert), hilft Die Anrufanalyse nicht. Verweisen Sie in diesem Fall auf die SBC-Protokolle. Direct Routing sendet eine detaillierte Beschreibung der Probleme an die SBCs. Diese Probleme können aus den SBC-Protokollen gelesen werden.