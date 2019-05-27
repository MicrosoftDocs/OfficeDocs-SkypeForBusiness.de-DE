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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems.
ms.openlocfilehash: 51f28b402fea69f0e5033954018a5f67bf6c90d6
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432777"
---
# <a name="set-up-call-analytics"></a>Einrichten von Anrufanalyse

Als Teams oder Skype for Business Online-Administrator können Sie die anrufanalyse verwenden, um die Anrufqualität von Skype for Business und Microsoft Teams und Verbindungsprobleme zu beheben. Dabei kann es hilfreich sein, die folgenden Funktionen in der Anrufanalyse einzurichten:
  
- Legen Sie Berechtigungen fest, die anderen Mitarbeitern wie Helpdesk-Agents die Verwendung von anrufanalyse ermöglichen, aber verhindern, dass Sie auf das restliche Microsoft Teams Admin Center zugreifen. 
    
- Fügen Sie Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzu, indem Sie eine TSV- oder CSV-Datendatei hochladen.
    
**Die anrufanalyse steht jetzt im Microsoft Teams Admin Center zur Verfügung**. Verwenden Sie die Registerkarte **Anrufverlauf** , um alle Anrufinformationen und Daten für einen Benutzer anzuzeigen. Sie können dies tun, indem Sie auf der Profilseite des Benutzers eine der folgenden Aktionen ausführen:

- Suchen Sie im Dashboard nach dem Benutzer.
  
   ![Screenshot der Benutzersuche auf dem Dashboard](media/set-up-call-analytics-image-1.png)

-  Wählen Sie im linken Navigationsbereich die Option **Benutzer** aus.

   ![Screenshot der linken Navigationsleiste](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Festlegen von Berechtigungen für die Anrufanalyse
<a name="BKMK_SetCAPerms"></a>

Als Administrator haben Sie vollständigen Zugriff auf alle Funktionen der anrufanalyse. Darüber hinaus können Sie Azure Active Directory-Rollen zuweisen, um Mitarbeiter zu unterstützen. Weisen Sie die Rolle des Teams Communications Support Specialist für Benutzer zu, die eine begrenzte Ansicht der anrufanalyse haben sollten. Weisen Sie Benutzern, die Zugriff auf die vollständige Funktionalität der anrufanalyse benötigen, die Rolle Teams Communications Support Engineer zu. Beide Berechtigungsstufen verhindern den Zugriff auf das restliche Microsoft Teams Admin Center.

> [!NOTE]
> Die Rolle "Kommunikations Support Spezialist" entspricht der Unterstützung der Stufe 1 und die Rolle des Kommunikations Support Ingenieurs entspricht der Unterstützung der Stufe 2.

Weitere Informationen zu Teams-Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md). 
  
Kommunikations Supportspezialisten behandeln grundlegende Probleme mit der Anrufqualität. Sie untersuchen keine Probleme mit Besprechungen. Stattdessen werden verwandte Informationen gesammelt und dann an einen Kommunikations Supporttechniker weitergeleitet. Kommunikations Support-Ingenieure sehen Informationen in detaillierten Anrufprotokollen, die von Experten für Kommunikationsunterstützung verborgen sind. In der folgenden Tabelle finden Sie eine Übersicht über die Informationen, die für Kommunikations Supportspezialisten und Kommunikations Support Ingenieure zur Verfügung stehen, wenn Sie die anrufanalyse verwenden.

|**Aktivität**|**Informationen in der Anrufanalyse**|**Was der Communications-Support Spezialist sieht**|**Was der Communications-Supporttechniker sieht**|
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

Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [anzeigen und Zuweisen von Rollen in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV- oder CSV-'Datei, um Informationen zu Gebäuden, Standorten und Mandanten hinzuzufügen
<a name="BKMK_UploadFiles"> </a>

Sie können Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzufügen, indem Sie eine CSV- oder TSV-Datei hochladen. Anhand aller dieser Informationen kann die Anrufanalyse IP-Adressen zu physischen Standorten zuordnen. Sie oder die Helpdesk-Agents können diese Informationen nutzen, um Trends bei Anrufproblemen zu erkennen. Beispiel: Warum haben zahlreiche Benutzer im gleichen Gebäude ähnliche Probleme mit der Anrufqualität? 

Wenn Sie ein Team und ein Skype for Business-Administrator sind, können Sie eine vorhandene Datendatei aus dem Dashboard "Teams & Skype for Business-Anrufqualität" verwenden. Zuerst laden Sie die Datei aus dem Anrufqualitätsdashboard herunter, und dann laden Sie sie in die Anrufanalyse hoch. 

- Wenn Sie eine vorhandene Datendatei herunterladen möchten, wechseln Sie jetzt zum **Microsoft Teams Admin Center** > -**Anruf Quality-Dashboard** > **hochladen**. Klicken Sie in der Liste **Meine Uploads** neben der gewünschten Datei auf **Herunterladen**.

- Wenn Sie die neue Datei hochladen möchten, wechseln Sie zu den **Microsoft Teams Admin Center** > -**Speicherorten**, und wählen Sie dann **Standortdaten hochladen** oder **Standortdaten ersetzen**aus.
  
Wenn Sie eine TSV- oder CSV-Datei von Grund auf neu erstellen, lesen Sie [Dateiformat der Mandantendaten und Dateistruktur der Gebäudedaten](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_UploadFiles"> </a>

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
