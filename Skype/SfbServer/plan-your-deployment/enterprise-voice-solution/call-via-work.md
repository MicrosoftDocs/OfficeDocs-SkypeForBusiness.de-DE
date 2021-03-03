---
title: Planen der Anruf-über-Arbeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planen der Funktion "Geschäft arbeitsplatz" in Skype for Business Server, die die Integration zwischen Skype for Business und Ihrem Nebenstellensystem ermöglicht, sodass Benutzer Skype for Business zum Steuern ihrer Nebenstellentelefone verwenden können.
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825875"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planen der Anruf-über-Arbeit in Skype for Business Server
 
Planen der Funktion "Geschäft arbeitsplatz" in Skype for Business Server, die die Integration zwischen Skype for Business und Ihrem Nebenstellensystem ermöglicht, sodass Benutzer Skype for Business zum Steuern ihrer Nebenstellentelefone verwenden können.
  
 **Anruf über Arbeit** ist eine neue Funktion in Skype for Business Server, mit der Sie Ihre Skype for Business-Lösung in Ihre vorhandenen Nebenstellenanlagen integrieren können. Ein für "Geschäft über Arbeit" aktivierter Benutzer kann in Skype for Business einen anderen Benutzer anrufen, entweder innerhalb Ihrer Bereitstellung oder eines externen Benutzers. Der Anruf wird über das Nebenstellentelefon des Benutzers abgeschlossen. Dadurch kann ein Benutzer mit einem Nebenstellentelefon Audio in seine reichhaltigen Skype for Business-Unterhaltungen aufnehmen. In früheren Versionen der Lync Server-Remoteanrufsteuerung konnten Benutzer ihre Nebenstellentelefone mit Lync Server steuern. In Skype for Business Server wurde diese Funktion durch "Geschäft arbeitsplatz" ersetzt.
  
"Über Arbeit anrufen" aktiviert Folgendes für Benutzer von Nebenstellentelefonen
  
- Klick-und-Anruf-Erfahrung mit den über das Nebenstellentelefon bereitgestellten Audiodaten.
    
- Anwesenheit, Benutzersuche und Integration von Telefonanrufen – beispielsweise können zwei Benutzer von "Anruf über Arbeit" in einer Sitzung mit Einer-Telefon-E-Mail Audio zu ihrer Sitzung hinzufügen, und die Audiodaten werden über die Nebenstellentelefone bereitgestellt.
    
- Die Möglichkeit zum Hinzufügen von Imitieren, Anwendungsfreigabe und Dateiübertragung zu einem Anruf über die Arbeit.
    
- Funktion zum Beitreten zu einer Besprechung mit einem Klick
    
## <a name="how-it-works"></a>Funktionsweise

Call Via Work verwendet Unified Communications Web API (UCWA) als Back-to-Back-Benutzer-Agent (B2BUA) zwischen dem Nebenstellensystem und Ihrer Skype for Business Server-Bereitstellung, sodass kein computergestütztes Gateway für Telekommunikationsanwendung (CSTA) erforderlich ist, um Skype for Business Server mit Ihrem Nebenstellensystem zu verbinden. UCWA ist ein Dienst, der in früheren Versionen von Lync Server eingeführt wurde, um verbindungen mit mobilen Clients und Webclients zu ermöglichen, und wird automatisch auf jedem Front-End-Server installiert.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Anrufworkflow für einen Anruf über die Arbeit

Im Folgenden wird veranschaulicht, wie ein für "Geschäft über Arbeit" aktivierter Benutzer skype for Business Server für einen Anruf verwenden kann:
  
