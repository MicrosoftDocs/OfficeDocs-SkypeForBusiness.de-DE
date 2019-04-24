---
title: Aktivieren Sie oder deaktivieren Sie Offline Sofortnachrichten (IM) in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Informationen Sie zum Aktivieren oder deaktivieren Offline Instant Messaging (IM) in Skype für Business Server.
ms.openlocfilehash: 29342f3903e58f90ab4d2a939be6cd20d3f8e31b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217663"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie Offline Sofortnachrichten (IM) in Skype für Business Server
 
Informationen Sie zum Aktivieren oder deaktivieren Offline Instant Messaging (IM) in Skype für Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren von Offline Sofortnachrichten (IM) in Skype für Business Server

Offline-Sofortnachrichten ist ein Client Side-Feature in Skype für Business-Client integriert (2016 C2R build 16.0.6701.1000 oder höher), die Exchange-Webdienste (EWS) zum Senden von Nachrichten aus der Skype für Business-Client mit Exchange-Postfach eines Benutzers nutzt. Offline-Sofortnachrichten verwendet Exchange-Webdienste (EWS) Offline Nachrichten an das Postfach des Empfängers aus der Skype für Business-Client zu senden. EWS müssen die Skype für Business-Client für Offline-Nachrichten gesendet werden zur Verfügung stehen. Weitere Informationen zum Planen von instant messaging und Anwesenheit, finden Sie unter [Planen von instant messaging und Anwesenheit in Skype für Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Wenn das Postfach des Benutzers in Exchange lokal gehostet wird, ist die Skype für Business-Client (2016 C2R build 16.0.6920.1000) erforderlich 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>So aktivieren oder deaktivieren Offline Sofortnachrichten in Skype für Business Server

1. Öffnen Sie die Skype für Business Server-Verwaltungsshell.
    
2. Führen Sie den folgenden Befehl aus, um Offline-Sofortnachrichten zu aktivieren.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype für Business Server 2015 CU3 ist die Option EnableOfflineIM standardmäßig auf $True gesetzt. Wenn Sie die Möglichkeit deaktivieren möchten, legen Sie den Wert auf „$False“ fest. 
  
3. Führen Sie den folgenden Befehl aus, um zu bestätigen, dass die Möglichkeit zum Speichern von Offline Instant Messaging gesetzt ist.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integration von Offline-Sofortnachrichten in Exchange

Offline-Sofortnachrichten sind nicht für Absender verfügbar, für die eine Clientrichtlinie das automatische Speichern von Offlinenachrichten im Ordner „Aufgezeichnete Unterhaltungen“ deaktiviert („EnableIMAutoArchiving = $false“). Es gibt keine Methode, mit der Sie überprüfen können, ob der Empfänger Offlinenachrichten empfangen kann.
  
Für Offline innerhalb derselben Organisation gesendeten Nachrichten werden sie als e-Mail-Nachricht mit der Nachrichtenklasse des Sofortnachrichten empfangen. Note.MissedConversation und wird in Outlook **Entgangene Unterhaltung** Ordner als auch Unterhaltungen, die in der Registerkarte Verlauf zuletzt Liste-Unterhaltung in Skype für Business Clients bearbeitet wird, hängt enthalten sein.
  

 Offlinenachrichten, die von einer Partnerorganisation gesendet werden, werden als E-Mail-Nachricht ohne „IM.Note.MissedConversation“ empfangen. Sie werden nicht in den Ordnern für verpasste Unterhaltungen oder aufgezeichnete Unterhaltungen gespeichert.  
  
## <a name="troubleshooting"></a>Problembehandlung

Es wird ein Timer zwei Minuten aus, wenn eine offline-Nachricht an gesendet wird, wenn es aufgenommene und verarbeitet wurde. Wenn offline Nachrichten nicht verarbeitet werden können, werden sie in das folgende Verzeichnis angezeigt: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Die primäre Skype für Business ETL-Protokoll enthält Informationen zur Verarbeitung von Offline-Nachricht und Ihre besten Untersuchung/bei der Problembehandlung. 
  
> [!NOTE]
> Es wurde ein Problem gemeldet, bei dem Offlinenachrichten nicht gewendet wurden und der Ordner „Entwürfe“ sich mit Nachrichten füllte. Das Problem trat bei Postfächern in der lokalen Exchange-Version auf. Seit dem 14.06.2016 ist das Problem in allen C2R-Kanälen behoben.   
