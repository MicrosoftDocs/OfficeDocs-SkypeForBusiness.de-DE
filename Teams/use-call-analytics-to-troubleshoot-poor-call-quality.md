---
title: Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
description: Verwenden Sie Analytics rufen Sie Informationen zu Geräten, Netzwerke und Konnektivität Benutzer bei Problemen mit Microsoft-Teams und Skype für geschäftliche Anrufe und Besprechungen.
ms.openlocfilehash: 45512012beb07403239ccd2f681edb7f0f9eff41
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "29442413"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität

Anruf Analytics Unterstützung bei der Anruf mit der Realität Probleme mit Microsoft-Teams und Skype für Unternehmen. Rufen Sie Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und Konnektivität für die Aufrufe und Besprechungen von jedem Benutzer in Ihrer Office 365-Konto ein. Wenn Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzugefügt wurden, werden auch diese für jeden Anruf und jede Sitzung angezeigt. Anhand der über die Anrufanalyse verfügbaren Informationen können Sie herausfinden, warum bestimmte Benutzer eine schlechte Anruf- oder Besprechungsqualität wahrnehmen. 
  
## <a name="call-analytics-permissions"></a>Analytics Anrufberechtigungen

Als Administrator verfügen Sie über Vollzugriff auf alle Funktionen der Anrufanalyse. Darüber hinaus können Sie zu support-Mitarbeiter Azure Active Directory-Rollen zuweisen. Weisen Sie die Teams Communications Support-Spezialisten-Rolle für Benutzer, die eine begrenzte Ansicht des Analytics aufrufen verfügen soll. Benutzer Zugriff auf den vollen Funktionsumfang von Analytics aufrufen benötigen weisen Sie die Teams Communications Support Engineer Rolle zu. Beide Berechtigungsstufen verhindern des Zugriffs auf den Rest der Microsoft-Teams, &, Skype für Business Admin Center.

Supportmitarbeitern Communications behandeln Sie grundlegende Anrufqualität Probleme. Sie untersuchen keine Probleme bei Besprechungen. Stattdessen verwandte Informationen sammeln und dann an einen Supportmitarbeiter Communications ausweiten. Supporttechniker Communications finden Sie Informationen im detaillierten mithilfe von Anruflisten, die Communications Supportmitarbeitern ausgeblendet wurde. In der folgenden Tabelle bietet eine Übersicht über verfügbaren Informationen zu Communications-Support-Spezialisten und Communications-Supporttechniker, bei Verwendung von Analytics aufrufen.

Die Ihnen zugewiesene Berechtigungsstufe entscheidet, auf welche Informationen Sie in der Anrufanalyse zugreifen können:
  
- **Teams service oder Teams Communications-Administrator**: haben Sie Zugriff auf alle Informationen in Analytics aufrufen und die Teams & Skype für Business Admin Center.
    
- **Teams Communications unterstützen Specialist**: eine begrenzte Auswahl von Daten in Aufrufen Analytics angezeigt. Sie können Anrufe Problembehandlung, aber Sie werden Probleme bei Besprechungen an einem Teams Communications Supporttechniker übergeben. Sie haben keinen Zugriff auf den Rest der Teams &, Skype für Business Admin Center.
    
- **Teams Communications Engineer Unterstützung**: finden Sie unter alle verfügbaren Daten in Analytics aufrufen und Problembehandlung bei Anrufen und Besprechungen helfen. Sie haben keinen Zugriff auf den Rest der Teams &, Skype für Business Admin Center.
    
> [!NOTE]
> Die Rolle des Supports Specialist von Communications Support der Ebene 1 entspricht, und die Kommunikation Support Engineer Rolle Support der Ebene 2 entspricht.

