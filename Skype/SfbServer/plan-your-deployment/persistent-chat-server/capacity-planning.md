---
title: Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu lernen Capacity planning for Persistent Chat Server in Skype für Business Server 2015.'
ms.openlocfilehash: 2ec69a5569eb73dba229a24528d811ab916de14c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906592"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zur kapazitätsplanung für Persistent Chat Server in Skype für Business Server 2015.
  
Persistent Chat-Server können mehrere Benutzer, Real-Time Chat, die beibehalten werden, kann für zukünftige abrufen, und suchen Sie ausführen. Im Gegensatz zu gruppensofortnachrichten (IM), gespeichert ist im Postfach eines Benutzers Wenn aufgezeichnete konfiguriert ist, eine Persistent Chat Server-Sitzung mehr geöffnet bleibt und der Inhalt gespeichert ist, auf einem Server, zusammen mit der Nachrichten, Dateien, URLs und anderen Daten, die Teil der sind ein laufenden Unterhaltung.
  
Planen der Kapazität ist ein wichtiger Teil der Vorbereitung zur Bereitstellung von Persistent Chat Server. Dieses Thema umfasst Tabellen zur Kapazitätsplanung, anhand derer Sie die beste Konfiguration für Ihre Bereitstellung ermitteln können. Es wird auch von Persistent Chat Server-Bereitstellungen am besten zu verwalten, die eine höhere Kapazität zu Spitzenzeiten erfordern beschrieben.
  
