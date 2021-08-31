---
title: Überwachung und Problembehandlung von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die Direct Routing-Konfiguration überwachen und behandeln, einschließlich Session Border Controller, Direct Routing-Komponenten und Telekommunikations-Trunks.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeff22bf3558c64111f0d1b66c2fd76288f81477
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726884"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Überwachung und Problembehandlung von direktem Routing

In diesem Artikel wird beschrieben, wie Sie Ihre Direct Routing-Konfiguration überwachen und Probleme damit behandeln können. 

Die Möglichkeit zum Anrufen und Empfangen von Anrufen mithilfe von Direct-Routing umfasst die folgenden Komponenten: 

- Session Border Controller (SBCs) 
- Direct Routing-Komponenten in der Microsoft Cloud 
- Telecom trunks 

Wenn Sie Schwierigkeiten bei der Problembehandlung haben, können Sie einen Supportfall bei Ihrem SBC-Anbieter oder microsoft öffnen. 

Microsoft arbeitet daran, weitere Tools für die Problembehandlung und Überwachung zur Verfügung zu haben. Überprüfen Sie die Dokumentation regelmäßig auf Aktualisierungen. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Überwachen der Verfügbarkeit von Session Border Controllern mithilfe von Sip-Optionsmeldungen (Session Initiation Protocol)

Direct Routing verwendet sip-Optionen, die von den Session Border Controllern gesendet werden, um den SBC-Status zu überwachen. Es sind keine Aktionen des Mandantenadministrators erforderlich, um die Überwachung der SIP-Optionen zu aktivieren. Die gesammelten Informationen werden bei Routingentscheidungen berücksichtigt. 

Wenn beispielsweise für einen bestimmten Benutzer mehrere SBCs zum Weiterleiten eines Anrufs verfügbar sind, verwendet Direct Routing die SIP-Optionsinformationen, die von jedem SBC empfangen werden, um das Routing zu bestimmen. 

Das folgende Diagramm zeigt ein Beispiel für die Konfiguration: 

![Konfigurationsbeispiel für SIP-Optionen.](media/sip-options-config-example.png)

Wenn ein Benutzer die Nummer +1 425 anruft, wertet \<any seven digits> Direct Routing die Route aus. Es gibt zwei SBCs an der Route: sbc1.contoso.com und sbc2.contoso.com. Beide SBCs haben die gleiche Priorität auf der Route. Vor der Auswahl eines SBC wertet der Routingmechanismus den Zustand der SBCs basierend darauf aus, wann der SBC die SIP-Optionen beim letzten Mal gesendet hat. 

Ein SBC gilt als fehlerfrei, wenn Statistiken zum Zeitpunkt des Sendens des Anrufs zeigen, dass der SBC Optionen jede Minute sendet.  

Wenn ein Aufruf erfolgt, gilt die folgende Logik:

- Der SBC wurde um 11:00 Uhr gekoppelt.  
- Der SBC sendet Optionen um 11:01, 11:02 und so weiter.  
- Um 11:15 Uhr nimmt ein Benutzer einen Anruf ab, und der Routingmechanismus wählt diesen SBC aus. 

Das direkte Routing verwendet die regulären Intervalloptionen dreimal (das normale Intervall beträgt eine Minute). Wenn in den letzten drei Minuten Optionen gesendet wurden, gilt der SBC als fehlerfrei.

Wenn der SBC im Beispiel Optionen zu einem beliebigen Zeitpunkt zwischen 11:12 und 11:15 (dem Zeitpunkt des Anrufs) gesendet hat, gilt er als fehlerfrei. Andern falls nicht, wird der SBC von der Route herabgestuft. 

Herabstufung bedeutet, dass SBC nicht zuerst ausprobiert wird. Beispielsweise haben wir eine sbc1.contoso.com und sbc2.contoso.com mit gleicher Priorität.  

Wenn sbc1.contoso.com SIP-Optionen nicht wie zuvor beschrieben in regelmäßigen Abständen senden, wird sie herabgestuft. Als Nächstes sbc2.contoso.com sie nach dem -Aufruf. Wenn "sbc2.contoso.con" den Anruf nicht abliefern kann, wird sbc1.contoso.com (herabgestuft) erneut versucht, bevor ein Fehler generiert wird. 

Wenn zwei (oder mehr) SBCs auf einer Route als fehlerfrei und gleich angesehen werden, wird Fisher-Yates gemischteUffle angewendet, um die Anrufe zwischen den SBCs zu verteilen.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Überwachen des Anrufqualitätsanalyse-Dashboards und von SBC-Protokollen 
 
In einigen Fällen kann es, insbesondere während der ersten Kopplung, zu Problemen im Zusammenhang mit der falschen Konfiguration der SBCs oder des Direct-Routingdiensts führen. 

Zur Überwachung der Konfiguration können Sie die folgenden Tools verwenden:  
 
- Anrufqualitäts-Dashboard 
- SBC-Protokolle 

Der Direct-Routingdienst verfügt über sehr beschreibende Fehlercodes, die entweder in der Anrufanalyse oder in den SBC-Protokollen gemeldet werden. 

Das Anrufqualitätsdashboard bietet Informationen zur Anrufqualität und Zuverlässigkeit. Weitere Informationen zur Problembehandlung mit der Anrufanalyse finden Sie unter Aktivieren und Verwenden des Anrufqualitätsdashboards für Microsoft Teams und [Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität. [](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

Bei einem Anruffehler bietet die Anrufanalyse SIP-Standardcodes, die Ihnen bei der Problembehandlung helfen. 

![Beispiel für SIP-Code für einen Anruffehler.](media/failed-response-code.png)

Die Anrufanalyse kann jedoch nur hilfreich sein, wenn Aufrufe die internen Komponenten von Direct-Routing erreichen und fehlschlagen. Bei Problemen mit der SBC-Kopplung oder bei Problemen, bei denen die SIP-Einladung abgelehnt wurde (z. B. wenn der Name des Trunk-FQDN falsch konfiguriert ist), hilft die Anrufanalyse nicht. Verweisen Sie in diesem Fall auf die SBC-Protokolle. Direct Routing sendet eine detaillierte Beschreibung der Probleme an die SBCs. diese Probleme können aus den SBC-Protokollen gelesen werden.