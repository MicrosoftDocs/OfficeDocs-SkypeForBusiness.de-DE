---
title: Benutzermodelle in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c551371c-d740-4372-bada-f0d713ec0d33
description: Die hier beschriebenen Benutzermodelle bilden die Grundlage für die kapazitätsplanung Zahlenangaben und Empfehlungen in Capacity beschriebenen Skype für Business Server 2015 Verwendung des Objektmodells für Benutzer planen.
ms.openlocfilehash: d26929f7ed9cf24ca3d13bf4f2ea7bf30172413d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="user-models-in-skype-for-business-server-2015"></a>Benutzermodelle in Skype for Business Server 2015
 
Die hier beschriebenen Benutzermodelle bilden die Grundlage für die kapazitätsplanung Zahlenangaben und Empfehlungen in [Capacity planning Verwendung des Objektmodells für Benutzer für Skype für Business Server 2015](user-model.md)beschrieben.
  
## <a name="skype-for-business-server-user-models"></a>Skype für Business Server-Benutzermodelle

In der folgenden Tabelle wird das Benutzermodell für Registrierung, Kontakte, instant messaging (IM) und Anwesenheit für Skype für Business Server beschrieben.
  
**Umgebung und Benutzermodell für Registrierung**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Bereitstellungsgröße und Verteilung  <br/> |Es wird eine große Bereitstellung mit drei zentralen Standorten und einem Front-End-Pool pro Standort modelliert.  <br/> |
|Prozentsatz der Active Directory-Benutzer  <br/> |Es wird davon ausgegangen, dass 70 % aller Active Directory-Benutzer in der Organisation für Skype für Business Server aktiviert sind. 80 % der Benutzer aktiviert sind Skype für Business Server jeden Tag (80 % Gleichzeitigkeit) angemeldet. Die gleichzeitigen Benutzer sind die Grundlage für die weiteren Zahlenangaben in diesem Abschnitt.  <br/> |
|Änderungen des Active Directory  <br/> |Es wird davon ausgegangen, dass 0,5 % aller Benutzer erstellt und jede Woche für Skype für Unternehmen in Active Directory aktiviert sind und 0,5 % aller Benutzer aus Active Directory und Skype für Unternehmen jede Woche deaktiviert sind. 5 % der Benutzer haben mindestens eine Active Directory-Attribut jede Woche geändert.  <br/> |
|Active Directory-Verteilergruppen  <br/> |Es wird davon ausgegangen, dass die Anzahl der Active Directory-Verteilergruppen in der Organisation gleich dreimal die Anzahl aller Benutzer in Active Directory ist. Die Verteilergruppen haben folgende Größen:  <br/> • 64 % umfassen 2-30 Benutzer  <br/> • 13 % umfassen 31-50 Benutzer  <br/> • 10 % umfassen 51-100 Benutzer  <br/> • 13 % umfassen 101-500 Benutzer  <br/> |
|VoIP-Benutzer (Voice over IP)  <br/> |60 % der Skype für Business Server-Benutzer sind für unified Communications (UC) (d. h., Telefonstatus Zahlen Skype für Business Server gehören) aktiviert.  <br/> |
|Verteilung registrierter Clients  <br/> |65 % der Clients ausführen Skype für Business-Software, einschließlich Skype für Unternehmen und Lync Phone Edition.  <br/> 30 % der Clients, die von einer früheren Version von Lync-Clientsoftware ausführen.  <br/> 5 % der Clients Skype für Business Web App verwenden.  <br/> Wenn die Mobilität aktiviert ist, wird davon ausgegangen, dass 40 % der Benutzer die Mobilität gleichzeitig mit anderen zuvor genannten registrierten Clientoptionen verwenden. In diesem Fall beträgt das MPOP-Verhältnis (Multiple Point Of Presence) für Clients 1:1,9. Wenn die Mobilität deaktiviert ist, beträgt das MPOP-Verhältnis 1:1,5.  <br/> |
|Verteilung von Remotebenutzern  <br/> |70 % der Benutzer verbinden sich intern.  <br/> 30 % der Benutzer verbinden sich über einen Edge-Server (Sie möglicherweise einen Director hier auch optional, aber es ist nicht erforderlich).  <br/> |
|Verteilung von Kontakten  <br/> |Die maximale Anzahl von Kontakten eines Benutzers beträgt 1.000. Weniger als 1 % der Benutzer verfügen über 1.000 Kontakte. Weniger als 25 % der Benutzer verfügen über 100 Kontakte oder mehr.  <br/> Benutzer, die mit einem öffentlichen Netz verbunden sind, verfügen über durchschnittlich 80 Kontakte. Für diese Benutzer gilt Folgendes:  <br/> • 50 % der Kontakte befinden sich innerhalb der Organisation. 10 % dieser Benutzer sind Remotebenutzer, die sich von außerhalb der Firewall verbinden.  <br/> • 40 % der Kontakte sind Skype-Benutzer.  <br/> • 10 % der Kontakte sind Benutzer von Verbundpartnern.  <br/> Benutzer ohne Verbindung mit einem öffentlichen Netz verfügen über durchschnittlich 50 Kontakte. Für diese Benutzer gilt Folgendes:  <br/> • 80 % der Kontakte befinden sich innerhalb der Organisation. 10 % dieser Benutzer sind Remotebenutzer, die sich von außerhalb der Firewall verbinden.  <br/> • 20 % der Kontakte sind Benutzer von Verbundpartnern.  <br/> Jeder Benutzer weist 1 Verteilergruppe in seiner Kontaktliste auf. Für Leistungstest wird davon ausgegangen, dass Verteilergruppen immer erweitert werden.  <br/> |
|Sitzungszeit  <br/> |Eine durchschnittliche Benutzeranmeldesitzung dauert 12 Stunden. Sämtliche Benutzer melden sich innerhalb von 120 Minuten nach dem Sitzungsstart an.  <br/> |
   
