---
title: Plan for Call Via Work in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planung von "Anruf über Arbeit" in Skype for Business Server, was die Integration zwischen Skype for Business und Ihrem PbX-Telefonsystem ermöglicht, sodass Benutzer Skype for Business verwenden können, um ihre Nebenstellentelefone zu steuern.
ms.openlocfilehash: 0dddb601ecf9928aa1bd1cd63bc8ed3628a1330d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854219"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Plan for Call Via Work in Skype for Business Server
 
Planung von "Anruf über Arbeit" in Skype for Business Server, was die Integration zwischen Skype for Business und Ihrem PbX-Telefonsystem ermöglicht, sodass Benutzer Skype for Business verwenden können, um ihre Nebenstellentelefone zu steuern.
  
 **Call Via Work** ist ein neues Feature in Skype for Business Server, mit dem Sie Ihre Skype for Business-Lösung in Ihre vorhandenen PBX-Telefonsysteme integrieren können. Ein Benutzer, der für "Über Arbeit anrufen" aktiviert ist, kann auf Skype for Business klicken, um einen anderen Benutzer anzurufen, entweder innerhalb Ihrer Bereitstellung oder eines externen Benutzers. Der Anruf wird über das PbX-Telefon des Benutzers abgeschlossen. Auf diese Weise kann ein Benutzer mit einem PbX-Telefon Audio in seine umfangreichen Skype for Business Unterhaltungen einschließen. In früheren Versionen von Lync Server war die Remoteanrufsteuerung ein Feature, mit dem Benutzer ihre Nebenstellenanlagentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch "Über Arbeit anrufen" ersetzt.
  
"Über Arbeit anrufen" ermöglicht Für PbX-Telefonbenutzer Folgendes:
  
- Klick-und-Anruf-Erfahrung mit den über das PbX-Telefon bereitgestellten Audiodaten.
    
- Anwesenheit, Benutzersuche und Chatintegration – zwei Benutzer von "Anruf über Arbeit" in einer Chatsitzung können ihrer Sitzung Audio hinzufügen, wobei die Audiodaten über die Nebenstellentelefone bereitgestellt werden.
    
- Die Möglichkeit, Chatnachrichten, Anwendungsfreigaben und Dateiübertragungen zu einem Anruf über Die Arbeit hinzuzufügen.
    
- Funktion für den Besprechungsbeitritt mit einem Klick
    
## <a name="how-it-works"></a>So funktioniert es

Call Via Work verwendet die Unified Communications Web API (UCWA) als Back-to-Back-Benutzer-Agent (B2BUA) zwischen dem Nebenstellensystem und Ihrer Skype for Business Server-Bereitstellung, sodass kein computergestütztes Telekommunikationsanwendungsgateway (CSTA) erforderlich ist, um Skype for Business Server mit Ihrer Nebenstellenanlage zu verbinden. UCWA ist ein Dienst, der in früheren Versionen von Lync Server eingeführt wurde, um die Konnektivität mit mobilen Clients und Webclients zu ermöglichen, und wird automatisch auf jedem Front-End-Server installiert.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Anrufworkflow für einen Anruf über Die Arbeit

Im Folgenden wird veranschaulicht, wie ein für "Anruf über Arbeit" aktivierter Benutzer die Skype for Business Server verwenden kann, um einen Anruf zu tätigen:
  
