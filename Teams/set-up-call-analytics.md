---
title: Einrichten von Anrufen Analytics
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
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
description: Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems.
ms.openlocfilehash: 1e7c7eaa769ba1e08a46b539b15e673d35891f5c
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016909"
---
# <a name="set-up-call-analytics"></a>Einrichten von Anrufen Analytics

Einen Skype für Business Online Admin können Analytics rufen Sie für die Problembehandlung bei Skype für Business und Microsoft-Teams, rufen Sie die Qualität und Verbindung Probleme. Dabei kann es hilfreich sein, die folgenden Funktionen in der Anrufanalyse einzurichten:
  
- Legen Sie Berechtigungen fest, mit denen andere Mitarbeiter wie beispielsweise Helpdesk-Agents zwar die Anrufanalyse verwenden, aber auf die übrigen Funktionen im Skype for Business Admin Center nicht zugreifen können. 
    
- Fügen Sie Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzu, indem Sie eine TSV- oder CSV-Datendatei hochladen.
    
**Anruf Analytics wird jetzt in der Microsoft-Teams und Skype für Business Admin Center verfügbar.** Um alle diese Informationen und Daten für einen Benutzer anzuzeigen, verwenden Sie die Registerkarte **Anrufverlauf** . Hierzu können Sie auf der Profilseite des Benutzers suchen, indem Sie entweder suchen für den Benutzer aus dem Dashboard, oder suchen den Benutzer von **Benutzern** im linken Navigationsbereich.

> [!IMPORTANT]
> Helpdesk-Agent-Berechtigungen und Netzwerk-Topologie hochladen verfügbar in das neue Administratorportal in den nächsten Monaten. Sie können in der Zwischenzeit weiterhin verwenden https://adminportal.services.skypeforbusiness.com für Ebene 1 und Ebene 2 Helpdesk-Zugriff.
  
## <a name="set-call-analytics-permissions"></a>Festlegen von Berechtigungen für die Anrufanalyse
<a name="BKMK_SetCAPerms"></a>

Als Administrator verfügen Sie über Vollzugriff auf alle Funktionen der Anrufanalyse. Darüber hinaus können Sie in der Anrufanalyse ein Helpdesk-Modell verwenden, das Berechtigungsgruppen der Stufen 1 und 2 umfasst. Benutzer mit Berechtigungen der Stufe 1 können nur auf eine begrenzte Ansicht der Anrufanalyse zugreifen. Benutzer mit Berechtigungen der Stufe 2 können auf die gesamte Funktionalität der Anrufanalyse zugreifen. Beide Berechtigungsstufen verhindern des Zugriffs auf den Rest der Microsoft-Teams und Skype für Business Admin Center. Sie können den Zugriff auf die Stufen gewähren, indem Sie zum Abschnitt für Stufe 1 oder für Stufe 2 auf der Seite „Berechtigungen" eine Gruppe hinzufügen, in der der jeweilige Benutzer enthalten ist. Weitere Details finden Sie unter [Einrichten von mehrstufigen Berechtigungen in der Anrufanalyse](set-up-call-analytics.md#BKMK_SetUpTier).
  
Helpdesk-Agents der Stufe 1 bearbeiten Standardprobleme im Zusammenhang mit der Anrufqualität. Agents der Stufe 1 untersuchen keine Probleme im Zusammenhang mit Besprechungen. Sie sammeln zugehörige Informationen und eskalieren dann an einen Agent der Stufe 2. Agents der Stufe 2 sehen Informationen in detaillierten Anruflisten, die für Agents der Stufe 1 ausgeblendet sind. Die folgende Tabelle enthält eine Übersicht über die Informationen, die für Agents in der Anrufanalyse verfügbar sind.


