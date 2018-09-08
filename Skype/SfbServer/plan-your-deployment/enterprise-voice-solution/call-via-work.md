---
title: Planen der Anruf über den Arbeitsplatz in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planen von Anrufen über Arbeitsplatz in Skype für Business Server, ermöglicht die Integration zwischen Skype für Unternehmen und Ihre Telefonanlage, damit Benutzer ihre Nebenstellentelefone über steuern Skype für Unternehmen verwenden können.
ms.openlocfilehash: b7c1765af7140bdfc1a0e304dd94218231ed41c7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887919"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planen der Anruf über den Arbeitsplatz in Skype für Business Server
 
Planen von Anrufen über Arbeitsplatz in Skype für Business Server, ermöglicht die Integration zwischen Skype für Unternehmen und Ihre Telefonanlage, damit Benutzer ihre Nebenstellentelefone über steuern Skype für Unternehmen verwenden können.
  
 **Über Arbeitsplatz anrufen** ist ein neues Feature in Skype für Business Server, dem Sie Ihre Skype for Business-Lösung in die vorhandene PBX-Telefonsysteme integrieren können. In Skype für Unternehmen aufrufen, einen anderen Benutzer, entweder innerhalb Ihrer Bereitstellung oder um einen externen Benutzer kann Benutzer mit aktivierter über Arbeitsplatz anrufen klicken. Der Anruf wird dann über das Festnetztelefon des Benutzers geführt. Dadurch können Benutzer mit einem PBX-Telefon Audio in ihren rich Skype für Business Unterhaltungen werden soll. In früheren Versionen von Lync Server Remoteaufruf war Steuerelement ein Feature, das Benutzer ihre Nebenstellentelefone über mit Lync Server steuern aktiviert. Dieses Feature wurde in Skype für Business Server mit über Arbeitsplatz anrufen ersetzt.
  
Über Arbeitsplatz anrufen ermöglicht die folgenden für Benutzer der PBX-Telefon
  
- Click-to-call-Benutzererfahrung, mit dem über das PBX-Telefon bereitgestellte Audio.
    
- Anwesenheit, Benutzersuche und Instant Messaging-Integration – können beispielsweise zwei über Arbeitsplatz anrufen Benutzer in Sofortnachrichtensitzungen Audio ihre Sitzung mit den Audiofunktionen zur Verfügung gestellt, über die Nebenstellenanlage Telefone hinzufügen.
    
- Die Möglichkeit zum Hinzufügen von Instant Messaging, Anwendungsfreigabe und Dateiübertragung zu einem Anruf über Arbeitsplatz anrufen.
    
- One-click-Funktion zur Besprechungsteilnahme
    
## <a name="how-it-works"></a>Funktionsweise

Über Arbeitsplatz anrufen verwendet Unified Communications Web API (UCWA) als Back User Agent (B2BUA) zwischen der PBX-System und Ihre Skype für Business Server-Bereitstellung, damit keine Computer unterstützt Telecommunications Application (CSTA)-Gateway benötigt werden, um eine Verbindung herstellen Skype für Business Server mit PBX-System. UCWA ist ein Dienst, der in früheren Versionen von Lync Server zum Aktivieren des Konnektivität mit Mobile und Web-Clients eingeführt, und automatisch auf jedem Front-End-Server installiert ist.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Rufen Sie Workflows für einen Anruf über Arbeitsplatz anrufen

Die folgende Abbildung zeigt, wie Benutzer mit aktivierter über Arbeitsplatz anrufen die Skype für Business Server verwenden kann, um einen Anruf zu tätigen:
  
