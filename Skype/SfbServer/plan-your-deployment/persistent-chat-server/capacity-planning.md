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
ms.localizationpriority: medium
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015 zu erfahren.'
ms.openlocfilehash: 430bceb547be9208348d61dc919ddb463f2d5ca2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615571"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Kapazitätsplanung für den Server für beständigen Chat in Skype for Business Server 2015 zu erfahren.
  
Der Server für beständigen Chat kann Chats mit mehreren Benutzern in Echtzeit durchführen, die für zukünftige Abrufe und Suchvorgänge beibehalten werden können. Im Gegensatz zu Gruppen-Chatnachrichten, die im Postfach eines Benutzers gespeichert werden, wenn der Unterhaltungsverlauf konfiguriert ist, bleibt eine Sitzung des Servers für beständigen Chat länger geöffnet, und der Inhalt wird zusammen mit den Nachrichten, Dateien, URLs und anderen Daten, die Teil einer laufenden Unterhaltung sind, auf einem Server gespeichert.
  
Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung auf die Bereitstellung des Servers für beständigen Chat. Dieses Thema enthält Tabellen zur Kapazitätsplanung, die Sie verwenden können, um die beste Konfiguration für Ihre Bereitstellung zu ermitteln. Außerdem wird beschrieben, wie Sie Bereitstellungen des Servers für beständigen Chat am besten verwalten, die zu Spitzenzeiten eine höhere Kapazität erfordern.
  
Bevor Sie diesen Abschnitt lesen, sollten Sie mit Topologien für beständigen Chat vertraut sein. Weitere Informationen finden Sie unter Planen der Topologie des [Servers für beständigen Chat.](topology.md)

> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Kapazitätsplanung für den Server für beständigen Chat

Die folgenden Tabellen können Ihnen bei der Kapazitätsplanung für den Server für beständigen Chat helfen, indem sie modellieren, wie sich verschiedene Einstellungen des Servers für beständigen Chat auf die Kapazität auswirken.
  
- Planen der Kapazität für die Anzahl der Benutzer
    
- Planen der Kapazität für den Chatroomzugriff
    
- Planen der Kapazität für den Chatroomzugriff nach Einladung
    
- Planen der Kapazität für die Leistung
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planen der Kapazität für die Anzahl der Benutzer für den Server für beständigen Chat

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.
  
**Beispiel für den Pool für den Server für beständigen Chat mit maximaler Kapazität**

|||
|:-----|:-----|
|Aktive Instanzen des Diensts für beständigen Chat  <br/> |4   <br/> |
|Dienstinstanzen für beständigen Chat  <br/> |8 (nur maximal 4 können aktiv sein; 4 muss inaktiv sein)  <br/> |
|Aktive Verbundene Benutzer  <br/> |80,000  <br/> |
|Gesamtzahl der bereitgestellten Benutzer  <br/> |150,000  <br/> |
|Anzahl der Endpunkte  <br/> |120,000  <br/> |
   
Im vorherigen Beispiel soll die maximale Anzahl von Benutzern unterstützt werden, die der Server für beständigen Chat zulässt: vier Server/Instanzen des Diensts für beständigen Chat (mit vier weiteren passiven Servern, auf denen der Server für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung ausgeführt wird) und 20.000 Benutzer pro Server für insgesamt 80.000 aktive Benutzer.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planen der Kapazität für den Chatroomzugriff

Die folgende Beispieltabelle kann Ihnen bei der Planung der Verwaltung des Chatroomzugriffs in einem Serverpool für beständigen Chat helfen.
  
**Beispiel für die Verwaltung des Chatroomzugriffs**