**Sofortnachrichten und Anwesenheit Benutzermodell**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Peer-zu-Peer-Chatsitzungen  <br/> |Jeder Benutzer verfügt über durchschnittlich sechs Peer-zu-Peer-Chatsitzungen pro Tag.  <br/> 10 Chatnachrichten pro Sitzung.  <br/> Jede Nachricht von zwei SIP INFO-Nachrichten und 2 200 OK SIP-Nachrichten zugeordnet ist (für die Statusindikatoren wie beispielsweise "\<Namen\> Eingabe ist")  <br/> |
|Gruppenchatsitzungen  <br/> |Die durchschnittliche Anzahl der gesendeten Nachrichten in einer Gruppe, in der nur Sofortnachrichten verschickt werden können, liegt bei fünf Nachrichten pro Benutzer.  <br/> Die durchschnittliche Anzahl der im Chatteil einer AV-Konferenz versendeten Nachrichten liegt bei zwei Nachrichten pro Benutzer.  <br/> |
|Abfrage von Anwesenheitsinformationen  <br/> |Insgesamt wird von durchschnittlich 60 Abfragen von Anwesenheitsinformationen pro Benutzer und Stunde ausgegangen. Für jeden Benutzer wird von folgenden Durchschnittswerten ausgegangen:  <br/> • Eine Umfrage pro Tag für die Anwesenheit von Benutzern in des Benutzers auf der Registerkarte Organisation (jedoch nicht die Liste Kontakte). Durchschnittliche Anzahl von Kontakten in der Benutzer auf der Registerkarte Organisation ist 15 Benutzer. Zwei Anzeigevorgänge für Visitenkarten pro Tag.  <br/> • Eine Anwesenheit Umfrage jedes Mal, wenn der Benutzer einen anderen Benutzer zum Starten einer Unterhaltung klickt geschätzte einmal pro Stunde.  <br/> • Sechs Benutzer sucht pro Stunde. Jedes Mal, wenn eine Suche durchgeführt wird, wird für alle Benutzer in der Suchergebnisliste eine Umfrage Batch gesendet. Es wird davon ausgegangen, dass die durchschnittliche Größe der Suchergebnisse 20 ist. Wenn die Suchergebnisse in der Bildschirm bleiben, ist die Umfrage Batch alle 5 Minuten aktualisiert; Es wird davon ausgegangen, dass zwei pro Stunde solche aktualisiert werden.  <br/> • Wenn der Benutzer öffnet oder eine eine e-Mail in Outlook, von der Anwesenheit von Benutzern zu einer Umfrage Vorschau: und CC: Felder der e-Mail, schätzte auf fünf-e-Mails pro Stunde und vier Benutzer pro e-Mail.  <br/> |
|Anwesenheitsabonnements  <br/> |Wenn ein Benutzer eine andere als Kontakt hinzufügt, wird der erste Benutzer fünf Kategorien von Informationen über den zweiten Benutzer abonnieren. Aktualisierungen dieser Informationskategorien werden automatisch an den ersten Benutzer gesendet. <br/> Für jeden Client wird eine einzige Stapelabonnementanforderung gesendet, um den Anwesenheitsstatus von durchschnittlich 40 Kontakten abzurufen, mit zusätzlich 40 Dialogen zum Abrufen von Anwesenheitsinformationen für Partnerkontakte.  <br/> Die Anwesenheitsinformationen für Mitglieder einer erweiterten Verteilergruppe werden über beständige Anwesenheitsabonnements ermittelt, nicht über Abrufe, und werden als 1 Erweiterung pro Benutzer für jeweils 2 Stunden modelliert.  <br/> Kurze Abonnements auftreten, wenn ein Benutzer anmeldet, ein Abonnement Batch für Kontakte des Benutzers vorhanden ist und klicken Sie dann bald der Benutzer abmeldet. Es wird von 6 kurzen Abonnements pro Benutzer und Stunde ausgegangen, wobei jedes Abonnement 10 Minuten dauert. <br/> |
|Veröffentlichung der Anwesenheit  <br/> |Der Anwesenheitsstatus wird durchschnittlich viermal pro Benutzer und Stunde veröffentlicht, mit einer maximalen Anzahl von 6 Veröffentlichungen pro Benutzer und Stunde.  <br/> |
|Größe des Anwesenheitsdokuments  <br/> |Bei einem vollständigen Anwesenheitsdokument wird von einer durchschnittlichen Größe von 4 KB ausgegangen, mit einer maximalen Größe von 25 KB.  <br/> |
   
