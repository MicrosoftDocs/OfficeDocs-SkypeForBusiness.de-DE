---
title: Planen von Beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Erfahren Sie mehr über die Beschäftigt-Optionen-Funktion in Skype for Business Server.
ms.openlocfilehash: d47b31c53b5357a520f6aa0b3a6c0a02c18df8f2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756542"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planen von Beschäftigt-Optionen für Skype for Business Server
 
Erfahren Sie mehr über die Beschäftigt-Optionen-Funktion in Skype for Business Server.
  
Beschäftigt-Optionen ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit der Sie konfigurieren können, wie eingehende Anrufe verarbeitet werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf gehalten wird. Neue oder eingehende Anrufe können mit einem Besetzt-Signal abgelehnt oder an Voicemail weitergeleitet werden. 
  
Die Beschäftigt-Optionen-Richtlinie wird für Failover und Notfallwiederherstellung in gekoppelten Front-End-Pools und Survivable Branch Servers (SBS) unterstützt.
  
In diesem Thema werden die Features von Beschäftigt-Optionen beschrieben. Informationen zum Installieren und Konfigurieren von Beschäftigt-Optionen finden Sie unter Installieren und Konfigurieren von [Beschäftigt-Optionen für Skype for Business Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)
  
## <a name="configuration-options"></a>Konfigurationsoptionen

Wenn beschäftigt-Optionen für die Organisation aktiviert ist, können alle Benutzer in Ihrer Organisation, sowohl Enterprise-VoIP als auch Nicht-Enterprise-VoIP Benutzer, die folgenden Features verwenden:
  
- Beschäftigt bei Beschäftigt – In dem neue eingehende Anrufe mit einem Besetzt-Signal abgelehnt werden, wenn der Benutzer ausgelastet ist.
    
- Voicemail bei Beschäftigt – In dem neue eingehende Anrufe an Voicemail weitergeleitet werden, wenn der Benutzer ausgelastet ist.
    
Das Feature Beschäftigt-Optionen bietet Failoverfunktionen. Wenn ein Problem auftritt und Benutzer zu einem anderen Front-End-Server oder zu einem anderen Pool in Skype for Business Server wechseln, bleiben die Beschäftigt-Optionen-Einstellungen erhalten.
  
Unabhängig davon, wie ihre Beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder personen mit einer Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren. 
  
Nach der Konfiguration ist die Beschäftigt-Optionen-Einstellung für alle Skype for Business Anrufgeräte und Clients des Benutzers wirksam. Basierend auf den Beschäftigt-Optionen-Einstellungen des Benutzers würde der Anruf, der abgelehnt oder an Voicemail gesendet wird, auf keinem der Anrufgeräte des Benutzers – einschließlich Macintosh, Windows Desktop, mobile Clients oder IP-Telefone – klingeln, auf denen der Benutzer angemeldet ist. 
  
Benutzern werden Benachrichtigungen über verpasste Anrufe auf ihren Skype for Business Clients und Geräten angezeigt, und sie werden auch per E-Mail benachrichtigt. Anrufer, deren Anruf aufgrund von Beschäftigt bei Gebucht abgelehnt wurde, sehen eine Benachrichtigung in ihrem Skype for Business Client, die besagt, dass der Benutzer, den sie zu erreichen versucht haben, bei einem anderen Anruf ausgelastet ist.
  
Sie können das Feature Beschäftigt-Optionen konfigurieren, indem Sie Skype for Business PowerShell-Cmdlets für Folgendes verwenden:
  
- Aktivieren oder deaktivieren Sie die VoIP-Richtlinie für Beschäftigt-Optionen für die Enterprise.
    
- Verwalten von "Beschäftigt bei Gebucht" oder "Voicemail bei Gebucht" für alle Benutzer im Enterprise.
    
- Verwalten von Beschäftigt bei Gebucht oder Voicemail bei Gebucht für alle Benutzer, die in einem bestimmten Front-End-Pool verwaltet werden.
    
- Verwalten von "Beschäftigt bei Gebucht" oder "Voicemail bei Gebucht" für eine Liste von Benutzern.
    