![Zeigt die Schritte während eines Anrufs über Die Arbeit; Zuerst klickt der Anrufer, um eine Person im Skype for Business-Client anzurufen. dann ruft die UCWA das Telefon des Anrufers an. Wenn der Anrufer das Telefon annimmt, wird der Empfänger angerufen.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. Der Benutzer wählt einen Benutzer in seiner Skype for Business Client aus und klickt auf das Telefonsymbol, um ihn anzurufen. Oder während einer Chatunterhaltung klickt der Benutzer, um den Benutzer aufzurufen, mit dem er die Sitzung führt.
    
2. Das Festnetztelefon des Benutzers, der den Anruf getätigt hat, beginnt zu klingeln. Die Anrufer-ID für dieses Telefon zeigt eine globale Telefonnummer an, die Sie so eingerichtet haben, dass sie in der Anrufer-ID aller Benutzer angezeigt wird, die Anrufe über Die Arbeit tätigen. Diese globale Telefonnummer ist keine tatsächliche Telefonnummer, die dem Telefon einer Person entspricht. Stattdessen ist es ein visuelles Signal, um einem Benutzer mitzuteilen, dass es sich um einen eigenen ausgehenden Anruf handelt und nicht um einen eingehenden Anruf, der gleichzeitig stattfindet. Wenn Sie "Anruf über Arbeit" bereitstellen, sollten Sie diese Benutzer über diese globale Telefonnummer und deren Bedeutung informieren.
    
3. Der Benutzer, der den Anruf getätigt hat, nimmt sein Festnetztelefon an. Skype for Business initiiert dann den Sprachanruf an den Angerufenen. 
    
4. Wenn der Angerufene antwortt, beginnt der Sprachanruf. Wenn für die beiden Benutzer bereits eine Chatsitzung ausgeführt wurde, kann der Vorgang fortgesetzt werden.
    
### <a name="joining-a-conference-with-call-via-work"></a>Teilnehmen an einer Konferenz mit "Anruf über Arbeit"

Ein Benutzer von "Anruf über Arbeit" kann an einer geplanten Besprechung teilnehmen, indem er auf die Besprechungs-URL klickt. Skype for Business zeigt dann eine **Ausgehend-an-Nachricht an,** bis der Besprechungsdienst das Festnetztelefon des Benutzers wählt. Der Benutzer von "Anruf über Arbeit" nimmt dann das Festnetztelefon an und nimmt an der Besprechung teil.
  
Ein Benutzer von "Über Arbeit anrufen" kann auch die Option **"Jetzt besprechen"** in Skype for Business verwenden, um Sofortbesprechungen zu erstellen. Der Benutzer sieht dann die **Ausgehend-an-Nachricht,** und die Nebenstellenanlage klingelt.
  
Ein Benutzer von "Anruf über Arbeit" kann sich auch in eine Besprechung einwählen, indem er die Konferenzbrückennummer aus Skype for Business anruft. Wenn eine Konferenz-PIN erforderlich ist, muss der Benutzer seine Nebenstellentelefonnummer verwenden, um die PIN einzugeben.
  
### <a name="incoming-calls"></a>Eingehende Anrufe

Wenn ein Benutzer, der für "Anruf über Arbeit" aktiviert ist, einen Skype for Business Anruf empfängt, klingeln das Nebenstellentelefon und die Skype for Business Clients des Benutzers alle gleichzeitig (wenn der Benutzer das gleichzeitige Klingeln eingerichtet hat). Der Benutzer kann den Anruf annehmen, indem er entweder die Nebenstellenanlage annimmt oder auf **"Annehmen"** in der Skype for Business-Benachrichtigung klickt. Wenn der Benutzer den Anruf mit Skype for Business annimmt, bleibt das fenster Skype for Business für den Anruf geöffnet. Wenn der Benutzer den Anruf jedoch annimmt, indem er die Nebenstellenanlage annimmt, wird das Skype for Business Benachrichtigungsfenster geschlossen, und es gibt keine Skype for Business Sitzung, sondern nur den Sprachanruf über das PbX-Telefon.
  
Wenn ein Benutzer, der für "Anruf über Arbeit" aktiviert ist, einen PBX-Anruf empfängt, klingelt nur die Nebenstellenanlage.
  
## <a name="limitations-of-call-via-work"></a>Einschränkungen des Anrufs über die Arbeit

"Anruf über Arbeit" ist eine VoIP-Lösung, die nur wenig Hardwareeinrichtung erfordert, jedoch im Vergleich zu den Funktionen, die in der vollständigen Enterprise-VoIP oder der Remoteanrufsteuerung verfügbar sind, Einschränkungen aufweist. Für "Anruf über Arbeit" gelten die folgenden Einschränkungen:
  
- Wenn ein Benutzer von "Anruf über Arbeit" die Anrufweiterleitung zur Rückrufnummer "Call Via Work" eingerichtet hat und jemand versucht, diesen Benutzer über die Telefonnummer des Benutzers zu einer Besprechung einzuladen, wird die Einladung nicht an den Benutzer weitergeleitet. Sie sollten Ihre Benutzer schulen, Teilnehmer zu Besprechungen einzuladen, indem Sie auf den Namen und nicht auf die Telefonnummer klicken. 
    
- Die erweiterte 911-Funktion und die Nachverfolgung bösartiger Anrufe sind bei Anrufen über Die Arbeit nicht verfügbar.
    
- Benutzer, die für "Über Arbeit anrufen" aktiviert sind, können die Funktionen delegierung, Teamanruf oder Reaktionsgruppe nicht verwenden.
    
- Benutzer von "Anruf über Arbeit" können Skype for Business nicht verwenden, um eine Besprechung zu aufzeichnen, den Anruf stumm zu schalten oder die Stummschaltung aufzuheben, den Anruf zu halten oder zu übertragen oder das Parken von Anrufen zu verwenden.
    
- Benutzer können "Anruf über Arbeit" nicht verwenden, um auf ihre PBX-Voicemailnachrichten zuzugreifen.
    
- Benutzer von "Anruf über Arbeit" können eine Sitzung, die als Sprachanruf begonnen hat, nicht zu einer Besprechung für die Zusammenarbeit eskalieren, die Kommunikation wie Video, PowerPoint, Whiteboard oder One Note umfasst.
    
- Benutzer von "Anruf über Arbeit" können einem Zwei-Personen-Anruf keine weiteren Benutzer hinzufügen.
    
- Keine Unterstützung für deskphone-Kopplung oder VDI-Plug-In-Kopplung.
    
- Wenn ein Benutzer einen Anruf über das Festnetztelefon (und nicht über das Skype for Business-Fenster) abnimmt oder beantwortet, gibt es kein Protokoll des Anrufs.
    
- Wenn Ihr Nebenstellensystem REFER nicht **mit Replaces** unterstützt, wird das folgende Verhalten ausgeführt. Wenn der Benutzer während eines Anrufs über Die Arbeit den laufenden Anruf von der Nebenstellenanlage Telefon überträgt, wird das Anruffenster nicht aus dem fenster Skype for Business entfernt. Wenn der Benutzer dann das Anruffenster schließt, wird der Anruf zwischen dem Übertragungsziel und dem Überstellungsempfänger beendet. 
    
## <a name="prerequisites-for-call-via-work"></a>Voraussetzungen für anruf per Arbeit

Um alle Benutzer für Anrufe per Arbeit zu aktivieren, müssen Sie über einige Voraussetzungen verfügen. Weitere Informationen zu diesen Voraussetzungen und Schritte zum Aktivieren von Benutzern für "Anruf über Arbeit" finden Sie unter [Deploy Call Via Work in Skype for Business Server 2015.](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>Siehe auch

[Planen der Remoteanrufsteuerung in Skype for Business](remote-call-control.md)
  
[Bereitstellen von "Anruf über Arbeit" in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

