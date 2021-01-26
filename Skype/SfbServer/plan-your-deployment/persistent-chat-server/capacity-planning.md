---
title: Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über die Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: d3d166f3b91ef0e7f711441387b4bef3d56f18b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834575"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015.
  
Der Server für beständigen Chat kann Chats mit mehreren Benutzern in Echtzeit ausführen, die für zukünftige Abrufe und Suchen beibehalten werden können. Im Gegensatz zu Gruppen-Chatnachrichten, die im Postfach eines Benutzers gespeichert werden, wenn der Unterhaltungsverlauf konfiguriert ist, bleibt eine Serversitzung für beständigen Chat länger geöffnet, und der Inhalt wird zusammen mit den Nachrichten, Dateien, URLs und anderen Daten, die Teil einer laufenden Unterhaltung sind, auf einem Server gespeichert.
  
Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung der Bereitstellung des Servers für beständigen Chat. Dieses Thema enthält Tabellen zur Kapazitätsplanung, die Sie verwenden können, um die beste Konfiguration für Ihre Bereitstellung zu ermitteln. Außerdem wird beschrieben, wie Sie Bereitstellungen für den Server für beständigen Chat am besten verwalten können, die zu Spitzenzeiten eine höhere Kapazität erfordern.
  
Bevor Sie diesen Abschnitt lesen, sollten Sie mit Topologien für beständigen Chat vertraut sein. Weitere Informationen finden Sie unter [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Kapazitätsplanung für den Server für beständigen Chat

Die folgenden Tabellen helfen Ihnen bei der Kapazitätsplanung für den Server für beständigen Chat, indem sie modellieren, wie sich verschiedene Einstellungen des Servers für beständigen Chat auf die Kapazität auswirken.
  
- Planen der Kapazität für die Anzahl der Benutzer
    
- Planen der Kapazität für den Chatroomzugriff
    
- Planen der Kapazität für den Chatroomzugriff nach Einladung
    
- Planen der Kapazität für die Leistung
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planen der Kapazität für die Anzahl der Benutzer für den Server für beständigen Chat

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.
  
**Beispiel für maximale Kapazität des Pools für beständigen Chat**

|||
|:-----|:-----|
|Dienstinstanzen für den aktiven beständigen Chat  <br/> |4   <br/> |
|Dienstinstanzen für beständigen Chat  <br/> |8 (nur maximal 4 können aktiv sein; 4 müssen inaktiv sein)  <br/> |
|Aktive Benutzer, die verbunden sind  <br/> |80,000  <br/> |
|Gesamtzahl der bereitgestellten Benutzer  <br/> |150,000  <br/> |
|Anzahl der Endpunkte  <br/> |120,000  <br/> |
   
Im vorherigen Beispiel wird die maximale Anzahl von Benutzern unterstützt, die der Server für beständigen Chat zulässt: vier Server/Instanzen des Diensts für beständigen Chat (kann vier weitere passive Server mit dem Server für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung haben) und 20.000 Benutzer pro Server für insgesamt 80.000 aktive Benutzer.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planen der Kapazität für den Chatroomzugriff

Die folgende Beispieltabelle kann Ihnen bei der Planung der Verwaltung des Chatroomzugriffs in einem Pool für den Server für beständigen Chat helfen.
  
**Beispiel für die Verwaltung des Chatroomzugriffs**

||**Kleine Chatrooms**|**Mittelgroße Chatrooms**|**Große Chatrooms**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Größe von Chatrooms (Anzahl der verbundenen Benutzer)  <br/> |30 pro Raum  <br/> |150 pro Raum  <br/> |16.000 pro Raum  <br/> ||
|Chatrooms  <br/> |32,000  <br/> |1,067  <br/> |10   <br/> |33,077  <br/> |
|% der Räume, bei der es sich um ein Auditorium handelt  <br/> |1%  <br/> |1%  <br/> |50%  <br/> ||
|% der geöffneten Räume  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Offene Räume (keine explizite Mitgliedschaft)  <br/> |960  <br/> |32  <br/> |5   <br/> |997  <br/> |
|Nicht offene Räume (reguläre Räume mit expliziter Mitgliedschaft)  <br/> |31,040  <br/> |1.035  <br/> |5   <br/> |32,080  <br/> |
|Auditoriumräume (zusätzlicher Presentereintrag)  <br/> |0  <br/> |32  <br/> |5   <br/> ||
|Räume, die über direkte Mitgliedschaft verwaltet werden  <br/> |50%  <br/> |10 %  <br/> |0 %  <br/> ||
|Von Benutzergruppen verwaltete Chatrooms  <br/> |50%  <br/> |90 %  <br/> |100 %  <br/> ||
|Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Chatrooms (nicht explizit angegeben)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht geöffnete Chatrooms  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht geöffnete Chatrooms  <br/> |3   <br/> |5   <br/> |10   <br/> ||
|Benutzer und Benutzergruppen in der Managerliste der einzelnen Chatrooms (für offene und nicht geöffnete Chatrooms)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Benutzer und Benutzergruppen in der Liste der Moderatoren jedes Auditoriumchatrooms (für offene und nicht offene Räume)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen nicht geöffneten Räumen  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht geöffneten Räumen  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Benutzer und Benutzergruppenbasierte Entitäten in allen Auditoriumchatrooms  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Benutzer und Benutzergruppen-basierte Managerentitäten in allen Listen der Chatroommanager  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Aktive Benutzer pro Chatroom  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Chatrooms pro Benutzer  <br/> |12   <br/> |2   <br/> |2   <br/> |16   <br/> |
|Benutzergruppen in der Mitgliederliste jedes Chatrooms  <br/> |10   <br/> |10   <br/> |15   <br/> ||
|Von Benutzergruppen verwaltete Chatrooms  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Benutzer und Benutzergruppen in allen Vorgesetzten-, Presenter- und Bereichslisten aller Chatrooms  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Zugriffssteuerungseinträge  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Maximale Anzahl von Zugriffssteuerungseinträgen  <br/> ||||2,000,000  <br/> |
   
Wenn Sie im vorherigen Beispiel die Server für beständigen Chat gemäß den empfohlenen Richtlinien bereitstellen, können sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern mit aktivierter Kompatibilität verarbeiten.
  
Dieses Beispiel zeigt Chatrooms, die als klein (30 aktive Benutzer zu einem bestimmten Zeitpunkt), mittel (150 aktive Benutzer) und groß (16.000 aktive Benutzer) kategorisiert sind. Die unterstützte Anzahl von Chatrooms einer bestimmten Größe in der obigen Tabelle wird basierend auf der Gesamtzahl der folgenden Chatrooms berechnet:
  
- Aktive Benutzer im System
    
- Aktive Benutzer in Chatrooms der jeweiligen Größe
    
- Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt
    
Für jeden Chatroom gibt die vorstehende Kapazitätsplanungstabelle die Anzahl der Zugriffssteuerungseinträge an, die dem Chatroom zugeordnet sind, einschließlich einträgen, die direkt dem Chatroom zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms mithilfe von Zugriffssteuerungslisten (Access Control Lists, ACLs) steuern. Sie können den Zugriff auch auf Kategorieebene steuern. In einer Zugriffssteuerungsliste kann ein einzelner Zugriffssteuerungseintrag entweder eine Benutzergruppe sein, z. B. eine Sicherheitsgruppe, eine Verteilerliste oder ein einzelner Benutzer. Sie können Zugriffssteuerungseinträge für Chatroommanager, Moderatoren und Mitglieder definieren.
  
> [!IMPORTANT]
> Beachten Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl der zulässigen Zugriffssteuerungseinträge 2 Millionen beträgt. Wenn die berechneten Zugriffssteuerungseinträge 2 Millionen überschreiten, kann die Serverleistung erheblich beeinträchtigt werden. Um dieses Problem zu vermeiden, stellen Sie nach Möglichkeit sicher, dass es sich bei den Zugriffssteuerungseinträgen um Benutzergruppen und nicht um einzelne Benutzer handelt. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planen der Kapazität für die Verwaltung des Chatroomzugriffs nach Einladung

Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um die Anzahl der Einladungen zu verstehen, die der Server für beständigen Chat erstellt und in der Datenbank für beständigen Chat speichert, wenn er für das Senden von Einladungen konfiguriert ist. Sie verwalten Einladungen für die  Kategorie über die Seite "Einstellungen für Chatroomkategorie" in der Skype for Business Server-Systemsteuerung oder über das cmdlet Windows PowerShell **set-csPersistentChatCategory**. Sie können Einladungen in einem Chatroom (im Einklang mit  der Kategorie) verwalten, indem Sie die Seite "Raumverwaltung" verwenden, die über den Skype for Business-Client gestartet wird, oder ein Windows PowerShell-Cmdlet, **set-csPersistentChatRoom**.
  
In den Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass auf der Seite **"Chatroomeinstellungen"** für 50 Prozent aller **Chatrooms** die Option "Einladungen" auf **"Ja" festgelegt ist.**
  
> [!IMPORTANT]
> Wenn der berechnete Wert für die Anzahl der vom Server generierten Einladungen 1 Million überschreitet, kann die Serverleistung erheblich beeinträchtigt werden. Um dieses Problem zu vermeiden, müssen Sie die Anzahl der Chatrooms minimieren, die für das Senden von Einladungen konfiguriert sind, oder die Anzahl der Benutzer einschränken, die chatrooms beitreten können, die für das Senden von Einladungen konfiguriert wurden. 
  
**Beispiel für chatroomzugriff nach Einladung**

||**Kleine Chatrooms**|**Mittelgroße Chatrooms**|**Große Chatrooms**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Benutzer, die auf den Chatroom zugreifen können  <br/> |30 pro Raum  <br/> |150 pro Raum  <br/> |16.000 pro Raum  <br/> ||
|Prozentsatz der Räume mit Einladungen  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Für das Senden von Einladungen konfigurierte Chatrooms  <br/> |16,000  <br/> |533  <br/> |5   <br/> ||
|Benutzer, die auf den Chatroom zugreifen können  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Vom Server für beständigen Chat generierte Einladungen  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Maximal zulässige Anzahl von Einladungen  <br/> ||||2,000,000  <br/> |
|Modell 1– Beginnen mit der erwarteten Anzahl von Nachrichten pro Raum und Tag  <br/> |||||
|Chatrate pro Chatroom (pro Tag)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Chatrate (pro Sekunde) in allen Chatrooms  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modell 2– Beginnen mit der Anzahl der pro Benutzer und Tag veröffentlichten Nachrichten  <br/> |||||
|Chatrate pro Benutzer und Tag  <br/> |15   <br/> |5   <br/> |0.1  <br/> |20  <br/> |
|Chatrate pro Chatroom (pro Tag)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Chatrate (pro Sekunde) in allen Chatrooms  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planen der Kapazität für die Leistung des Servers für beständigen Chat

In der folgenden Tabelle wird das Benutzermodell für den Server für beständigen Chat beschrieben. Es stellt die Grundlage für die Kapazitätsplanungsanforderungen dar und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.
  
**Benutzermodell für die Leistung des Servers für beständigen Chat**

|||
|:-----|:-----|
|Anzahl der verbundenen aktiven Benutzer  <br/> |80,000  <br/> |
|Anzahl der Dienstinstanzen für den Server für beständigen Chat  <br/> |4   <br/> |
|Umfang kleiner Chatrooms  <br/> |30 Benutzer  <br/> |
|Umfang mittelgroßer Chatrooms  <br/> |150 Benutzer  <br/> |
|Umfang großer Chatrooms  <br/> |16.000 Benutzer  <br/> |
|Gesamtzahl von Chatrooms  <br/> |33,077  <br/> |
|Anzahl von kleinen Chatrooms  <br/> |32,000  <br/> |
|Anzahl von mittelgroßen Chatrooms  <br/> |1,067  <br/> |
|Anzahl von großen Chatrooms  <br/> |10   <br/> |
|Gesamtzahl von Chatrooms pro Benutzer  <br/> |16   <br/> |
|Anzahl von kleinen Chatrooms pro Benutzer  <br/> |12   <br/> |
|Anzahl von mittelgroßen Chatrooms pro Benutzer  <br/> |2   <br/> |
|Anzahl von großen Chatrooms pro Benutzer  <br/> |2   <br/> |
|Anzahl der Räume, die pro Benutzer beigetreten sind  <br/> |24  <br/> |
|Maximale Beitrittsrate  <br/> |10/Sekunde  <br/> |
|Gesamtchatrate  <br/> |24/Sekunde  <br/> |
|Chatrate für kleine Chatrooms  <br/> |22,22/Sekunde  <br/> |
|Chatrate für mittelgroße Chatrooms  <br/> |1,67/Sekunde  <br/> |
|Chatrate für große Chatrooms  <br/> |~0,15/Sekunde  <br/> |
|Prozentsatz von Chatrooms, die für Einladungen konfiguriert sind  <br/> |50%  <br/> |
|Prozentsatz von direkten Mitgliedschaften  <br/> |50%  <br/> |
|Prozentsatz von Gruppenmitgliedschaften  <br/> |50%  <br/> |
|Durchschnittliche Anzahl von Vorgängerzugehörigkeiten in Active Directory Domain Services  <br/> |100 - 200  <br/> |
|Anzahl von abonnierten Kontakten pro Benutzer  <br/> |80  <br/> |
|Durchschnittliche Anzahl von Endpunkten pro Benutzer  <br/> |1,5  <br/> |
|Durchschnittliche Anzahl sichtbarer Chatrooms pro Endpunkt  <br/> |1,5  <br/> |
|Durchschnittliche Anzahl der sichtbaren Chatrooms pro Benutzer  <br/> |2,25 (50 % für 1 Raum und 50 % für 2 Räume); Bis zu 6 Räume geöffnet, einer pro Monitor  <br/> |
|Anzahl von Teilnehmern, die pro Intervall abgerufen werden  <br/> |25 pro sichtbaren Chatroom  <br/> |
|Länge des Abrufintervalls  <br/> |5 Minuten  <br/> |
|Anzahl von Teilnehmern, die pro Sekunde abgerufen werden  <br/> |15,000  <br/> |
|Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer  <br/> |6   <br/> |
|Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde  <br/> |133.33  <br/> |
   

