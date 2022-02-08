---
title: Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015 zu erfahren.'
ms.openlocfilehash: 48df53528b31babe6419bc42ac303b810abdf197
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389997"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015 zu erfahren.
  
Der Server für beständigen Chat kann Chats mit mehreren Benutzern in Echtzeit durchführen, die für zukünftige Abrufe und Suchvorgänge beibehalten werden können. Im Gegensatz zu Gruppen-Chatnachrichten, die im Postfach eines Benutzers gespeichert werden, wenn der Unterhaltungsverlauf konfiguriert ist, bleibt eine Serversitzung für beständigen Chat länger geöffnet, und der Inhalt wird zusammen mit den Nachrichten, Dateien, URLs und anderen Daten, die Teil einer laufenden Unterhaltung sind, auf einem Server gespeichert.
  
Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung auf die Bereitstellung des Servers für beständigen Chat. Dieses Thema enthält Tabellen zur Kapazitätsplanung, die Sie verwenden können, um die beste Konfiguration für Ihre Bereitstellung zu ermitteln. Außerdem wird beschrieben, wie Sie Bereitstellungen des Servers für beständigen Chat am besten verwalten, die zu Spitzenzeiten eine höhere Kapazität erfordern.
  
Bevor Sie diesen Abschnitt lesen, sollten Sie mit Topologien für beständigen Chat vertraut sein. Weitere Informationen finden Sie unter [Planen der Topologie des Servers für beständigen Chat](topology.md).

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Kapazitätsplanung für den Server für beständigen Chat

Die folgenden Tabellen können Ihnen bei der Kapazitätsplanung für den Server für beständigen Chat helfen, indem sie modellieren, wie sich verschiedene Einstellungen des Servers für beständigen Chat auf die Kapazität auswirken.
  
- Planen der Kapazität für die Anzahl der Benutzer
    
- Planen der Kapazität für den Chatroomzugriff
    
- Planen der Kapazität für den Chatroomzugriff nach Einladung
    
- Planen der Kapazität für die Leistung
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planen der Kapazität für die Anzahl der Benutzer für den Server für beständigen Chat

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.
  
**Beispiel für den Pool für den Server für beständigen Chat mit maximaler Kapazität**

- Aktive Dienstinstanzen für beständigen Chat: 4  <br/> 
- Dienstinstanzen für beständigen Chat: 8 (maximal 4 können aktiv sein; 4 müssen inaktiv sein)  <br/>
- Aktive Benutzer verbunden: 80.000  <br/>
- Gesamtzahl der bereitgestellten Benutzer: 150.000  <br/>
- Anzahl der Endpunkte: 120.000  <br/>
   
Im vorherigen Beispiel soll die maximale Anzahl von Benutzern unterstützt werden, die der Server für beständigen Chat zulässt: vier Server/Instanzen des Diensts für beständigen Chat (kann vier weitere passive Server mit dem Server für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung haben) und 20.000 Benutzer pro Server für insgesamt 80.000 aktive Benutzer.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planen der Kapazität für den Chatroomzugriff

Die folgende Beispieltabelle kann Ihnen bei der Planung der Verwaltung des Chatroomzugriffs in einem Serverpool für beständigen Chat helfen.
  
**Beispiel für die Verwaltung des Chatroomzugriffs**

|&nbsp;|Kleine Chatrooms|Mittlere Chatrooms|Große Chatrooms|Summe|
|:-----|:-----|:-----|:-----|:-----|
|Größe von Chatrooms (Anzahl der verbundenen Benutzer)   |30 pro Raum   |150 pro Raum   |16.000 pro Raum   ||
|Chatrooms   |32,000   |1,067   |10   |33,077   |
|% der Räume, die ein Auditorium sind   |1%   |1%   |50%   ||
|% der geöffneten Räume   |3%   |3%   |50%   ||
|Offene Räume (keine explizite Mitgliedschaft)   |960   |32   |5   |997   |
|Nicht offene Räume (reguläre Räume mit expliziter Mitgliedschaft)   |31,040   |1.035   |5   |32,080   |
|Auditorium-Räume (zusätzlicher Referenteneintrag)   |0   |32   |5   ||
|Durch direkte Mitgliedschaft verwaltete Räume   |50%   |10 %   |0%   ||
|Von Benutzergruppen verwaltete Chatrooms   |50%   |90 %   |100 %   ||
|Benutzergruppen in der Mitgliedschaftsliste jedes Chatrooms für offene Chatrooms (nicht explizit angegeben)   |0   |0   |0   ||
|Benutzer in der Mitgliedschaftsliste jedes Chatrooms für nicht offene Chatrooms   |30   |150   |16,000   ||
|Benutzergruppen in der Mitgliedschaftsliste jedes Chatrooms für nicht offene Chatrooms   |3   |5   |10   ||
|Benutzer und Benutzergruppen in der Managerliste jedes Chatrooms (für offene und nicht offene Chatrooms)   |6    |6    |6    ||
|Benutzer und Benutzergruppen in der Referentenliste jedes Auditorium-Chatrooms (für offene und nicht offene Chatrooms)   |6    |6    |6    ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms   |465,600   |15,520   |-   ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms   |46,560   |4656   |50   ||
|Benutzer und benutzergruppenbasierte Entitäten in allen Auditorium-Chatrooms   |0   |192   |50   ||
|Benutzer und Benutzergruppen-basierte Managerentitäten in allen Verwaltungslisten für Chatrooms   |192,000   |6,400   |60   ||
|Aktive Benutzer pro Chatroom   |30   |150   |16,000   ||
|Chatrooms pro Benutzer   |12    |2   |2   |16   |
|Benutzergruppen in der Mitgliedschaftsliste jedes Chatrooms   |10   |10   |15    ||
|Von Benutzergruppen verwaltete Chatrooms   |50%   |50%   |50%   ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms   |155,200   |5173   |68   ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms   |465,600   |77,600   |72,000   ||
|Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms   |6    |6    |6    ||
|Benutzer und Benutzergruppen in allen Verwaltungs-, Referenten- und Bereichslisten aller Chatrooms   |192,000   |6400   |60   ||
|Zugriffssteuerungseinträge   |704,160   |26,768   |160   |731,088   |
|Maximale Anzahl von Zugriffssteuerungseinträgen   ||||2,000,000   |
   
