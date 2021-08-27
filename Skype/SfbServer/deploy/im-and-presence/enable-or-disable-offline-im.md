---
title: Aktivieren oder Deaktivieren von Offline-Chatnachrichten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Erfahren Sie, wie Sie Offline-Chatnachrichten in Skype for Business Server aktivieren oder deaktivieren.
ms.openlocfilehash: 31c27a84965e3b75515c206f8dc984b2eaa178eb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578039"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Offline-Chatnachrichten in Skype for Business Server
 
Erfahren Sie, wie Sie Offline-Chatnachrichten in Skype for Business Server aktivieren oder deaktivieren.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren von Offline-Chatnachrichten in Skype for Business Server

Offline-Chat ist ein clientseitiges Feature, das in Skype for Business Client integriert ist (2016 C2R Build 16.0.6701.1000 oder höher), das Exchange Webdienste (EWS) nutzt, um Nachrichten vom Skype for Business-Client an das Exchange Postfach eines Benutzers zu senden. Offlinenachrichten verwenden Exchange Webdienste (EWS), um Offlinenachrichten vom Skype for Business-Client an das Postfach des Empfängers zu senden. EWS muss für den Skype for Business Client verfügbar sein, damit Offlinenachrichten gesendet werden können. Weitere Informationen zur Planung von Chatnachrichten und Anwesenheitsinformationen finden Sie unter [Plan for instant messaging and presence in Skype for Business Server.](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> Wenn das Postfach des Benutzers in Exchange lokal gehostet wird, ist der Skype for Business-Client (2016 C2R Build 16.0.6920.1000) erforderlich. 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>So aktivieren oder deaktivieren Sie Offlinenachrichten in Skype for Business Server

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie den folgenden Befehl aus, um Offlinenachrichten zu aktivieren.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3 ist die Option EnableOfflineIM standardmäßig auf $True festgelegt. Zum Deaktivieren legen Sie diesen Wert auf $False fest. 
  
3. Führen Sie den folgenden Befehl aus, um zu bestätigen, dass die Möglichkeit zum Speichern von Offline-Chatnachrichten festgelegt ist.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Offline-Chatintegration mit Exchange

Offlinenachrichten sind für Absender nicht verfügbar, wenn sie über eine Clientrichtlinie verfügen, die das automatische Speichern von Offlinenachrichten im Unterhaltungsverlaufsordner deaktiviert (EnableIMAutoArchiving = $false). Es gibt keinen Mechanismus, um zu überprüfen, ob der Empfänger Offlinenachrichten empfangen kann.
  
Für Offlinenachrichten, die innerhalb derselben Organisation gesendet werden, werden sie als E-Mail-Nachricht mit der Nachrichtenklasse "IM.Note.MissedConversation" empfangen und in Outlook Ordner **"Verpasste Unterhaltung"** sowie in den Unterhaltungsverlauf aufgenommen, der auf der Registerkarte "Zuletzt geöffneter Listen-/Unterhaltungsverlauf" in Skype for Business Clients angezeigt wird.
  
Bei Offlinenachrichten, die von einer Verbundorganisation gesendet werden, werden sie als E-Mail-Nachricht ohne IM.Note.MisssedConversation empfangen und nicht in den Ordnern für verpasste Unterhaltungen oder Aufgezeichnete Unterhaltungen aufgenommen. 
  
## <a name="troubleshooting"></a>Problembehandlung

Es gibt einen Zwei-Minuten-Timer vom Zeitpunkt, an den eine Offlinenachricht gesendet wird, wenn sie angenommen und verarbeitet wird. Wenn Offlinenachrichten nicht verarbeitet werden können, werden sie im folgenden Verzeichnis angezeigt: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Das primäre Skype for Business ETL-Protokoll enthält Informationen zur Offlinenachrichtenverarbeitung und ist die beste Quelle für Untersuchung/Problembehandlung. 
  
> [!NOTE]
> Es wurde ein Problem gemeldet, bei dem Offlinenachrichten nicht gesendet werden konnten und der Ordner "Entwürfe" mit Nachrichten gefüllt wurde. Dies ist bei Exchange lokalen Postfächern aufgetreten. Das Problem wurde ab dem 14.06.2016 in allen C2R-Kanälen behoben.  
