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
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: Im Dashboard Berichte wird eine Aktivitätsübersicht über die verschiedenen Microsoft 365 oder Office 365 in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten.
ms.openlocfilehash: 522a82bf9b93a590f8f319d59e805b23ba34d4665b34eb05541aa18d1b9ba89e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308016"
---
# <a name="session-details-report"></a>Bericht „Sitzungsdetails“

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Im **Dashboard** Berichte wird eine Aktivitätsübersicht über die verschiedenen Microsoft 365 oder Office 365 in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten. So können Sie beispielsweise den Bericht Skype for Business **Sitzungsdetails** verwenden, um Details zu den Anruferfahrungen einzelner Benutzer anzuzeigen.
  
Weitere verfügbare [Berichte finden](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) Sie unter Übersicht über Berichte.
  
Dieser Bericht enthält zusammen mit den Skype for Business Bericht Details zu den Aktivitäten, einschließlich Sitzungsdetails in Der gesamten Organisation. Diese Details sind beim Untersuchen, Planen und Treffen anderer Geschäftsentscheidungen für Ihre Organisation sowie für das Einrichten von Guthaben für [Kommunikationen sehr hilfreich.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Wenn Sie sich als Administrator bei der Skype for Business anmelden, können Sie alle Microsoft 365 Admin Center. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>So erhalten Sie den Bericht Skype for Business Sitzungsdetails

1. Wechseln Sie zum Admin Center, und > **Berichte.**
    
2. Wählen **Sie im** linken Menü Berichte aus, und klicken Sie dann auf **Verwendung.**
    
3. Klicken Sie in der Liste **unter Bericht auswählen** Skype for Business **Sitzungsdetails**.
    
    > [!TIP]
    > Wenn dieser Bericht nicht aufgelistet ist, wechseln Sie zu Skype for Business **Admin Center**:  >  **Sitzungsdetails.**  >   
  
    > [!IMPORTANT]
    > Je nach Microsoft 365 oder Office 365-Abonnement werden möglicherweise nicht alle Produkte und Berichte angezeigt, die hier angezeigt werden. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpretieren des Berichts Skype for Business Sitzungsdetails"

Sie können einen Einblick in die Details der Skype for Business-Sitzung erhalten, indem Sie sich die einzelnen angezeigten Spalten ansehen.
  
Der Bericht sieht folgendermaßen aus:
  
![Skype for Business Sitzungsdetails, Berichtsdashboard.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Mit Benutzer nach Alias suchen** können Sie nach einem einzelnen Benutzer suchen und alle Sitzungsdetails des Benutzers in der nachstehenden Tabelle anzeigen. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Wenn Sie vom Datumstermin** eingeben, können Sie das Startdatum eingeben. Sie können den Kalender verwenden, um das Datum auszuwählen oder das Datum manuell ein eingeben. Dieses Feld muss ausgefüllt sein.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Mit "Bis Datumszeit** eingeben" können Sie das Enddatum eingeben. Sie können den Kalender verwenden, um das Datum auszuwählen oder das Datum manuell ein eingeben. Wenn kein Enddatum festgelegt ist, liegt der Standardwert 30 Tage nach dem Startdatum.
***
![Nummer 4](../images/sfbcallout4.png)<br/>Die Tabelle zeigt eine Aufschlüsselung aller Sitzungsdetails pro Benutzer. Hier werden alle Benutzer, denen Skype for Business zugewiesen sind, sowie ihre Sitzungsinformationen gezeigt. Sie können der Tabelle Spalten hinzufügen/entfernen. <br/><br/>Die Tabelle enthält die folgenden Spalten für jede Sitzung:
*    **Die Dialogfeld-ID** ist die ID für den eindeutigen Bezeichner der SIP-Sitzung.
*    **Die Beschreibung der Medientypen** beschreibt, ob es sich bei der Sitzung um eine Telefonkonferenz oder eine P2P-Sitzung handelt, und es wird der Verwendete Medientyp (Audio/Video/Anwendungsfreigabe) beschrieben.
*    **Startzeit ist** die Uhrzeit, zu der die Sitzung gestartet wurde.
*    **Endzeit ist** die Uhrzeit, zu der die Sitzung beendet wurde.
*    **Von URI** ist der URI des Benutzers oder Diensts, der die Sitzung initiiert hat. Kann leer sein, wenn der Benutzer die Sitzung von einem PSTN-Telefon aus initiiert hat.
*    **To URI** is the URI of the user or service that was the target of the session initiation. Im Fall der Konferenz ist dies der URI des Organisators. Kann leer sein, wenn das Ziel der Sitzung eine PSTN-Telefonnummer war.
*    **Von der Clientversion** erfahren Sie, dass der Benutzer-Agent und die Version des Clients verwendet werden, der bzw. der von dem Benutzer oder Dienst verwendet wurde, der die Sitzung initiiert hat.
*    **Die Clientversion teilt** Ihnen mit, dass der Benutzer-Agent und die Version des Vom Benutzer oder Dienst verwendeten Clients das Ziel der Sitzungsinitiierung war.
*    **Konferenz-URL** ist die SIP-URL für die Konferenz, wenn es sich bei der Sitzung um eine Telefonkonferenz handelte. Alle Benutzer derselben Telefonkonferenz haben dieselbe Konferenz-URL. 
*    **From Tel number** is the telephone number that was the target of the session, if applicable. Zum Schutz der Privatsphäre des Benutzers können die letzten Ziffern der Telefonnummer durch "x" ersetzt werden.
*    **To Tel number** is the telephone number that was the target of the session, if. Zum Schutz der Privatsphäre des Benutzers können die letzten Ziffern der Telefonnummer durch "x" ersetzt werden.
*    **Von Endpunkt-ID** ist eine eindeutige GUID des Endpunkts, der vom Benutzer "Von" verwendet wird. Wird verwendet, um zu identifizieren, ob der Benutzer mehrere Sitzungen von demselben Endpunkt aus kommuniziert. Kann leer sein, wenn der Benutzer ein Festnetztelefon verwendet oder die Sitzung von einem Dienst initiiert wurde.
*    **Für Endpunkt-ID** ist eine eindeutige GUID des Endpunkts, der vom An-Benutzer verwendet wird. Wird verwendet, um zu identifizieren, ob der Benutzer mehrere Sitzungen von demselben Endpunkt aus kommuniziert. Kann leer sein, wenn der Benutzer ein Festnetztelefon verwendet, wenn die Sitzung von einem Dienst initiiert wurde oder wenn eine Sitzung nicht gestartet werden konnte.
*    **Conf Instance** ist eine eindeutige GUID für die Instanz der Konferenz unter Verwendung der Konferenz-URL. Besprechungsserien haben dieselbe Konferenz-URL, aber für jede Instanz der Besprechung gibt es einen Unterschied zwischen "Conf Instance".
*    **Im Auftrag von URI** ist der URI des Delegators, in dessen Auftrag die Sitzung eingerichtet wird. <br/> **Von URI bezeichnet** ist der URI des Benutzers, der auf die Einführung einer Sitzung verwiesen hat.
*    **Antwortcode** ist der SIP-Antwortcode für die Einrichtung der Sitzung, der angibt, ob die Sitzung erfolgreich eingerichtet wurde.

Für jede Sitzung gibt es eine Untertabelle mit unterschiedlichen Daten, die je nach Szenario verfügbar sind. In der folgenden Liste sind die Registerkarten aufgeführt, die in der Untertabelle für die Von- und Bis-Benutzer oder -Dienste verfügbar sind.
*    Auf der Registerkarte SITZUNG werden Daten zu den Computern und Betriebssystemen angezeigt.
*    Auf der Registerkarte MEDIALINES werden Netzwerkverbindungsinformationen und Geräteinformationen angezeigt.
*    Auf der Registerkarte AUDIOSTREAMS werden Netzwerkleistungsdaten zu den audiostreams angezeigt, die an einer Sitzung beteiligt sind.
*    Die Registerkarte "AUDIOCLIENTEVENTS" zeigt Daten zu vom Client erkannten Problemen bei der Audiowiedergabe an.
*    Auf der Registerkarte AUDIOSIGNALS werden Daten zur Audiosignalverarbeitung für die Sitzung angezeigt.
*    Auf der Registerkarte "APPSHARINGSTREAMS" werden Daten zur Netzwerkleistung zu den Anwendungsfreigabe- oder Desktopfreigabe-Streams angezeigt, die an einer Sitzung beteiligt sind.
*    Die Registerkarte VIDEOCLIENTEVENTS zeigt Daten zu vom Client erkannten Problemen an, die sich auf die Videoerfahrung auswirken.
*    Auf der Registerkarte VIDEOSTREAMS werden Netzwerkleistungsdaten zu den videostreams angezeigt, die an einer Sitzung beteiligt sind.
*    Auf der Registerkarte TRACEROUTES werden die Netzwerkhops angezeigt, die während der Sitzung über TraceRoute gesammelt wurden. Der tatsächliche Medienpfad, der für die Sitzung verwendet wird, kann variieren, und diese Daten sind nur verfügbar, wenn in der Sitzung Audio vorhanden ist.
*    Auf der Registerkarte FEEDBACKREPORTS werden alle End-of-Call-Umfragedaten angezeigt, die von den Benutzern der Sitzung bereitgestellt werden.
***
![Nummer 5](../images/sfbcallout5.png)<br/>Klicken Sie, um eine Spalte nach Zu gruppieren nach einer bestimmten Spalte zu **ziehen,** ziehen Sie die Spaltenüberschrift hier, und legen Sie sie dort ab, wenn Sie eine Ansicht erstellen möchten, in der alle Daten in einer oder mehreren Spalten angeordnet sind. 
***
![Nummer 6](../images/sfbcallout6.png)<br/>Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen. <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Ein-/Auswahl (Drittanbieter) und Ein-/Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) Sie können sehen, an wie vielen Ein-/Einwahlkonferenzen, Audio/Video-, Anwendungsfreigabe-, Web- und Ein-/Aus-Konferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) : Sie können die Anzahl der Minuten sehen, die für eingehende/ausgehende Anrufe aufgewendet wurden, sowie die Kosten für diese Anrufe.

- [Skype for Business von Benutzern gesperrter Bericht](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation sehen, die für das Erstellen von PSTN-Anrufen gesperrt wurden.

- [Skype for Business Bericht zu PSTN-Minutenpools](pstn-minute-pools-report.md) können Sie die Anzahl der Minuten sehen, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
