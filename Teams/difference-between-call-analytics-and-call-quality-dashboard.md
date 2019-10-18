---
title: Anrufanalyse- und Anrufqualitäts-Dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Erfahren Sie mehr über die anrufanalyse und das Anruf Qualitäts Dashboard, und wann Sie diese verwenden können, um Probleme mit der Anrufqualität zu überwachen und zu beheben.
ms.openlocfilehash: 70efd7f17189d9aac2236383a07cfc5fc0a37096
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571769"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Anrufanalyse- und Anrufqualitäts-Dashboard

Microsoft Teams und Skype for Business bieten Ihnen zwei Möglichkeiten, um Probleme mit der Anrufqualität zu überwachen und zu beheben: anrufanalyse und Anruf Qualitäts Dashboard (CQD). In diesem Artikel werden beide Methoden beschrieben, und Sie erfahren, welche Sie jeweils verwenden sollten.

Die Anrufanalyse und das Anrufqualitätsdashboard werden parallel ausgeführt und können unabhängig voneinander oder zusammen verwendet werden. Angenommen, ein Spezialist für Kommunikations Support stellt fest, dass er weitere Hilfe bei der Behandlung eines Anruf Problems benötigt. Der Support-Spezialist für Kommunikation leitet den Anruf an einen Communications Support Engineer weiter, der Zugriff auf Weitere Informationen in der anrufanalyse hat als der Spezialist für Kommunikationsunterstützung. Der Communications Support Engineer kann einen Netzwerktechniker wiederum auf ein Problem hinweisen. Der Netzwerktechniker kann CQD überprüfen, um festzustellen, ob ein Problem mit der allgemeinen Website eine Ursache für Anruf Probleme sein könnte.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Was ist die Anrufanalyse, und wann sollte ich sie verwenden?

**Die anrufanalyse steht jetzt im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com)zur Verfügung.** Wenn Sie alle Anrufinformationen und Daten für einen Benutzer anzeigen möchten, verwenden Sie die Registerkarte **Anrufverlauf** auf der Profilseite eines Benutzers. Wenn Sie die Registerkarte anzeigen möchten, suchen Sie entweder im Dashboard nach dem Benutzer, oder suchen Sie den Benutzer auf der Registerkarte **Benutzer** in der linken Navigationsleiste.

In der anrufanalyse werden detaillierte Informationen zu den Geräten, Netzwerken und Verbindungen angezeigt, die sich auf die Anrufe und Besprechungen für jeden Benutzer in einem Microsoft Teams-oder Skype for Business-Mandantenkonto beziehen. Warum hat dieser Benutzer heute Nachmittag einen schlechten Anruf? Mit der anrufanalyse kann ein Office 365-Administrator oder ein ausgebildeter Helpdesk-Agent das Gerät, das Netzwerk, die Konnektivität und andere Faktoren untersuchen, die mit einem Anruf zur Behandlung von Anrufqualität und Verbindungsproblemen in Microsoft Teams und Skype for Business zusammenhängen.

Wenn Sie diese Informationen für einen Benutzer im Microsoft Teams Admin Center anzeigen möchten, klicken Sie auf der Seite Benutzerdetail auf die Registerkarte **Anrufverlauf** , um alle Anrufe und Besprechungen für diesen Benutzer in den letzten 30 Tagen anzuzeigen.

![Screenshot aller Analytics-Benutzerdaten](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Wenn Sie weitere Informationen zu einer bestimmten Sitzung einschließlich detaillierter Medien-und Netzwerkstatistiken erhalten möchten, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Screenshot der Benutzersitzungsdaten der anrufanalyse](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Wenn Sie nicht-Administratoren (wie Helpdesk-Agents von einem externen Anbieter) die Verwendung von Anruf Analysen verwenden möchten, können Sie Berechtigungen zuweisen, damit Sie die anrufanalyse verwenden können, aber nicht auf das restliche Microsoft Teams Admin Center zugreifen können:
  
- **Helpdesk-Agents mit Berechtigungen für Communications Support Specialist**: Agents sehen eine begrenzte Anzahl von Daten und personenbezogene Informationen (PII) in der anrufanalyse. Sie können Probleme mit anrufen beheben, aber Sie eskalieren Probleme mit Besprechungen an einen Kommunikations Supporttechniker.
- **Helpdesk-Agents mit Berechtigungen für Communications Support Engineer**: Agents sehen alle verfügbaren Daten in der anrufanalyse und behandeln sowohl Anrufe als auch Besprechungen. Sie haben Vollzugriff auf Anruflisten und Kundeninformationen.

> [!NOTE]
> Die Rolle "Kommunikations Unterstützungs Spezialist" entspricht der Support Rolle "Stufe 1" im Preview-Portal, und die Rolle des Kommunikations Support Ingenieurs entspricht der Support Rolle der Stufe 2 aus dem Preview-Portal.

Weitere Informationen zu den Rollen für Communications Support Specialist und Communications Support Engineer finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md).

