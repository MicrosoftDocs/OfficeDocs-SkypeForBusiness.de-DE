---
title: Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
description: Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings.
ms.openlocfilehash: 8f782a18dd7cb7fe7cbae73c7bd43b3e44c6928c
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business

Mithilfe der Anrufanalyse können Sie Probleme im Zusammenhang mit Anrufen oder Verbindungen in Skype for Business behandeln. Die Anrufanalyse zeigt detaillierte Informationen zu den Geräten und Netzwerken sowie zur Konnektivität für die Anrufe und Besprechungen der einzelnen Benutzer in Ihrem Skype for Business-Konto. Wenn Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzugefügt wurden, werden auch diese für jeden Anruf und jede Sitzung angezeigt. Anhand der über die Anrufanalyse verfügbaren Informationen können Sie herausfinden, warum bestimmte Benutzer eine schlechte Anruf- oder Besprechungsqualität wahrnehmen. 
  
> [!NOTE]
> Die Anrufanalyse wird zurzeit als Vorschau bereitgestellt. Die hier beschriebenen Texte und Bilder entsprechen möglicherweise nicht dem, was Sie tatsächlich sehen.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Behandeln von Problemen mit der Anrufqualität mithilfe der Anrufanalyse

Die Ihnen zugewiesene Berechtigungsstufe entscheidet, auf welche Informationen Sie in der Anrufanalyse zugreifen können:
  
- **Skype for Business-Administrator**: Sie können auf alle Informationen in der Anrufanalyse und im Skype for Business Admin Center zugreifen.
    
- **Helpdesk-Agent mit Berechtigungen der Stufe 1**: Sie sehen in der Anrufanalyse begrenzte Daten. Sie können Problembehandlungen für Anrufe ausführen, geben aber Probleme mit Besprechungen an einen Agent der Stufe 2 weiter. Auf die übrigen Funktionen im Skype for Business Admin Center können Sie nicht zugreifen.
    
- **Helpdesk-Agent mit Berechtigungen der Stufe 2**: Sie sehen in der Anrufanalyse alle verfügbaren Daten und können bei Problembehandlungen für Anrufe und Besprechungen helfen. Auf die übrigen Funktionen im Skype for Business Admin Center können Sie nicht zugreifen.
    
Wenden Sie sich an Ihren Skype for Business-Administrator, wenn Sie Hilfe im Zusammenhang mit Berechtigungen benötigen.
  
 **Öffnen der Anrufanalyse als Helpdesk-Agent der Stufe 1 oder 2**
  
1. Besuchen Sie das Office 365 Administrationscenter, und melden Sie sich mit Ihrem Konto arbeiten oder Schule. Wechseln Sie in Ihrem Webbrowser zu *https://adminportal.services.skypeforbusiness.com*.
    
2. Beginnen Sie in **Benutzersuche**, den Namen oder die SIP-Adresse des Benutzers einzugeben, für dessen Anrufe Sie eine Problembehandlung ausführen möchten. Wählen Sie dann den Benutzer in der Liste aus.
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Wählen Sie in **Call history** (Anrufliste) den Anruf oder die Besprechung aus, für den bzw. für die Sie eine Problembehandlung ausführen möchten.
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.
    
    In den Sitzungsdetails für die einzelnen Anrufe oder Besprechungen werden geringfügige Probleme gelb dargestellt. (Im folgenden Screenshot zum Beispiel werden die Werte für „Durchschnittlicher Jitter", „Max. Jitter" und „Durchschnittliche Paketverlustrate" in Gelb angezeigt.) Gelbe Elemente befinden sich außerhalb des normalen Bereichs und können zum Problem beitragen. Sie sind aber wahrscheinlich nicht die Hauptursache des Problems. Rote Elemente weisen auf ein wichtiges Problem hin und stellen wahrscheinlich die Hauptursache für die schlechte Anrufqualität in dieser Sitzung dar. 
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
In seltenen Fällen ist nicht für audiositzungen Daten Quality of Experience empfangen. Häufig ist dies durch den Aufruf ablegen und Verbindung mit dem Client beenden verursacht. In diesem Fall ist die Sitzung Bewertung "nicht verfügbar".
  
Für audio-Sitzungen, die Daten Quality of Experience (QoE) verfügen, wird beschrieben, in der folgenden Tabelle Hauptprobleme, die für die Verwendung eine Sitzung als "schlecht".
  
|**Problem**|**Bereich**|**Beschreibung**|
|:-----|:-----|:-----|
|Verbindungsaufbau  <br/> |Sitzung  <br/> |Der Fehlercode 20-29 Ms-Diagnose zeigt den Anruf ist ein Fehler aufgetreten. Der Benutzer konnte nicht dem Anruf oder der Besprechung teilnehmen.  <br/> |
|Audio Netzwerk klassifiziert Anrufe schlechter Qualität  <br/> |Sitzung  <br/> |Qualität Netzwerkprobleme aufgetreten in Bereichen wie Paketverlust, Jitter, NMOS-Beeinträchtigung, Zeit, oder Verhältnis verborgen. Weitere Informationen über die Bedingungen, die zum Klassifizieren von schlechter Anrufe verwendet finden Sie unter in diesem [Blogbeitrag Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Gerät nicht funktionsfähig  <br/> |Gerät  <br/> | Ein Gerät ist nicht ordnungsgemäß funktioniert. Gerät nicht funktioniert Verhältnisse verwendet werden: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>See Also
[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 