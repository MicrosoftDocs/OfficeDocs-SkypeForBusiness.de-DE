---
title: Anrufanalyse- und Anrufqualitäts-Dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
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
ms.openlocfilehash: b3a65c4fa6a3dfe8de6b4ef70cd7657661cf4dc9
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178669"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Anrufanalyse- und Anrufqualitäts-Dashboard

Microsoft-Teams und Skype für Unternehmen bieten Ihnen zwei Möglichkeiten zur Überwachung und Problembehandlung Anrufqualität: Analytics aufrufen, und rufen Sie Qualitätsdashboard. In diesem Artikel werden beide Methoden beschrieben, und Sie erfahren, welche Sie jeweils verwenden sollten.

Die Anrufanalyse und das Anrufqualitätsdashboard werden parallel ausgeführt und können unabhängig voneinander oder zusammen verwendet werden. Angenommen Sie, ein Communications Supportspezialisten bestimmt, dass sie einen Anruf Problembehandlung Weitere Hilfe benötigen. Der Communications-Supportspezialisten übergibt den Anruf an einen Supportmitarbeiter Communications, wer hat Zugriff auf Weitere Informationen im Analytics rufen Sie die Kommunikation Specialist unterstützt. Infolgedessen kann der Supporttechniker Communications Netzwerktechniker auf ein Problem benachrichtigen. Die Netzwerktechniker kann CQD, um festzustellen, ob eine allgemeine Problem im Zusammenhang mit der Website die Mitwirkenden Ursache für Anruf Probleme sein konnte überprüfen.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Was ist die Anrufanalyse, und wann sollte ich sie verwenden?

**Anruf Analytics ist jetzt im Microsoft-Teams, Administrationscenter verfügbar.** Um alle diese Informationen und Daten für einen Benutzer anzuzeigen, verwenden Sie die Registerkarte **Anrufverlauf** . Hierzu können Sie auf der Profilseite des Benutzers suchen, indem Sie entweder suchen für den Benutzer aus dem Dashboard, oder suchen den Benutzer von **Benutzern** im linken Navigationsbereich.

> [!IMPORTANT]
> Helpdesk-Agent-Berechtigungen und Netzwerk-Topologie hochladen verfügbar in das neue Administratorportal in den nächsten Monaten. Sie können in der Zwischenzeit weiterhin verwenden https://adminportal.services.skypeforbusiness.com für Ebene 1 und Ebene 2 Helpdesk-Zugriff.
  

Anruf Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und im Zusammenhang mit der bestimmte Aufrufe und Besprechungen für jeden Benutzer in einem Microsoft-Teams oder Skype für Konto Business Connectivity. Warum diese Benutzer einen Anruf schlechter Qualität dieses Tag? Analytics anrufen verwenden, kann ein Office 365 Admin oder geschult Helpdesk-Agent des Geräts, Netzwerk, Konnektivität und anderen Faktoren im Zusammenhang mit seinen Anruf von Anruf Qualität und Verbindung Problemen in Microsoft-Teams und Skype für Business überprüfen.

Wenn Sie diese Informationen für einen Benutzer in der Microsoft-Teams-Verwaltungskonsole angezeigt wird, klicken Sie auf der Registerkarte **Anrufverlauf** für diesen Benutzer auf der Seite Benutzer Detail zeigt alle Anrufe und Besprechungen, dass der Benutzer in den letzten 30 Tagen teilgenommen hat.

![Rufen Sie Analytics Benutzerdaten.](media/call-analytics-user-data.png)

Wenn Sie weitere Informationen zu einer bestimmten Sitzung einschließlich detaillierte Medien und Netzwerke Statistiken erhalten möchten, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Rufen Sie Analytics Benutzersitzungsdaten.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Nicht-Administratoren, beispielsweise einen externen Anbieter, Helpdesk-Agents auf Wunsch können zum Aufrufen, Analyse, verwenden Sie Berechtigungen zuweisen, damit Analytics aufrufen können, dieser Zugriff jedoch nicht den Rest von der Microsoft-Teams-Verwaltungskonsole: 
  
- **Helpdesk-Agents mit Communications unterstützen Specialist Berechtigungen**: Agents finden Sie unter eine begrenzte Auswahl von Daten und personenbezogene Informationen (PII) in Analytics aufrufen. Sie können Anrufe Problembehandlung, aber sie werden Probleme bei Besprechungen an einen Supporttechniker Communications übergeben.
    
- **Helpdesk-Agents mit Communications unterstützen Engineer Berechtigungen**: Agents finden Sie unter alle verfügbaren Daten in Analytics aufrufen und Problembehandlung bei Anrufen und Besprechungen. Sie haben Vollzugriff auf Anruflisten und Kundeninformationen.

> [!NOTE]
> Die Rolle des Supports Specialist von Communications Support der Ebene 1 entspricht, und die Kommunikation Support Engineer Rolle Support der Ebene 2 entspricht.

