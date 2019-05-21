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
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Im neuen Office 365-Dashboard Berichte wird eine Aktivitätsübersicht über die Office 365-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten.
ms.openlocfilehash: 62b64fd971d776b265d7b78789e8ac7684cc5e26
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302087"
---
# <a name="session-details-report"></a>Bericht „Sitzungsdetails“

Im neuen Office 365-Dashboard **Berichte** wird eine Aktivitätsübersicht über die Office 365-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten. So können Sie beispielsweise den Bericht **Skype for Business-Sitzungsdetails** verwenden, um Details zu den Anruf Erfahrungen einzelner Nutzer anzuzeigen.
  
Weitere verfügbare Berichte finden Sie unter [Übersicht über Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) .
  
Dieser Bericht sowie die anderen Skype for Business-Berichte geben Ihnen detaillierte Informationen zu Aktivitäten, einschließlich Sitzungsdetails in Ihrer Organisation. Diese Informationen sind sehr hilfreich, wenn Sie untersuchen, planen und andere geschäftliche Entscheidungen für Ihre Organisation treffen und [Kommunikationsguthaben](/microsoftteams/what-are-communications-credits)einrichten.
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>So erhalten Sie den Bericht "Skype for Business-Sitzungsdetails"

1. Wechseln Sie zu den **Office 365 Admin Center** > -**Berichten** .
    
2. Wählen Sie im linken Menü **Berichte** aus, und klicken Sie dann auf **Verwendung**.
    
3. Klicken Sie in der Liste unter **Bericht auswählen**auf **Skype for Business-Sitzungsdetails**.
    
    > [!TIP]
    > Wenn dieser Bericht nicht aufgeführt ist, wechseln Sie zu den**Berichten** > zur **Skype for Business Admin Center** > -**Sitzungsdetails**. 
  
    > [!IMPORTANT]
    > Je nach vorhandenem Office 365-Abonnement werden möglicherweise nicht alle Produkte und Berichte angezeigt, die in diesem Artikel besprochen werden. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretieren des Berichts "Skype for Business-Sitzungsdetails"

Sie können sich einen Überblick über die Skype for Business-Sitzungsdetails Ihrer Benutzer verschaffen, indem Sie sich die einzelnen angezeigten Spalten ansehen.
  
Der Bericht sieht folgendermaßen aus:
  
