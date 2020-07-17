---
title: Verwenden von Anruf Analysen zur Fehlerbehebung bei schlechter Anrufqualität
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Verwenden Sie benutzerspezifische anrufanalyse Details zu Geräten, Netzwerken und Verbindungen zur Behandlung von Benutzerproblemen mit Microsoft Teams-anrufen und-Besprechungen.
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085321"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Verwenden von Anruf Analysen zur Fehlerbehebung bei schlechter Anrufqualität

In diesem Artikel wird erläutert, wie Sie mithilfe der anrufanalyse schlechte Microsoft Teams-Anruf-oder Besprechungs Qualität für einzelne Benutzer beheben können, wenn Sie ein Teamadministrator oder ein Team-Support Spezialist oder-Ingenieur sind.


  
## <a name="call-analytics-permissions"></a>Anrufanalyse Berechtigungen

In diesem Artikel wird davon ausgegangen, dass Sie die anrufanalyse bereits eingerichtet haben. Wenn dies nicht der Fall ist, lesen Sie [Einrichten der anrufanalyse für Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Einführung in die anrufanalyse

In der anrufanalyse werden detaillierte Informationen zu Team anrufen und Besprechungen für jeden Benutzer in Ihrem Office 365-Konto angezeigt. Sie enthält Informationen zu Geräten, Netzwerken, Konnektivität und Anrufqualität (jeder dieser Elemente kann einen Faktor bei schlechter Anruf-oder Besprechungs Qualität darstellen). Wenn Sie Gebäude-, Website-und Mandanteninformationen hochladen, werden diese Informationen auch für jeden Anruf und jede Besprechung angezeigt. Verwenden Sie die anrufanalyse, um herauszufinden, warum ein Benutzer eine schlechte Anruf-oder Besprechungs Erfahrung hatte.

Die anrufanalyse zeigt Ihnen jede Etappe eines Anrufs oder einer Besprechung an – beispielsweise von einem Teilnehmer zu einem zweiten Teilnehmer. Durch Analyse dieser Details kann ein Teamadministrator Problembereiche isolieren und die Ursache für schlechte Qualität ermitteln.
   
Als Team-Administrator erhalten Sie vollständigen Zugriff auf alle anrufanalyse Daten für jeden Benutzer. Darüber hinaus können Sie Azure Active Directory-Rollen zuweisen, um Mitarbeiter zu unterstützen. Wenn Sie mehr über diese Rollen erfahren möchten, lesen Sie [erteilen der Berechtigung für Support-und Helpdesk-Mitarbeiter](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). Verpassen Sie nicht, [was die Rolle jedes Teams unterstützt?](#what-does-each-teams-support-role-do) weiter unten.

## <a name="where-to-find-per-user-call-analytics"></a>Wo finden Sie die pro-Benutzer-anrufanalyse

Wenn Sie alle Anrufinformationen und Daten für einen Benutzer anzeigen möchten, wechseln Sie zum [Team Admin Center](https://admin.teams.microsoft.com). Wählen Sie unter **Benutzer**einen Benutzer aus, und öffnen Sie dann die Registerkarte **Anrufverlauf** auf der Profilseite des Benutzers. Hier finden Sie alle Anrufe und Besprechungen für diesen Benutzer für die letzten 30 Tage.

![Screenshot aller Analytics-Benutzerdaten](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Wenn Sie weitere Informationen zu einer bestimmten Sitzung, einschließlich detaillierter Medien-und Netzwerkstatistiken, erhalten möchten, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Screenshot der Benutzersitzungsdaten der anrufanalyse](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>Was unterstützt die Rolle jedes Teams?

Der Support **Spezialist für Teams Communications** (Stufe 1) behandelt grundlegende Probleme mit der Anrufqualität. Sie untersuchen keine Probleme mit Besprechungen. Stattdessen werden verwandte Informationen gesammelt und dann an einen Kommunikations Supporttechniker weitergeleitet. 

Der Support- **Techniker für Teams Communications** (Stufe 2) sieht Informationen in detaillierten Anrufprotokollen, die dem Supportspezialisten für Team Kommunikation verborgen sind. In der folgenden Tabelle sind die Informationen aufgeführt, die für die einzelnen Teams zur Unterstützung der Rolle verfügbar sind.

In der folgenden Tabelle wird erläutert, welche Informationen pro Benutzer für die einzelnen Kommunikations Unterstützungsfunktionen zur Verfügung stehen.

|**Aktivität**|**Informationen**|Was der Communications-Support **Spezialist** sieht|Was der Communications-Support **Techniker** sieht|
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
  
## <a name="troubleshoot-user-call-quality-problems"></a>Behandeln von Problemen mit der Benutzer Anrufqualität 

1. Öffnen Sie das Team Admin Center ( https://admin.teams.microsoft.com) und melden Sie sich mit Ihrem Team Communications Support oder den Administratoranmeldeinformationen für Teams an.

2. Beginnen Sie im **Dashboard**in der **Benutzersuche**mit der Eingabe des Namens oder der SIP-Adresse des Benutzers, dessen Anrufe Sie beheben möchten, oder wählen Sie **Benutzer anzeigen** aus, um eine Liste der Benutzer anzuzeigen.

3. Wählen Sie den Benutzer in der Liste aus.

4. Wählen Sie **Anrufprotokoll**aus, und wählen Sie dann den Anruf oder die Besprechung aus, für den Sie eine Problembehandlung durchführen möchten.
    
5. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.
    
    In den Sitzungsdetails für jeden Anruf oder jede Besprechung werden kleinere Probleme in gelb angezeigt. Wenn etwas gelb ist, liegt es außerhalb des normalen Bereichs, und es kann zu dem Problem beitragen, doch es ist unwahrscheinlich, dass es die Hauptursache des Problems ist. Wenn etwas rot ist, ist es ein erhebliches Problem, und es ist wahrscheinlich die Hauptursache für die schlechte Anrufqualität für diese Sitzung. 
      
In seltenen Fällen werden die Daten für die Qualität der Erfahrung nicht für audiositzungen empfangen. Häufig wird dies durch einen unterbrochenen Anruf verursacht, oder wenn die Verbindung mit dem Client beendet wird. In diesem Fall ist die Sitzungs Bewertung **nicht verfügbar**.
  
Bei audiositzungen, die QoE-Daten (Quality of Experience) aufweisen, werden in der folgenden Tabelle wichtige Probleme beschrieben, die eine Sitzung als **schlecht**qualifizieren.
  
|**Problem**|**Bereich**|**Beschreibung**|
|:-----|:-----|:-----|
|Anrufeinrichtung  <br/> |Session  <br/> |Der Fehlercode MS-Diag 20-29 gibt an, dass die Anrufeinrichtung fehlgeschlagen ist. Der Benutzer konnte nicht an dem Anruf oder der Besprechung teilnehmen.  <br/> |
|Audionetz klassifizierter schlechter Anruf  <br/> |Session  <br/> |Probleme mit der Netzwerkqualität (wie Paketverlust, Jitter, NMOS-Verschlechterung, RTT oder verdecktes Verhältnis) waren aufgetreten.  <br/> |
|Gerät funktioniert nicht  <br/> |Gerät  <br/> | Ein Gerät funktioniert nicht ordnungsgemäß. Das Funktions Verhältnis des Geräts funktioniert nicht: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der pro-Benutzer-anrufanalyse](set-up-call-analytics.md)



  
 