||**Kleine Chatrooms**|**Mittlere Chatrooms**|**Große Chatrooms**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Größe von Chatrooms (Anzahl der verbundenen Benutzer)  <br/> |30 pro Raum  <br/> |150 pro Raum  <br/> |16.000 pro Raum  <br/> ||
|Chatrooms  <br/> |32,000  <br/> |1,067  <br/> |10   <br/> |33,077  <br/> |
|% der Räume, die ein Auditorium sind  <br/> |1%  <br/> |1%  <br/> |50 %  <br/> ||
|% der geöffneten Räume  <br/> |3%  <br/> |3%  <br/> |50 %  <br/> ||
|Offene Räume (keine explizite Mitgliedschaft)  <br/> |960  <br/> |32  <br/> |5   <br/> |997  <br/> |
|Nicht offene Räume (reguläre Räume mit expliziter Mitgliedschaft)  <br/> |31,040  <br/> |1.035  <br/> |5   <br/> |32,080  <br/> |
|Auditorium-Räume (zusätzlicher Referenteneintrag)  <br/> |0  <br/> |32  <br/> |5   <br/> ||
|Durch direkte Mitgliedschaft verwaltete Räume  <br/> |50 %  <br/> |10 %  <br/> |0 %  <br/> ||
|Von Benutzergruppen verwaltete Chatrooms  <br/> |50 %  <br/> |90 %  <br/> |100 %  <br/> ||
|Benutzergruppen in der Mitgliedschaftsliste jedes Chatrooms für offene Chatrooms (nicht explizit angegeben)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Benutzer in der Mitgliedschaftsliste jedes Chatrooms für nicht offene Chatrooms  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Benutzergruppen in der Mitgliedschaftsliste jedes Chatrooms für nicht offene Chatrooms  <br/> |3   <br/> |5   <br/> |10   <br/> ||
|Benutzer und Benutzergruppen in der Managerliste jedes Chatrooms (für offene und nicht offene Chatrooms)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Benutzer und Benutzergruppen in der Referentenliste jedes Auditorium-Chatrooms (für offene und nicht offene Chatrooms)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Benutzer und benutzergruppenbasierte Entitäten in allen Auditorium-Chatrooms  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Benutzer und Benutzergruppen-basierte Managerentitäten in allen Verwaltungslisten für Chatrooms  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Aktive Benutzer pro Chatroom  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Chatrooms pro Benutzer  <br/> |12   <br/> |2   <br/> |2   <br/> |16   <br/> |
|Benutzergruppen in der Mitgliedschaftsliste jedes Chatrooms  <br/> |10   <br/> |10   <br/> |15   <br/> ||
|Von Benutzergruppen verwaltete Chatrooms  <br/> |50 %  <br/> |50 %  <br/> |50 %  <br/> ||
|Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Benutzer und Benutzergruppen in allen Verwaltungs-, Referenten- und Bereichslisten aller Chatrooms  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Zugriffssteuerungseinträge  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Maximale Anzahl von Zugriffssteuerungseinträgen  <br/> ||||2,000,000  <br/> |
   
Wenn Sie im vorherigen Beispiel die Server für beständigen Chat gemäß den empfohlenen Richtlinien bereitstellen, können sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern verarbeiten, für den die Kompatibilität aktiviert ist.
  
Dieses Beispiel zeigt Chatrooms, die als kleine (30 aktive Benutzer zu einem bestimmten Zeitpunkt), mittel (150 aktive Benutzer) und groß (16.000 aktive Benutzer) kategorisiert sind. Die unterstützte Anzahl von Chatrooms einer bestimmten Größe in der obigen Tabelle wird basierend auf der Gesamtzahl der folgenden Chatrooms berechnet:
  
- Aktive Benutzer im System
    
- Aktive Benutzer in Chatrooms der jeweiligen Größe
    
- Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt
    
Für jeden Chatroom gibt die vorherige Tabelle zur Kapazitätsplanung die Anzahl der Zugriffssteuerungseinträge an, die dem Chatroom zugeordnet sind, einschließlich einträgen, die direkt dem Chatroom zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms mithilfe von Zugriffssteuerungslisten (Access Control Lists, ACLs) steuern. Sie können den Zugriff auch auf Kategorieebene steuern. In einer ACL kann ein einzelner Zugriffssteuerungseintrag entweder eine Benutzergruppe sein, z. B. eine Sicherheitsgruppe, eine Verteilerliste oder ein einzelner Benutzer. Sie können Zugriffssteuerungseinträge für Chatroommanager, Referenten und Mitglieder definieren.
  
> [!IMPORTANT]
> Berücksichtigen Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl der Einträge für die Zugriffssteuerung insgesamt 2 Millionen beträgt. Wenn die berechneten Zugriffssteuerungseinträge 2 Millionen überschreiten, kann die Serverleistung erheblich beeinträchtigt werden. Um dieses Problem zu vermeiden, sollten Sie, wann immer möglich, sicherstellen, dass Ihre Zugriffssteuerungseinträge Benutzergruppen anstelle einzelner Benutzer sind. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planen der Kapazität für die Verwaltung des Chatroomzugriffs nach Einladung

Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um die Anzahl der Einladungen zu verstehen, die der Server für beständigen Chat erstellt und in der Datenbank für beständigen Chat speichert, wenn er für das Senden von Einladungen konfiguriert ist. Sie verwalten Einladungen in der Kategorie mithilfe der Einstellungsseite **"Chatroomkategorie"** in der Skype for Business Server Systemsteuerung oder mithilfe des Cmdlets "set-csPersistentChatCategory" Windows PowerShell.  Sie können Einladungen in einem Chatroom (in Übereinstimmung mit den in der Kategorie zulässigen Einstellungen) über die vom Skype for Business Client gestartete **Seite "Raumverwaltung"** oder mithilfe eines Windows PowerShell Cmdlets **"set-csPersistentChatRoom"** verwalten.
  