|**Aktivität**|**Informationen in der Anrufanalyse**|**Für Agents der Stufe 1 sichtbar**|**Für Agents der Stufe 2 sichtbar**|
|:-----|:-----|:-----|:-----|
|**Anrufe** <br/> |Name des Anrufers  <br/> |Nur der Name des Benutzers, nach dem der Agent gesucht hat.  <br/> |Benutzername  <br/> |
||Name des Angerufenen  <br/> |Wird als „Interner Benutzer" oder „Externer Benutzer" angezeigt.  <br/> |Name des Angerufenen  <br/> |
||Telefonnummer des Anrufers  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |
||Telefonnummer des Angerufenen  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823***.  <br/> |
||**Call Details** > **Advanced** tab <br/> |Es werden keine Informationen angezeigt.  <br/> |Es werden alle Details angezeigt, beispielsweise Gerätenamen, IP-Adresse, Subnetzzuordnung und mehr.  <br/> |
||**Call Details** > **Advanced** > **Debug** tab <br/> |Es werden keine Informationen angezeigt.  <br/> |Es werden alle Details angezeigt, beispielsweise DNS-Suffix und SSID.  <br/> |
|**Besprechungen** <br/> |Namen der Teilnehmer  <br/> |Nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert.  <br/> |Es werden alle Namen angezeigt.  <br/> |
||Anzahl der Teilnehmer  <br/> |Anzahl der Teilnehmer  <br/> |Anzahl der Teilnehmer  <br/> |
||Sitzungsdetails  <br/> |Die Sitzungsdetails werden mit Ausnahmen angezeigt. Angezeigt wird nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.  <br/> |Die Sitzungsdetails werden angezeigt. Benutzernamen und Sitzungsdetails werden angezeigt. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.  <br/> |
   
 **Einrichten von gestuften Berechtigungen in Aufrufen Analytics** 
 <a name="BKMK_SetUpTier"> </a>

![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**
  
1. Erstellen Sie Office 365-Sicherheitsgruppen für Stufe 1 und Stufe 2, und fügen Sie die gewünschten Personen zu den einzelnen Gruppen hinzu. Sie können auch vorhandene Sicherheitsgruppen wiederverwenden. Weitere Informationen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Office 365 Admin Center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Gehen Sie im Office 365 Admin Center zu **Admin Center** > **Skype for Business**.

    > [!NOTE]
    > Wenn Sie Sie in den **Microsoft-Teams und Skype für Business Admin Center**sind klicken Sie im linken Navigationsbereich auf **Legacy-Portal**.
  
3. Wählen Sie **Extras** > **Skype für aufrufen BA (Preview)** > **Einstellungen**, und klicken Sie dann auf **Berechtigungen**.
    
4. Fügen Sie die Office 365-Sicherheitsgruppen zu den Feldern **Stufe 1** und **Stufe 2** hinzu. Sie können jeder Rolle mehrere Gruppen hinzufügen.
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](media/setup-call-analytics-image1.png)
  
 Benutzer mit einem der folgenden Berechtigungsstufen erhalten Sie auf Anrufen Analytics über den dedizierten URL *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen
<a name="BKMK_UploadFiles"> </a>

Sie können Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzufügen, indem Sie eine CSV- oder TSV-Datei hochladen. Anhand aller dieser Informationen kann die Anrufanalyse IP-Adressen zu physischen Standorten zuordnen. Sie oder die Helpdesk-Agents können diese Informationen nutzen, um Trends bei Anrufproblemen zu erkennen. Beispiel: Warum haben zahlreiche Benutzer im gleichen Gebäude ähnliche Probleme mit der Anrufqualität? 
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](media/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Wenn Sie Skype for Business-Administrator sind, können Sie eine vorhandene Datendatei aus dem Skype for Business Online-Anrufqualitätsdashboard verwenden. Zuerst laden Sie die Datei aus dem Anrufqualitätsdashboard herunter, und dann laden Sie sie in die Anrufanalyse hoch. Um eine vorhandene Datendatei herunterzuladen, wechseln Sie zu **Skype for Business Admin Center** > **Extras** > **Qualitätsdashboard für Anrufe mit Skype for Business Online** > **Jetzt hochladen**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**.
  
Wenn Sie eine TSV- oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Dateiformat der Mandantendaten und Dateistruktur der Gebäudedaten](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_UploadFiles"> </a>

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anruf Analyse- und Anrufqualität Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
