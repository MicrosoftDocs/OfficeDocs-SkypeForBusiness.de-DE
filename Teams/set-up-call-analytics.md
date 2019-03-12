---
title: Einrichten von Anrufanalyse
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
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
ms.openlocfilehash: ebd5ec0ea60a59e50c3ce7137f518d9a596074a5
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542327"
---
# <a name="set-up-call-analytics"></a>Einrichten von Anrufanalyse

Als eine Teams oder Skype für Business Online Admin, können Analytics rufen Sie für die Problembehandlung bei Skype für Unternehmen und Microsoft-Teams, rufen Sie die Qualität und Verbindung Probleme. Dabei kann es hilfreich sein, die folgenden Funktionen in der Anrufanalyse einzurichten:
  
- Festlegen von Berechtigungen, mit denen andere Mitarbeiter, wie etwa Helpdesk-Agenten, Analytics anrufen verwenden, jedoch verhindern, dass sie den Zugriff auf den Rest des Microsoft-Teams, Administrationscenter. 
    
- Fügen Sie Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzu, indem Sie eine TSV- oder CSV-Datendatei hochladen.
    
**Analytics aufrufen, steht in der Verwaltungskonsole von Microsoft-Teams**. Um den Anrufinformationen und Daten für einen Benutzer angezeigt wird, verwenden Sie die Registerkarte **Anrufverlauf** . Dazu können Sie auf der Profilseite des Benutzers suchen, indem Sie einen der folgenden Schritte ausführen:

- Suchen Sie nach dem Benutzer aus dem Dashboard.
  
   ![Screenshot der Benutzersuche auf dashboard](media/set-up-call-analytics-image-1.png)

-  Wählen Sie im linken Navigationsbereich **Benutzer** aus.

   ![Screenshot des linken Navigationsbereich](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Festlegen von Berechtigungen für die Anrufanalyse
<a name="BKMK_SetCAPerms"></a>

Als Administrator müssen Sie Vollzugriff auf alle Funktionen von Analytics aufrufen. Darüber hinaus können Sie zu support-Mitarbeiter Azure Active Directory-Rollen zuweisen. Weisen Sie die Teams Communications Support-Spezialisten-Rolle für Benutzer, die eine begrenzte Ansicht des Analytics aufrufen verfügen soll. Benutzer Zugriff auf den vollen Funktionsumfang von Analytics aufrufen benötigen weisen Sie die Teams Communications Support Engineer Rolle zu. Beide Berechtigungsstufen verhindern des Zugriffs auf den Rest der im Microsoft-Teams, Administrationscenter.

> [!NOTE]
> Die Rolle des Supports Specialist von Communications Support der Ebene 1 entspricht, und die Kommunikation Support Engineer Rolle Support der Ebene 2 entspricht.

Weitere Informationen zu Administratorrollen Teams finden Sie unter [Verwendung von Microsoft-Teams Administratorrollen zum Verwalten von Teams](using-admin-roles.md). 
  
Supportmitarbeitern Communications behandeln Sie grundlegende Anrufqualität Probleme. Sie untersuchen keine Probleme bei Besprechungen. Stattdessen verwandte Informationen sammeln und dann an einen Supportmitarbeiter Communications ausweiten. Supporttechniker Communications finden Sie Informationen im detaillierten mithilfe von Anruflisten, die Communications Supportmitarbeitern ausgeblendet wurde. In der folgenden Tabelle bietet eine Übersicht über verfügbaren Informationen zu Communications-Support-Spezialisten und Communications-Supporttechniker, bei Verwendung von Analytics aufrufen.

|**Aktivität**|**Informationen in der Anrufanalyse**|**Welche die Kommunikation Specialist dies unterstützen**|**Welche die Kommunikation Engineer dies unterstützen**|
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
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Einrichten von Berechtigungen durch Zuweisen von Administratorrollen
<a name="BKMK_SetUpTier"> </a>

Gewusst wie: Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [anzeigen und Zuweisen von Rollen in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen
<a name="BKMK_UploadFiles"> </a>

Sie können Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzufügen, indem Sie eine CSV- oder TSV-Datei hochladen. Anhand aller dieser Informationen kann die Anrufanalyse IP-Adressen zu physischen Standorten zuordnen. Sie oder die Helpdesk-Agents können diese Informationen nutzen, um Trends bei Anrufproblemen zu erkennen. Beispiel: Warum haben zahlreiche Benutzer im gleichen Gebäude ähnliche Probleme mit der Anrufqualität? 

Wenn Sie eine Teams sind und Skype für Business Admin, können Sie eine vorhandene Datendatei aus der Teams & Skype für Business aufrufen Qualitätsdashboard verwenden. Zuerst laden Sie die Datei aus dem Anrufqualitätsdashboard herunter, und dann laden Sie sie in die Anrufanalyse hoch. 

- Um eine vorhandene Datendatei herunterladen möchten, wechseln Sie zur **Microsoft-Teams-Verwaltungskonsole** > **Aufrufen Qualitätsdashboard** > **jetzt hochladen**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**.

- Um die neue Datei hochzuladen, wechseln Sie zur **Microsoft-Teams-Verwaltungskonsole** > **Speicherorte**, und wählen Sie dann **Standortdaten hochladen** oder **Standortdaten ersetzen**.
  
Wenn Sie eine TSV- oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Dateiformat der Mandantendaten und Dateistruktur der Gebäudedaten](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_UploadFiles"> </a>

[Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