![Zeigt die Schritte während eines geschäftlichen Anrufs; zunächst klickt der Anrufer im Skype for Business-Client auf das entsprechende Symbol, um jemanden anzurufen; anschließend lässt die UCWA das Telefon des Anrufers klingeln. Wenn der Anrufer abhebt, wird der Empfänger angerufen](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. Der Benutzer wählt einen Benutzer in ihrer Skype für Business-Client und klickt auf das Telefonsymbol, um sie anzurufen. Im Fall einer Chatunterhaltung klickt der Benutzer, um den Benutzer anzurufen, mit dem die Sitzung stattfindet.
    
2. Das PBX-Telefon des Benutzers, der den Anruf ausgeführt hat, beginnt zu klingeln. Die Anrufer-ID für dieses Telefon zeigt eine globale Rufnummer das zum Anzeigen in der Anrufer-ID aller Benutzer tätigen von Anrufen über Arbeitsplatz anrufen eingerichtet haben. Diese globale Telefonnummer ist nicht die tatsächliche Telefonnummer, die dem Telefon eines Benutzers entspricht. Es ist stattdessen ein visuelles Signal, durch das der Benutzer weiß, dass es sein eigener ausgehender Anruf und nicht ein eingehender Anruf zur selben Zeit ist. Bei der Bereitstellung über Arbeitsplatz anrufen, sollten Sie die Benutzer über diese Telefonnummer für die globale und was es bedeutet informieren.
    
3. Der Benutzer, der den Anruf ausgeführt hat, nimmt den Anruf an. Skype für Unternehmen initiiert dann den Anruf an den angerufenen. 
    
4. Wenn der Angerufene antwortet, beginnt der Sprachanruf. Wenn die beiden Benutzer bereits eine laufende Chatsitzung hatten, kann diese fortgeführt werden.
    
### <a name="joining-a-conference-with-call-via-work"></a>Einer Konferenz beitreten mithilfe von „Anruf über Arbeit“

Ein Benutzer über Arbeitsplatz anrufen kann einer geplanten Besprechung teilnehmen, indem Sie auf die besprechungs-URL. Skype für Unternehmen zeigt anschließend eine **anwählen einer** Nachricht, bis der Meeting-Dienst PBX-Telefon des Benutzers wählt. Der Benutzer über Arbeitsplatz anrufen, und klicken Sie dann das PBX-Telefon nimmt und der Besprechung teilnimmt.
  
Ein Benutzer über Arbeitsplatz anrufen können die Option **Jetzt besprechen** in Skype für Unternehmen auch um sofort-Besprechungen zu erstellen. Der Benutzer sieht dann die Nachricht **Ausgehende Verbindung**, und das PBX-Telefon klingelt.
  
Ein Benutzer über Arbeitsplatz anrufen kann auch in einer Besprechung einwählen durch Aufrufen von die Konferenzbrücke Nummer aus in Skype für Unternehmen. Wenn eine Konferenz-PIN angefordert wird, muss der Benutzer sein PBX-Telefon verwenden, um die PIN einzugeben.
  
### <a name="incoming-calls"></a>Eingehende Anrufe

Wenn Benutzer mit aktivierter empfängt über Arbeitsplatz anrufen ein Skype für Business Anruf, der PBX-Telefon und des Benutzers Skype für Business-Clients, die alle anrufen gleichzeitig (wenn der Benutzer Gleichzeitiges Klingeln eingerichtet wurden). Der Benutzer kann den Anruf entweder das PBX-Telefon abnehmen, oder klicken Sie auf **annehmen** , für die Skype für Business Notification annehmen. Wenn der Benutzer den Anruf Verwendung Skype für Unternehmen akzeptiert, bleibt die Skype für Business-Fenster für den Anruf geöffnet. Aber, wenn der Benutzer den Anruf annimmt, durch abnehmen PBX-Telefon, klicken Sie dann die Skype für Business Notification Fenster wird geschlossen, und es ist keine Skype für Business-Sitzung, nur die VoIP-Anruf über das PBX-Telefon.
  
Wenn ein Benutzer mit aktivierter über Arbeitsplatz anrufen PBX-Anruf, nur das PBX-Telefon klingelt empfängt.
  
## <a name="limitations-of-call-via-work"></a>Einschränkungen von "geschäftlich anrufen"

Über Arbeitsplatz anrufen ist eine VoIP-Lösung, die wenig Hardwaresetup erfordert, jedoch ist im Vergleich zu in vollständige Enterprise-VoIP oder Remoteanrufsteuerung verfügbaren Features eingeschränkt. Über Arbeitsplatz anrufen weist die folgenden Nachteile:
  
- Wenn ein Benutzer über Arbeitsplatz anrufen die anrufweiterleitung, die über Arbeitsplatz anrufen Rückrufnummer eingerichtet hat und jemand versucht, die diesen Benutzer zu einer Besprechung mithilfe des Benutzers Telefonnummer einladen, wird die Einladung den Benutzer nicht angezeigt. Sie sollten Ihre Benutzer darüber informieren, dass sie Besprechungsteilnehmer einladen, indem sie den entsprechenden Namen anklicken, nicht die Telefonnummer. 
    
- Erweiterte 911-Funktion und Missbrauch sind bei Anrufen über Arbeitsplatz anrufen nicht verfügbar.
    
- Anruf über Arbeitsplatz-fähigen Benutzer können nicht die Delegierung, teamanrufe oder reaktionsgruppenfeatures verwenden.
    
- Benutzer von Anrufen über Arbeitsplatz können Skype für Business zum Aufzeichnen einer Besprechung, stumm schalten oder stummschaltung Aufheben des Anrufs, halten oder leitet den Anruf oder verwenden Sie das Parken von Anrufen verwenden.
    
- Benutzer können nicht über Arbeitsplatz anrufen verwenden, um ihre Voicemailnachrichten PBX zuzugreifen.
    
- Benutzer von Anrufen über Arbeitsplatz können keine Sitzung ausweiten, die als einen Anruf zu einer gemeinsamen Besprechung gestartet, die Kommunikation wie Video, Powerpoint, Whiteboard oder ein Hinweis enthält.
    
- Benutzer von Anrufen über Arbeitsplatz können nicht zu einem Anruf 2 Person weitere Benutzer hinzufügen.
    
- Keine Unterstützung von Deskphonekopplung oder VDI-Plug-In-Kopplung.
    
- Wenn ein Benutzer macht oder ein Anruf über das PBX-Telefon (und nicht die Skype für Business Fenster) Antworten, werden keine Protokolldatei des Anrufs.
    
- Wenn Ihr PBX-System **REFER with Replaces** nicht unterstützt, tritt folgendes Verhalten auf. Klicken Sie auf einen Anruf über Arbeitsplatz anrufen, wenn der Benutzer den laufenden Anruf von der PBX-Telefon übermittelt, wird im Anruffenster nicht von ihrer Skype für Business Fenster ausgeblendet. Wenn der Benutzer dann das Anruffenster schließt, wird der Anruf zwischen dem Durchstellungsziel und dem Durchstellenden beendet. 
    
## <a name="prerequisites-for-call-via-work"></a>Erforderliche Komponenten für Anruf über den Arbeitsplatz

Um alle Benutzer für über Arbeitsplatz anrufen zu aktivieren, müssen Sie einige erforderliche Komponenten für erfüllt sein. Weitere Informationen zu diesen Voraussetzungen und Schritte zum Aktivieren von Benutzern für über Arbeitsplatz anrufen finden Sie unter [Bereitstellen von Anrufen über Arbeitsplatz in Skype für Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Siehe auch

[Plan für die Remoteanrufsteuerung in Skype für Unternehmen](remote-call-control.md)
  
[Bereitstellen der Funktion „Anruf über Arbeit“ in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

