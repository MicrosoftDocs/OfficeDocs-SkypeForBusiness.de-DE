---
title: Anruf Analyse- und Anrufqualität Dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Informationen Sie zu Analytics aufrufen und Qualitätsdashboard aufrufen und verwenden sie zur Überwachung und Problembehandlung Anrufqualität.
ms.openlocfilehash: 8f664dfc8a609e23485f1dd935c00d8e5a745943
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742989"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Anruf Analyse- und Anrufqualität Dashboard

Microsoft-Teams und Skype für Unternehmen bieten Ihnen zwei Möglichkeiten zur Überwachung und Problembehandlung Anrufqualität: Analytics aufrufen, und rufen Sie Qualitätsdashboard. In diesem Artikel werden beide Methoden beschrieben, und Sie erfahren, welche Sie jeweils verwenden sollten.
  
**Anruf Analytics wird jetzt in der Microsoft-Teams und Skype für Business Admin Center verfügbar.** Um alle diese Informationen und Daten für einen Benutzer anzuzeigen, verwenden Sie die Registerkarte **Anrufverlauf** . Hierzu können Sie auf der Profilseite des Benutzers suchen, indem Sie entweder suchen für den Benutzer aus dem Dashboard, oder suchen den Benutzer von **Benutzern** im linken Navigationsbereich.

> [!IMPORTANT]
> Helpdesk-Agent-Berechtigungen und Netzwerk-Topologie hochladen verfügbar in das neue Administratorportal in den nächsten Monaten. Sie können in der Zwischenzeit weiterhin verwenden https://adminportal.services.skypeforbusiness.com für Ebene 1 und Ebene 2 Helpdesk-Zugriff.
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Was ist die Anrufanalyse, und wann sollte ich sie verwenden?

Anruf Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und im Zusammenhang mit der bestimmte Aufrufe und Besprechungen für jeden Benutzer in einem Microsoft-Teams oder Skype für Konto Business Connectivity. Wenn Sie ein Office 365-Administrator sind, können Sie Analytics Aufrufen von Anruf Qualität und Verbindung Problemen in Microsoft-Teams und Skype für Unternehmen verwenden.

Wenn Sie diese Informationen für einen Benutzer in der Microsoft-Teams & Skype für Business Admin Center angezeigt wird, klicken Sie auf der Registerkarte **Anrufverlauf** für diesen Benutzer auf der Seite Benutzer Detail zeigt alle Anrufe und Besprechungen, dass der Benutzer in den letzten 30 Tagen teilgenommen hat.

![Rufen Sie Analytics Benutzerdaten.](media/call-analytics-user-data.png)

Wenn Sie weitere Informationen zu einer bestimmten Sitzung einschließlich detaillierte Medien und Netzwerke Statistiken erhalten möchten, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Rufen Sie Analytics Benutzersitzungsdaten.](media/call-analytics-user-data-session.png)

Wenn Sie nicht-Administratoren, beispielsweise einen externen Anbieter, Helpdesk-Agents möchten können Analytics anrufen verwenden, um Sie Berechtigungen zuweisen, damit Analytics aufrufen können, dieser Zugriff jedoch nicht den Rest von der Microsoft-Teams & Skype für Business Admin Center: 
  
- **Helpdesk-Agents mit Communications unterstützen Specialist Berechtigungen**: Agents finden Sie unter eine begrenzte Auswahl von Daten und personenbezogene Informationen (PII) in Analytics aufrufen. Sie können Anrufe Problembehandlung, aber sie werden Probleme bei Besprechungen an einen Supporttechniker Communications übergeben.
    
- **Helpdesk-Agents mit Communications unterstützen Engineer Berechtigungen**: Agents finden Sie unter alle verfügbaren Daten in Analytics aufrufen und Problembehandlung bei Anrufen und Besprechungen. Sie haben Vollzugriff auf Anruflisten und Kundeninformationen.

> [!NOTE]
> Die Rolle des Supports Specialist von Communications Support der Ebene 1 entspricht, und die Kommunikation Support Engineer Rolle Support der Ebene 2 entspricht.