Wenn Sie im vorherigen Beispiel die Server für beständigen Chat gemäß den empfohlenen Richtlinien bereitstellen, können sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern verarbeiten, für den die Kompatibilität aktiviert ist.
  
Dieses Beispiel zeigt Chatrooms, die als kleine (30 aktive Benutzer zu einem bestimmten Zeitpunkt), mittel (150 aktive Benutzer) und groß (16.000 aktive Benutzer) kategorisiert sind. Die unterstützte Anzahl von Chatrooms einer bestimmten Größe in der obigen Tabelle wird basierend auf der Gesamtzahl der folgenden Chatrooms berechnet:
  
- Aktive Benutzer im System
    
- Aktive Benutzer in Chatrooms der jeweiligen Größe
    
- Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt
    
Für jeden Chatroom gibt die vorherige Tabelle zur Kapazitätsplanung die Anzahl der Zugriffssteuerungseinträge an, die dem Chatroom zugeordnet sind, einschließlich einträgen, die direkt dem Chatroom zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms mithilfe von Zugriffssteuerungslisten (Access Control Lists, ACLs) steuern. Sie können den Zugriff auch auf Kategorieebene steuern. In einer ACL kann ein einzelner Zugriffssteuerungseintrag entweder eine Benutzergruppe sein, z. B. eine Sicherheitsgruppe, eine Verteilerliste oder ein einzelner Benutzer. Sie können Zugriffssteuerungseinträge für Chatroommanager, Referenten und Mitglieder definieren.
  
> [!IMPORTANT]
> Berücksichtigen Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl der Einträge für die Zugriffssteuerung insgesamt 2 Millionen beträgt. Wenn die berechneten Zugriffssteuerungseinträge 2 Millionen überschreiten, kann die Serverleistung erheblich beeinträchtigt werden. Um dieses Problem zu vermeiden, sollten Sie, wann immer möglich, sicherstellen, dass Ihre Zugriffssteuerungseinträge Benutzergruppen anstelle einzelner Benutzer sind. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planen der Kapazität für die Verwaltung des Chatroomzugriffs nach Einladung

Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um die Anzahl der Einladungen zu verstehen, die der Server für beständigen Chat erstellt und in der Datenbank für beständigen Chat speichert, wenn er für das Senden von Einladungen konfiguriert ist. Sie verwalten Einladungen in der Kategorie mithilfe der Einstellungsseite "**Chatroomkategorie"** in der systemsteuerung Skype for Business Server oder mit dem Cmdlet "**set-csPersistentChatCategory**" Windows PowerShell Cmdlet. Sie können Einladungen in einem Chatroom (in Übereinstimmung mit dem, was die Kategorie zulässt) verwalten, indem Sie die Seite "**Raumverwaltung**" verwenden, die vom Skype for Business-Client gestartet wurde, oder mithilfe eines Windows PowerShell Cmdlets, **"set-csPersistentChatRoom"**.
  
Die Beispieldaten in der folgenden Tabelle gehen davon aus, dass auf der Seite **"Chatroomeinstellungen** " für 50 Prozent aller **Chatrooms die Option "Einladungen** " auf **"Ja**" festgelegt ist.
  
> [!IMPORTANT]
> Wenn der berechnete Wert für die Anzahl der vom Server generierten Einladungen 1 Million überschreitet, kann die Serverleistung erheblich beeinträchtigt werden. Um dieses Problem zu vermeiden, minimieren Sie die Anzahl der Chatrooms, die für das Senden von Einladungen konfiguriert sind, oder beschränken Sie die Anzahl der Benutzer, die chatrooms beitreten können, die für das Senden von Einladungen konfiguriert wurden. 
  
