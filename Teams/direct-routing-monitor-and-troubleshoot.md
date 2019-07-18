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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: In diesem Artikel wird beschrieben, wie Sie Ihre direkte Routing Konfiguration überwachen und beheben können.
ms.openlocfilehash: d20a409c7a5e902149ff20e72dde90850f0f5d12
ms.sourcegitcommit: 9751f34318119991b1bd32b384b8e1479c83cb0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "35768156"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Überwachung und Problembehandlung von direktem Routing

In diesem Artikel wird beschrieben, wie Sie Ihre direkte Routing Konfiguration überwachen und beheben können. 

Die Möglichkeit zum tätigen und empfangen von Anrufen mithilfe des direkten Routings umfasst die folgenden Komponenten: 

- Session Border Controllers (SBCS) 
- Direkte Routing Komponenten in der Microsoft-Cloud 
- Telekom-Stämme 

Wenn Sie Probleme bei der Problembehandlung haben, öffnen Sie bitte einen Support-Fall mit Ihrem SBC-Anbieter oder Microsoft. 

Microsoft arbeitet an der Bereitstellung weiterer Tools für die Problembehandlung und Überwachung. Bitte überprüfen Sie die Dokumentation regelmäßig auf Updates. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Überwachen der Verfügbarkeit von Sitzungs Grenz Controllern mithilfe von SIP-Options Meldungen (Session Initiation Protocol)

Das direkte Routing verwendet SIP-Optionen, die von den Session Border Controllern zur Überwachung des SBC-Status gesendet werden. Vom mandantenadministrator sind keine Aktionen erforderlich, um die Überwachung der SIP-Optionen zu aktivieren. Die gesammelten Informationen werden berücksichtigt, wenn Routingentscheidungen getroffen werden. 

Wenn beispielsweise für einen bestimmten Benutzer mehrere SBCS verfügbar sind, um einen Anruf weiterleiten zu können, werden bei der direkten Weiterleitung die SIP-Optionsinformationen berücksichtigt, die von jedem SBC empfangen werden, um das Routing zu ermitteln. 

Das folgende Diagramm zeigt ein Beispiel für die Konfiguration: 

![Konfigurationsbeispiel für SIP-Optionen](media/sip-options-config-example.png)

Wenn ein Benutzer einen Anruf an Number + 1 425 \<mit sieben Ziffern> durchführt, wird die Route von einem direkten Routing ausgewertet. Die Route umfasst zwei SBCS: sbc1.contoso.com und sbc2.contoso.com. Beide SBCS haben in der Route dieselbe Priorität. Vor der Auswahl eines SBC bewertet der Routingmechanismus die Integrität des SBCS basierend auf dem Zeitpunkt, zu dem der SBC die SIP-Optionen beim letzten Mal gesendet hat. 

Ein SBC wird als "fehlerfrei" eingestuft, wenn beim Senden des Anrufs Statistiken angezeigt werden, dass die SBC-Optionen jede Minute gesendet werden.  

Wenn ein Anruf durchgeführt wird, gilt die folgende Logik:

- Der SBC wurde um 11,00 Uhr gekoppelt.  
- Der SBC sendet Optionen für 11,01 Uhr, 11,02 Uhr usw.  
- Bei 11,15 führt ein Benutzer einen Anruf aus, und der Routingmechanismus wählt diesen SBC aus. 

Beim direkten Routing werden die regulären Intervall Optionen dreimal verwendet (das reguläre Intervall beträgt eine Minute). Wenn Optionen in den letzten drei Minuten gesendet wurden, gilt der SBC als fehlerfrei.

Wenn der SBC im Beispiel Optionen zu einem beliebigen Zeitraum zwischen 11,12 und 11,15 Uhr (der Zeitpunkt, zu dem der Anruf getätigt wurde) gesendet hat, wird er als fehlerfrei angesehen. Wenn dies nicht der Fall ist, wird der SBC von der Route herabgestuft. 

Herabstufung bedeutet, dass der SBC nicht zuerst getestet wird. Beispielsweise haben wir sbc1.contoso.com und sbc2.contoso.com mit gleicher Priorität.  

Wenn sbc1.contoso.com die SIP-Optionen nicht wie oben beschrieben in regelmäßigen Abständen sendet, wird es herabgestuft. Als nächstes versucht sbc2.contoso.com den Anruf. Wenn sbc2. contoso. con den Anruf nicht übermitteln kann, wird der sbc1.contoso.com (degradiert) erneut versucht, bevor ein Fehler generiert wird. 

Wenn zwei (oder mehr) SBCS in einer Route auf "gesund" und "gleich" bestanden, wurde Fisher-Yates shuffle angewendet, um die Aufrufe zwischen SBCS zu distrubute.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Überwachen von Anruf Qualitätsanalyse-Dashboard und SBC-Protokollen 
 
In einigen Fällen, besonders während der anfänglichen Kopplung, gibt es möglicherweise Probleme im Zusammenhang mit der Fehlkonfiguration des SBCS und/oder des Direct Routing-Diensts. 

Sie können die folgenden Tools verwenden, um Ihre Konfiguration zu überwachen:  
 
- Anrufqualitäts-Dashboard 
- SBC-Protokolle 

Der Direct Routing-Dienst weist sehr anschauliche Fehlercodes auf, die entweder für die anrufanalyse oder für die SBC-Protokolle gemeldet wurden. 

Das Dashboard "Anrufqualität" bietet Informationen zur Anrufqualität und Zuverlässigkeit. Weitere Informationen zur Behandlung von Problemen mit der anrufanalyse finden Sie unter [aktivieren und Verwenden von Anruf Qualitäts Dashboard für Microsoft Teams und Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und [Verwenden von Anruf Analysen zur Behandlung schlechter Anrufqualität](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

Bei Anruf Fehlern bietet die anrufanalyse Standard-SIP-Codes, die Ihnen bei der Problembehandlung helfen. 

![Beispiel für SIP-Code für Anruf Fehler](media/failed-response-code.png)

Anruf Analysen können jedoch nur dann hilfreich sein, wenn Anrufe die internen Komponenten des direkten Routings erreichen und Fehler auftreten. Bei Problemen mit SBC-Kopplungen oder Problemen, bei denen SIP "Invite" abgelehnt wurde (beispielsweise ist der Name des trunk-FQDN falsch konfiguriert), kann die anrufanalyse nicht helfen. Beziehen Sie sich in diesem Fall bitte auf die SBC-Protokolle. Direktes Routing sendet eine detaillierte Beschreibung der Probleme an die SBCS. Diese Probleme können aus den SBC-Protokollen gelesen werden. 