![Bericht Dashboard für Skype for Business-Sitzungs Details](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Durchsuchen des Benutzers nach Alias** können Sie nach einem einzelnen Benutzer suchen und alle Sitzungsdetails des Benutzers in der folgenden Tabelle anzeigen. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Geben Sie ab Datum ein** , damit Sie den Anfangstermin eingeben können. Sie können den Kalender verwenden, um das Datum auszuwählen oder das Datum manuell einzugeben. Dieses Feld muss ausgefüllt werden.
***
![Nummer 3](../images/sfbcallout3.png)<br/>Geben Sie in das Feld **Datum ein, damit** Sie das Enddatum eingeben können. Sie können den Kalender verwenden, um das Datum auszuwählen oder das Datum manuell einzugeben. Wenn kein Enddatum gesetzt ist, ist der Standardwert 30 Tage ab dem Anfangstermin.
***
![Nummer 4](../images/sfbcallout4.png)<br/>Die Tabelle zeigt eine Aufschlüsselung aller Sitzungsdetails pro Benutzer. Dies zeigt alle Benutzer an, denen Skype for Business zugewiesen ist, sowie deren Sitzungsinformationen. Sie können der Tabelle Spalten hinzufügen oder daraus entfernen. <br/><br/>Die Tabelle enthält die folgenden Spalten für jede Sitzung:
*    Die **Dialog Feld-ID** ist die ID für den eindeutigen Bezeichner der SIP-Sitzung.
*    **Beschreibung der Medientypen** beschreibt, ob es sich bei der Sitzung um einen Konferenzanruf oder eine P2P-Sitzung handelt sowie um die Art des verwendeten Mediums (Audio/Video/Anwendungsfreigabe).
*    **Startzeit** ist der Zeitpunkt, zu dem die Sitzung gestartet wurde.
*    **Endzeit** ist der Zeitpunkt, zu dem die Sitzung beendet wurde.
*    **Von URI** ist der URI des Benutzers oder Diensts, der die Sitzung initiiert hat. Kann leer sein, wenn der Benutzer die Sitzung von einem PSTN-Telefon aus initiiert hat.
*    **Bei URI** handelt es sich um den URI des Benutzers oder Diensts, der das Ziel der Sitzungs Initiierung war. Im Fall der Konferenz handelt es sich um den URI des Organisators. Möglicherweise ist das Ziel der Sitzung leer, wenn es sich um eine PSTN-Telefonnummer handelt.
*    **In der Client Version** erfahren Sie den Benutzer-Agent und die Version des Clients, der vom Benutzer oder Dienst, der die Sitzung initiiert hat, verwendet wurde.
*    **In der Client Version** wird der Benutzer-Agent und die Version des Clients angegeben, der vom Benutzer oder Dienst verwendet wurde, der das Ziel der Sitzungs Initiierung war.
*    **Konferenz-URL** ist die SIP-URL für die Konferenz, wenn es sich bei der Sitzung um einen Konferenzanruf handelt. Alle Benutzer im gleichen Konferenzanruf haben dieselbe Konferenz-URL. 
*    Bei **Tel-Nummer** handelt es sich um die Telefonnummer, die das Ziel der Sitzung war (falls zutreffend). Die letzten Ziffern der Telefonnummer können durch "x" ersetzt werden, um die Privatsphäre der Nutzer zu schützen.
*    Bei **Tel-Nummer** handelt es sich um die Telefonnummer, die das Ziel der Sitzung war (falls zutreffend). Die letzten Ziffern der Telefonnummer können durch "x" ersetzt werden, um die Privatsphäre der Nutzer zu schützen.
*    **Von Endpunkt-ID** ist eine eindeutige GUID des vom from-Benutzer verwendeten Endpunkts. Wird verwendet, um zu ermitteln, ob der Benutzer mehrere Sitzungen desselben Endpunkts kommuniziert. Kann leer sein, wenn der Benutzer ein PSTN-Telefon verwendet oder wenn die Sitzung von einem Dienst initiiert wurde.
*    Die **Endpunkt-ID** ist eine eindeutige GUID des vom to-Benutzer verwendeten Endpunkts. Wird verwendet, um zu ermitteln, ob der Benutzer mehrere Sitzungen desselben Endpunkts kommuniziert. Kann leer sein, wenn der Benutzer ein PSTN-Telefon verwendet, wenn die Sitzung von einem Dienst initiiert wurde oder eine Sitzung nicht erstellt werden konnte.
*    **Conf-Instanz** ist eine eindeutige GUID für die Instanz der Konferenz mit der Konferenz-URL. Wiederkehrende Besprechungen verfügen über die gleiche Konferenz-URL, aber jede Instanz der Besprechung verfügt über eine Difference conf-Instanz.
*    **Im Auftrag von URI** befindet sich der URI des delegaters, in dessen Auftrag die Sitzung hergestellt wird. <br/> **URI** ist der URI des Benutzers, der die Einrichtung einer Sitzung angewiesen hat.
*    **Antwortcode** ist der SIP-Antwortcode für die Einrichtung der Sitzung, die angibt, ob die Sitzung erfolgreich hergestellt wurde.

Für jede Sitzung steht je nach Szenario eine unter Tabelle mit unterschiedlichen Daten zur Verfügung. Im folgenden werden die Registerkarten aufgeführt, die in der unter Tabelle für die von-und für-Benutzer oder-Dienste zur Verfügung stehen.
*    Auf der Registerkarte Sitzung werden die Daten zu den Computern und Betriebssystemen angezeigt.
*    Registerkarte "MEDIALINES" zeigt Netzwerk Verbindungsinformationen und Geräteinformationen an.
*    Auf der Registerkarte AUDIOSTREAMS werden die Netzwerkleistungsdaten zu den Audiostreams angezeigt, die an der Sitzung beteiligt sind.
*    Auf der Registerkarte "AUDIOCLIENTEVENTS" werden Daten zu Clientproblemen angezeigt, die sich auf die Audioqualität auswirken.
*    Registerkarte "AUDIOSIGNALS" zeigt Daten zur Audiosignal-Verarbeitung für die Sitzung an.
*    Registerkarte "APPSHARINGSTREAMS" zeigt Netzwerkleistungsdaten über die Anwendungsfreigabe-oder Desktopfreigabedaten Ströme an, die an einer Sitzung beteiligt sind.
*    Auf der Registerkarte "VIDEOCLIENTEVENTS" werden Daten zu Clientproblemen angezeigt, die sich auf das Videoverhalten auswirken.
*    Auf der Registerkarte VIDEOSTREAMS werden die Netzwerkleistungsdaten zu den in der Sitzung beteiligten Videodatenströmen angezeigt.
*    Die Registerkarte Traceroutes zeigt die Netzwerkhops an, die während der Sitzung über traceroute gesammelt wurden. Der für die Sitzung verwendete tatsächliche Medienpfad kann variieren, und diese Daten stehen nur zur Verfügung, wenn in der Sitzung Audio vorhanden ist.
*    Auf der Registerkarte FEEDBACKREPORTS werden alle von den Benutzern in der Sitzung bereitgestellten Ende der Anruf Umfragedaten angezeigt.
***
![Nummer 5](../images/sfbcallout5.png)<br/>Click to drag a column to **To group by a particular column, drag and drop the column header here** if you want to create a view that groups all of the data in one or more columns. 
***
![Nummer 6](../images/sfbcallout6.png)<br/>Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen. <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Ein-/Auswahl (Drittanbieter) und Ein-/Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business-Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) Sie können sehen, wie viele Chats, Audio/Video, Anwendungsfreigabe, Web-und Einwahlkonferenz Konferenzen teilnehmen.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) : Sie können die Anzahl der Minuten sehen, die für eingehende/ausgehende Anrufe aufgewendet wurden, sowie die Kosten für diese Anrufe.

- [Bericht "Skype for Business-Benutzer blockiert](users-blocked-report.md) " Sie können die Benutzer in Ihrer Organisation sehen, die für das tätigen von PSTN-anrufen gesperrt wurden.

- [Skype for Business-PSTN-Minuten Pools-Bericht](pstn-minute-pools-report.md) Sie können die Anzahl der Minuten anzeigen, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 