> [!IMPORTANT]
> Helpdesk-Agent-Berechtigungen und Upload der Netzwerktopologie stehen im Microsoft Teams Admin Center zur Verfügung. Kommunikations Supportspezialisten und Kommunikations Supporttechniker können dieses Portal verwenden, um auf die anrufanalyse und das Dashboard für die Anrufqualität zuzugreifen.

Details zur anrufanalyse finden Sie unter [Einrichten der anrufanalyse von Skype for Business](set-up-call-analytics.md). Weitere Informationen dazu, wie Helpdesk-Agents mit der anrufanalyse arbeiten können, finden Sie unter [Verwenden von Anruf Analysen zur Behandlung schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Was ist das Anrufqualitätsdashboard, und wann sollte ich es verwenden?
  
Die anrufanalyse soll Administratoren und Helpdesk-Mitarbeitern helfen, Probleme mit der Anrufqualität bei *bestimmten*anrufen zu beheben. Das Dashboard für die Anrufqualität (CQD) wurde entwickelt, um Teams-Administratoren, Skype for Business-Administratoren und Netzwerk Ingenieuren zu helfen, *ein Netzwerk zu optimieren*. CQD verschiebt den Fokus von bestimmten Benutzern und sucht stattdessen aggregierte Informationen für ein gesamtes Team oder eine Skype for Business-Organisation. Weitere Informationen finden Sie unter [Features des Anruf Qualitäts Dashboards für Teams und Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Angenommen, die schlechte Anrufqualität eines Benutzers ist auf ein Netzwerkproblem zurückzuführen, das auch viele andere Benutzer betrifft. Die individuelle Anruf Erfahrung wird in CQD nicht angezeigt, aber die Gesamtqualität der Anrufe, die über Microsoft Teams oder Skype for Business getätigt werden, wird erfasst. Bei CQD können die allgemeinen Muster deutlich werden, sodass Netzwerkingenieure fundierte Bewertungen der Anrufqualität vornehmen können. CQD stellt Berichte über Anruf Qualitäts Metriken bereit, mit denen Sie Einblicke in die allgemeine Anrufqualität, Server-Client-Streams, Client-Client-Streams und [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)für die Sprachqualität erhalten.
  
![Screenshot des Dashboards für die Anrufqualität.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD es Location-Enhanced Reports aggregierte Anrufqualität und Zuverlässigkeit im Gebäude eines Benutzers. Die Daten können ausgewertet werden, um festzustellen, ob das Problem für einen einzelnen Benutzer isoliert ist oder ein größeres Segment von Benutzern betrifft.

![Screenshot der Standort optimierten Berichte des Anruf Qualitäts Dashboards](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> Damit Gebäude-oder Endpunkt spezifische Ansichten in CQD aktiviert werden können, muss ein Administrator [Gebäude-oder Endpunktinformationen](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) auf der CQD-Seite "Mandantendaten hochladen" hochladen.

Wenn Sie möchten, dass Benutzer, die kein Administrator sind (wie Helpdesk-Agents), das Dashboard für die Anrufqualität verwenden, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die auch über die erforderlichen Berechtigungen für den Zugriff auf das Dashboard für die Anrufqualität verfügen:

- Globaler Administrator
- Globaler Leser
- Skype for Business-Administrator
- Teams-Dienstadministrator
- Teams-Kommunikationsadministrator
- Teams-Kommunikationssupporttechniker
- Teams Communications-Support Spezialist
- Berichtsleser

> [!NOTE]
> Der Team Communications Support Engineer, Team Communications Support Specialist und die Rollen des Berichts Lesers können Dateien auf der CQD-Seite "Mandantendaten hochladen" nicht ändern oder CQD für einen Mandanten aktivieren.

Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen](/office365/admin/add-users/about-admin-roles).

Weitere Informationen zu CQD finden Sie unter [aktivieren und Verwenden des Anruf Qualitäts Dashboards für Microsoft Teams und Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) sowie [Dimensionen und Measures, die im Anruf qualitätsdashboard für Microsoft Teams und Skype for Business Online zur Verfügung stehen](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Verwandte Themen

[Video: Übersicht über die Anrufqualität](https://aka.ms/teams-quality)

[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Aktivieren und Verwenden des Dashboards für die Anrufqualität für Microsoft Teams und Skype for Business Online](turning-on-and-using-call-quality-dashboard.md)