In der folgenden Tabelle wird das Benutzermodell für die Adressbuchverwendung beschrieben.
  
**Benutzermodell für Address Book**

|**Adressbuchsuchmodus**|**Verwendung**|
|:-----|:-----|
|Nur Adressbuchwebabfrage (alle Abfragen werden vom Adressbuch-Webabfragedienst ausgeführt)  <br/> |Vier Präfixabfragen pro Benutzer und Tag.  <br/> 60 exakte Suchabfragen pro Benutzer und Tag. 40 % dieser Abfragen werden als Batchabfragen ausgeführt, mit durchschnittlich 20 Kontakten pro Abfrage. Die übrigen 60 % der Abfragen werden für einen einzelnen Kontakt ausgeführt.  <br/> 25 Fotoabfragen pro Benutzer und Tag. 24 Abfragen für ein einzelnes Foto, die verbleibende Abfrage wird als Batchabfrage mit durchschnittlich 20 Kontakten ausgeführt.  <br/> Eine Suchabfrage für die gesamte Organisation pro Benutzer und Tag.  <br/> |
|Im gemischten Modus werden sowohl die Adressbuchdatei als auch Webabfragen verwendet. Dies ist der Standardmodus.  <br/> |Nur zwei Abfragetypen werden über das Netzwerk ausgeführt, die Suchabfragen für Fotos und für die gesamte Organisation.  <br/> 25 Fotoabfragen pro Benutzer und Tag. 24 Abfragen für ein einzelnes Foto, die verbleibende Abfrage wird als Batchabfrage mit durchschnittlich 20 Kontakten ausgeführt.  <br/> Eine Suchabfrage für die gesamte Organisation pro Benutzer und Tag.  <br/> |
   
In der folgenden Tabelle ist das Konferenzmodell beschrieben.
  