![Zeigt die Schritte während eines Anrufs über arbeit; zuerst klickt der Anrufer, um eine Person im Skype for #A0 an anruft. anschließend klingelt die UCWA am Telefon des Anrufers. Wenn der Anrufer das Telefon an sich nimmt, wird der Empfänger angerufen.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. Der Benutzer wählt einen Benutzer in ihrem Skype for Business-Client aus und klickt auf das Telefonsymbol, um ihn anwählen. Oder während einer Unterhaltung im Rahmen einer Telefonkonferenz klickt der Benutzer, um den Benutzer an anruft, mit dem die Sitzung geführt wird.
    
2. Das Nebenstellentelefon des Benutzers, der den Anruf platziert hat, beginnt zu klingeln. Die Anrufer-ID für dieses Telefon zeigt eine globale Telefonnummer an, die Sie so eingerichtet haben, dass sie in der Anrufer-ID aller Benutzer, die Anrufe über die Arbeit tätigt, anzeigen. Diese globale Telefonnummer ist keine tatsächliche Telefonnummer, die dem Telefon einer Person entspricht. Stattdessen ist es ein visuelles Signal, um einem Benutzer zu signalisieren, dass es sich um einen eigenen ausgehenden Anruf und nicht um einen gleichzeitigen eingehenden Anruf handelt. Wenn Sie "Anruf über Arbeit" bereitstellen, sollten Sie diese Benutzer über diese globale Telefonnummer informieren und wissen, was dies bedeutet.
    
3. Der Benutzer, der den Anruf abting, nimmt sein Nebenstellentelefon auf. Skype for Business initiiert dann den Sprachanruf an den Ansprecher. 
    
4. Wenn der Ansprecher antwortet, beginnt der Sprachanruf. Wenn für die beiden Benutzer bereits eine Im-Im-Sitzung anfing, kann sie fortgesetzt werden.
    
### <a name="joining-a-conference-with-call-via-work"></a>Beitreten zu einer Konferenz mit "Anruf über Arbeit"

Ein Benutzer von "Anruf über Arbeit" kann an einer geplanten Besprechung teilnehmen, indem er auf die Besprechungs-URL klickt. Skype for Business zeigt  dann eine Auswahl für eine Nachricht an, bis der Besprechungsdienst das Nebenstellentelefon des Benutzers wählt. Der Benutzer "Anruf über Arbeit" nimmt dann das Nebenstellentelefon auf und nimmt an der Besprechung teil.
  
Ein Benutzer von "Geschäftfreundliche  Anrufe" kann auch die Option "Sofortbesprechungen" in Skype for Business verwenden, um Sofortbesprechungen zu erstellen. Der Benutzer sieht dann die Nachricht "Auswählen **an",** und das Nebenstellentelefon klingelt.
  
Ein Benutzer von "Geschäftfreundliche Anrufe" kann sich auch in eine Besprechung einwählen, indem er die Nummer der Konferenzbrücke in Skype for Business anruft. Wenn eine Konferenz-PIN erforderlich ist, muss der Benutzer die PIN über sein Nebenstellentelefon eingeben.
  
### <a name="incoming-calls"></a>Eingehende Anrufe

Wenn ein für "Geschäftlich anrufen" aktivierter Benutzer einen Skype for Business-Anruf erhält, klingeln das Nebenstellentelefon und die Skype for Business-Clients des Benutzers gleichzeitig (wenn der Benutzer gleichzeitiges Klingeln eingerichtet hat). Der Benutzer kann den Anruf annehmen, indem er  entweder das Nebenstellentelefon annimmt oder in der Skype for Business-Benachrichtigung auf "Annehmen" klickt. Wenn der Benutzer den Anruf über Skype for Business annimmt, bleibt das Skype for Business-Fenster für den Anruf geöffnet. Wenn der Benutzer den Anruf jedoch über das Nebenstellentelefon annimmt, wird das Skype for Business-Benachrichtigungsfenster geschlossen, und es gibt keine Skype for Business-Sitzung, sondern nur den Sprachanruf über das Nebenstellentelefon.
  
Wenn ein für "Über Arbeit anrufen" aktivierter Benutzer einen Nebenstellenanruf erhält, klingelt nur das PbX-Telefon.
  
## <a name="limitations-of-call-via-work"></a>Einschränkungen der Anruf-über-Arbeit

"Anruf über Arbeit" ist eine Sprachlösung, für die nur wenig Hardware eingerichtet werden muss, aber im Vergleich zu den Funktionen, die in der Enterprise-VoIP oder der Remoteanrufsteuerung verfügbar sind, Einschränkungen gelten. "Anruf über Arbeit" hat die folgenden Einschränkungen:
  
- Wenn ein Benutzer von "Anruf über Arbeit" die Anrufanrufnummer eingerichtet hat und jemand versucht, diesen Benutzer über die Telefonnummer des Benutzers zu einer Besprechung einzuladungen, erreicht die Einladung den Benutzer nicht. Sie sollten Ihre Benutzer erziehen, Teilnehmer zu Besprechungen einzu einladen, indem Sie auf den Namen und nicht auf die Telefonnummer klicken. 
    
- Die erweiterte 911-Funktion und die Nachverfolgung bösartiger Anrufe sind bei Anrufen über die Arbeit nicht verfügbar.
    
- Benutzer, die für "Über Arbeit anrufen" aktiviert sind, können die Delegierungs-, Teamanruf- oder Reaktionsgruppesfunktionen nicht verwenden.
    
- Benutzer von "Geschäftlich anrufen" können Skype for Business nicht zum Aufzeichnen einer Besprechung, stummschalten oder Stummschalten des Anrufs, Zum Halten oder Übertragen des Anrufs oder zum Parken von Anrufen verwenden.
    
- Benutzer können nicht mit "Über Arbeit anrufen" auf ihre Voicemailnachrichten der Nebenstellenanlage zugreifen.
    
- Benutzer von "Anruf über Arbeit" können eine Sitzung, die als Sprachanruf gestartet wurde, nicht zu einer gemeinsamen Besprechung eskalieren, die Kommunikation wie Video, PowerPoint, Whiteboard oder One Note umfasst.
    
- Benutzer von "Anruf über Arbeit" können keine weiteren Benutzer zu einem Zwei-Personen-Anruf hinzufügen.
    
- Keine Unterstützung für die Kopplung von Tischtelefonen oder VDI-Plug-Ins.
    
- Wenn ein Benutzer einen Anruf über das Nebenstellentelefon (und nicht über das Skype for Business-Fenster) anruft oder beantwortet, wird kein Protokoll des Anrufs angezeigt.
    
- Wenn Ihr Nebenstellensystem REFER mit **"Replaces"** nicht unterstützt, wird das folgende Verhalten auftreten. Wenn der Benutzer bei einem Anruf über die Geschäftstätigkeit den laufenden Anruf über das Nebenstellentelefon weitergibt, wird das Anruffenster nicht aus dem Skype for Business-Fenster ausgeblendet. Wenn der Benutzer dann das Anruffenster schließt, wird der Anruf zwischen dem Übertragungsziel und dem Durchgangsbenutzer beendet. 
    
## <a name="prerequisites-for-call-via-work"></a>Voraussetzungen für "Anruf über Arbeit"

Um Benutzer für die Funktion "Über Arbeit anrufen" zu aktivieren, müssen einige Voraussetzungen erfüllt sein. Weitere Informationen zu diesen Voraussetzungen und Schritte zum Aktivieren von Benutzern für die Funktion "Geschäft", finden Sie unter "Anruf über Arbeit [bereitstellen" in Skype for Business Server 2015.](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>Siehe auch

[Planen der Remoteanrufsteuerung in Skype for Business](remote-call-control.md)
  
[Bereitstellen von "Anruf über Arbeit" in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

