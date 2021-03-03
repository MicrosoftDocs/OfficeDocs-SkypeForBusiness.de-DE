---
title: Planen von Gebucht-Optionen für Skype for Business Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Erfahren Sie mehr über das Feature "Besetzt-Optionen" in Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813695"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planen von Gebucht-Optionen für Skype for Business Server
 
Erfahren Sie mehr über das Feature "Besetzt-Optionen" in Skype for Business Server.
  
Bei den Besetztoptionen handelt es sich um eine neue, im kumulativen Update vom Juli 2016 eingeführte Sprachrichtlinie, mit der Sie konfigurieren können, wie eingehende Anrufe behandelt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in der Warteschleife platziert wurde. Neue oder eingehende Anrufe können mit einem Besetztzeichen abgelehnt oder an Voicemail weitergeleitet werden. 
  
Die Richtlinie "Besetzt-Optionen" wird für Failover und Notfallwiederherstellung auf gekoppelten Front-End-Pools und Survivable Branch Servers (SBS) unterstützt.
  
In diesem Thema werden die Features von "Beschäftigt"-Optionen beschrieben. Informationen zum Installieren und Konfigurieren von Besetzt-Optionen finden Sie unter "Installieren und Konfigurieren von [Beschäftigt-Optionen für Skype for Business Server".](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)
  
## <a name="configuration-options"></a>Konfigurationsoptionen

Wenn die Gebucht-Optionen für die Organisation aktiviert sind, können alle Benutzer in Ihrer Organisation, sowohl Enterprise-VoIP als auch Benutzer ohne Enterprise-VoIP, die folgenden Features verwenden:
  
- Beschäftigt bei Gebucht: Neue eingehende Anrufe werden mit einem Besetztzeichen zurückgewiesen, wenn der Benutzer ausgelastet ist.
    
- Voicemail bei Gebucht- Dabei werden neue eingehende Anrufe an Voicemail weitergeleitet, wenn der Benutzer ausgelastet ist.
    
Das Feature "Besetzt-Optionen" bietet Failoverfunktionen. Wenn ein Problem auftritt und Benutzer ein Failover zu einem anderen Front-End-Server oder zu einem anderen Pool in Skype for Business Server vornehmen, bleiben die Einstellungen für die Besetzt-Optionen erhalten.
  
Unabhängig davon, wie die Gebucht-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder Benutzer mit einem Anruf in der Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. 
  
Nach der Konfiguration ist die Einstellung "Besetzt-Optionen" für alle Skype for Business-Anrufgeräte und -Clients des Benutzers wirksam. Basierend auf den Einstellungen für die Besetzt-Optionen des Benutzers klingelt der Anruf, der abgelehnt oder an Voicemail gesendet wird, nicht auf den Anrufgeräten des Benutzers , einschließlich Macintosh, Windows Desktop, mobilen Clients oder IP-Telefonen, auf denen der Benutzer angemeldet ist. 
  
Benutzern werden Benachrichtigungen über verpasste Anrufe auf ihren Skype for Business-Clients und -Geräten angezeigt, und sie werden ebenfalls per E-Mail benachrichtigt. Anrufern, deren Anruf aufgrund von "Besetzt bei Gebucht" abgelehnt wurde, wird auf ihrem Skype for Business-Client eine Benachrichtigung angezeigt, dass der Benutzer, den sie erreichen wollten, bei einem anderen Anruf beschäftigt ist.
  
Sie können das Feature "Besetzt-Optionen" konfigurieren, indem Sie Skype for Business -PowerShell-Cmdlets verwenden, um:
  
- Aktivieren oder deaktivieren Sie die Besetzt-Optionen-Voice-Richtlinie für das Unternehmen.
    
- Verwalten von "Beschäftigt bei Beschäftigt" oder "Voicemail bei Gebucht" für alle Benutzer im Unternehmen.
    
- Verwalten von "Besetzt bei Beschäftigt" oder "Voicemail bei Gebucht" für alle Benutzer, die in einem bestimmten Front-End-Pool verwaltet werden.
    
- Verwalten von "Beschäftigt bei Beschäftigt" oder "Voicemail bei Gebucht" für eine Liste von Benutzern.
    