**Konferenzmodell**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Geplante Besprechungen im Vergleich zu Sofortbesprechungen  <br/> |60 % geplant, 40 % ungeplant.  <br/> Bei den geplanten Besprechungen wird von 80 % zugewiesenen Konferenzen ausgegangen, wobei es sich um Instanzen von wiederkehrenden Konferenzen handelt. 10 % sind einmalige offene Besprechungen, 8 % sind einmalige anonyme Besprechungen und 2 % sind einmalige geschlossene Besprechungen.  <br/> |
|Verteilung von Konferenzclients  <br/> |Für geplante Besprechungen:  <br/> • 65 % der Konferenzbenutzer verwenden Skype für Business 2016.  <br/> • 5 % der Konferenzbenutzer verwenden Skype für Web-Geschäfts-App.  <br/> • 30 % der Konferenzbenutzer verwenden Clients früherer Versionen, einschließlich Lync 2013 und Microsoft Lync 2010.  <br/> Für ungeplante Besprechungen:  <br/> • 70 % der Konferenzbenutzer verwenden Skype für Unternehmen.  <br/> • 30 % der Konferenzbenutzer verwenden Clients früherer Versionen, einschließlich Lync 2013 und Microsoft Lync 2010.  <br/> |
|Gleichzeitigkeit von Besprechungen  <br/> |5 % der Benutzer befinden sich während der Arbeitszeiten in Konferenzen. Bei einem Pool mit 80.000 Benutzern können sich daher bis zu 4.000 Benutzer gleichzeitig in Konferenzen befinden.  <br/> |
|Verteilung der Audiofunktion in Besprechungen  <br/> |40 % Kombination aus VoIP-Audio- und Einwahlkonferenzen, mit einem Verhältnis von 3:1 von VoIP-Benutzern zu Einwahlbenutzern.  <br/> 35 % nur VoIP-Audio.  <br/> 15 % nur Audio bei Einwahlkonferenzen.  <br/> 10 % ohne Audio (reine Chatkonferenzen mit durchschnittlich fünf gesendeten Nachrichten pro Benutzer).  <br/> |
|Medienmix für Konferenzen  <br/> |Bei 75 % der Konferenzen handelt es sich um Webkonferenzen mit Audio sowie einigen anderen Methoden für die Zusammenarbeit.  <br/> Für diesen Konferenzen werden die folgenden weiteren Methoden für die Zusammenarbeit genutzt:  <br/> **Hinweis:** Diese Nummern hinzufügen bis zu mehr als 100 %, da eine Konferenz mehrere Methoden der Zusammenarbeit werden kann. <br/> • 50 % nutzen zusätzlich die Anwendungsfreigabe. Es wird davon ausgegangen, dass ein Benutzer Daten mit maximal 1,1 MB pro Sekunde sendet.  <br/> • 50 % nutzen zusätzlich instant messaging (mit durchschnittlich 2 Nachrichten pro Benutzer).  <br/> • 20 % fügen Zusammenarbeit an Daten, einschließlich PowerPoint oder Whiteboard In diesen, durchschnittlich 2 PowerPoint-Dateien pro Konferenz, mit einer durchschnittlichen Größe für die PowerPoint von 10 MB (ohne eingebettetem Video) oder 30 MB (mit eingebettetem Video) dargestellt. Durchschnittlich 20 Anmerkungen pro Whiteboard.  <br/> • 20 % hinzufügen Video. 70 % dieser Benutzer nehmen an Konferenzen teil, für die Mehrfachansicht-Video aktiviert ist, wobei jeder Benutzer 2 bis 3 Videostreams empfängt.  <br/> • 15 % fügen Freigegebene Notizen hinzu.  <br/> |
|Verteilung der Konferenzteilnehmer  <br/> |50 % interne, authentifizierte Benutzer.  <br/> 25 % authentifizierte Benutzer mit Remotezugriff.  <br/> 15 % anonyme Benutzer.  <br/> 10 % Partnerbenutzer.  <br/> |
|Verteilung für den Besprechungsbeitritt  <br/> |Für die Benutzer wird simuliert, dass sie der Besprechung innerhalb der ersten 5 Minuten beitreten.  <br/> |
   
