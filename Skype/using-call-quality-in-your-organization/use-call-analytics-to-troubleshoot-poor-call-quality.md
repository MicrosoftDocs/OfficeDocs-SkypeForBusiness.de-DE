---
title: "Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Skype für Unternehmen die Anrufqualität"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Verwenden Sie Analytics rufen Sie Informationen zu Geräten, Netzwerke und Konnektivität Benutzer bei Problemen mit Skype für geschäftliche Anrufe und Besprechungen."
ms.openlocfilehash: 043c7eac6099f23217c155ad91bf818aa4e57892
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Skype für Unternehmen die Anrufqualität

Anruf Analytics hilft Ihnen beim Aufruf der Realität bei Problemen mit der Skype für Unternehmen. Rufen Sie Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und Konnektivität für die Aufrufe und Besprechungen von jedem Benutzer in Ihrer Skype für Business-Konto ein. Beim Erstellen von Websites und Mandanten Informationen hinzugefügt wurde Analyse aufrufen, wird auch für jeden Anruf und die Sitzung angezeigt. Informationen über Analytics aufrufen kann Ihnen herauszufinden, warum ein Benutzer einen Anruf schlechter Qualität aufwies oder meeting wünschen. 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Problembehandlung bei Aufruf Qualitätsprobleme mit Analytics aufrufen

Die Ihnen zugewiesenen Berechtigungsstufen bestimmt, welche Art von Informationen haben Sie Zugriff auf in Analytics aufrufen:
  
- **Skype für Business Admin**: haben Sie Zugriff auf alle Informationen in Analytics aufrufen und die Skype für Business Admin Center.
    
- **Helpdesk-Agent mit den Berechtigungen der Stufe 1**: eine begrenzte Auswahl von Daten in Aufrufen Analytics angezeigt. Sie können Anrufe Problembehandlung, aber Sie werden Probleme bei Besprechungen an einem Agent Stufe 2 übergeben. Sie haben keinen Zugriff auf den Rest der der Skype für Business Admin Center.
    
- **Helpdesk-Agent mit den Berechtigungen der Stufe 2**: finden Sie unter alle verfügbaren Daten in Analytics aufrufen und Problembehandlung bei Anrufen und Besprechungen helfen. Sie haben keinen Zugriff auf den Rest der der Skype für Business Admin Center.
    
Wenn Sie Hilfe mit Berechtigungen benötigen, finden Sie unter Ihrer Skype für Business Admin.
  
 **Öffnen Sie als Agent Helpdesk Stufe 1 oder Stufe 2 Analytics aufrufen**
  
1. Besuchen Sie das Office 365 Administrationscenter, und melden Sie sich mit Ihrem Konto arbeiten oder Schule. Wechseln Sie in Ihrem Webbrowser zu *https://adminportal.services.skypeforbusiness.com*.
    
2. Bei der **Benutzersuche**, beginnen Sie mit den Namen oder die Sip-Adresse des Benutzers, dessen Anrufe zu behandeln, und wählen Sie dann den Benutzer aus der Liste.
    
    ![Screenshot des Suchfelds für Benutzer von Anrufen Analytics in der Skype für Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Wählen Sie in **die Anrufliste...**den Anruf oder Besprechung, den Sie behandeln möchten.
    
    ![Screenshot zeigt die Seite ' Versionsverlauf Anruf ' für einen Benutzer mit Informationen wie Kontaktdetails für den Benutzer, eine Übersicht über die 7-Tage-Qualität und Aktivität für Besprechungen und Telefonkonferenzen und eine Übersicht über Datumsangaben und Uhrzeiten, Empfänger und Audioqualität,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Wählen Sie die Registerkarte **Erweitert** , und suchen Sie nach gelbe und rote Elemente, die Anruf schlechter Qualität oder Verbindung Probleme hinweisen.
    
    Kleinere Probleme werden in der Sitzungsdetails für jeden Anruf oder Besprechung gelb angezeigt. (Beispielsweise sind im folgenden Screenshot, der Werte in Gelb für durchschnittliche Jitter, Max Jitter und durchschnittliche paketverlustrate.) Ist etwas Gelb, es ist außerhalb der normalen Bereich und als Beitrag für dieses Problem, aber es ist wahrscheinlich nicht die wichtigste Ursache des Problems. Wenn etwas rot angezeigt wird, ist ein Problem, und es ist wahrscheinlich die wichtigste Ursache für die Qualität der Anrufe schlechter Qualität für diese Sitzung. 
    
    ![Screenshot zeigt die Registerkarte Erweitert des Anrufverlaufs eines Benutzers mit dem eingehenden Netzwerkabschnitt erweitert, um anzuzeigen, dass die Daten für die durchschnittliche Jitter, max Jitter und durchschnittliche paketverlustrate in einer gelb angezeigt werden, was bedeutet, dass sie kleinere Probleme sind.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
In seltenen Fällen ist nicht für audiositzungen Daten Quality of Experience empfangen. Häufig ist dies durch den Aufruf ablegen und Verbindung mit dem Client beenden verursacht. In diesem Fall ist die Sitzung Bewertung "nicht verfügbar".
  
Für audio-Sitzungen, die Daten Quality of Experience (QoE) verfügen, wird beschrieben, in der folgenden Tabelle Hauptprobleme, die für die Verwendung eine Sitzung als "schlecht".
  
|**Problem**|**Bereich**|**Beschreibung**|
|:-----|:-----|:-----|
|Verbindungsaufbau  <br/> |Sitzung  <br/> |Der Fehlercode 20-29 Ms-Diagnose zeigt den Anruf ist ein Fehler aufgetreten. Der Benutzer konnte nicht dem Anruf oder der Besprechung teilnehmen.  <br/> |
|Audio Netzwerk klassifiziert Anrufe schlechter Qualität  <br/> |Sitzung  <br/> |Qualität Netzwerkprobleme aufgetreten in Bereichen wie Paketverlust, Jitter, NMOS-Beeinträchtigung, Zeit, oder Verhältnis verborgen. Weitere Informationen über die Bedingungen, die zum Klassifizieren von schlechter Anrufe verwendet finden Sie unter in diesem [Blogbeitrag Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Gerät nicht funktionsfähig  <br/> |Gerät  <br/> | Ein Gerät ist nicht ordnungsgemäß funktioniert. Gerät nicht funktioniert Verhältnisse verwendet werden: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype für BA aufrufen](set-up-call-analytics.md)

[Was ist der Unterschied zwischen Analytics aufrufen, und rufen Sie Qualitätsdashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)

