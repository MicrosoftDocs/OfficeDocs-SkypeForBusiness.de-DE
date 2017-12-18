---
title: "Bericht zum PSTN-Verbrauch in Skype for Business"
ms.author: tonysmit
author: tonysmit
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
description: "Die neue Skype für Business-Verwaltungskonsole, Berichte Bereich zeigt anrufen und Konferenzen Aktivität in Ihrer Organisation. Sie können in Berichten zur Verfügung, eine genauere Einblicke zu den Aktivitäten von jedem Benutzer einen Drilldown ausführen. Den Bericht Skype für Business PSTN Verwendungsdetails können Sie beispielsweise die Anzahl der Minuten in ein-/ausgehende Anrufe aufgewendet und Kosten für diese Aufrufe finden Sie unter. Sie können anzeigen einwahlkonferenzen PSTN-Verwendungsdetails einschließlich der die Kosten des Anrufs, damit Sie Ihre Verwendung verstehen und anrufen Abrechnungsinformationen Verwendung innerhalb Ihrer Organisation ermitteln können."
---

# Bericht zum PSTN-Verbrauch in Skype for Business

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](74eda791-c41f-4fd9-ae0b-913342e7ab04.md#MT_Footer).  
  
Die neue Skype für Business-Verwaltungskonsole, **Berichte** Bereich zeigt anrufen und Konferenzen Aktivität in Ihrer Organisation. Sie können in Berichten zur Verfügung, eine genauere Einblicke zu den Aktivitäten von jedem Benutzer einen Drilldown ausführen. Den Bericht **Skype für Business PSTN Verwendungsdetails** können Sie beispielsweise die Anzahl der Minuten in ein-/ausgehende Anrufe aufgewendet und Kosten für diese Aufrufe finden Sie unter. Sie können anzeigen einwahlkonferenzen PSTN-Verwendungsdetails einschließlich der die Kosten des Anrufs, damit Sie Ihre Verwendung verstehen und anrufen Abrechnungsinformationen Verwendung innerhalb Ihrer Organisation ermitteln können.
  
 In der[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) finden Sie weitere verfügbare Berichte.
  
Diesen Bericht zusammen mit den anderen Skype für Geschäftsberichten bieten Ihnen Details auf Aktivität einschließlich PSTN-Verwendung in Ihrer Organisation. Diese Details sind sehr hilfreich, wenn Sie untersuchen, für Ihre Organisation und zum Einrichten der [Was ist Guthaben für Kommunikationen?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)planen und Bereitstellen von anderen Unternehmen Entscheidungen.
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden 
  
## Abrufen des Berichts zu den PSTN-Verbrauchsdetails in Skype for Business

1. Wechseln Sie zu Office 365 Administrationscenter > Klicken Sie auf die Verwaltungskonsolen > Klicken Sie dann auf **Skype für Business Admin Center**
    
2. Aus der Skype für Business Admin Center > Wählen Sie aus dem linken Menü **Berichte** aus, und klicken Sie auf **PSTN Verwendungsdetails.**
    
3.     > [!NOTE]
    > Je nach vorhandenem Office 365-Abonnement werden möglicherweise nicht alle Produkte und Berichte angezeigt, die in diesem Artikel besprochen werden. 
  
## Interpretieren des Berichts zur Skype for Business PSTN-Verwendung

Sie können die Skype for Business PSTN-Verwendung des Benutzers anzeigen, indem Sie sich alle angezeigten Spalten ansehen.
  
Der Bericht sieht wie folgt aus:
  
![Skype for Business PSTN usage report.](../images/d3fee22a-a163-45c5-921a-45191288e0c8.png)
  
## 

|||
|:-----|:-----|
|**1** <br/> | Die Tabelle zeigt Sie einen Überblick über die alle PSTN-Verwendung pro Benutzer. Zeigt alle Benutzer, die Skype for Business für sie und ihre Verwendung PSTN zugewiesen haben. Sie können hinzufügen/Spalten, um die Tabelle entfernen. <br/> **Anruf-ID** ist die ID für einen Anruf. Damit wird der Anruf eindeutig identifiziert, wenn Sie beim Microsoft-Support anrufen. <br/> **Benutzer-ID** ist der Anmeldename des Benutzers. <br/> **Rufnummer** ist die Skype for Business-Rufnummer, unter der ein eingehender Anruf empfangen wurde, oder die Nummer, die für einen ausgehenden Anruf gewählt wurde. <br/> **Benutzerstandort** ist das Land/die Region, in dem bzw. der sich der Benutzer befindet. <br/> **Anrufer-ID** ist die Telefonnummer des Anrufers (Anrufer-ID). Bei eingehenden Anrufen handelt es sich um die Nummer, von der der Anruf ausging, und bei ausgehenden Anrufen um die Skype for Business-Nummer, von der der Anruf ausging. <br/> **Anruftyp** gibt an, ob es sich um einen aus- oder eingehenden PSTN-Anruf handelte und um welchen Anruftyp es sich handelte (z. B. von einem Benutzer getätigter Anruf oder Einwahlkonferenz). Die folgenden Anruftypen sind möglich: <br/> **Typen von Anrufen Plan Anruf** <br/> **user_in** (Der Benutzer hat einen eingehenden PSTN-Anruf erhalten.) <br/> **﻿user_out** (Der Benutzer hat einen ausgehenden PSTN-Anruf getätigt.) <br/> **﻿user_out_conf** (Der Benutzer hat zwei oder mehr PSTN-Teilnehmer zum Anruf hinzugefügt, beispielsweise in einer Dreier-Telefonkonferenz.) <br/> **﻿user_out_transfer** (Der Benutzer hat den Anruf an eine PSTN-Nummer durchgestellt.) <br/> **user_out_forwarding** (Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.) <br/> **Typen von Audiokonferenzanbieter anrufen** <br/> **﻿conf_in** (Ein eingehender Anruf an die PSTN-Konferenzbrücke) <br/> **conf_out** (ein ausgehenden Anruf aus der Audio Konferenzbrücke normalerweise so zur Konferenz PSTN-Nummer hinzu) <br/>  ﻿Unified Communication Applications (UCAP) <br/> **﻿ucap_in** (Ein eingehender Anruf an die UC-Anwendung, beispielsweise eine automatische Telefonzentrale oder eine Anrufwarteschleife) <br/> **﻿ucap_out** (Ein ausgehender Anruf von der UC-Anwendung, beispielsweise einer automatischen Telefonzentrale oder einer Anrufwarteschleife) <br/> **Inland/International** gibt an, ob der getätigte Anruf basierend auf dem Standort des Benutzers ein Inlandsanruf (innerhalb eines Lands bzw. einer Region) oder ein Auslandsanruf (außerhalb eines Lands bzw. einer Region) war. <br/> **Gewähltes Ziel** ist der Name des gewählten Lands bzw. der gewählten Region, beispielsweise Frankreich, Deutschland oder Vereinigte Staaten (USA). <br/> **Nummerntyp** ist der Typ der Telefonnummer (Telefonnummer eines Benutzers, Servicenummer oder gebührenfreie Telefonnummer). <br/> **Startzeit (UTC)** ist die Uhrzeit, zu der der Anruf gestartet bzw. getätigt wurde. <br/> **Dauer** gibt an, wie lange der Anruf verbunden war. <br/> **ConfID** ist die Konferenz-ID der audio Conference. <br/> **Gebühren** ist der Betrag (Kosten des Anrufs), der Ihrem Konto für den Anruf belastet wird. <br/> **Währung** ist der Typ der Währung, der zum Berechnen der Kosten des Anrufs verwendet wird. <br/> **Funktion** ist die Lizenz für den Anruf verwendet. Lizenz werden, die möglicherweise angezeigt: <br/> **MCOPSTNPP** - Gutschriften für Office 365-Kommunikation <br/> **MCOPSTN1** - Office 365 nationalen aufrufen planen (3000 min US / 1200 min EU-Pläne) <br/> **MCOPSTN2** - Plan für Office 365 nationalen und internationalen Anrufen <br/> **MCOPSTN5** - Office 365 nationalen aufrufen-Plan (120 min einen Plan) <br/> **MCOMEETADD** - Audiokonferenzanbieter für Office 365 <br/> **MCOMEETACPEA** - Office 365 Bezahlung pro Minute Audiokonferenzanbieter <br/> |
|**2** <br/> |Klicken Sie, um eine Spalte nach **Um eine bestimmte Spalte zu gruppieren, fügen Sie die Spaltenüberschrift per Drag &amp; Drop hier ein** zu ziehen, wenn Sie eine Ansicht erstellen möchten, in der alle Daten in mindestens einer Spalte gruppiert sind. <br/> |
|**3** <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen. <br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
   
## Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](skype-for-business-activity-report.md) Sie können sehen, wie viel Ihre Benutzer Peer-to-Peer, Aufbau des Programms und Konferenzen Sitzungen teilgenommen verwenden.
    
- [Bericht „Skype for Business - verwendete Clients"](skype-for-business-device-usage-report.md) Sie können, um die Windows-basierte Betriebssysteme einschließlich Geräte finden Sie unter und mobile Geräte, die die Skype for Business-app installiert und verwenden sie für Chats und onlinebesprechungen.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](skype-for-business-conference-organizer-activity-report.md) Sie können sehen, wie viel Ihre Benutzer Konferenzen organisieren sind, in denen Chat, Audio und Video, Anwendungsfreigabe, Web - 3rd Party in/durchführen und in/durchführen - Microsoft verwendet.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](skype-for-business-conference-participant-activity-report.md) Sie können sehen, wie viele Chat, Audio und Video Anwendungsfreigabe, Web und und werden in/durchführen Konferenzen Konferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](skype-for-business-peer-to-peer-activity-report.md) Sie können sehen, wie viel Ihre Benutzer Chat, Audio und Video, Anwendungsfreigabe und Übertragen von Dateien verwendet werden.
    
- [Bericht zu gesperrten Benutzern in Skype for Business](skype-for-business-users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation anzeigen, die von PSTN-Anrufe blockiert wurden.
    
- [Bericht zu gesperrten Benutzern in Skype for Business](skype-for-business-users-blocked-report.md) Sie können Details zu den Typ von Medien verwendet wird, die Dauer der Sitzung, den Client verwendet und die Konferenz-URL anzeigen.
    
## Verwandte Themen

[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