Bei regulären Front-End-Pools und bietet Skype für Business Server einen maximale unterstützte Besprechungsumfang von 250 Benutzern. Jeder Pool kann zu einem bestimmten Zeitpunkt eine Besprechung mit 250 Benutzern hosten. Während eine Besprechung dieser Größe stattfindet, kann der Pool zusätzlich weitere kleinere Konferenzen hosten. Darüber hinaus können Sie Besprechungen mit bis zu 1.000 Benutzern unterstützen, indem Sie einen Pool speziell zum Hosten dieser Besprechungen einrichten. Weitere Informationen hierzu finden Sie unter [Planen von großen Besprechungen in Skype für Business Server 2015](../../plan-your-deployment/conferencing/large-meetings.md).
  
Konferenzen wurden wie folgt simuliert:
  
- 85 % der Konferenzen wiesen vier Teilnehmer auf.
    
- 10 % der Konferenzen wiesen sechs Teilnehmer auf.
    
- 5 % der Konferenzen wiesen elf Teilnehmer auf.
    
- Eine große Konferenz mit 250 Benutzern.
    
Die folgende Tabelle enthält ausführliche Informationen zum Benutzermodell für Konferenzen mit Einwahlbenutzern.
  
**Benutzermodell für Einwahlkonferenzen**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Authentifiziert/anonym  <br/> |70 % der Anrufer treten anonym bei und werden zur Aufzeichnung ihres Namens aufgefordert. 30 % nehmen als authentifizierte Benutzer teil.  <br/> |
|Anrufdauer und Wartemusik  <br/> |Durchschnittliche Anrufdauer ohne Wartemusik: 50 Sekunden.  <br/> Für 50 % der Einwahlbenutzer wird Wartemusik wiedergegeben (durchschnittlich 5 Minuten).  <br/> |
|DTMF (Dual-Tone Multifrequency, Mehrfrequenzverfahren)  <br/> |15 % der Konferenzen, auf die ausschließlich per Einwahl zugegriffen wird, werden per Telefon geleitet. 10 % der gemischten Konferenzen, an denen Einwahlbenutzer teilnehmen, werden ebenfalls per Telefon geleitet.  <br/> 20 % der Konferenzleiter (per Telefon) nutzen 2 DTMF-Befehle pro Konferenz.  <br/> |
|Sprache von Ansagen  <br/> |Bei Simulationen wird Englisch als Ansagensprache verwendet.  <br/> |
   
Die folgende Tabelle enthält ausführliche Informationen zum Benutzermodell für die Konferenzlobby.
  
**Benutzermodell für die Konferenzlobby**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Anzahl von Benutzern in der Lobby  <br/> |5 % der Einwahlbenutzer betreten zunächst die Lobby, 25 % der anderen Benutzer werden zunächst in die Lobby weitergeleitet.  <br/> |
|Zulassen von Benutzern aus der Lobby  <br/> |Bei Simulationen wurden alle Benutzer vom Referenten zugelassen, bevor ein Clienttimeout auftritt.  <br/> |
   
In der folgenden Tabelle ist das Benutzermodell für andere Peer-zu-Peer-Sitzungen beschrieben.
  
**Benutzermodell für Peer-zu-Peer-Sitzungen**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Anwendungsfreigabe  <br/> |Jeder Benutzer nimmt an fünf Peer-zu-Peer-Anwendungsfreigabesitzungen pro Monat teil (durchschnittlich 0,25 Sitzungen pro Tag).  <br/> |
|Dateiübertragung  <br/> |Jeder Benutzer nimmt (im Rahmen einer Chatsitzung) an einer Peer-zu-Peer-Dateiübertragungssitzung pro Monat teil (durchschnittlich 0,05 Sitzungen pro Tag). Die durchschnittliche Größe der in einer Sitzung übertragenen Dateien beträgt 1 MB.  <br/> |
   
In der folgenden Tabelle wird das Benutzermodell für Richtlinien beschrieben.
  
