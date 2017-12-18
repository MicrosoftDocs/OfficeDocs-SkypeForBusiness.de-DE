---
title: "Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](66945036-ae87-4c08-a0bb-984e50d6b009.md#MT_Footer).  
  
Mithilfe der Anrufanalyse können Sie Probleme im Zusammenhang mit Anrufen oder Verbindungen in Skype for Business behandeln. Die Anrufanalyse zeigt detaillierte Informationen zu den Geräten und Netzwerken sowie zur Konnektivität für die Anrufe und Besprechungen der einzelnen Benutzer in Ihrem Skype for Business-Konto. Wenn Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzugefügt wurden, werden auch diese für jeden Anruf und jede Sitzung angezeigt. Anhand der über die Anrufanalyse verfügbaren Informationen können Sie herausfinden, warum bestimmte Benutzer eine schlechte Anruf- oder Besprechungsqualität wahrnehmen. 
  
> [!NOTE]
> Die Anrufanalyse wird zurzeit als Vorschau bereitgestellt. Die hier beschriebenen Texte und Bilder entsprechen möglicherweise nicht dem, was Sie tatsächlich sehen. 
  
## Behandeln von Problemen mit der Anrufqualität mithilfe der Anrufanalyse

Die Ihnen zugewiesene Berechtigungsstufe entscheidet, auf welche Informationen Sie in der Anrufanalyse zugreifen können:
  
- **Skype for Business-Administrator**: Sie können auf alle Informationen in der Anrufanalyse und im Skype for Business Admin Center zugreifen.
    
- **Helpdesk-Agent mit Berechtigungen der Stufe 1**: Sie sehen in der Anrufanalyse begrenzte Daten. Sie können Problembehandlungen für Anrufe ausführen, geben aber Probleme mit Besprechungen an einen Agent der Stufe 2 weiter. Auf die übrigen Funktionen im Skype for Business Admin Center können Sie nicht zugreifen.
    
- **Helpdesk-Agent mit Berechtigungen der Stufe 2**: Sie sehen in der Anrufanalyse alle verfügbaren Daten und können bei Problembehandlungen für Anrufe und Besprechungen helfen. Auf die übrigen Funktionen im Skype for Business Admin Center können Sie nicht zugreifen.
    
Wenden Sie sich an Ihren Skype for Business-Administrator, wenn Sie Hilfe im Zusammenhang mit Berechtigungen benötigen.
  
 **Öffnen der Anrufanalyse als Helpdesk-Agent der Stufe 1 oder 2**
  
1. Gehen Sie zu [https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com), und melden Sie sich mit Ihrem Benutzernamen und dem zugehörigen Kennwort an.
    
2. Beginnen Sie in **Benutzersuche**, den Namen oder die SIP-Adresse des Benutzers einzugeben, für dessen Anrufe Sie eine Problembehandlung ausführen möchten. Wählen Sie dann den Benutzer in der Liste aus.
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Wählen Sie in **Call history** (Anrufliste) den Anruf oder die Besprechung aus, für den bzw. für die Sie eine Problembehandlung ausführen möchten.
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.
    
    In den Sitzungsdetails für die einzelnen Anrufe oder Besprechungen werden geringfügige Probleme gelb dargestellt. (Im folgenden Screenshot zum Beispiel werden die Werte für „Durchschnittlicher Jitter", „Max. Jitter" und „Durchschnittliche Paketverlustrate" in Gelb angezeigt.) Gelbe Elemente befinden sich außerhalb des normalen Bereichs und können zum Problem beitragen. Sie sind aber wahrscheinlich nicht die Hauptursache des Problems. Rote Elemente weisen auf ein wichtiges Problem hin und stellen wahrscheinlich die Hauptursache für die schlechte Anrufqualität in dieser Sitzung dar. 
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
In rare cases, quality of experience data isn't received for audio sessions. Often this is caused by the call dropping and connection with the client terminating. When this occurs, the session rating is "unavailable".
  
For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."
  
|**Problem**|**Bereich**|**Beschreibung**|
|:-----|:-----|:-----|
|Call setup  <br/> |Session  <br/> |The error code Ms-diag 20-29 indicates the call setup failed. The user couldn't join the call or meeting.  <br/> |
|Audio network classified poor call  <br/> |Session  <br/> |Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio. For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Device not functioning  <br/> |Gerät  <br/> | A device isn't functioning correctly. Device not functioning ratios are : <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Einrichten der Anrufanalyse von Skype for Business](set-up-skype-for-business-call-analytics.md)

