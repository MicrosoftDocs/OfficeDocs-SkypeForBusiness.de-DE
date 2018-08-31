---
title: Bericht „Sitzungsdetails“
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Im neuen Office 365-Dashboard Berichte wird eine Aktivitätsübersicht über die Office 365-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten.
search.appverid: MET150
ms.openlocfilehash: ae892766be3b9bc18f37ae8b551678a738743325
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780855"
---
# <a name="session-details-report"></a>Bericht „Sitzungsdetails“

Im neuen Office 365-Dashboard **Berichte** wird eine Aktivitätsübersicht über die Office 365-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten. **Skype für Business Sitzungsdetails** Bericht können Sie Details zu einzelnen Benutzers Anruf Erfahrungen finden Sie unter.
  
Checken Sie [Übersicht über die Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) für weitere Berichte, die verfügbar sind.
  
In diesem Bericht, zusammen mit den anderen Skype für Business Berichte enthalten Details auf Aktivität, einschließlich Sitzungsdetails in Ihrer Organisation. Diese Angaben sind sehr hilfreich, wenn Sie untersuchen, für Ihre Organisation und für das Einrichten von [Communications haben](/microsoftteams/what-are-communications-credits)planen und Durchführen von anderen Business Entscheidungen.
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Wie auf der Skype für Detailbericht Business-Sitzung abgerufen.

1. Wechseln Sie zu der **Office 365 Administrationscenter** > **Berichte**
    
2. Wählen Sie im linken Menü **Berichte** aus, und klicken Sie dann auf **Verwendung**.
    
3. Klicken Sie in der Liste unter **Wählen Sie einen Bericht**auf **Skype für Business Sitzungsdetails**.
    
    > [!TIP]
    > Wenn Sie diesen Bericht aufgeführten nicht angezeigt wird, fahren Sie mit **Skype für Business Administrationscenter** > **Berichte** > **Sitzungsdetails**. 
  
    > [!IMPORTANT]
    > Je nach vorhandenem Office 365-Abonnement werden möglicherweise nicht alle Produkte und Berichte angezeigt, die in diesem Artikel besprochen werden. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretieren der Skype für Detailbericht Business-Sitzung

Sie können eine Ansicht in Skype ausführliche Business-Sitzung des Benutzers abrufen, indem Sie betrachten jede der Spalten, die angezeigt werden.
  
Der Bericht sieht folgendermaßen aus:
  
