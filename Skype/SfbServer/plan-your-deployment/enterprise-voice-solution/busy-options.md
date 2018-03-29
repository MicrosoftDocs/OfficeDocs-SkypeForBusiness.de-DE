---
title: Planen der Beschäftigt-Optionen für Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Informieren Sie sich über das Feature beschäftigt Optionen in Skype für Business Server 2015.
ms.openlocfilehash: ed04ae8709215d8b247672f789e84ea2be64949d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planen der Beschäftigt-Optionen für Skype for Business Server
 
Informieren Sie sich über das Feature beschäftigt Optionen in Skype für Business Server 2015.
  
Wird eine neue VoIP-Richtlinie eingeführt beschäftigt Optionen in der Juli 2016 kumulative Update, mit dem Sie zum Konfigurieren eingehender Anrufe verarbeitet werden, wenn ein Benutzer ist bereits in einem Anruf oder einer Konferenz oder ein Anruf in die Warteschleife gestellt. Neue oder eingehende Anrufe können mit einem Besetztzeichen abgelehnt oder an die Voicemail weitergeleitet werden. 
  
Die Richtlinie für Beschäftigt-Optionen wird für Failover- und Notfallwiederherstellung in gepaarten Front-End-Pools und Survivable Branch Servers (SBS) unterstützt.
  
In diesem Thema werden die Funktionen der Beschäftigt-Optionen beschrieben. Informationen zum Installieren und Konfigurieren von Optionen für beschäftigt finden Sie unter [Installieren und Konfigurieren von beschäftigt Optionen für Skype für Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Konfigurationsoptionen

Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer der Organisation (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Funktionen verwenden:
  
- Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.
    
- Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.
    
Die Beschäftigt-Optionen stellen Failover-Möglichkeiten bereit. Wenn ein Problem auftritt, und Benutzer ein Failover auf einen anderen Front-End-Server oder in einen anderen Pool in Skype für Business Server, werden deren beschäftigt Optionen Einstellungen beibehalten.
  
Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.   
  
Nach der Konfiguration ist die Einstellung beschäftigt Optionen für Skype für Business Anruf Geräte und Clients des Benutzers aktiviert. Auf der Grundlage der festgelegten Beschäftigt-Optionen des Benutzers ertönt bei Ablehnung oder Senden an Voicemail des Anrufs kein Klingelton auf den Anrufgeräten – einschließlich Macintosh, Windows Desktop, Mobilclients oder IP-Telefonen –, bei denen der Benutzer angemeldet ist. 
  
Die Benutzer sehen Benachrichtigungen über verpasste Anrufe auf ihren Skype für Business-Clients und Geräten, und Benutzer werden informiert per e-Mail sowie. Anrufer, dessen Aufruf aufgrund beschäftigt auf beschäftigt abgelehnt wurde, sieht eine Benachrichtigung in ihren Skype für Business-Client, die besagt, dass der Benutzer, den sie verwenden wollten, klicken Sie auf einen weiteren Anruf ausgelastet ist.
  
Sie können das Feature beschäftigt Optionen mithilfe von Skype für Business-PowerShell-Cmdlets zu konfigurieren:
  
- VoIP-Richtlinie der Beschäftigt-Optionen für das Unternehmen aktivieren oder deaktivieren.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für alle Benutzer im Unternehmen verwalten.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für alle Benutzer in einem bestimmten Front-End-Pool verwalten.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für eine Liste von Benutzern verwalten.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für einen einzelnen Benutzer verwalten.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilität mit VoIP-Anwendungen

Ausgelastet Optionen bietet Interoperabilität mit den folgenden VoIP-Anwendungen in Skype für Unternehmen:
  
- Reaktionsgruppen
    
  - Für Reaktionsgruppennummern festgelegte Beschäftigt-Optionen werden vom System ignoriert; mehrere gleichzeitige Anrufe sind zulässig.  
    
  - Die derzeitige Telefonzentralen-Weiterleitung in Reaktionsgruppen bleibt für die Agenten mit festgelegten Beschäftigt-Optionen unverändert.
    
  - Die von Reaktionsgruppen an die Benutzer, die Reaktionsgruppenagenten sind, eingehenden Anrufe werden nicht durch die festgelegten Beschäftigt-Optionen gedrosselt, und die derzeitige Reaktionsgruppenerfahrung bleibt beibehalten.
    
  - Nicht mit Reaktionsgruppen zusammenhängende Anrufe an Agenten werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.
    
- Teamanruf
    
  - Eingehende Anrufe für Benutzer, die für einen Teamanruf eingerichtet sind, werden priorisiert werden, um auf beschäftigt beschäftigt und Voicemail auf beschäftigt Einstellungen ignoriert.
    
  - Die derzeitige Teamanruferfahrung bleibt unverändert, wenn Beschäftigt-Optionen für die Benutzer festgelegt sind.
    
  - Nicht mit Teamanrufen zusammenhängende Anrufe diese Benutzer werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.
    
- Delegierung für Chef/Verwaltung  
    
  - Eingehende Anrufe für Benutzer, die für eine Vorgesetztenverwaltung/Delegierung entweder als Vorgesetzten oder ein Administrator eingerichtet sind Prioritäten zugewiesen beschäftigt auf beschäftigt und Voicemail auf beschäftigt Einstellungen ignoriert.
    
  - Die derzeitige Erfahrung bei Delegierung für Chef/Verwaltung bleibt unverändert, wenn Beschäftigt-Optionen für die Administratoren oder Chefs festgelegt sind.
    
  - Nicht mit der Delegierung für Chefs/Verwaltung zusammenhängende Anrufe dieser Benutzer werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.
    
- Funktion „Gemeinsame Leitungen“    
    
  - Festgelegte Beschäftigt-Optionen für Benutzerkonten, die mit der Funktion „Gemeinsame Leitungen“ eingerichtet sind, werden ignoriert.  
    
  - Freigegebene Zeile Darstellung systemeigene beschäftigt auf beschäftigt und Voicemail zu stark ausgelastet Optionen werden stattdessen erfüllt.
    
- Anrufparkdienst  
    
  - Geparkte Anrufe, die wegen einer Zeitüberschreitung nicht abgerufen wurden und zurückrufen, können anhand der Beschäftigt-Optionen an den Benutzer durchgestellt werden, der den Anruf geparkt hat.  
    
- Telefonkonferenzen
    
  - Benutzer, die sich in Telefonkonferenzen befinden, gelten als beschäftigt, und neue eingehende Anrufe werden je nach den festgelegten Beschäftigt-Optionen mit einem Besetztzeichen abgelehnt oder an Voicemail weitergeleitet.
    
  - Durch die Beschäftigt-Optionen wird aber nicht verhindert, dass Benutzer in Telefonkonferenzen neue Anrufe oder Konferenzen beginnen.
    
  - Benutzer in Konferenzen können neue Konferenzeinladungen erhalten, Peer-zu-Peer-Anrufe werden jedoch entsprechend ihren festgelegten Beschäftigt-Optionen abgelehnt.
    
- Paralleles Anrufen und Anrufweiterleitung
    
    Die „Besetzt wenn beschäftigt“-Funktion kann nicht gemeinsam mit „Paralleles Anrufen“ und „Anrufweiterleitung“ genutzt werden.
    

