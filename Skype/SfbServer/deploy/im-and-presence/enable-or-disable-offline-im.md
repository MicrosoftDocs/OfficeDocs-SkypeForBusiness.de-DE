---
title: Aktivieren oder Deaktivieren von Offline instant Messaging (IM) in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Erfahren Sie, wie Sie Offline instant Messaging (IM) in Skype for Business Server aktivieren oder deaktivieren.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801945"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Offline instant Messaging (IM) in Skype for Business Server
 
Erfahren Sie, wie Sie Offline instant Messaging (IM) in Skype for Business Server aktivieren oder deaktivieren.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Aktivieren von Offline instant Messaging (IM) in Skype for Business Server

#A0 ist ein clientseitiges Feature, das in den Skype for #A1 (2016 C2R Build 16.0.6701.1000 oder höher) integrierte Funktion ist, die #A2 (EWS) zum Senden von Nachrichten vom Skype for #A3 an das #A3 eines Benutzers nutzt. Offlinenachrichten verwenden Exchange Web Services (EWS), um Offlinenachrichten vom Skype for Business-Client an das Postfach des Empfängers zu senden. EWS muss für den Skype for Business-Client verfügbar sein, damit Offlinenachrichten gesendet werden können. Weitere Informationen zur Planung von Chat und Anwesenheit finden Sie unter "Planen von Chat [und Anwesenheit in Skype for Business Server".](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> Wenn das Postfach des Benutzers lokal in Exchange gehostet wird, ist der Skype for #A0 (2016 C2R Build 16.0.6920.1000) erforderlich. 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>So aktivieren oder deaktivieren Sie Offline-Chat in Skype for Business Server

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie den folgenden Befehl aus, um Offline-IM zu aktivieren.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3 ist die Option "EnableOfflineIM" standardmäßig auf $True festgelegt. Legen Sie zum Deaktivieren diesen Wert auf $False. 
  
3. Führen Sie den folgenden Befehl aus, um zu bestätigen, dass die Möglichkeit zum Speichern von Offline-Imiten festgelegt ist.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Offline-Im-Integration in Exchange

Offlinenachrichten stehen Absendern nicht zur Verfügung, wenn sie über eine Clientrichtlinie verfügen, die das automatische Speichern von Offlinenachrichten im Ordner "Unterhaltungsverlauf" deaktiviert (EnableIMAutoArchiving = $false). Es gibt keinen Mechanismus, um zu überprüfen, ob der Empfänger Offlinenachrichten empfangen kann.
  
Bei Offlinenachrichten, die innerhalb derselben Organisation gesendet werden, werden sie als E-Mail-Nachricht mit der Nachrichtenklasse "IM.Note.MissedConversation" empfangen und im Ordner **"Outlook-Verpasste** Unterhaltungen" sowie im Unterhaltungsverlauf angezeigt, der auf der Registerkarte "Zuletzt geöffnete Listen-/Unterhaltungsverlauf" in Skype for Business-Clients angezeigt wird.
  
Bei Offlinenachrichten, die von einer Verbundorganisation gesendet werden, werden sie als E-Mail ohne IM.Note.MisssedConversation empfangen und nicht in den Ordnern für verpasste Unterhaltungen oder Unterhaltungsverlauf aufgenommen. 
  
## <a name="troubleshooting"></a>Problembehandlung

Es gibt einen zweiminütigen Timer, ab dem eine Offlinenachricht gesendet wird, wenn sie abgeholt und verarbeitet wird. Wenn Offlinenachrichten nicht verarbeitet werden können, werden sie im folgenden Verzeichnis angezeigt: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Das primäre Skype for Business-ETL-Protokoll enthält Informationen zur Offlinenachrichtenverarbeitung und ist die beste Quelle für Untersuchungen/Problembehandlung. 
  
> [!NOTE]
> Es wurde ein Problem gemeldet, bei dem Offlinenachrichten nicht gesendet werden konnten und der Ordner "Entwürfe" mit Nachrichten gefüllt wurde. Dies ist bei lokalen Exchange-Postfächern aufgetreten. Das Problem wurde seit dem 14.06.2016 in allen #A0 behoben.  