Die Beispieldaten in der folgenden Tabelle gehen davon aus, dass auf der Seite **"Chatroomeinstellungen"** für 50 Prozent aller Chatrooms die Option **"Einladungen"** auf **"Ja"** festgelegt ist.
  
> [!IMPORTANT]
> Wenn der berechnete Wert für die Anzahl der vom Server generierten Einladungen 1 Million überschreitet, kann die Serverleistung erheblich beeinträchtigt werden. Um dieses Problem zu vermeiden, minimieren Sie die Anzahl der Chatrooms, die für das Senden von Einladungen konfiguriert sind, oder beschränken Sie die Anzahl der Benutzer, die chatrooms beitreten können, die für das Senden von Einladungen konfiguriert wurden. 
  
**Chatroomzugriff nach Einladungsbeispiel**

||**Kleine Chatrooms**|**Mittlere Chatrooms**|**Große Chatrooms**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Benutzer, die auf den Chatroom zugreifen können  <br/> |30 pro Raum  <br/> |150 pro Raum  <br/> |16.000 pro Raum  <br/> ||
|Prozentsatz der Räume mit Einladungen  <br/> |50 %  <br/> |50 %  <br/> |50 %  <br/> ||
|Für das Senden von Einladungen konfigurierte Chatrooms  <br/> |16,000  <br/> |533  <br/> |5   <br/> ||
|Benutzer, die auf den Chatroom zugreifen können  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Vom Server für beständigen Chat generierte Einladungen  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Maximal zulässige Anzahl von Einladungen  <br/> ||||2,000,000  <br/> |
|Modell 1 – Start mit der erwarteten Anzahl von Nachrichten pro Raum und Tag  <br/> |||||
|Chatrate pro Chatroom (pro Tag)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Chatrate (pro Sekunde) in allen Chatrooms  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modell 2 – Start mit der Anzahl der Nachrichten, die pro Benutzer und Tag gepostet werden  <br/> |||||
|Chatrate pro Benutzer und Tag  <br/> |15   <br/> |5   <br/> |0.1  <br/> |20  <br/> |
|Chatrate pro Chatroom (pro Tag)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Chatrate (pro Sekunde) in allen Chatrooms  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planen der Kapazität für die Leistung des Servers für beständigen Chat

In der folgenden Tabelle wird das Benutzermodell für den Server für beständigen Chat beschrieben. Sie bildet die Grundlage für die Anforderungen an die Kapazitätsplanung und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.
  
**Benutzermodell für die Leistung des Servers für beständigen Chat**

|||
|:-----|:-----|
|Anzahl der aktiven Benutzer, die verbunden sind  <br/> |80,000  <br/> |
|Anzahl der Dienstinstanzen des Servers für beständigen Chat  <br/> |4   <br/> |
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
|Anzahl der Räume, die pro Benutzer verbunden sind  <br/> |24  <br/> |
|Maximale Beitrittsrate  <br/> |10/Sekunde  <br/> |
|Gesamtchatrate  <br/> |24/Sekunde  <br/> |
|Chatrate für kleine Chatrooms  <br/> |22,22/Sekunde  <br/> |
|Chatrate für mittelgroße Chatrooms  <br/> |1,67/Sekunde  <br/> |
|Chatrate für große Chatrooms  <br/> |~0,15/Sekunde  <br/> |
|Prozentsatz von Chatrooms, die für Einladungen konfiguriert sind  <br/> |50 %  <br/> |
|Prozentsatz von direkten Mitgliedschaften  <br/> |50 %  <br/> |
|Prozentsatz von Gruppenmitgliedschaften  <br/> |50 %  <br/> |
|Durchschnittliche Anzahl von Vorgängermitgliedschaften in Active Directory Domain Services  <br/> |100 - 200  <br/> |
|Anzahl von abonnierten Kontakten pro Benutzer  <br/> |80  <br/> |
|Durchschnittliche Anzahl von Endpunkten pro Benutzer  <br/> |1,5  <br/> |
|Durchschnittliche Anzahl sichtbarer Chatrooms pro Endpunkt  <br/> |1,5  <br/> |
|Durchschnittliche Anzahl sichtbarer Chatrooms pro Benutzer  <br/> |2,25 (50 % für 1 Raum und 50 % für 2 Räume); Bis zu 6 Räume sind geöffnet, eins pro Monitor  <br/> |
|Anzahl von Teilnehmern, die pro Intervall abgerufen werden  <br/> |25 pro sichtbaren Chatroom  <br/> |
|Länge des Abrufintervalls  <br/> |5 Minuten  <br/> |
|Anzahl von Teilnehmern, die pro Sekunde abgerufen werden  <br/> |15.000  <br/> |
|Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer  <br/> |6   <br/> |
|Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde  <br/> |133.33  <br/> |
   