Bevor Sie diesen Abschnitt lesen, sollten Sie sich mit Topologien für beständigen Chat vertraut machen. Weitere Informationen finden Sie unter [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Persistent Chat Server-kapazitätsplanung

In den folgenden Tabellen können Sie mit der kapazitätsplanung für Persistent Chat Server durch modellieren, wie verschiedene Persistent Chat Server-Einstellungen Kapazität auswirken.
  
- Kapazitätsplanung für die Anzahl von Benutzern
    
- Kapazitätsplanung für den Chatroomzugriff
    
- Planen der Kapazität für des chatroomzugriffs über eine Einladung
    
- Kapazitätsplanung für die Leistung
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planen der Kapazität für die Anzahl von Benutzern für Persistent Chat Server

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.
  
**Persistent Chat Server Pool maximalen Kapazität-Beispiel**

|||
|:-----|:-----|
|Aktive beständigen Chat Dienstinstanzen  <br/> |4  <br/> |
|Persistent Chat-Dienstinstanzen  <br/> |8 (nur maximal 4 können aktiv sein; 4 müssen inaktiv sein)  <br/> |
|Aktive verbundene Benutzer  <br/> |80,000  <br/> |
|Gesamtzahl der bereitgestellten Benutzer  <br/> |150,000  <br/> |
|Anzahl der Endpunkte  <br/> |120,000  <br/> |
   
Im vorstehenden Beispiel, es ist geplant, die maximale Anzahl von Benutzern unterstützt, die Persistent Chat Server ermöglicht: vier Servern/Instanzen des Persistent Chat-Dienstes (können vier weitere passive Servern Persistent Chat Server für hohe Verfügbarkeit ausgeführt haben und Disaster Recovery) und 20.000 Benutzer pro Server, für insgesamt 80.000 aktive Benutzer unterstützt.
  
### <a name="plan-capacity-for-chat-room-access"></a>Kapazitätsplanung für den Chatroomzugriff

Die folgende Beispieltabelle helfen Ihnen bei der Planung für die Verwaltung des chatroomzugriffs in einem Pool Persistent Chat Server.
  
**Beispiel für die Verwaltung des Chatroomzugriffs**

||**Kleine Chatrooms**|**Mittlere Chatrooms**|**Große Chatrooms**|**Gesamt**|
|:-----|:-----|:-----|:-----|:-----|
|Größe der Chatrooms (Anzahl der verbundenen Benutzer)  <br/> |30 pro Chatroom  <br/> |150 pro Chatroom  <br/> |16.000 pro Chatroom  <br/> ||
|Chatrooms  <br/> |32,000  <br/> |1,067  <br/> |10  <br/> |33,077  <br/> |
|% der Chatrooms als Auditorium verwendet  <br/> |1 %  <br/> |1 %  <br/> |50%  <br/> ||
|% der Chatrooms sind offen  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Offene Chatrooms (ohne explizite Mitgliedschaft)  <br/> |960  <br/> |32  <br/> |5  <br/> |997  <br/> |
|Nicht offene Chatrooms (herkömmliche Chatrooms mit expliziter Mitgliedschaft)  <br/> |31,040  <br/> |1.035  <br/> |5  <br/> |32,080  <br/> |
|Auditorium-Chatrooms (zusätzlicher Zugang für Referenten)  <br/> |0  <br/> |32  <br/> |5  <br/> ||
|Über direkte Mitgliedschaft verwaltete Chatrooms  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Von Benutzergruppen verwaltete Chatrooms  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Chatrooms (nicht explizit angegeben)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms  <br/> |3  <br/> |5  <br/> |10  <br/> ||
|Benutzer und Benutzergruppen in der Managerliste der einzelnen Chatrooms (für offene und nicht offene Chatrooms)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Benutzer und Benutzergruppen in der Referentenliste der einzelnen Auditorium-Chatrooms (für offene und nicht offene Chatrooms)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Benutzer- und benutzergruppenbasierte Entitäten für alle Auditorium-Chatrooms  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Benutzer- und benutzergruppenbasierte Managerentitäten für alle Chatroom-Managerlisten  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Aktive Benutzer pro Chatroom  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Chatrooms pro Benutzer  <br/> |12  <br/> |2  <br/> |2  <br/> |16  <br/> |
|Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms  <br/> |10  <br/> |10  <br/> |15  <br/> ||
|Von Benutzergruppen verwaltete Chatrooms  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten aller Chatrooms  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Zugriffssteuerungseinträge  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Maximale Anzahl von Zugriffssteuerungseinträgen  <br/> ||||2,000,000  <br/> |
   
Im vorstehenden Beispiel bei der Bereitstellung der Persistent Chatserver entsprechend der empfohlenen Richtlinien können sie bis zu 80.000 aktive Benutzer über einen vier-Server-Pool mit aktiviertem kompatibilitätsdienst behandeln.
  
In diesem Beispiel werden Chatrooms in kleine (30 aktive gleichzeitige Benutzer), mittelgroße (150 aktive Benutzer) und große Chatrooms (16.000 aktive Benutzer) unterteilt. Die unterstützte Anzahl von Chatrooms einer bestimmten Größe in der oben stehenden Tabelle wird anhand der Gesamtzahl der folgenden Elemente berechnet:
  
- Aktive Benutzer im System
    
- Aktive Benutzer in Chatrooms der jeweiligen Größe
    
- Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt
    
Die vorstehende Tabelle zur Kapazitätsplanung gibt für jeden Chatroom die Anzahl von Zugriffssteuerungseinträgen an, die dem jeweiligen Chatroom zugeordnet sind. Dies umfasst die Einträge, die dem Chatroom direkt zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms über Zugriffssteuerungslisten steuern. Darüber hinaus können Sie den Zugriff auf Kategorieebene steuern. In einer Zugriffssteuerungsliste kann es sich bei einem einzelnen Zugriffssteuerungseintrag entweder um eine Benutzergruppe (z. B. eine Sicherheitsgruppe oder Verteilerliste) oder einen einzelnen Benutzer handeln. Sie können Zugriffssteuerungseinträge für Manager, Referenten und Mitglieder eines Chatrooms definieren.
  
> [!IMPORTANT]
> Bedenken Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl von zulässigen Zugriffssteuerungseinträgen zwei Millionen beträgt. Wenn die berechnete Anzahl von Zugriffssteuerungseinträgen eine Million überschreitet, kann die Leistung signifikant beeinträchtigt werden. Um dieses Problem zu verhindern, sollten Sie wenn möglich sicherstellen, dass Ihre Zugriffssteuerungseinträge keine einzelnen Benutzer, sondern Benutzergruppen umfassen. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Kapazitätsplanung für die Verwaltung des Chatroomzugriffs über eine Einladung

In der folgenden Tabelle Capacity planning können Sie um die Anzahl von Einladungen zu verstehen, die Persistent Chat Server erstellt und speichert in der Datenbank für beständigen Chat, wenn es zum Senden von Einladungen konfiguriert ist. Sie können mithilfe der Seite **Einstellungen für den Chatroomkategorie** in der Skype Business Server-Systemsteuerung oder mithilfe des Windows PowerShell-Cmdlets **"Set-cspersistentchatcategory"** Einladungen auf die Kategorie verwalten. Sie können Einladungen auf einen Chatroom (in einer Reihe, mit was die Kategorie ermöglicht) mithilfe der Seite **Chatroom-Verwaltung** aus der Skype für Business-Client gestartet oder mithilfe eines Windows PowerShell-Cmdlets **"Set-cspersistentchatroom"** verwalten.
  
Für die Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass die **Einladungsoption** auf der Seite mit den **Chatroomeinstellungen** für 50 % aller Chatrooms auf **Ja** festgelegt ist.
  
> [!IMPORTANT]
> Wenn der berechnete Wert für die Anzahl von Einladungen, die der Server generiert, eine Million überschreitet, kann die Serverleistung signifikant beeinträchtigt werden. Um dieses Problem zu vermeiden, achten Sie darauf, dass Sie die Anzahl von Chatrooms minimieren, die zum Senden von Einladungen oder Beschränken der Anzahl der Benutzer, die Chatrooms beitreten können, die zum Senden von Einladungen konfiguriert wurden konfiguriert sind. 
  
**Beispiel für den Chatroomzugriff über eine Einladung**

||**Kleine Chatrooms**|**Mittlere Chatrooms**|**Große Chatrooms**|**Gesamt**|
|:-----|:-----|:-----|:-----|:-----|
|Benutzer, die auf den Chatroom zugreifen können  <br/> |30 pro Chatroom  <br/> |150 pro Chatroom  <br/> |16.000 pro Chatroom  <br/> ||
|Prozentsatz an Chatrooms mit Einladung  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Für das Senden von Einladungen konfigurierte Chatrooms  <br/> |16,000  <br/> |533  <br/> |5  <br/> ||
|Benutzer, die auf den Chatroom zugreifen können  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Vom Persistent Chat Server generierte Einladungen  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Maximal zulässige Anzahl von Einladungen  <br/> ||||2,000,000  <br/> |
|Modell 1: Start mit der erwarteten Anzahl an Nachrichten pro Chatroom und Tag  <br/> |||||
|Chatrate pro Chatroom (pro Tag)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Chatrate (pro Sekunde) für alle Chatrooms  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modell 2: Start mit der Anzahl an veröffentlichten Nachrichten pro Benutzer und Tag  <br/> |||||
|Chatrate pro Benutzer und Tag  <br/> |15  <br/> |5  <br/> |0.1  <br/> |20  <br/> |
|Chatrate pro Chatroom (pro Tag)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Chatrate (pro Sekunde) für alle Chatrooms  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planen der Kapazität für Persistent Chat Server-Leistung

In der folgenden Tabelle wird das Benutzermodell für Persistent Chat Server beschrieben. Dieses Modell bildet die Grundlage für die Kapazitätsplanungsanforderungen und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.
  
**Persistent Chat Server Performance Benutzermodell**

|||
|:-----|:-----|
|Anzahl der aktiven verbundenen Benutzer  <br/> |80,000  <br/> |
|Anzahl der Persistent Chat Server-Dienstinstanzen  <br/> |4  <br/> |
|Umfang kleiner Chatrooms  <br/> |30 Benutzer  <br/> |
|Umfang mittelgroßer Chatrooms  <br/> |150 Benutzer  <br/> |
|Umfang großer Chatrooms  <br/> |16.000 Benutzer  <br/> |
|Gesamtzahl der Chatrooms  <br/> |33,077  <br/> |
|Anzahl kleiner Chatrooms  <br/> |32,000  <br/> |
|Anzahl mittelgroßer Chatrooms  <br/> |1,067  <br/> |
|Anzahl großer Chatrooms  <br/> |10  <br/> |
|Gesamtzahl der Chatrooms pro Benutzer  <br/> |16  <br/> |
|Anzahl kleiner Chatrooms pro Benutzer  <br/> |12  <br/> |
|Anzahl mittelgroßer Chatrooms pro Benutzer  <br/> |2  <br/> |
|Anzahl großer Chatrooms pro Benutzer  <br/> |2  <br/> |
|Anzahl der betretenen Chatrooms pro Benutzer  <br/> |24  <br/> |
|Maximale Beitrittsrate  <br/> |10/s  <br/> |
|Gesamtchatrate  <br/> |24/s  <br/> |
|Chatrate für kleine Chatrooms  <br/> |22.22/second  <br/> |
|Chatrate für mittelgroße Chatrooms  <br/> |1.67/second  <br/> |
|Chatrate für große Chatrooms  <br/> |~0.15/second  <br/> |
|Prozentsatz der Chatrooms, die für Einladungen konfiguriert sind  <br/> |50%  <br/> |
|Prozentsatz der direkten Mitgliedschaften  <br/> |50%  <br/> |
|Prozentsatz der Gruppenmitgliedschaften  <br/> |50%  <br/> |
|Durchschnittliche Anzahl von zugehörigkeiten zu vorgängerobjekten in Active Directory-Domänendienste  <br/> |100 - 200  <br/> |
|Anzahl abonnierter Kontakte pro Benutzer  <br/> |80  <br/> |
|Durchschnittliche Anzahl von Endpunkten pro Benutzer  <br/> |1.5  <br/> |
|Durchschnittliche Anzahl von sichtbaren Chatrooms pro Endpunkt  <br/> |1.5  <br/> |
|Durchschnittliche Anzahl von sichtbaren Chatrooms pro Benutzer  <br/> |2,25 (50 % für 1 Chatroom und 50 % für 2 Chatrooms); bis zu 6 Chatrooms offen, ein Chatroom pro Bildschirm  <br/> |
|Anzahl von Teilnehmern, die pro Intervall abgerufen werden  <br/> |25 pro sichtbarem Chatroom  <br/> |
|Länge des Abrufintervalls  <br/> |5 Minuten  <br/> |
|Anzahl von Teilnehmern, die pro Sekunde abgerufen werden  <br/> |15,000  <br/> |
|Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer  <br/> |6  <br/> |
|Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde  <br/> |133.33  <br/> |
   

