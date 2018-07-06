---
title: Anruf Analyse- und Anrufqualität Dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business.
ms.openlocfilehash: 3871db21fef268f9589246b31ee285aa117d0412
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205086"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Anruf Analyse- und Anrufqualität Dashboard

Microsoft-Teams und Skype für Unternehmen bieten Ihnen zwei Möglichkeiten zur Überwachung und Problembehandlung Anrufqualität: Analytics aufrufen, und rufen Sie Qualitätsdashboard. In diesem Artikel werden beide Methoden beschrieben, und Sie erfahren, welche Sie jeweils verwenden sollten.
  
> [!NOTE]
> Anruf Analytics ist jetzt verfügbar in den Microsoft-Teams und Skype für Business Administrationscenter unter https://admin.teams.microsoft.com. Nur letzte 30 Tagen von Daten ist in Aufrufen Analytics verfügbar.
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Was ist die Anrufanalyse, und wann sollte ich sie verwenden?

Anruf Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und im Zusammenhang mit der bestimmte Aufrufe und Besprechungen für jeden Benutzer in einem Microsoft-Teams oder Skype für Konto Business Connectivity. Wenn Sie ein Office 365-Administrator sind, können Sie Analytics Aufrufen von Anruf Qualität und Verbindung Problemen in Microsoft-Teams und Skype für Unternehmen verwenden.

> [!NOTE]
> Helpdesk-Agent-Berechtigungen und Netzwerk-Topologie hochladen verfügbar in das neue Administratorportal in den nächsten Monaten.

Wenn Sie Benutzern ohne Administratorrechte (zum Beispiel Helpdesk-Agents eines externen Anbieters) die Verwendung der Anrufanalyse ermöglichen möchten, können Sie ihnen entsprechende Berechtigungen zuweisen, sodass sie zwar die Anrufanalyse verwenden, aber auf die übrigen Funktionen im Skype for Business Admin Center nicht zugreifen können: 
  
- **Helpdesk-Agents mit Berechtigungen der Stufe 1**: Die Agents sehen in der Anrufanalyse in begrenztem Umfang Daten und personenbezogene Informationen. Sie können Problembehandlungen für Anrufe ausführen, müssen aber Probleme mit Besprechungen an einen Agent der Stufe 2 weitergeben.
    
- **Helpdesk-Agents mit Berechtigungen der Stufe 2**: Die Agents sehen in der Anrufanalyse alle verfügbaren Daten und führen Problembehandlungen für Anrufe und Besprechungen aus. Sie haben Vollzugriff auf Anruflisten und Kundeninformationen.
    
Details zum Einrichten der Anrufanalyse finden Sie unter [Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md). Weitere Informationen zur Funktionsweise von Helpdesk-Agents mit Analysen aufrufen können finden Sie unter [Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Was ist das Anrufqualitätsdashboard, und wann sollte ich es verwenden?

Die Anrufanalyse liefert Ihnen detaillierte, spezifische Informationen zu der Anrufqualität, die die Benutzer wahrnehmen. Warum hatte der Benutzer Tony Smith heute Nachmittag einen Anruf mit schlechter Qualität? Analytics anrufen verwenden, kann eine Microsoft-Teams oder Skype für Business Admin oder geschult Helpdesk-Agent des Geräts, Netzwerk, Konnektivität und anderen Faktoren im Zusammenhang mit Tony Anruf untersuchen.
  
Während die Anrufanalyse dazu gedacht ist, Administratoren und Helpdesk-Agents bei der Behandlung von Problemen mit der Anrufqualität bei bestimmten Anrufen zu unterstützen, soll das Anrufqualitätsdashboard Skype for Business-Administratoren und Netzwerktechnikern beim Optimieren von Netzwerken helfen. Das Anrufqualitätsdashboard stellt nicht bestimmte Benutzer, sondern aggregierte Informationen für die gesamte Skype for Business-Organisation in den Mittelpunkt. 
  
Vielleicht ist Tonys schlechte Anrufqualität auf ein Netzwerkproblem zurückzuführen, das sich auch auf viele andere Benutzer auswirkt. Wie Tony diesen einzelnen Anruf wahrgenommen hat, ist im Anrufqualitätsdashboard nicht sichtbar, dafür wird die allgemeine Qualität der Anrufe über Skype for Business erfasst. Durch das Anrufqualitätsdashboard können allgemeine Muster sichtbar werden, die Netzwerktechnikern fundierte Bewertungen der Anrufqualität ermöglichen. Das Anrufqualitätsdashboard bietet Berichte zu Qualitätsmetriken, die Ihnen Aufschluss über die allgemeine Anrufqualität, über Datenströme zwischen Server und Clients sowie zwischen Clients und über die [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) zur Sprachqualität geben. 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Weitere Details finden Sie unter [Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Die Anrufanalyse und das Anrufqualitätsdashboard werden parallel ausgeführt und können unabhängig voneinander oder zusammen verwendet werden. Beispiel: Ein Agent der Stufe 1 kommt zu dem Schluss, dass er bei der Behandlung eines Anrufproblems weitere Hilfe benötigt. Der Agent der Stufe 1 gibt den Anruf an einen Agent der Stufe 2 weiter, der auf mehr Informationen in der Anrufanalyse zugreifen kann als der Agent der Stufe 1. Der Agent der Stufe 2 wiederum kann einen Netzwerktechniker über ein Problem benachrichtigen. Der Netzwerktechniker kann im Anrufqualitätsdashboard überprüfen, ob möglicherweise ein allgemeines standortbezogenes Problem zur Ursache der Anrufprobleme beiträgt.
  
Weitere Informationen zu CQD finden Sie unter [aktivieren, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](turning-on-and-using-call-quality-dashboard.md) und [Dimensionen und Measures in Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verfügbar](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>See Also
[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 