**Benutzermodell für Richtlinien**

|**Kategorie**|**Beschreibung**|
|:-----|:-----|
|Konferenz-, Anwesenheits- und Archivierungsrichtlinien  <br/> |Es wird von einer globalen Richtlinie, zehn Konferenzrichtlinien, vier Archivierungsrichtlinien und zehn Anwesenheitsrichtlinien ausgegangen.  <br/> |
|VoIP-Richtlinie  <br/> |Es wird von einer globalen Richtlinie und zwei Richtlinien pro Standort ausgegangen. 100 % der Standorte verfügen über eine Standortrichtlinie, und 30 % der Benutzer ist eine benutzerbasierte Richtlinie zugewiesen. Pro Standort wird von einem Wählplan und zwei Routen ausgegangen.  <br/> |
   
## <a name="busy-hour"></a>Spitzenzeiten

Die Spitzenauslastung für Peer-zu-Peer-Sitzungen wird basierend auf der Anzahl von Anrufversuchen (Busy Hour Call Attempts, BHCA) zu Spitzenzeiten berechnet. Für diesen Begriff aus der VoIP-Branche wird davon ausgegangen, dass 50 % aller Anrufe an einem Tag innerhalb von 20 % der Gesamtzeit getätigt werden. Der BHCA-Wert wird mithilfe der folgenden Formel berechnet:
  
 `BHCA=(total calls * 0.5) / 1.6`
  
Zur Simulation von Spitzenzeiten wurden in Leistungstests VoIP- und andere Peer-zu-Peer-Sitzungen bei einer Spitzenauslastung mit einer Dauer von mindestens 1,6 Stunden pro Tag ausgeführt.
  
Für die Spitzenauslastung bei Konferenzen wird davon ausgegangen, dass 75 % aller Konferenzen an einem achtstündigen Arbeitstag innerhalb von vier Stunden zu Spitzenzeiten stattfinden. Für diese Spitzenzeiten wird das 1,5-Fache der durchschnittlichen Konferenzauslastung verzeichnet.
  
## <a name="enterprise-voice-to-pstn-calls"></a>Enterprise-VoIP zu PSTN-Anrufe

Enterprise-VoIP-Anrufe gelten die folgenden Annahmen:
  
- 60 % der Benutzer für Enterprise Voice aktiviert sind, und 60 % dieser Benutzer sind für PSTN aktiviert aufrufen.
    
- Jeder dieser Benutzer, für den PSTN-Anrufe aktiviert sind, tätigt 4 PSTN-Anrufe in Spitzenzeiten. Jeder Anruf dauert 3 Minuten.
    
- 65 % dieser PST-VoIP-Anrufe verwenden die Medienumgehung.
    
## <a name="mobility"></a>Mobilität

Es wird davon ausgegangen, dass für 40 % der registrierten Benutzer die Mobilität aktiviert ist. Für jeden Benutzer mit aktivierter Mobilität wird davon ausgegangen, dass sich die Aktivität des mobilen Clients zur Aktivität der anderen MPOP-Instanzen für diesen Benutzer summiert. Mit Ausnahme von Konferenzinteraktionen, für die der Mobilitätsclient einfach ein weiterer Clienttyp ist, der für die Teilnahme an Konferenzen verwendet werden kann.
  
## <a name="persistent-chat"></a>Beständiger Chat

Es wird davon ausgegangen, dass 25 % der registrierten Benutzer an Sitzungen für beständigen Chat beteiligt sind, wobei Folgendes gilt:
  
- Durchschnittlich 1,5 Chatrooms pro Benutzer
    
- Jeder Chatroom führt zu 12 Abrufanforderungen pro Stunde, mit einem Zielwert von durchschnittlich je 10 Benutzern
    
## <a name="response-group-and-call-park"></a>Reaktionsgruppe und Parken von Anrufen

Es wird davon ausgegangen, dass 0,15 % der registrierten Benutzer Reaktionsgruppen angehören. Außerdem wird davon ausgegangen, dass 0,02 % der registrierten Benutzer zu einem bestimmten Zeitpunkt Anrufe parken.
  

