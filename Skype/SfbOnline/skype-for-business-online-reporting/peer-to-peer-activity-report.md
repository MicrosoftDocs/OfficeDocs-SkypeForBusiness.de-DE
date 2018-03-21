---
title: "Bericht über Peer-zu-Peer-Aktivität"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.custom:
- Reporting
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: ebf1336fb45cbbb6d0b9d6044fb5ae389c2b9dab
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="peer-to-peer-activity-report"></a>Bericht über Peer-zu-Peer-Aktivität

Im neuen Office 365-Dashboard **Berichte** wird eine Aktivitätsübersicht über die Office 365-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten. Beispielsweise können Sie den Bericht **Skype für geschäftliche Peer-zu-Peer-Aktivität** verwenden, sehen, wie viel die Benutzer Sofortnachrichten, Audio, video, Anwendung freigeben und Übertragen von Dateien verwendet werden. 

Checken Sie die [Berichte (Übersicht)](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
In diesem Bericht, zusammen mit den anderen Skype für Business-Berichte, erhalten Sie Details auf Aktivität innerhalb Ihrer Organisation. Diese Details sind beim Untersuchen, Planen und Treffen anderer Geschäftsentscheidungen für Ihre Organisation äußerst hilfreich. 
  
> [!NOTE]
> Sie können alle Skype for Business-Berichte anzeigen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden. 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>So rufen Sie den Bericht „Skype for Business - Peer-zu-Peer-Aktivitäten" ab

1. Navigieren Sie zu **Office 365 Admin Center** > **Berichte** > **Nutzung**.
    
2. Klicken Sie auf der Seite **Usage** **Skype für geschäftliche Peer-zu-Peer-Aktivität** auf die **Auswahlliste einen Bericht** auf der linken Seite auf. Oder klicken Sie auf das Widget **Skype für geschäftliche Aktivität** , und klicken Sie dann auf die Liste **Skype für geschäftliche Aktivität** **Skype für geschäftliche Peer-zu-Peer-Aktivität** .
    
     ![Skype-Peer-zu-Peer-Menü ausgewählt](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > Je nach vorhandenem Office 365-Abonnement sehen Sie möglicherweise nicht alle Produkte und Aktivitätsberichte, die hier angezeigt werden. 
  
## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Interpretieren des Berichts „Skype for Business - Peer-zu Peer-Aktivitäten"

Einen Einblick in die Peer-zu-Peer-Aktivitäten in Skype for Business erhalten Sie, wenn Sie sich die Diagramme **Aktivität**, **Benutzer** und **Minuten** ansehen.
  
![Skype-Peer-zu-Peer-Bericht mit Legenden.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>Im Bericht **Skype for Business - Peer-zu-Peer-Aktivität** werden die Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Nummer 2](../images/sfbcallout2.png)<br/>Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. 
***
![Nummer 3](../images/sfbcallout3.png)<br/>Verwenden Sie die interaktiven Diagrammdaten im Diagramm **Aktivität**, um die Nutzungstrends nachzuvollziehen und die Gesamtanzahl der in Ihrer Organisation abgehaltenen Sitzungen pro Sitzungstyp einzusehen. Es werden insgesamt Anzahl und Typen von **Sofortnachrichten**, **Audio**, **Video**, **Anwendungsfreigabe**und **dateiübertragungen** Sitzungen in Ihrer Organisation angezeigt. 
***
![Nummer 4](../images/sfbcallout4.png)<br/>Verwenden Sie die interaktiven Diagrammdaten im Diagramm **Benutzer**, um Nutzungstrends nachzuvollziehen und die Anzahl an eindeutigen Benutzern, die an den in Ihrer Organisation abgehaltenen Peer-zu-Peer-Aktivitäten teilgenommen haben, anzuzeigen. Die Gesamtzahl der Benutzer sowie die Arten von **Sofortnachrichten**, **Audio**, **Video**, **Anwendungsfreigabe**und **dateiübertragungen** wird in Peer-zu-Peer-Sitzungen angezeigt.
***
![Zahl 5](../images/sfbcallout5.png)<br/>Verwenden Sie die interaktiven Diagrammdaten im Diagramm **Minuten**, um Nutzungstrends nachzuvollziehen und zu sehen, wie viele Minuten von Benutzern für Peer-zu-Peer-Aktivitäten mit Audio und Video genutzt werden. Es zeigt Ihnen die Gesamtanzahl der Minuten für **Audio** und **Video**, die in Peer-zu-Peer-Sitzungen genutzt werden.  
***
![Zahl 6](../images/sfbcallout6.png)<br/>Jedes Diagramm verfügt über eine (horizontale) „X"- und eine (vertikale) „Y"-Achse. 
*    Im Aktivitätsdiagramm **Aktivität** entspricht die Y-Achse der Gesamtanzahl an Chat-, Audio-, Video-, Anwendungsfreigabe- und Dateiübertragungssitzungen, die Ihre Benutzer in der Organisation abgehalten haben.
*    Klicken Sie auf das Diagramm für **Benutzer** Aktivitäten ist die y-Achse die insgesamt Anzahl Benutzer, die für Sofortnachrichten, Audio, video, Anwendung freigeben und Übertragen von Dateien Sitzungen reserviert. 
*    Im Aktivitätsdiagramm **Minuten** entspricht die Y-Achse der Gesamtanzahl an Minuten, die Benutzer in Ihrer Organisation mit der Nutzung von Peer-zu-Peer-Sitzungen mit Audio und Video verbracht haben. 

Die X-Achse bezeichnet in beiden Diagrammen den ausgewählten Zeitraum für diesen bestimmten Bericht.
***
![Anzahl 7](../images/sfbcallout7.png)<br/>Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende auf ein Element klicken. Beispielsweise im Diagramm **Aktivität** klicken Sie oder tippen Sie auf **Sofortnachrichten**, **Audio**, **Video**, **Anwendungsfreigabe**und **dateiübertragungen** , um nur die Informationen im Zusammenhang mit jeweils finden Sie unter. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert. 
***
![Zahl 8](../images/sfbcallout8.png)<br/>Die Tabelle zeigt eine Aufschlüsselung der Peer-zu-Peer-Aktivitäten pro Benutzer an. Diese Auflistung enthält alle Benutzer, denen Skype for Business zugewiesen ist, sowie deren Peer-zu-Peer-Aktivitäten. Sie können zusätzliche Spalten zur Tabelle hinzufügen.
*    **Benutzername** ist der Name des Benutzers.
*    **Gelöscht** bedeutet, dass die Lizenz des Benutzers entfernt wurde. <br/> <br/> **Hinweis:**  Aktivitäten für eine gelöschte Benutzer wird weiterhin in einem Bericht angezeigt, solange er zu einem Zeitpunkt während des ausgewählten Zeitraums lizenziert wurde. Der Spalte **Gelöscht** können Sie entnehmen, dass der Benutzer zwar möglicherweise nicht mehr aktiv ist, aber dass der Bericht dennoch ihn betreffende Daten enthält.  <br/><br/>
*    **Gelöscht am** ist das Datum, an dem die Lizenz des Benutzers entfernt wurde. 
*    **Datum der letzten Aktivität (UTC)** ist das Datum der letzten Aktivität (UTC) für diesen Benutzer.
*    **Chat** zeigt die Gesamtanzahl der von dem Benutzer verwendeten Peer-zu-Peer-Sitzungen an.
*    **Audio** zeigt die Gesamtanzahl der Peer-zu-Peer-Sitzungen an, in denen Audio verwendet wurde.
*    **Video** zeigt die Gesamtanzahl der Peer-zu-Peer-Sitzungen an, in denen Video verwendet wurde.
*    **Anwendungsfreigabe** zeigt die Gesamtanzahl der Peer-zu-Peer-Sitzungen mit Anwendungsfreigabe an.
*    **Dateiübertragungen** zeigt die Gesamtanzahl der Peer-zu-Peer-Sitzungen mit Dateiübertragung an.
*    **Audiominuten** zeigt die Gesamtanzahl der in der Organisation verwendeten Audiominuten an. 
*    **Videominuten** zeigt die Gesamtanzahl der in der Organisation verwendeten Videominuten an. 

Wenn Richtlinien Ihrer Organisation verhindert, dass Sie Berichte anzeigen, in dem Benutzerinformationen erkennbar ist, können Sie die für den Datenschutz für alle diese Berichte ändern. Checken Sie die **wie blenden Sie Ebene Benutzerdetails?** Abschnitt in der [Berichte im Office 365 Administrationscenter](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
***
![Zahl 9](../images/sfbcallout9.png)<br/>Sie können die Berichtsdaten auch in eine Excel-Datei im Format .csv exportieren, indem Sie auf den Link **Exportieren** klicken oder tippen.           <br/> ![Skype für das Business Reporting Schaltfläche Exportieren.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.
***
![Anzahl 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>Klicken Sie oder tippen Sie auf das Symbol **Spalten** in einer der Spalten hinzufügen oder Entfernen von Spalten aus dem Bericht.         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Ein-/Auswahl (Drittanbieter) und Ein-/Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Einwahl-/Auswahlkonferenzen teilgenommen wird.
    
- [Skype für Unternehmensbenutzer blockiert Bericht](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation, die vom PSTN-Anrufe tätigen blockiert wurden, finden Sie unter.
    
- [Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) : Sie können die Anzahl der Minuten sehen, die für eingehende/ausgehende Anrufe aufgewendet wurden, sowie die Kosten für diese Anrufe.
    
- [Skype für Business PSTN Minute Pools Bericht](pstn-minute-pools-report.md) sehen Sie die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht.

- [Skype für Business Sitzung Detailbericht](session-details-report.md) Sie können die Details zu einzelnen Benutzers Anruf Erfahrungen sehen.
    
## <a name="related-topics"></a>See Also
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

## <a name="feedback"></a>Feedback?
Geben Sie Feedback zu Produkten oder uns Ihre Meinung kennen, finden Sie unter [Skype für Business Feedback](https://www.skypefeedback.com).