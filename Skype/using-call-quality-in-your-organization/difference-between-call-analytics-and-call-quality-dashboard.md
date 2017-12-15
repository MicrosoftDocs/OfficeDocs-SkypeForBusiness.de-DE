---
title: "Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
description: "Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business."
---

# Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?

Sie haben in Skype for Business zwei Möglichkeiten, Probleme mit der Anrufqualität zu überwachen und zu behandeln: die Anrufanalyse und das Anrufqualitätsdashboard. In diesem Artikel werden beide Methoden beschrieben, und Sie erfahren, welche Sie jeweils verwenden sollten.
  
> [!NOTE]
> Die Anrufanalyse wird zurzeit als Vorschau bereitgestellt. Die hier beschriebenen Texte und Bilder entsprechen möglicherweise nicht dem, was Sie tatsächlich sehen. 
  
## Was ist die Anrufanalyse, und wann sollte ich sie verwenden?

Die Anrufanalyse zeigt detaillierte Informationen zu den Geräten und Netzwerken sowie zur Konnektivität im Zusammenhang mit bestimmten Anrufen und Besprechungen für die einzelnen Benutzer in einem Skype for Business-Konto. Wenn Sie Skype for Business-Administrator sind, können Sie die Anrufanalyse für die Problembehandlung im Zusammenhang mit der Anrufqualität und mit Verbindungen in Skype for Business verwenden.
  
Wenn Sie Benutzern ohne Administratorrechte (zum Beispiel Helpdesk-Agents eines externen Anbieters) die Verwendung der Anrufanalyse ermöglichen möchten, können Sie ihnen entsprechende Berechtigungen zuweisen, sodass sie zwar die Anrufanalyse verwenden, aber auf die übrigen Funktionen im Skype for Business Admin Center nicht zugreifen können: 
  
- **Helpdesk-Agents mit Berechtigungen der Stufe 1**: Die Agents sehen in der Anrufanalyse in begrenztem Umfang Daten und personenbezogene Informationen. Sie können Problembehandlungen für Anrufe ausführen, müssen aber Probleme mit Besprechungen an einen Agent der Stufe 2 weitergeben.
    
- **Helpdesk-Agents mit Berechtigungen der Stufe 2**: Die Agents sehen in der Anrufanalyse alle verfügbaren Daten und führen Problembehandlungen für Anrufe und Besprechungen aus. Sie haben Vollzugriff auf Anruflisten und Kundeninformationen.
    
Details zum Einrichten der Anrufanalyse finden Sie unter [Einrichten der Anrufanalyse von Skype for Business](set-up-skype-for-business-call-analytics.md). Weitere Informationen dazu, wie Helpdesk-Agents mit der Anrufanalyse arbeiten können, finden Sie unter [Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md).
  
## Was ist das Anrufqualitätsdashboard, und wann sollte ich es verwenden?

Die Anrufanalyse liefert Ihnen detaillierte, spezifische Informationen zu der Anrufqualität, die die Benutzer wahrnehmen. Warum hatte der Benutzer Tony Smith heute Nachmittag einen Anruf mit schlechter Qualität? Mit der Anrufanalyse können Skype for Business-Administratoren oder geschulte Helpdesk-Agents das Gerät, das Netzwerk, die Konnektivität und andere Faktoren im Zusammenhang mit Tonys Anruf untersuchen.
  
Während die Anrufanalyse dazu gedacht ist, Administratoren und Helpdesk-Agents bei der Behandlung von Problemen mit der Anrufqualität bei bestimmten Anrufen zu unterstützen, soll das Anrufqualitätsdashboard Skype for Business-Administratoren und Netzwerktechnikern beim Optimieren von Netzwerken helfen. Das Anrufqualitätsdashboard stellt nicht bestimmte Benutzer, sondern aggregierte Informationen für die gesamte Skype for Business-Organisation in den Mittelpunkt. 
  
Vielleicht ist Tonys schlechte Anrufqualität auf ein Netzwerkproblem zurückzuführen, das sich auch auf viele andere Benutzer auswirkt. Wie Tony diesen einzelnen Anruf wahrgenommen hat, ist im Anrufqualitätsdashboard nicht sichtbar, dafür wird die allgemeine Qualität der Anrufe über Skype for Business erfasst. Durch das Anrufqualitätsdashboard können allgemeine Muster sichtbar werden, die Netzwerktechnikern fundierte Bewertungen der Anrufqualität ermöglichen. Das Anrufqualitätsdashboard bietet Berichte zu Qualitätsmetriken, die Ihnen Aufschluss über die allgemeine Anrufqualität, über Datenströme zwischen Server und Clients sowie zwischen Clients und über die [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) zur Sprachqualität geben.
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Weitere Details finden Sie unter [Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_FeaturesOfTheCQD).
  
Die Anrufanalyse und das Anrufqualitätsdashboard werden parallel ausgeführt und können unabhängig voneinander oder zusammen verwendet werden. Beispiel: Ein Agent der Stufe 1 kommt zu dem Schluss, dass er bei der Behandlung eines Anrufproblems weitere Hilfe benötigt. Der Agent der Stufe 1 gibt den Anruf an einen Agent der Stufe 2 weiter, der auf mehr Informationen in der Anrufanalyse zugreifen kann als der Agent der Stufe 1. Der Agent der Stufe 2 wiederum kann einen Netzwerktechniker über ein Problem benachrichtigen. Der Netzwerktechniker kann im Anrufqualitätsdashboard überprüfen, ob möglicherweise ein allgemeines standortbezogenes Problem zur Ursache der Anrufprobleme beiträgt.
  
Weitere Informationen zum Anrufqualitätsdashboard finden Sie unter [Aktivieren und Verwenden des Anrufqualitäts-Dashboards für Microsoft Teams und Skype for Business Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md) und[Dimensionen und Measures anrufen Qualitätsdashboard für Microsoft Teams und Skype für Business Online zur Verfügung](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  

