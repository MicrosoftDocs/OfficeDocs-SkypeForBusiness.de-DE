---
title: Clientversionsregel
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.
ms.openlocfilehash: 88316487ccd6f061127f92a762ac2d8c17b6a9c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-rule"></a>Clientversionsregel
 
Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen neuer Regeln zu einer Clientversionsrichtlinie
    
- Ändern der Regeln, aus denen eine vorhandene Clientversionsrichtlinie besteht
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Benutzer-agent** Sie können einen Clienttyp aus der Liste auswählen. In der folgenden Tabelle sind die Codes der Benutzer-Agents definiert.
    
|**Clientname**|**Benutzer-Agent**|
|:-----|:-----|
|Lync 2013, Lync 2010, Officecommunicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Office Communicator Phone Lync Phone Edition  <br/> |OCPhone  <br/> |
|Communicator Phone Edition-Plattform  <br/> |CPE  <br/> |
|Unified Communications-Plattform  <br/> |UCCP  <br/> |
|Lync 2010-Teilnehmer  <br/> |AOC  <br/> |
|Live Meeting-Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client für Real-Time Communications  <br/> |RTC  <br/> |
|Lync 2010 für iPad  <br/> |iPadLync  <br/> |
|Lync 2010 für iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 für Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 für Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 für Android  <br/> |AndroidLync  <br/> |
|Mobilitätsdienst  <br/> |McxService  <br/> |
   
- **Versionsnummer** Sie können die Versionsnummern für die folgenden Felder angeben oder Platzhalter verwenden, um die clientversionsnummer anzugeben.
    
  - **Hauptversion** Gibt die Nummer, die der Hauptversion des Clients entspricht.
    
  - **Nebenversion** Gibt die Nummer, die der Nebenversion des Clients entspricht.
    
  - **Erstellen** Gibt die Buildnummer an, die der Haupt- und Nebenversion des Clients entspricht.
    
  - **Update** Gibt die Nummer, die der aktualisierten Version des Clients entspricht.
    
- **Vergleichsvorgang** Sie können den Vergleichsvorgang für die Clientversion angeben, die Sie in den vorherigen Schritten angegeben. Die folgenden Vorgänge sind verfügbar:
    
  - **Identisch mit**
    
  - **Ist nicht**
    
  - **Neuer als**
    
  - **Neuer als oder identisch mit**
    
  - **Älter als**
    
  - **Älter als oder identisch mit**
    
- **Aktion** Sie können angeben, dass die Aktion ausführen, wenn die Kriterien in den vorherigen Schritten erfüllt sind. Die folgenden Aktionen sind verfügbar:
    
  - **Zulassen** Ermöglicht dem Client anmelden.
    
  - **Zulassen und Upgrade** Ermöglicht dem Client anmelden und Updates von Windows Server Update Service oder Microsoft Update zu erhalten. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.
    
    > [!NOTE]
    > Wählen diese Aktion bewirkt, dass eine Benachrichtigung der Benutzer das nächste Mal Skype für Unternehmen anmelden angezeigt werden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden. 
  
  - **Mit URL zulassen** Erlaubt die Anmeldung des Clients und zeigt eine Meldung an, wo Sie ein anderes Clientversion herunterladen. Sie geben die URL im Feld **URL** an.
    
  - **Blockieren** Verhindert die Anmeldung des Clients.
    
  - **Blockieren und Upgrade** Verhindert die Clientanmeldung auf und ermöglicht den Client die Updates von Windows Server Update Service oder Microsoft Update zu erhalten. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.
    
  - **Mit URL blockieren**   Verhindert die Anmeldung des Clients und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL im Feld **URL** an.
    
Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von clientversionskonfigurationen finden Sie unter [Ändern der Standardaktion für Clients nicht explizit unterstützt oder eingeschränkt](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in der Betriebsdokumentation.