Weitere Informationen zu den Communications Supportspezialisten und Kommunikation unterstützen Engineer Rollen finden Sie [Administratorrollen zum Verwalten von Teams verwenden Microsoft-Teams](using-admin-roles.md).

> [!IMPORTANT]
> Helpdesk-Agent-Berechtigungen und Hochladen der Netzwerk-Topologie sind im Microsoft-Teams, Administrationscenter verfügbar. Supportmitarbeitern Communications und Communications Supporttechniker können dieses Portal Analytics aufrufen und das Aufrufen Qualitätsdashboard zugreifen.
    
Details zum Einrichten der Anrufanalyse finden Sie unter [Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md). Weitere Informationen zur Funktionsweise von Helpdesk-Agents mit Analysen aufrufen können finden Sie unter [Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Was ist das Anrufqualitätsdashboard, und wann sollte ich es verwenden?
  
Wo Zertifizierungsstelle soll helfen, Administratoren und Helpdesk-Agents Problembehandlung Anrufqualität für bestimmte Aufrufe aufrufen Quality Dashboard (CQD) soll helfen, Microsoft-Teams Admins, Skype Informationen zu Business-Administratoren, und Netzwerktechniker Optimieren der Leistung von einem Netzwerk. CQD verschiebt den Fokus von bestimmten Benutzern und stattdessen untersucht aggregierte Informationen für ein ganzes Microsoft-Teams oder Skype für Business-Organisation. Weitere Details finden Sie unter [Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Möglicherweise ist der Benutzer Anrufe schlechter Qualität Qualität aufgrund ein Problem mit der, die auch zahlreiche andere Benutzer auswirkt. Die Erfahrung einzelner Anruf nicht in CQD sichtbar ist, aber die allgemeine Qualität der Anrufe, die mithilfe von Microsoft-Teams oder Skype für Unternehmen werden erfasst. Durch das Anrufqualitätsdashboard können allgemeine Muster sichtbar werden, die Netzwerktechnikern fundierte Bewertungen der Anrufqualität ermöglichen. CQD bietet Berichte über die Anruf-Qualitätsmetriken, mit denen Sie Einblicke in insgesamt Qualität, Server-Client-Streams, Client-Client-Streams und Sprachqualität [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)aufrufen.
  
![Screenshot des Anrufqualität Dashboard. Registerkarten dargestellt sind allgemeine Anrufqualität - Client, Client - Server-Client und VoIP Qualität Vereinbarung zum SERVICELEVEL.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Mit der Hilfe CQDs Location-Enhanced Berichte können aggregierte Anrufqualität und Zuverlässigkeit innerhalb des Benutzers zum Erstellen von bewertet werden, um festzustellen, ob das Problem zu einem einzelnen Benutzer isoliert wird oder wirkt sich auf einer größeren Benutzersegment.

![Screenshot des Anrufqualität Dashboard Speicherort mit erhöhter Berichte. Registerkarten dargestellt sind Übersicht, Gebäude - verkabelt, Gebäude - WiFi und Mobile (LZF). Ein Filter wird angewendet, um die Datenströme in einem bestimmten Gebäude anzuzeigen.](media/call-quality-dashboard-location-enhanced-reports-building-selection.png)

> [!NOTE]
> Um-spezifische Erstellen von Ansichten in CQD zu aktivieren, müssen ein Administrator auf CQDs Mandanten Datenupload Seite [Informationen zum Erstellen von hochladen](turning-on-and-using-call-quality-dashboard.md#BKMKBuildingInformationUpload) .

Nicht-Administratoren, wie etwa Helpdesk-Agents auf Wunsch können zum Aufrufen Dashboard für die Qualität, verwenden Sie diese Benutzer die Rolle **Teams Communications Supporttechniker**, **Teams Communications Supportspezialisten**oder **Leser von Berichten** zuweisen. Benutzer mit den folgenden Rollen können aufrufen Qualitätsdashboard zugreifen:

- Globaler Administrator
- Skype für Business-Administratoren
- Teams-Dienstadministrator
- Teams-Kommunikationsadministrator
- Teams-Kommunikationssupporttechniker
- Teams Communications-Supportspezialisten
- Leser von Berichten

> [!NOTE]
> Die Rollen Teams Communications Supporttechniker, Teams Communications Supportspezialisten und Berichte Reader keine Dateien auf CQDs Mandanten Datenupload Seite ändern oder CQD für einen Mandanten zu aktivieren.

Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen](/office365/admin/add-users/about-admin-roles).

Weitere Informationen zu CQD finden Sie unter [aktivieren, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](turning-on-and-using-call-quality-dashboard.md) und [Dimensionen und Measures in Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verfügbar](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Verwandte Themen

[Video: Übersicht über die Qualität aufrufen](https://aka.ms/teams-quality)

[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einschalten und Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online](turning-on-and-using-call-quality-dashboard.md)