---
title: Aktivieren Sie oder deaktivieren Sie Offline Sofortnachrichten (IM) in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Informationen Sie zum Aktivieren oder deaktivieren Offline Instant Messaging (IM) in Skype für Business Server.
ms.openlocfilehash: f033a3953e2be215f4acb587414cad4faf35855f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019559"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="59d94-103">Aktivieren Sie oder deaktivieren Sie Offline Sofortnachrichten (IM) in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="59d94-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="59d94-104">Informationen Sie zum Aktivieren oder deaktivieren Offline Instant Messaging (IM) in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d94-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="59d94-105">Aktivieren von Offline Sofortnachrichten (IM) in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="59d94-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="59d94-106">Offline-Sofortnachrichten ist ein Client Side-Feature in Skype für Business-Client integriert (2016 C2R build 16.0.6701.1000 oder höher), die Exchange-Webdienste (EWS) zum Senden von Nachrichten aus der Skype für Business-Client mit Exchange-Postfach eines Benutzers nutzt.</span><span class="sxs-lookup"><span data-stu-id="59d94-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="59d94-107">Offline-Sofortnachrichten verwendet Exchange-Webdienste (EWS) Offline Nachrichten an das Postfach des Empfängers aus der Skype für Business-Client zu senden.</span><span class="sxs-lookup"><span data-stu-id="59d94-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="59d94-108">EWS müssen die Skype für Business-Client für Offline-Nachrichten gesendet werden zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="59d94-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="59d94-109">Weitere Informationen zum Planen von instant messaging und Anwesenheit, finden Sie unter [Planen von instant messaging und Anwesenheit in Skype für Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="59d94-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="59d94-110">Wenn das Postfach des Benutzers in Exchange lokal gehostet wird, ist die Skype für Business-Client (2016 C2R build 16.0.6920.1000) erforderlich</span><span class="sxs-lookup"><span data-stu-id="59d94-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="59d94-111">So aktivieren oder deaktivieren Offline Sofortnachrichten in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="59d94-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="59d94-112">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="59d94-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="59d94-113">Führen Sie den folgenden Befehl aus, um Offline-Sofortnachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="59d94-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="59d94-114">In Skype für Business Server 2015 CU3 ist die Option EnableOfflineIM standardmäßig auf $True gesetzt.</span><span class="sxs-lookup"><span data-stu-id="59d94-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="59d94-115">Wenn Sie die Möglichkeit deaktivieren möchten, legen Sie den Wert auf „$False“ fest.</span><span class="sxs-lookup"><span data-stu-id="59d94-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="59d94-116">Führen Sie den folgenden Befehl aus, um zu bestätigen, dass die Möglichkeit zum Speichern von Offline Instant Messaging gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="59d94-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="59d94-117">Integration von Offline-Sofortnachrichten in Exchange</span><span class="sxs-lookup"><span data-stu-id="59d94-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="59d94-p103">Offline-Sofortnachrichten sind nicht für Absender verfügbar, für die eine Clientrichtlinie das automatische Speichern von Offlinenachrichten im Ordner „Aufgezeichnete Unterhaltungen“ deaktiviert („EnableIMAutoArchiving = $false“). Es gibt keine Methode, mit der Sie überprüfen können, ob der Empfänger Offlinenachrichten empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="59d94-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="59d94-120">Für Offline innerhalb derselben Organisation gesendeten Nachrichten werden sie als e-Mail-Nachricht mit der Nachrichtenklasse des Sofortnachrichten empfangen. Note.MissedConversation und wird in Outlook **Entgangene Unterhaltung** Ordner als auch Unterhaltungen, die in der Registerkarte Verlauf zuletzt Liste-Unterhaltung in Skype für Business Clients bearbeitet wird, hängt enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="59d94-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="59d94-121">
 Offlinenachrichten, die von einer Partnerorganisation gesendet werden, werden als E-Mail-Nachricht ohne „IM.Note.MissedConversation“ empfangen. Sie werden nicht in den Ordnern für verpasste Unterhaltungen oder aufgezeichnete Unterhaltungen gespeichert. </span><span class="sxs-lookup"><span data-stu-id="59d94-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="59d94-122">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="59d94-122">Troubleshooting</span></span>

<span data-ttu-id="59d94-123">Es wird ein Timer zwei Minuten aus, wenn eine offline-Nachricht an gesendet wird, wenn es aufgenommene und verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="59d94-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="59d94-124">Wenn offline Nachrichten nicht verarbeitet werden können, werden sie in das folgende Verzeichnis angezeigt:</span><span class="sxs-lookup"><span data-stu-id="59d94-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="59d94-125">Die primäre Skype für Business ETL-Protokoll enthält Informationen zur Verarbeitung von Offline-Nachricht und Ihre besten Untersuchung/bei der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="59d94-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="59d94-p105">Es wurde ein Problem gemeldet, bei dem Offlinenachrichten nicht gewendet wurden und der Ordner „Entwürfe“ sich mit Nachrichten füllte. Das Problem trat bei Postfächern in der lokalen Exchange-Version auf. Seit dem 14.06.2016 ist das Problem in allen C2R-Kanälen behoben. </span><span class="sxs-lookup"><span data-stu-id="59d94-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  