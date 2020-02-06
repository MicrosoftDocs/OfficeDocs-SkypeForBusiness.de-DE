---
title: Planen der Beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Informieren Sie sich über das Feature "beschäftigte Optionen" in Skype for Business Server.
ms.openlocfilehash: cf9ee9dbb3785804b1bb63f4118a29d29cf7715c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803245"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planen der Beschäftigt-Optionen für Skype for Business Server
 
Informieren Sie sich über das Feature "beschäftigte Optionen" in Skype for Business Server.
  
"Busy Options" ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit dem Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder wenn ein Anruf in Wartestellung gesetzt wurde. Neue oder eingehende Anrufe können mit einem Busy-Signal zurückgewiesen oder an die Voicemail weitergeleitet werden. 
  
Die Richtlinie für Beschäftigt-Optionen wird für Failover- und Notfallwiederherstellung in gepaarten Front-End-Pools und Survivable Branch Servers (SBS) unterstützt.
  
In diesem Thema werden die Funktionen der Beschäftigt-Optionen beschrieben. Weitere Informationen zum Installieren und Konfigurieren der Beschäftigt-Optionen finden Sie unter [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Konfigurationsoptionen

Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer der Organisation (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Funktionen verwenden:
  
- Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.
    
- Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.
    
Die Beschäftigt-Optionen stellen Failover-Möglichkeiten bereit. Wenn ein Problem auftritt und Benutzer einen Failover zu einem anderen Front-End-Server oder zu einem anderen Pool in Skype for Business Server durchführen, bleiben die Einstellungen für die busy-Optionen erhalten.
  
Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.   
  
Nach der Konfiguration ist die Einstellung "busy Options" für alle Skype for Business-Anruf Geräte und-Clients des Benutzers gültig. Auf der Grundlage der festgelegten Beschäftigt-Optionen des Benutzers ertönt bei Ablehnung oder Senden an Voicemail des Anrufs kein Klingelton auf den Anrufgeräten – einschließlich Macintosh, Windows Desktop, Mobilclients oder IP-Telefonen –, bei denen der Benutzer angemeldet ist. 
  
Benutzern werden Benachrichtigungen über verpasste Anrufe auf Ihren Skype for Business-Clients und-Geräten angezeigt, und Sie werden ebenfalls per e-Mail benachrichtigt. Anrufern, deren Anruf wegen busy on Busy abgelehnt wurde, wird in Ihrem Skype for Business-Client eine Benachrichtigung angezeigt, die besagt, dass der Nutzer, den Sie erreichen wollten, bei einem anderen Anruf beschäftigt ist.
  
Sie können das Feature "busy-Optionen" mithilfe von Skype for Business PowerShell-Cmdlets konfigurieren, um Folgendes zu tun:
  
- VoIP-Richtlinie der Beschäftigt-Optionen für das Unternehmen aktivieren oder deaktivieren.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für alle Benutzer im Unternehmen verwalten.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für alle Benutzer in einem bestimmten Front-End-Pool verwalten.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für eine Liste von Benutzern verwalten.
    
- „Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für einen einzelnen Benutzer verwalten.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilität mit VoIP-Anwendungen

Busy-Optionen bieten Interoperabilität mit den folgenden Sprachanwendungen in Skype for Business:
  
- Reaktionsgruppen
    
  - Für Reaktionsgruppennummern festgelegte Beschäftigt-Optionen werden vom System ignoriert; mehrere gleichzeitige Anrufe sind zulässig.  
    
  - Die derzeitige Telefonzentralen-Weiterleitung in Reaktionsgruppen bleibt für die Agenten mit festgelegten Beschäftigt-Optionen unverändert.
    
  - Die von Reaktionsgruppen an die Benutzer, die Reaktionsgruppenagenten sind, eingehenden Anrufe werden nicht durch die festgelegten Beschäftigt-Optionen gedrosselt, und die derzeitige Reaktionsgruppenerfahrung bleibt beibehalten.
    
  - Nicht mit Reaktionsgruppen zusammenhängende Anrufe an Agenten werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.
    
- Teamanruf
    
  - Eingehende Anrufe an Benutzer, die für einen Teamanruf eingerichtet sind, werden priorisiert, um busy für busy und Voicemail auf busy-Einstellungen zu ignorieren.
    
  - Die derzeitige Teamanruferfahrung bleibt unverändert, wenn Beschäftigt-Optionen für die Benutzer festgelegt sind.
    
  - Nicht mit Teamanrufen zusammenhängende Anrufe diese Benutzer werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.
    
- Delegierung für Chef/Verwaltung  
    
  - Eingehende Anrufe an Benutzer, die für eine Boss/Administrator-Delegierung entweder als Boss oder als Administrator eingerichtet sind, werden priorisiert, wenn busy und Voicemail auf busy-Einstellungen ignoriert werden.
    
  - Die derzeitige Erfahrung bei Delegierung für Chef/Verwaltung bleibt unverändert, wenn Beschäftigt-Optionen für die Administratoren oder Chefs festgelegt sind.
    
  - Nicht mit der Delegierung für Chefs/Verwaltung zusammenhängende Anrufe dieser Benutzer werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.
    
- Funktion „Gemeinsame Leitungen“    
    
  - Festgelegte Beschäftigt-Optionen für Benutzerkonten, die mit der Funktion „Gemeinsame Leitungen“ eingerichtet sind, werden ignoriert.  
    
  - Die Darstellung der freigegebenen Zeile für "beschäftigt" und "Voicemail" auf "busy"-Optionen wird stattdessen berücksichtigt.
    
- Anrufparkdienst  
    
  - Geparkte Anrufe, die wegen einer Zeitüberschreitung nicht abgerufen wurden und zurückrufen, können anhand der Beschäftigt-Optionen an den Benutzer durchgestellt werden, der den Anruf geparkt hat.  
    
- Telefonkonferenzen
    
  - Benutzer, die sich in Telefonkonferenzen befinden, gelten als beschäftigt, und neue eingehende Anrufe werden je nach den festgelegten Beschäftigt-Optionen mit einem Besetztzeichen abgelehnt oder an Voicemail weitergeleitet.
    
  - Durch die Beschäftigt-Optionen wird aber nicht verhindert, dass Benutzer in Telefonkonferenzen neue Anrufe oder Konferenzen beginnen.
    
  - Benutzer in Konferenzen können neue Konferenzeinladungen erhalten, Peer-zu-Peer-Anrufe werden jedoch entsprechend ihren festgelegten Beschäftigt-Optionen abgelehnt.
    
- Paralleles Anrufen und Anrufweiterleitung
    
    Die „Besetzt wenn beschäftigt“-Funktion kann nicht gemeinsam mit „Paralleles Anrufen“ und „Anrufweiterleitung“ genutzt werden.
    

