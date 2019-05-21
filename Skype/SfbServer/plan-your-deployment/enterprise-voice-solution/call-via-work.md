---
title: Planen eines Anrufs über die Arbeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planung des Anrufs über die Arbeit in Skype for Business Server, der die Integration von Skype for Business und Ihrer Telefonanlage ermöglicht, damit Benutzer Skype for Business nutzen können, um Ihre Telefonanlagen zu kontrollieren.
ms.openlocfilehash: b2f0e57a33f6e194dc981b623a641850ed3c8de5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277027"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planen eines Anrufs über die Arbeit in Skype for Business Server
 
Planung des Anrufs über die Arbeit in Skype for Business Server, der die Integration von Skype for Business und Ihrer Telefonanlage ermöglicht, damit Benutzer Skype for Business nutzen können, um Ihre Telefonanlagen zu kontrollieren.
  
 **Call per work** ist eine neue Funktion in Skype for Business Server, die es Ihnen ermöglicht, Ihre Skype for Business-Lösung mit ihren bestehenden Telefonanlagen zu verbinden. Ein Benutzer, der über die Arbeit für einen Anruf aktiviert ist, kann in Skype for Business klicken, um einen anderen Benutzer anzurufen, entweder innerhalb Ihrer Bereitstellung oder eines externen Benutzers. Das Gespräch wird dann mit dem Festnetztelefon des Benutzers durchgeführt. Auf diese Weise kann ein Benutzer mit einem PBX-Telefon Audio in seine reichhaltigen Skype for Business-Unterhaltungen aufnehmen. In früheren Versionen von lync Server war die Remoteanrufsteuerung ein Feature, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten. In Skype for Business Server wurde diese Funktion durch Anruf über Arbeit ersetzt.
  
Anruf über Arbeit ermöglicht für Telefonanlagen Nutzer die folgenden Optionen:
  
- Click-to-call-Benutzererfahrung, mit dem über das PBX-Telefon bereitgestellte Audio.
    
- Anwesenheit, Benutzersuche und Chat-Integration – beispielsweise können zwei Anrufe über Arbeits Benutzer in einer Chatsitzung ihrer Sitzung Audio hinzufügen, wobei die Audiofunktionen über die PBX-Telefone bereitgestellt werden.
    
- Die Möglichkeit, Chats, Anwendungsfreigaben und Dateiübertragungen zu einem Anruf per Arbeits Anruf hinzuzufügen.
    
- Funktion für Besprechungsteilnahme mit einem Mausklick
    
## <a name="how-it-works"></a>Funktionsweise

Bei Anrufen per Arbeit wird Unified Communications Web API (UCWA) als Back-to-Back-Benutzer-Agent (B2BUA) zwischen dem PBX-System und ihrer Skype for Business Server-Bereitstellung verwendet, sodass kein Computerunterstütztes Telecommunications Application (CSTA)-Gateway benötigt wird, um eine Verbindung herzustellen. Skype for Business Server mit Ihrem PBX-System. UCWA ist ein Dienst, der in früheren Versionen von lync Server eingeführt wurde, um die Konnektivität mit mobilen und Webclients zu ermöglichen, und wird automatisch auf jedem Front-End-Server installiert.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Anruf Workflow für einen Anruf per Arbeits Anruf

Die folgende Abbildung zeigt, wie ein Benutzer, der über Arbeit aktiviert ist, den Skype for Business-Server verwenden kann, um einen Anruf zu tätigen:
  
