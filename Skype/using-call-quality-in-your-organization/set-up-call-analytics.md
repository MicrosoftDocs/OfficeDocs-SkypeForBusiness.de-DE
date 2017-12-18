---
title: "Einrichten der Anrufanalyse von Skype for Business"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
description: "Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems."
---

# Einrichten der Anrufanalyse von Skype for Business

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Analytics aufrufen, können Sie als Administrator Skype for Business Online um Skype for Business und Microsoft Teams Anruf Qualität und Verbindung Probleme zu beheben. Möglicherweise finden Sie es sinnvoll, um die folgenden Funktionen in anrufen Analytics einzurichten:
  
- Legen Sie Berechtigungen fest, mit denen andere Mitarbeiter wie beispielsweise Helpdesk-Agents zwar die Anrufanalyse verwenden, aber auf die übrigen Funktionen im Skype for Business Admin Center nicht zugreifen können. 
    
- Fügen Sie Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzu, indem Sie eine TSV- oder CSV-Datendatei hochladen.
    
> [!NOTE]
> Die Anrufanalyse wird zurzeit als Vorschau bereitgestellt. Die hier beschriebenen Texte und Bilder entsprechen möglicherweise nicht dem, was Sie tatsächlich sehen. 
  
## Festlegen von Berechtigungen für die Anrufanalyse
<a name="BKMK_SetCAPerms"> </a>

Als Administrator verfügen Sie über Vollzugriff auf alle Funktionen der Anrufanalyse. Darüber hinaus können Sie in der Anrufanalyse ein Helpdesk-Modell verwenden, das Berechtigungsgruppen der Stufen 1 und 2 umfasst. Benutzer mit Berechtigungen der Stufe 1 können nur auf eine begrenzte Ansicht der Anrufanalyse zugreifen. Benutzer mit Berechtigungen der Stufe 2 können auf die gesamte Funktionalität der Anrufanalyse zugreifen. Beide Berechtigungsstufen verhindern den Zugriff auf die übrigen Funktionen im Skype for Business Admin Center. Sie können den Zugriff auf die Stufen gewähren, indem Sie zum Abschnitt für Stufe 1 oder für Stufe 2 auf der Seite „Berechtigungen" eine Gruppe hinzufügen, in der der jeweilige Benutzer enthalten ist. Weitere Details finden Sie unter [Einrichten von mehrstufigen Berechtigungen in der Anrufanalyse](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#BKMK_SetUpTier).
  
Helpdesk-Agents der Stufe 1 bearbeiten Standardprobleme im Zusammenhang mit der Anrufqualität. Agents der Stufe 1 untersuchen keine Probleme im Zusammenhang mit Besprechungen. Sie sammeln zugehörige Informationen und eskalieren dann an einen Agent der Stufe 2. Agents der Stufe 2 sehen Informationen in detaillierten Anruflisten, die für Agents der Stufe 1 ausgeblendet sind. Die folgende Tabelle enthält eine Übersicht über die Informationen, die für Agents in der Anrufanalyse verfügbar sind.
  
|
|
|**Aktivität**|**Informationen in der Anrufanalyse**|**Für Agents der Stufe 1 sichtbar**|**Für Agents der Stufe 2 sichtbar**|
|:-----|:-----|:-----|:-----|
|**Anrufe** <br/> |Name des Anrufers  <br/> |Nur der Name des Benutzers, nach dem der Agent gesucht hat.  <br/> |Benutzername  <br/> |
||Name des Angerufenen  <br/> |Wird als „Interner Benutzer" oder „Externer Benutzer" angezeigt.  <br/> |Name des Angerufenen  <br/> |
||Telefonnummer des Anrufers  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |
||Telefonnummer des Angerufenen  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |
||**Anrufdetails** > Registerkarte **Erweitert** <br/> |Es werden keine Informationen angezeigt.  <br/> |Es werden alle Details angezeigt, beispielsweise Gerätenamen, IP-Adresse, Subnetzzuordnung und mehr.  <br/> |
||**Anrufdetails** > **Erweitert** > Registerkarte **Debug** <br/> |Es werden keine Informationen angezeigt.  <br/> |Es werden alle Details angezeigt, beispielsweise DNS-Suffix und SSID.  <br/> |
|**Besprechungen** <br/> |Namen der Teilnehmer  <br/> |Nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert.  <br/> |Es werden alle Namen angezeigt.  <br/> |
||Anzahl der Teilnehmer  <br/> |Anzahl der Teilnehmer  <br/> |Anzahl der Teilnehmer  <br/> |
||Sitzungsdetails  <br/> |Die Sitzungsdetails werden mit Ausnahmen angezeigt. Angezeigt wird nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.  <br/> |Die Sitzungsdetails werden angezeigt. Benutzernamen und Sitzungsdetails werden angezeigt. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.  <br/> |
   
 **Einrichten von mehrstufigen Berechtigungen in der Anrufanalyse**
  
1. Erstellen Sie Office 365-Sicherheitsgruppen für Stufe 1 und Stufe 2, und fügen Sie die gewünschten Personen zu den einzelnen Gruppen hinzu. Sie können auch vorhandene Sicherheitsgruppen wiederverwenden. Weitere Informationen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Office 365 Admin Center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Gehen Sie im Office 365 Admin Center zu **Admin Center** > **Skype for Business**.
    
    > [!NOTE]
    > Wenn das alte Skype for Business Admin Center angezeigt wird, wechseln Sie zur neuen Version, indem Sie auf **Lernen Sie unser neues Admin Center kennen** klicken.
  
3. Klicken Sie im neuen Skype for Business Admin Center auf **Berechtigungen**.
    
4. Fügen Sie die Office 365-Sicherheitsgruppen zu den Feldern **Stufe 1** und **Stufe 2** hinzu. Sie können jeder Rolle mehrere Gruppen hinzufügen.
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Benutzer beider Berechtigungsstufen können die Anrufanalyse über die dedizierte URL „https://adminportal.services.skypeforbusiness.com" aufrufen.
  
## Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen
<a name="BKMK_UploadFiles"> </a>

Sie können Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzufügen, indem Sie eine CSV- oder TSV-Datei hochladen. Anhand aller dieser Informationen kann die Anrufanalyse IP-Adressen zu physischen Standorten zuordnen. Sie oder die Helpdesk-Agents können diese Informationen nutzen, um Trends bei Anrufproblemen zu erkennen. Beispiel: Warum haben zahlreiche Benutzer im gleichen Gebäude ähnliche Probleme mit der Anrufqualität? 
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Wenn Sie Skype for Business-Administrator sind, können Sie eine vorhandene Datendatei aus dem Skype for Business Online-Anrufqualitätsdashboard verwenden. Zuerst laden Sie die Datei aus dem Anrufqualitätsdashboard herunter, und dann laden Sie sie in die Anrufanalyse hoch. Um eine vorhandene Datendatei herunterzuladen, wechseln Sie zu **Skype for Business Admin Center** > **Extras** > **Qualitätsdashboard für Anrufe mit Skype for Business Online** > **Jetzt hochladen**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**.
  
Wenn Sie eine TSV- oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Dateiformat der Mandantendaten und Dateistruktur der Gebäudedaten](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_TenantDataFile).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)
  
[Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?](what-s-the-difference-between-call-analytics-and-call-quality-dashboard.md)