**Chatroomzugriff nach Einladungsbeispiel**

|&nbsp;|Kleine Chatrooms|Mittlere Chatrooms|Große Chatrooms|Summe|
|:-----|:-----|:-----|:-----|:-----|
|Benutzer, die auf den Chatroom zugreifen können   |30 pro Raum   |150 pro Raum   |16.000 pro Raum   ||
|Prozentsatz der Räume mit Einladungen   |50%   |50%   |50%   ||
|Für das Senden von Einladungen konfigurierte Chatrooms   |16,000   |533   |5   ||
|Benutzer, die auf den Chatroom zugreifen können   |60   |225   |16,000   ||
|Vom Server für beständigen Chat generierte Einladungen   |960,000   |120,000   |80,000   |1,160,000   |
|Maximal zulässige Anzahl von Einladungen   ||||2,000,000   |
|Modell 1 – Start mit der erwarteten Anzahl von Nachrichten pro Raum und Tag   |||||
|Chatrate pro Chatroom (pro Tag)   |50   |500   |100   |650   |
|Chatrate (pro Sekunde) in allen Chatrooms   |55.56   |18.52   |0.03   |74   |
|Modell 2 – Start mit der Anzahl der Nachrichten, die pro Benutzer und Tag gepostet werden   |||||
|Chatrate pro Benutzer und Tag   |15    |5   |0,1   |20   |
|Chatrate pro Chatroom (pro Tag)   |38   |375   |800   |1,213   |
|Chatrate (pro Sekunde) in allen Chatrooms   |41.67   |13.89   |0.28   |56   |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planen der Kapazität für die Leistung des Servers für beständigen Chat

In der folgenden Tabelle wird das Benutzermodell für den Server für beständigen Chat beschrieben. Sie bildet die Grundlage für die Anforderungen an die Kapazitätsplanung und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.
  
**Benutzermodell für die Leistung des Servers für beständigen Chat**

- Anzahl der verbundenen aktiven Benutzer: 80.000  <br/>
- Anzahl der Dienstinstanzen für den Server für beständigen Chat: 4  <br/>
- Größe kleiner Chatrooms: 30 Benutzer  <br/> 
- Größe mittelgroßer Chatrooms: 150 Benutzer  <br/>
- Größe großer Chatrooms: 16.000 Benutzer  <br/>
- Gesamtzahl der Chatrooms: 33.077  <br/> 
- Anzahl kleiner Chatrooms: 32.000  <br/> 
- Anzahl der mittleren Chatrooms: 1.067  <br/> 
- Anzahl der großen Chatrooms: 10  <br/> 
- Gesamtzahl der Chatrooms pro Benutzer: 16  <br/> 
- Anzahl kleiner Chatrooms pro Benutzer: 12  <br/> 
- Anzahl der mittleren Chatrooms pro Benutzer: 2  <br/> 
- Anzahl der großen Chatrooms pro Benutzer: 2  <br/> 
- Anzahl der räume, die pro Benutzer verbunden sind: 24  <br/>
- Spitzenverknüpfungsrate: 10/Sekunde  <br/> 
- Gesamt-Chatrate: 24/Sekunde  <br/> 
- Chatrate für kleine Chatrooms: 22,22/Sekunde  <br/> 
- Chatrate für mittlere Chatrooms: 1,67/Sekunde  <br/> 
- Chatrate für große Chatrooms: ~0,15/Sekunde  <br/> 
- Prozentsatz der chatrooms für Einladungen konfiguriert: 50 %  <br/>
- Prozentsatz der direkten Mitgliedschaften: 50 %  <br/>
- Prozentsatz der Gruppenmitgliedschaften: 50 %  <br/> 
- Durchschnittliche Anzahl von Vorgängermitgliedschaften in Active Directory Domain Services: 100 - 200  <br/>
- Anzahl der abonnierten Kontakte pro Benutzer: 80  <br/> 
- Durchschnittliche Anzahl von Endpunkten pro Benutzer: 1,5  <br/> 
- Durchschnittliche Anzahl sichtbarer Chatrooms pro Endpunkt: 1,5  <br/> 
- Durchschnittliche Anzahl der sichtbaren Chatrooms pro Benutzer: 2,25 (50 % für 1 Chatroom und 50 % für 2 Chatrooms); Bis zu 6 Räume sind geöffnet, eins pro Monitor  <br/> 
- Anzahl der pro Intervall abgefragten Teilnehmer: 25 pro sichtbaren Chatroom  <br/> 
- Dauer des Abrufintervalls: 5 Minuten  <br/> 
- Anzahl der pro Sekunde abgefragten Teilnehmer: 15.000  <br/>
- Anzahl der Anwesenheitsänderungen pro Stunde und Benutzer: 6  <br/> 
- Anzahl der Anwesenheitsänderungen pro Sekunde: 133,33  
   