![Zeigt die Schritte während eines geschäftlichen Anrufs; zunächst klickt der Anrufer im Skype for Business-Client auf das entsprechende Symbol, um jemanden anzurufen; anschließend lässt die UCWA das Telefon des Anrufers klingeln. Wenn der Anrufer abhebt, wird der Empfänger angerufen](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. Der Benutzer wählt einen Benutzer in seinem Skype for Business-Client aus und klickt auf das Telefonsymbol, um ihn anzurufen. Oder während einer Chat Unterhaltung klickt der Benutzer auf den Benutzer, mit dem Sie die Sitzung führen.
    
2. Die Telefonanlage des Benutzers, der den Anruf getätigt hat, beginnt zu klingeln. Die Rufnummernanzeige für dieses Telefon zeigt eine globale Telefonnummer, die Sie in der Rufnummernanzeige aller Nutzer anzeigen lassen, die Anrufe über geschäftliche Anrufe tätigen. Bei dieser globalen Telefonnummer handelt es sich nicht um eine tatsächliche Telefonnummer, die dem Telefon einer Person entspricht. Stattdessen ist es ein visuelles Signal, um Benutzern mitzuteilen, dass es sich um einen eigenen ausgehenden Anruf handelt, und kein eingehender Anruf zur gleichen Zeit stattfindet. Wenn Sie den Anruf über die Arbeit bereitstellen, sollten Sie diese Benutzer über diese globale Telefonnummer informieren und was dies bedeutet.
    
3. Der Nutzer, der den Anruf getätigt hat, nimmt seine Telefonanlage an. Skype for Business initiiert dann den Sprachanruf an den angerufenen. 
    
4. Wenn der aufgerufene antwortet, beginnt der Sprachanruf. Wenn die beiden Benutzer bereits eine Chatsitzung durchlaufen haben, kann Sie fortfahren.
    
### <a name="joining-a-conference-with-call-via-work"></a>Teilnehmen an einer Konferenz mit Anruf über die Arbeit

Ein Anruf über Arbeit Benutzer kann an einer geplanten Besprechung teilnehmen, indem Sie auf die Besprechungs-URL klickt. Skype for Business zeigt dann eine **Anruf Nachricht an,** bis der Besprechungs Dienst das PBX-Telefon des Benutzers wählt. Der Anruf über den Arbeits Benutzer nimmt dann das PBX-Telefon auf und tritt der Besprechung bei.
  
Ein Anruf über die Arbeit Benutzer kann auch die Option " **jetzt** besprechen" in Skype for Business verwenden, um Besprechungen jetzt erstellen zu können. Der Benutzer sieht dann den Anruf **aus, um Nachrichten zu** senden, und die Telefonanlage klingelt.
  
Ein Anruf über den Arbeits Benutzer kann sich auch in eine Besprechung einwählen, indem er in Skype for Business die Konferenz Brücken Nummer anruft. Wenn eine Konferenz-PIN erforderlich ist, muss der Benutzer sein PBX-Telefon verwenden, um die PIN einzugeben.
  
### <a name="incoming-calls"></a>Eingehende Anrufe

Wenn ein Benutzer, der über Work aktiviert ist, einen Skype for Business-Anruf erhält, klingelt das Telefon der Telefonanlage und die Skype for Business-Clients des Benutzers alle gleichzeitig (wenn der Benutzer einen gleichzeitigen Ring eingerichtet hat). Der Benutzer kann den Anruf annehmen, indem er das PBX-Telefon auswählt oder in der Skype for Business-Benachrichtigung auf **annehmen** klickt. Wenn der Benutzer den Anruf über Skype for Business annimmt, bleibt das Skype for Business-Fenster für den Anruf geöffnet. Wenn der Benutzer aber den Anruf annimmt, indem er das PBX-Telefon auswählt, wird das Benachrichtigungsfenster von Skype for Business geschlossen, und es gibt keine Skype for Business-Sitzung, sondern nur den Sprachanruf über das PBX-Telefon.
  
Wenn ein für einen Anruf über Arbeit aktivierter Nutzer einen PBX-Anruf erhält, klingelt nur das Telefon der Telefonanlage.
  
## <a name="limitations-of-call-via-work"></a>Einschränkungen des Anrufs über die Arbeit

Call per Work ist eine Sprachlösung, die ein kleines Hardware-Setup erfordert, aber im Vergleich zu den Funktionen, die in der vollständigen Enterprise-VoIP-oder Remote-Anrufsteuerung zur Verfügung stehen. Bei Anrufen über Arbeit gelten die folgenden Einschränkungen:
  
- Wenn ein Anruf über den Arbeits Benutzer die Anrufweiterleitung für den Anruf über die geschäftliche Rückrufnummer eingerichtet hat und jemand versucht, diesen Nutzer über die Telefonnummer des Benutzers zu einer Besprechung einzuladen, wird die Einladung den Nutzer nicht erreichen. Informieren Sie Ihre Benutzer, dass Sie Teilnehmer zu Besprechungen einladen möchten, indem Sie auf den Namen und nicht auf die Telefonnummer klicken. 
    
- Die erweiterte 911-Funktion und die Nachverfolgung böswilliger Anrufe sind während eines Anrufs über geschäftliche Anrufe nicht verfügbar.
    
- Für Benutzer, die über Arbeit aktiviert sind, können die Features Delegation, Team Anruf oder Reaktionsgruppe nicht verwendet werden.
    
- Nutzer von Anrufen über die Arbeit können Skype for Business nicht verwenden, um eine Besprechung aufzuzeichnen, den Anruf stummzuschalten oder die Stummschaltung aufzuheben, den Anruf zu halten oder zu übertragen oder den Anruf Park zu verwenden.
    
- Benutzer können den Anruf nicht über work verwenden, um auf Ihre Telefonanlagen-Voicemail-Nachrichten zuzugreifen.
    
- Benutzer von Anrufen über die Arbeit können keine Sitzung eskalieren, die als Sprachanruf zu einer kollaborativen Besprechung gestartet wurde, die Kommunikation wie Video, PowerPoint, Whiteboard oder eine Notiz umfasst.
    
- Benutzer von Anrufen über Arbeit können einem zwei-Personen-Anruf keine weiteren Benutzer hinzufügen.
    
- Keine Unterstützung für Deskphone-Kopplung oder VDI-Plug-in-Kopplung.
    
- Wenn ein Benutzer einen Anruf über das PBX-Telefon (und nicht über das Skype for Business-Fenster) tätigt oder annimmt, wird kein Protokoll des Anrufs angezeigt.
    
- Wenn Ihr PBX-System das **verweisen mit ersetzen**nicht unterstützt, wird das folgende Verhalten auftreten. Wenn der Benutzer während eines Anrufs über einen geschäftlichen Anruf den laufenden Anruf vom PBX-Telefon übertragen lässt, verschwindet das Anruffenster nicht mehr im Skype for Business-Fenster. Wenn der Benutzer dann das Anruffenster schließt, endet der Anruf zwischen dem Übergabeziel und dem übertragenden. 
    
## <a name="prerequisites-for-call-via-work"></a>Voraussetzungen für Anrufe über die Arbeit

Damit alle Benutzer den Anruf über die Arbeit tätigen können, müssen Sie über einige Voraussetzungen verfügen. Weitere Informationen zu diesen Voraussetzungen sowie Schritte zum Aktivieren von Benutzern für den Anruf über Arbeit finden Sie unter [Bereitstellen von Anrufen über die Arbeit in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Siehe auch

[Planen der Remoteanrufsteuerung in Skype for Business](remote-call-control.md)
  
[Bereitstellen der Funktion „Anruf über Arbeit“ in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

