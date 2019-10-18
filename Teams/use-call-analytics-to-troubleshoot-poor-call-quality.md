---
title: Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
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
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: Verwenden Sie Details zur anrufanalyse zu Geräten, Netzwerken und Verbindungen zur Behandlung von Benutzerproblemen mit Microsoft Teams und Skype for Business-anrufen und-Besprechungen.
ms.openlocfilehash: 4b2d6a5a18bf0a13f3fd32aecb8ad98192f3851a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568634"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln

Anrufanalyse unterstützt Sie bei der Behandlung von Anruf-oder Verbindungsproblemen mit Microsoft Teams und Skype for Business. In der anrufanalyse werden detaillierte Informationen zu den Geräten, Netzwerken und Verbindungen für die Anrufe und Besprechungen der einzelnen Benutzer in Ihrem Office 365-Konto angezeigt. Wenn Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzugefügt wurden, werden auch diese für jeden Anruf und jede Sitzung angezeigt. Anhand der über die Anrufanalyse verfügbaren Informationen können Sie herausfinden, warum bestimmte Benutzer eine schlechte Anruf- oder Besprechungsqualität wahrnehmen. 
  
## <a name="call-analytics-permissions"></a>Anrufanalyse Berechtigungen

Als Administrator verfügen Sie über Vollzugriff auf alle Funktionen der Anrufanalyse. Darüber hinaus können Sie Azure Active Directory-Rollen zuweisen, um Mitarbeiter zu unterstützen. Weisen Sie die Rolle des Teams Communications Support Specialist für Benutzer zu, die eine begrenzte Ansicht der anrufanalyse haben sollten. Weisen Sie Benutzern, die Zugriff auf die vollständige Funktionalität der anrufanalyse benötigen, die Rolle Teams Communications Support Engineer zu. Beide Berechtigungsstufen verhindern den Zugriff auf das restliche Microsoft Teams Admin Center.

Kommunikations Supportspezialisten behandeln grundlegende Probleme mit der Anrufqualität. Sie untersuchen keine Probleme mit Besprechungen. Stattdessen werden verwandte Informationen gesammelt und dann an einen Kommunikations Supporttechniker weitergeleitet. Kommunikations Support-Ingenieure sehen Informationen in detaillierten Anrufprotokollen, die von Experten für Kommunikationsunterstützung verborgen sind. In der folgenden Tabelle finden Sie eine Übersicht über die Informationen, die für Kommunikations Supportspezialisten und Kommunikations Support Ingenieure zur Verfügung stehen, wenn Sie die anrufanalyse verwenden.

Die Ihnen zugewiesene Berechtigungsstufe entscheidet, auf welche Informationen Sie in der Anrufanalyse zugreifen können:
  
- **Teams-Dienstadministrator oder Teams Communications Administrator**: Sie haben Zugriff auf alle Informationen in der anrufanalyse und im Microsoft Teams Admin Center.
    
- **Teams Communications Support-Spezialist**: in der anrufanalyse wird eine begrenzte Anzahl von Daten angezeigt. Sie können die Behandlung von Anrufen beheben, aber Sie werden Probleme mit Besprechungen an einen Team-Supporttechniker weitergeben. Sie haben keinen Zugriff auf das restliche Microsoft Teams Admin Center.
    
- **Teams Communications Support Engineer**: Sie sehen alle verfügbaren Daten in der anrufanalyse und können bei der Behebung von Problemen mit beiden anrufen und Besprechungen behilflich sein. Sie haben keinen Zugriff auf das restliche Microsoft Teams Admin Center.
    
> [!NOTE]
> Die Rolle "Kommunikations Support Spezialist" entspricht der Unterstützung der Stufe 1 und die Rolle des Kommunikations Support Ingenieurs entspricht der Unterstützung der Stufe 2.

Weitere Informationen zu Teams-Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md). Einen detaillierten Vergleich der Rollen des Teams Communications Support Specialist und Teams Communications Support Engineer finden Sie unter [Einrichten der anrufanalyse](set-up-call-analytics.md#set-call-analytics-permissions) . 
  
Wenn Sie Hilfe zu Berechtigungen benötigen, sehen Sie sich Ihre Teams und den Skype for Business-Administrator an.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Behandeln von Problemen mit der Anrufqualität mithilfe der Anrufanalyse

1. Melden Sie sich mit Ihrem Team Communications-Support oder den Team-Administratoranmeldeinformationen an.

2. Wechseln Sie in Ihrem Webbrowser zu *https://admin.teams.microsoft.com*.
    
3. Beginnen Sie im **Dashboard**in der **Benutzersuche**mit der Eingabe des Namens oder der SIP-Adresse des Benutzers, dessen Anrufe Sie behandeln möchten, oder wählen Sie **Benutzer anzeigen** aus, um eine Liste der Benutzer anzuzeigen.
    
    ![Screenshot des Felds "Benutzersuche" in der anrufanalyse](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Wählen Sie den Benutzer in der Liste aus.

5. Wählen Sie **Anrufprotokoll**aus, und wählen Sie dann den Anruf oder die Besprechung aus, für den Sie eine Problembehandlung durchführen möchten.
    
    ![Screenshot der Seite "Anrufverlauf" für einen Benutzer](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.
    
    In den Sitzungsdetails für die einzelnen Anrufe oder Besprechungen werden geringfügige Probleme gelb dargestellt. (Im folgenden Screenshot zum Beispiel werden die Werte für „Durchschnittlicher Jitter", „Max. Jitter" und „Durchschnittliche Paketverlustrate" in Gelb angezeigt.) Gelbe Elemente befinden sich außerhalb des normalen Bereichs und können zum Problem beitragen. Sie sind aber wahrscheinlich nicht die Hauptursache des Problems. Rote Elemente weisen auf ein wichtiges Problem hin und stellen wahrscheinlich die Hauptursache für die schlechte Anrufqualität in dieser Sitzung dar. 
    
    ![Screenshot der Registerkarte "Erweitert" im Anrufverlauf eines Benutzers ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
In seltenen Fällen werden die Daten für die Qualität der Erfahrung nicht für audiositzungen empfangen. Dies wird häufig dadurch verursacht, dass der Anruf abfällt und die Verbindung mit dem Client beendet wird. In diesem Fall ist die Sitzungs Bewertung **nicht verfügbar**.
  
Bei audiositzungen, die QoE-Daten (Quality of Experience) aufweisen, werden in der folgenden Tabelle wichtige Probleme beschrieben, die eine Sitzung als **schlecht**qualifizieren.
  
|**Problem**|**Bereich**|**Beschreibung**|
|:-----|:-----|:-----|
|Anrufeinrichtung  <br/> |Session  <br/> |Der Fehlercode MS-Diag 20-29 gibt an, dass die Anrufeinrichtung fehlgeschlagen ist. Der Benutzer konnte nicht an dem Anruf oder der Besprechung teilnehmen.  <br/> |
|Audionetz klassifizierter schlechter Anruf  <br/> |Session  <br/> |Probleme mit der Netzwerkqualität (wie Paketverlust, Jitter, NMOS-Verschlechterung, RTT oder verdecktes Verhältnis) waren aufgetreten. Weitere Informationen zu den Bedingungen, die für die Klassifizierung schlechter Anrufe verwendet werden, finden Sie in diesem [Microsoft-Blogbeitrag](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Gerät funktioniert nicht  <br/> |Gerät  <br/> | Ein Gerät funktioniert nicht ordnungsgemäß. Das Funktions Verhältnis des Geräts funktioniert nicht: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