Weitere Informationen zu den Communications Supportspezialisten und Kommunikation unterstützen Engineer Rollen finden Sie [Administratorrollen zum Verwalten von Teams verwenden Microsoft-Teams](using-admin-roles.md).

> [!IMPORTANT]
> Helpdesk-Agent-Berechtigungen und Hochladen der Netzwerk-Topologie sind in der Microsoft-Teams & Skype für Business Admin Center verfügbar. Supportmitarbeitern Communications und Communications Supporttechniker können dieses Portal Analytics aufrufen und das Aufrufen Qualitätsdashboard zugreifen.
    
Details zum Einrichten der Anrufanalyse finden Sie unter [Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md). Weitere Informationen zur Funktionsweise von Helpdesk-Agents mit Analysen aufrufen können finden Sie unter [Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Was ist das Anrufqualitätsdashboard, und wann sollte ich es verwenden?

Die Anrufanalyse liefert Ihnen detaillierte, spezifische Informationen zu der Anrufqualität, die die Benutzer wahrnehmen. Warum hatte der Benutzer Tony Smith heute Nachmittag einen Anruf mit schlechter Qualität? Analytics anrufen verwenden, kann eine Microsoft-Teams oder Skype für Business Admin oder geschult Helpdesk-Agent des Geräts, Netzwerk, Konnektivität und anderen Faktoren im Zusammenhang mit Tony Anruf untersuchen.
  
Während die Anrufanalyse dazu gedacht ist, Administratoren und Helpdesk-Agents bei der Behandlung von Problemen mit der Anrufqualität bei bestimmten Anrufen zu unterstützen, soll das Anrufqualitätsdashboard Skype for Business-Administratoren und Netzwerktechnikern beim Optimieren von Netzwerken helfen. Das Anrufqualitätsdashboard stellt nicht bestimmte Benutzer, sondern aggregierte Informationen für die gesamte Skype for Business-Organisation in den Mittelpunkt. 
  
Vielleicht ist Tonys schlechte Anrufqualität auf ein Netzwerkproblem zurückzuführen, das sich auch auf viele andere Benutzer auswirkt. Wie Tony diesen einzelnen Anruf wahrgenommen hat, ist im Anrufqualitätsdashboard nicht sichtbar, dafür wird die allgemeine Qualität der Anrufe über Skype for Business erfasst. Durch das Anrufqualitätsdashboard können allgemeine Muster sichtbar werden, die Netzwerktechnikern fundierte Bewertungen der Anrufqualität ermöglichen. Das Anrufqualitätsdashboard bietet Berichte zu Qualitätsmetriken, die Ihnen Aufschluss über die allgemeine Anrufqualität, über Datenströme zwischen Server und Clients sowie zwischen Clients und über die [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) zur Sprachqualität geben. 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Weitere Details finden Sie unter [Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Die Anrufanalyse und das Anrufqualitätsdashboard werden parallel ausgeführt und können unabhängig voneinander oder zusammen verwendet werden. Angenommen Sie, ein Communications Supportspezialisten bestimmt, dass sie einen Anruf Problembehandlung Weitere Hilfe benötigen. Der Communications-Supportspezialisten übergibt den Anruf an einen Supportmitarbeiter Communications, wer hat Zugriff auf Weitere Informationen im Analytics rufen Sie die Kommunikation Specialist unterstützt. Infolgedessen kann der Supporttechniker Communications Netzwerktechniker auf ein Problem benachrichtigen. Die Netzwerktechniker kann CQD, um festzustellen, ob eine allgemeine Problem im Zusammenhang mit der Website die Mitwirkenden Ursache für Anruf Probleme sein konnte überprüfen.
  
Weitere Informationen zu CQD finden Sie unter [aktivieren, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](turning-on-and-using-call-quality-dashboard.md) und [Dimensionen und Measures in Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verfügbar](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Verwandte Themen

[Video: Übersicht über die Qualität aufrufen](https://aka.ms/teams-quality)

[Einrichten von Anrufen Analytics](set-up-call-analytics.md)

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einschalten und Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online](turning-on-and-using-call-quality-dashboard.md)