---
title: Direktes Routing überwachen
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
description: Erfahren Sie, wie Sie die Direct Routing-Konfiguration überwachen und behandeln, einschließlich Session Border Controller, Direct Routing-Komponenten und Telecom-Trunks.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657245"
---
# <a name="monitor-direct-routing"></a>Direktes Routing überwachen

In diesem Artikel wird beschrieben, wie Sie Ihre Direct Routing-Konfiguration überwachen und Probleme beheben. 

Die Möglichkeit zum Tätigen und Empfangen von Anrufen mit direct Routing umfasst die folgenden Komponenten: 

- Session Border Controller (SBCs) 
- Direct Routing-Komponenten in der Microsoft Cloud 
- Telekommunikationstrunks 

Wenn Sie Schwierigkeiten bei der Problembehandlung haben, können Sie einen Supportfall bei Ihrem SBC-Anbieter oder Microsoft öffnen. 

Microsoft arbeitet daran, weitere Tools zur Problembehandlung und Überwachung bereitzustellen. Überprüfen Sie in regelmäßigen Abständen in der Dokumentation nach Updates. 

## <a name="troubleshoot-direct-routing"></a>Problembehandlung bei Direct Routing

Informationen zur Behandlung von Direct Routing finden [Sie unter Diagnose von Problemen mit Direct Routing](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Überwachen der Verfügbarkeit von Session Border Controllern mithilfe von SIP-Optionsmeldungen (Session Initiation Protocol)

Direct Routing verwendet SIP-Optionen, die von den Session Border Controllern gesendet werden, um die SBC-Integrität zu überwachen. Es sind keine Aktionen vom Mandantenadministrator erforderlich, um die Überwachung der SIP-Optionen zu aktivieren. Die gesammelten Informationen werden bei Routingentscheidungen berücksichtigt. 

Wenn beispielsweise für einen bestimmten Benutzer mehrere SBCs zum Weiterleiten eines Anrufs verfügbar sind, berücksichtigt Direct Routing die SIP-Optionsinformationen, die von jedem SBC empfangen werden, um das Routing zu bestimmen. 

Das folgende Diagramm zeigt ein Beispiel für die Konfiguration: 

![Beispiel für die Konfiguration von SIP-Optionen.](media/sip-options-config-example.png)

Wenn ein Benutzer die Nummer +1 425 \<any seven digits>aufruft, wertet Direct Routing die Route aus. Es gibt zwei SBCs auf der Route: sbc1.contoso.com und sbc2.contoso.com. Beide SBCs haben auf der Route dieselbe Priorität. Vor der Auswahl eines SBC wertet der Routingmechanismus die Integrität der SBCs basierend auf dem Zeitpunkt aus, an dem der SBC die SIP-Optionen das letzte Mal gesendet hat. 

Ein SBC gilt als fehlerfrei, wenn statistiken zum Zeitpunkt des Sendens des Anrufs zeigen, dass der SBC Optionen jede Minute sendet.  

Wenn ein Aufruf erfolgt, gilt die folgende Logik:

- Der SBC wurde um 11:00 Uhr gekoppelt.  
- Der SBC sendet Optionen um 11:01 Uhr, 11:02 Uhr usw.  
- Um 11:15 Uhr führt ein Benutzer einen Anruf aus, und der Routingmechanismus wählt diesen SBC aus. 

Direct Routing verwendet die regulären Intervalloptionen dreimal (das reguläre Intervall beträgt eine Minute). Wenn während der letzten drei Minuten Optionen gesendet wurden, gilt der SBC als fehlerfrei.

Wenn der SBC im Beispiel Optionen in einem beliebigen Zeitraum zwischen 11:12 Uhr und 11:15 Uhr (zeitpunkt des Anrufs) gesendet hat, gilt er als fehlerfrei. Andernfalls wird der SBC von der Route herabgestuft. 

Herabstufung bedeutet, dass der SBC nicht zuerst ausprobiert wird. Beispielsweise haben wir sbc1.contoso.com und sbc2.contoso.com mit gleicher Priorität.  

Wenn sbc1.contoso.com sip-Optionen nicht in einem regelmäßigen Intervall sendet, wie zuvor beschrieben, wird es herabgestuft. Als Nächstes versucht sbc2.contoso.com, den Anruf auszuführen. Wenn sbc2.contoso.con den Anruf nicht übermitteln kann, wird die sbc1.contoso.com (herabgestuft) erneut versucht, bevor ein Fehler generiert wird. 

Wenn zwei (oder mehr) SBCs in einer Route als fehlerfrei und gleich angesehen werden, wird Fisher-Yates Shuffle angewendet, um die Anrufe zwischen den SBCs zu verteilen.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Überwachen des Dashboards "Anrufqualitätsanalyse" und der SBC-Protokolle 
 
In einigen Fällen, insbesondere während der anfänglichen Kopplung, können Probleme im Zusammenhang mit der Fehlkonfiguration der SBCs oder des Direct Routing-Diensts auftreten. 

Sie können die folgenden Tools verwenden, um Ihre Konfiguration zu überwachen:  
 
- Anrufqualitäts-Dashboard 
- SBC-Protokolle 

Der Direct Routing-Dienst verfügt über beschreibende Fehlercodes, die entweder der Anrufanalyse oder den SBC-Protokollen gemeldet wurden.

Das Anrufqualitäts-Dashboard enthält Informationen zur Anrufqualität und Zuverlässigkeit. Weitere Informationen zum Beheben von Problemen mithilfe der Anrufanalyse finden Sie unter [Aktivieren und Verwenden des Anrufqualitäts-Dashboards für Microsoft Teams und Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und [Verwenden der Anrufanalyse zur Behandlung schlechter Anrufqualität](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

Bei Anruffehlern stellt die Anrufanalyse Standard-SIP-Codes bereit, die Sie bei der Problembehandlung unterstützen. 

![Beispiel-SIP-Code für Anruffehler.](media/failed-response-code.png)

Die Anrufanalyse kann jedoch nur hilfreich sein, wenn Anrufe die internen Komponenten von Direct Routing erreichen und fehlschlagen. Bei Problemen mit der SBC-Kopplung oder bei Problemen, bei denen SIP "Invite" abgelehnt wurde (z. B. ist der Name des Trunk-FQDN falsch konfiguriert), hilft die Anrufanalyse nicht. Verweisen Sie in diesem Fall auf die SBC-Protokolle. Direct Routing sendet eine detaillierte Beschreibung der Probleme an die SBCs; Diese Probleme können aus den SBC-Protokollen gelesen werden.