- Verwalten von "Besetzt bei Beschäftigt" oder "Voicemail bei Beschäftigt" für einen einzelnen Benutzer.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilität mit Sprachanwendungen

Die Besetzt-Optionen bieten Interoperabilität mit den folgenden Sprachanwendungen in Skype for Business:
  
- Reaktionsgruppen (Response Groups, RGS)
    
  - Für Reaktionsgruppesnummern festgelegte #A0 werden vom System ignoriert. Mehrere gleichzeitige Anrufe sind zulässig. 
    
  - Die aktuelle Routingerfahrung der Attendant in Reaktionsgruppen bleibt für agents with Busy Options settings unverändert.
    
  - Die Anrufe von Reaktionsgruppen an die Benutzer, die Reaktionsgruppenagenten sind, werden nicht durch die Einstellungen für die Besetzt-Optionen gedrosselt, und die aktuelle RGS-Erfahrung wird beibehalten.
    
  - Die Nicht-RGS-bezogenen Anrufe an die Agents werden durch ihre Einstellungen für die Besetzt-Optionen berücksichtigt.
    
- Teamanruf
    
  - Eingehende Anrufe an Benutzer, die für einen Teamanruf eingerichtet sind, werden so priorisiert, dass "Beschäftigt bei Beschäftigt" und "Voicemail bei Gebucht" ignoriert werden.
    
  - Die aktuelle Teamanruferfahrung bleibt unverändert, wenn die Besetzt-Optionen für die Benutzer festgelegt sind.
    
  - Die Nicht-Teamanruf-bezogenen Anrufe an solche Benutzer werden durch ihre Einstellungen für die Besetzt-Optionen berücksichtigt.
    
- Chef/Administratordelegierung 
    
  - Eingehende Anrufe an Benutzer, die für eine Chef-/Administratordelegierung entweder als Chef oder Administrator eingerichtet sind, werden priorisiert, um die Einstellungen "Beschäftigt bei Beschäftigt" und "Voicemail bei Gebucht" zu ignorieren.
    
  - Die aktuelle Besendungserfahrung von Chef/Administrator bleibt unverändert bei den für Administratoren oder Chef festgelegten Gebucht-Optionen.
    
  - Die Nicht-Chef/Admin-Delegierung bezogenen Anrufe an Administratoren werden durch ihre Einstellungen für die Besetzt-Optionen berücksichtigt.
    
- Darstellung der "Gemeinsame Leitungen" 
    
  - Die Einstellungen für die Gebucht-Optionen für Benutzerkonten, die für die Darstellung freigegebener Zeilen eingerichtet wurden, werden ignoriert. 
    
  - Stattdessen werden die systemeigenen Optionen "Beschäftigt bei Beschäftigt" und "Voicemail bei Gebucht" bei der Erscheinungsbild der gemeinsamen Leitung berücksichtigt.
    
- Anrufparkdienst 
    
  - Geparkte Anrufe, die nicht abgerufen wurden und aufgrund eines Timeouts zurück läuten, dürfen beim Benutzer klingeln, der den Anruf über die Besetzt-Optionen geparkt hat. 
    
- Anrufkonferenzen
    
  - Benutzer in Konferenzanrufen werden als beschäftigt betrachtet, und neue eingehende Anrufe werden mit einem Besetztzeichen zurückgewiesen oder gemäß ihren Einstellungen für die Besetztoptionen an Voicemail weitergeleitet.
    
  - Benutzer in Konferenzen werden nicht daran gehindert, neue Anrufe oder Konferenzen über die Besetzt-Optionen zu initiieren.
    
  - Benutzer in Konferenzen können weiterhin neue Konferenzeinladungen empfangen, neue Peer-zu-Peer-Anrufe werden jedoch entsprechend ihren Einstellungen für die Besetzt-/Gebucht-Optionen abgelehnt.
    
- Gleichzeitiges Klingeln und Anruf weiterleiten
    
    Die Funktion "Besetzt bei Gebucht" ist nicht für die Gleichzeitige Anrufanruf- und Anrufanruffunktion ausgelegt.
    