![Skype für Business Sitzung Detailbericht Dashboard.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Suchen Benutzer durch Alias** können Sie die für einen einzelnen Benutzer suchen und alle Sitzungsdetails des Benutzers in der folgenden Tabelle angezeigt. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Geben Sie den Zeitpunkt** können, die Sie in das Startdatum platzieren. Im Kalender können Sie wählen Sie das Datum oder das Datum manuell eingeben. Dieses Feld muss aufgefüllt werden.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**EINGABETASTE, um den Zeitpunkt** können, die Sie in das Enddatum zu platzieren. Im Kalender können Sie wählen Sie das Datum oder das Datum manuell eingeben. Wenn kein Enddatum festgelegt ist, ist der Standardwert 30 Tagen ab dem Startdatum an.
***
![Nummer 4](../images/sfbcallout4.png)<br/>Die Tabelle zeigt Sie einen Überblick über die alle Sitzungsdetails pro Benutzer. Zeigt alle Benutzer, die Skype für Unternehmen und ihren Sitzungsinformationen zugewiesen haben. Sie können hinzufügen/Spalten der Tabelle entfernen. <br/><br/>Die Tabelle enthält die folgenden Spalten für jede Sitzung:
*    **Dialog-ID** ist die ID für die eindeutige ID der SIP-Sitzung.
*    **Media-Typen Beschreibung** beschreibt, ob die Sitzung einer Telefonkonferenz oder einer Sitzung P2P und den Typ der verwendeten Medien (Audio/Video/Anwendungsfreigabe) ist.
*    **Startzeit** ist die Uhrzeit des Sitzungsbeginns.
*    **End** ist die Zeit, wenn die Sitzung beendet wurde.
*    **Von URI** ist der URI des Benutzers oder der Dienst, der die Sitzung initiiert hat. Kann leer sein, wenn der Benutzer den Anruf von einem PSTN-Telefon initiiert hat.
*    **To-URI** ist der URI des Benutzers oder der Dienst, der das Ziel der Session Initiation war. Bei der Konferenz ist dies der Organisator URI. Kann leer sein, wenn das Ziel der Sitzung ein PSTN-Nummer war.
*    **Von der Clientversion** erfahren Sie, den Benutzer-Agent und die Version des Clients verwendet, die vom Benutzer oder der Dienst, der die Sitzung initiiert hat.
*    **Um Clientversion** erfahren Sie, den Benutzer-Agent und die Version des Clients verwendet, die vom Benutzer oder der Dienst, der das Ziel der Session Initiation war.
*    **Konferenz-URL** ist der SIP-URL für die Konferenz, wenn die Sitzung einer Telefonkonferenz wurde. Alle Benutzer in der gleichen Telefonkonferenz müssen die gleichen Konferenz-URL. 
*    **Anzahl von Tel** ist die Telefonnummer ein, die das Ziel der Sitzung war, falls zutreffend. Mit "X" zum Schutz der Privatsphäre der Benutzer können die letzten Ziffern der Rufnummer ersetzt werden.
*    **Um Tel Anzahl** ist die Telefonnummer ein, die das Ziel der Sitzung war, falls zutreffend. Mit "X" zum Schutz der Privatsphäre der Benutzer können die letzten Ziffern der Rufnummer ersetzt werden.
*    **Von den Endpunkt-Id** ist eine eindeutige GUID des Endpunkts des Benutzers aus. Festgestellt, ob Benutzer mehrere Sitzungen von denselben Endpunkt kommuniziert. Kann leer sein, wenn Benutzer eine PSTN-Telefon verwendet oder aus einem Dienst, die die Sitzung initiiert wurde.
*    **Endpunkt-Id** ist eine eindeutige GUID des Endpunkts des Benutzers an. Festgestellt, ob Benutzer mehrere Sitzungen von denselben Endpunkt kommuniziert. Kann leer sein, wenn Benutzer einem PSTN-Telefon verwendet wird, wenn die Sitzung aus einem Dienst initiiert wurde, oder Fehler bei einer Sitzung herstellen.
*    **Conf-Instanz** ist eine eindeutige GUID für die Instanz der Konferenz mithilfe des Konferenz-URL. Besprechungsserien werden dieselbe URL der Konferenz, aber jede Instanz der Besprechung wird einen Unterschied Conf Instanz haben.
*    **Im Auftrag von URI** ist der URI des Stellvertreters in dessen Namen die Sitzung hergestellt wird. <br/> **Durch URI bezeichnet** ist der URI des Benutzers, der die Einrichtung einer Sitzung bezeichnet.
*    **Antwortcode** ist der SIP-Antwortcode für die Einrichtung der Sitzung, die angibt, ob die Sitzung erfolgreich hergestellt wurde.

Für jede Sitzung ist eine Sub-Tabelle mit unterschiedlichen Daten je nach Szenario zur Verfügung. Im folgenden werden die Registerkarten in der Tabelle "Sub" für der FROM- und für Benutzer oder Dienste.
*    Auf der Registerkarte SITZUNG werden Daten zu den Betriebssystemen und Computern.
*    Auf der Registerkarte MEDIALINES werden Konnektivitätsinformationen Netzwerk und Geräteinformationen.
*    Registerkarte AUDIOSTREAMS werden Leistungsdaten Netzwerk über die Audiostreams in Sitzung angezeigt.
*    Auf der Registerkarte AUDIOCLIENTEVENTS werden Daten zu Problemen auf dem Client erkannt Paketverlust beeinflusst die Audioqualität.
*    Auf der Registerkarte AUDIOSIGNALS werden Daten über das Audiosignal Verarbeitung für die Sitzung.
*    Registerkarte APPSHARINGSTREAMS zeigt Netzwerk Leistungsdaten für die Anwendungsfreigabe oder desktop freigeben Streams in Sitzung.
*    Auf der Registerkarte VIDEOCLIENTEVENTS werden Daten über das Videoerlebnis beeinträchtigen Problemen auf dem Client erkannt.
*    Registerkarte VIDEOSTREAMS werden Leistungsdaten Netzwerk über die Videostreams in Sitzung angezeigt.
*    Auf der Registerkarte PINGSIGNALE werden die Netzwerkhops über Traceroute während der Sitzung erfasst. Der tatsächliche Medienpfad für die Sitzung verwendete variieren, und diese Daten ist nur verfügbar, wenn Audiodaten in der Sitzung ist.
*    Auf der Registerkarte FEEDBACKREPORTS werden alle Ende des Anrufs Umfragedaten von den Benutzern in der Sitzung bereitgestellt.
***
![Zahl 5](../images/sfbcallout5.png)<br/>Click to drag a column to **To group by a particular column, drag and drop the column header here** if you want to create a view that groups all of the data in one or more columns. 
***
![Zahl 6](../images/sfbcallout6.png)<br/>Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen. <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Ein-/Auswahl (Drittanbieter) und Ein-/Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Einwahl-/Auswahlkonferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) : Sie können die Anzahl der Minuten sehen, die für eingehende/ausgehende Anrufe aufgewendet wurden, sowie die Kosten für diese Anrufe.

- [Skype für Unternehmensbenutzer blockiert Bericht](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation, die vom PSTN-Anrufe tätigen blockiert wurden, finden Sie unter.

- [Skype für Business PSTN Minute Pools Bericht](pstn-minute-pools-report.md) sehen Sie die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 