Weitere Informationen zu Administratorrollen Teams finden Sie unter [Verwendung von Microsoft-Teams Administratorrollen zum Verwalten von Teams](using-admin-roles.md). Einen ausführlichen Vergleich der Unterstützung von Teams Communications Experte und Teams Communications Engineer Rollen unterstützen, finden Sie unter [Einrichten von Anrufen Analytics](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Finden Sie unter Ihrer Teams und Skype Business Admin Wenn Sie Hilfe mit Berechtigungen benötigen.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Behandeln von Problemen mit der Anrufqualität mithilfe der Anrufanalyse

1. Melden Sie sich mit Ihren Teams Communications Support oder Teams-Admin-Anmeldeinformationen.

2. Besuchen Sie das Office 365 Administrationscenter, und melden Sie sich mit Ihrem Konto arbeiten oder Schule. Wechseln Sie in Ihrem Webbrowser zu *https://adminportal.services.skypeforbusiness.com*.

3. Wählen Sie **Admin zentriert** > **Teams & Skype**. 
    
4. Klicken Sie im **Dashboard**in **Benutzersuche**starten Sie entweder den Namen eingeben oder sip-Adresse des Benutzers, dessen Anrufe zu beheben, oder wählen Sie **Ansicht, die Benutzer** zum Anzeigen einer Liste von Benutzern verwendet werden soll.
    
    ![Screenshot des Felds Benutzersuche im of Analytics Aufrufen der Teams & Skype für Business Admin Center.](media/use-call-analytics-to-troubleshoot-image-1.png)
  
5. Wählen Sie den Benutzer aus der Liste aus.

6. Wählen Sie **die Anrufliste...** aus, und wählen Sie dann den Anruf oder Besprechung, den Sie behandeln möchten.
    
    ![Screenshot zeigt die Seite ' Versionsverlauf Anruf ' für einen Benutzer.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
7. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.
    
    Kleinere Probleme werden in der Sitzungsdetails für jeden Anruf oder Besprechung gelb angezeigt. (Beispielsweise sind im folgenden Screenshot, der Werte in Gelb für durchschnittliche Jitter, Max Jitter und durchschnittliche paketverlustrate.) Ist etwas Gelb, es ist außerhalb der normalen Bereich und als Beitrag für dieses Problem, aber es ist wahrscheinlich nicht die wichtigste Ursache des Problems. Wenn etwas rot angezeigt wird, ist ein Problem, und es ist wahrscheinlich die wichtigste Ursache für die Qualität der Anrufe schlechter Qualität für diese Sitzung. 
    
    ![Screenshot zeigt die Registerkarte Erweitert des Anrufverlaufs eines Benutzers ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
In seltenen Fällen ist nicht für audiositzungen Daten Quality of Experience empfangen. Häufig ist dies durch den Aufruf ablegen und Verbindung mit dem Client beenden verursacht. In diesem Fall ist die Bewertung der Sitzung **nicht verfügbar**.
  
Für audio-Sitzungen, die Daten Quality of Experience (QoE) verfügen, werden in der folgenden Tabelle Hauptprobleme, die eine Sitzung als **schlechte**qualifiziert werden, beschrieben.
  
|**Problem**|**Bereich**|**Beschreibung**|
|:-----|:-----|:-----|
|Verbindungsaufbau  <br/> |Sitzung  <br/> |Der Fehlercode 20-29 Ms-Diagnose zeigt den Anruf ist ein Fehler aufgetreten. Der Benutzer konnte nicht dem Anruf oder der Besprechung teilnehmen.  <br/> |
|Audio Netzwerk klassifiziert Anrufe schlechter Qualität  <br/> |Sitzung  <br/> |Qualität Netzwerkprobleme (beispielsweise Paketverlust, Jitter, NMOS-Beeinträchtigung, Zeit oder ausgeblendeter Verhältnis) sind aufgetreten. Weitere Informationen über die Bedingungen, die zum Klassifizieren von schlechter Anrufe verwendet finden Sie unter in diesem [Blogbeitrag Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Gerät nicht funktionsfähig  <br/> |Gerät  <br/> | Ein Gerät ist nicht ordnungsgemäß funktioniert. Gerät nicht funktioniert Verhältnisse verwendet werden: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Anrufen Analytics](set-up-call-analytics.md)

[Anruf Analyse- und Anrufqualität Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
