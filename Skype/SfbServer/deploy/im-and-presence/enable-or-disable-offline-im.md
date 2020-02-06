---
title: Aktivieren oder Deaktivieren von Instant Messaging (im) für Offline-Chats in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Erfahren Sie, wie Sie offline-Sofortnachrichten (im) in Skype for Business Server aktivieren oder deaktivieren können.
ms.openlocfilehash: d96c7fc0de51cbdcfb6ba3acde3bf854c874f05b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795326"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Instant Messaging (im) für Offline-Chats in Skype for Business Server
 
Erfahren Sie, wie Sie offline-Sofortnachrichten (im) in Skype for Business Server aktivieren oder deaktivieren können.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Offline-Sofortnachrichten (im) in Skype for Business Server aktivieren

Offline-Chat ist eine clientseitige Funktion, die in den Skype for Business-Client (2016 C2R Build 16.0.6701.1000 oder höher) integriert ist und Exchange-Webdienste (EWS) nutzt, um Nachrichten aus dem Skype for Business-Client an das Exchange-Postfach eines Benutzers zu senden. Offline-Chat verwendet Exchange-Webdienste (EWS) zum Senden von Offline Nachrichten aus dem Skype for Business-Client an das Postfach des Empfängers. EWS muss für den Skype for Business-Client verfügbar sein, damit Offline-Nachrichten gesendet werden können. Weitere Informationen zur Planung von Sofortnachrichten und Anwesenheitsinformationen finden Sie unter [Planen von Sofortnachrichten und Anwesenheit in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Wenn das Postfach des Benutzers in Exchange lokal gehostet wird, ist der Skype for Business-Client (2016 C2R Build 16.0.6920.1000) erforderlich. 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>So aktivieren oder deaktivieren Sie die Offline-Chatfunktion in Skype for Business Server

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie den folgenden Befehl aus, um Offline-Sofortnachrichten zu aktivieren.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3 ist die Option EnableOfflineIM standardmäßig auf $true eingestellt. Wenn Sie die Möglichkeit deaktivieren möchten, legen Sie den Wert auf „$False“ fest. 
  
3. Führen Sie den folgenden Befehl aus, um zu bestätigen, dass die Möglichkeit zum Speichern von Offline Chats festgesetzt ist.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integration von Offline-Sofortnachrichten in Exchange

Offline-Sofortnachrichten sind nicht für Absender verfügbar, für die eine Clientrichtlinie das automatische Speichern von Offlinenachrichten im Ordner „Aufgezeichnete Unterhaltungen“ deaktiviert („EnableIMAutoArchiving = $false“). Es gibt keine Methode, mit der Sie überprüfen können, ob der Empfänger Offlinenachrichten empfangen kann.
  
Für Offline-Nachrichten, die innerhalb derselben Organisation gesendet werden, werden Sie als e-Mail-Nachricht mit der Nachrichtenklasse Chat empfangen. Hinweis. MissedConversation und wird im Outlook-Ordner " **verpasste Unterhaltungen** " sowie im Konversationsprotokoll enthalten sein, das in den Reitern "letzte Liste/Konversations Verlauf" in Skype for Business-Clients aufgenommen wird.
  

 Offlinenachrichten, die von einer Partnerorganisation gesendet werden, werden als E-Mail-Nachricht ohne „IM.Note.MissedConversation“ empfangen. Sie werden nicht in den Ordnern für verpasste Unterhaltungen oder aufgezeichnete Unterhaltungen gespeichert.  
  
## <a name="troubleshooting"></a>Problembehandlung

Es gibt einen zweiminütigen Timer ab dem Zeitpunkt, zu dem eine Offline Nachricht gesendet wird, wenn Sie abgeholt und verarbeitet wird. Wenn Offline-Nachrichten nicht verarbeitet werden können, werden Sie im folgenden Verzeichnis angezeigt: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Das primäre ETL-Protokoll von Skype for Business enthält Informationen zur Offline-Nachrichtenverarbeitung und ist die beste Quelle für die Untersuchung/Fehlerbehebung. 
  
> [!NOTE]
> Es wurde ein Problem gemeldet, bei dem Offlinenachrichten nicht gewendet wurden und der Ordner „Entwürfe“ sich mit Nachrichten füllte. Das Problem trat bei Postfächern in der lokalen Exchange-Version auf. Seit dem 14.06.2016 ist das Problem in allen C2R-Kanälen behoben.   