- Verwalten von "Beschäftigt bei Gebucht" oder "Voicemail bei Gebucht" für einen einzelnen Benutzer.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilität mit VoIP-Anwendungen

Beschäftigt-Optionen bieten Interoperabilität mit den folgenden VoIP-Anwendungen in Skype for Business:
  
- Reaktionsgruppen (Response Groups, RGS)
    
  - Beschäftigt-Optionen, die für Reaktionsgruppennummern festgelegt sind, werden vom System ignoriert. Mehrere gleichzeitige Anrufe sind zulässig. 
    
  - Die aktuelle Telefonzentralenrouting-Erfahrung in Reaktionsgruppen bleibt für die Agents mit Beschäftigt-Optionen unverändert.
    
  - Die Anrufe von Reaktionsgruppen an die Benutzer, die Reaktionsgruppen-Agents sind, werden nicht durch die Beschäftigt-Optionen-Einstellungen gedrosselt, und die aktuelle RGS-Erfahrung wird beibehalten.
    
  - Die Nicht-RGS-bezogenen Anrufe an die Agents werden durch ihre Beschäftigt-Optionen-Einstellungen berücksichtigt.
    
- Teamanruf
    
  - Eingehende Anrufe an Benutzer, die für einen Teamanruf eingerichtet sind, werden priorisiert, um die Einstellungen "Beschäftigt bei Beschäftigt" und "Voicemail bei Gebucht" zu ignorieren.
    
  - Die aktuelle Teamanruferfahrung bleibt unverändert, wobei beschäftigt-Optionen für die Benutzer festgelegt sind.
    
  - Die Nicht-Teamanruf-bezogenen Anrufe an solche Benutzer werden durch ihre Beschäftigt-Optionen-Einstellungen berücksichtigt.
    
- Delegation von Administratoren/Administratoren 
    
  - Eingehende Anrufe an Benutzer, die für eine Delegation von Administratoren oder Administratoren eingerichtet sind, werden priorisiert, um die Einstellungen "Beschäftigt bei Beschäftigt" und "Voicemail bei Gebucht" zu ignorieren.
    
  - Die aktuelle Erfahrung mit der Delegation von Administratoren/Administratoren bleibt unverändert, wenn beschäftigt-Optionen für die Administratoren oder Dener festgelegt sind.
    
  - Die Nicht-Administratoren-/Administratordelegierungsbezogenen Anrufe an Administratoren werden durch ihre Beschäftigt-Optionen berücksichtigt.
    
- Darstellung der "Gemeinsame Leitungen" 
    
  - Die Beschäftigt-Optionen-Einstellungen für Benutzerkonten, die für die Gemeinsame Leitungen-Darstellung eingerichtet sind, werden ignoriert. 
    
  - Stattdessen werden die nativen Optionen "Besetzt bei Beschäftigt" und "Voicemail bei Gebucht" der Shared Line Appearance berücksichtigt.
    
- Anrufparkdienst 
    
  - Geparkte Anrufe, die nicht abgerufen wurden und aufgrund eines Timeouts zurückgerufen werden, dürfen jedoch an den Benutzer klingeln, der den Anruf über die Beschäftigt-Optionen geparkt hat. 
    
- Anrufkonferenzen
    
  - Benutzer in Konferenzanrufen gelten als beschäftigt, und neue eingehende Anrufe werden mit einem Besetzt-Signal abgelehnt oder gemäß ihren Beschäftigt-Optionen-Einstellungen an Voicemail weitergeleitet.
    
  - Benutzer in Konferenzen werden nicht daran gehindert, neue Anrufe oder Konferenzen über Beschäftigt-Optionen zu initiieren.
    
  - Benutzer in Konferenzen können weiterhin neue Konferenzseinladungen empfangen, neue Peer-to-Peer-Anrufe werden jedoch gemäß ihren Beschäftigt-Optionen-Einstellungen abgelehnt.
    
- Gleichzeitiges Klingeln und Anrufweiterleitung
    
    Die Beschäftigt-bei-Gebucht-Funktion ist nicht für das Arbeiten mit gleichzeitigen Anrufen und Anrufweiterleitung ausgelegt.
    

