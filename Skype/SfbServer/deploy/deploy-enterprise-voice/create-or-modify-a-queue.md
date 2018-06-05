---
title: Erstellen oder Ändern einer Warteschleife in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Erstellen Sie oder ändern Sie einer Warteschleife für Reaktionsgruppen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: d959ca00829200ac8ad54168d72ca108adabb39f
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500984"
---
# <a name="create-or-modify-a-queue-in-skype-for-business-2015"></a><span data-ttu-id="35a7a-103">Erstellen oder Ändern einer Warteschleife in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="35a7a-103">Create or modify a queue in Skype for Business 2015</span></span>
 
<span data-ttu-id="35a7a-104">Erstellen Sie oder ändern Sie einer Warteschleife für Reaktionsgruppen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="35a7a-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="35a7a-105">Anrufer verbleiben in Warteschlangen, bis ein Agent den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="35a7a-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="35a7a-106">Wenn die Anwendung "Reaktionsgruppe" nach einem verfügbaren Agent sucht, sucht es Agentengruppen in der Reihenfolge, dass Sie diese auflisten.</span><span class="sxs-lookup"><span data-stu-id="35a7a-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="35a7a-107">Sie können die agentgruppen auswählen, die an die Warteschlange zugewiesen sind, und geben Sie Warteschlange Verhalten, beispielsweise Beschränken der Anzahl der Anrufe, die die Warteschleife aufnehmen kann und die Zeitspanne, ein Anruf, bis ein Agent den Anruf annimmt den Anruf wartet.</span><span class="sxs-lookup"><span data-stu-id="35a7a-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="35a7a-108">Verwenden Sie eines der folgenden Verfahren, um eine Warteschleife zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="35a7a-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="35a7a-109">Verwenden Sie zum Erstellen oder Ändern einer Warteschleife Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="35a7a-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="35a7a-110">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35a7a-111">Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Reaktionsgruppen-Warteschleifen erstellen und ändern und diese den von Ihnen verwalteten Workflows zuweisen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="35a7a-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="35a7a-113">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="35a7a-114">Führen Sie auf der Seite **Warteschleife** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="35a7a-115">Klicken Sie zum Erstellen einer neuen Warteschleife auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="35a7a-116">Fügen in **Wählen Sie einen Dienst**Typ Teil oder den vollständigen Namen des **ApplicationServer** -Diensts, in dem Sie möchten, die Warteschlange in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="35a7a-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="35a7a-117">Klicken Sie in der Dienstliste auf den gewünschten Dienst und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="35a7a-p103">Geben Sie den Warteschleifennamen vollständig oder teilweise in das Suchfeld ein, um eine vorhandene Warteschleife zu ändern. Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="35a7a-120">Geben Sie bei **Name** einen Namen ein, mit dem die Warteschleife bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="35a7a-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="35a7a-121">Geben Sie in **Beschreibung** eine Beschreibung für die Warteschleife ein.</span><span class="sxs-lookup"><span data-stu-id="35a7a-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="35a7a-p104">Geben Sie in **Gruppen** die Gruppen an, die Sie der Warteschleife zuweisen möchten. Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="35a7a-p105">Klicken Sie auf **Auswählen**, um eine Gruppe zu der Warteschleife hinzuzufügen. Geben Sie im Suchfeld **Gruppen auswählen** den Namen der Agentgruppe, die Sie der Warteschleife zuweisen möchten, teilweise oder vollständig ein, klicken Sie auf die gewünschte Agentgruppe und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="35a7a-126">Um eine Gruppe aus der Warteschleife zu entfernen, klicken Sie in der Liste der Agentgruppen auf die Gruppe, die Sie entfernen möchten und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="35a7a-127">Um die Reihenfolge zu ändern, in der Agents durchsucht werden, klicken Sie in der Liste der Agentgruppen auf eine Gruppe und klicken Sie dann auf den Pfeil nach oben oder nach unten.</span><span class="sxs-lookup"><span data-stu-id="35a7a-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35a7a-p106">Bei der Suche des Servers nach einem verfügbaren Agent werden Gruppen in der vorhandenen Reihenfolge durchlaufen. Die erste Gruppe in der Liste wird also zuerst durchsucht, dann die zweite Gruppe in der Liste usw.</span><span class="sxs-lookup"><span data-stu-id="35a7a-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="35a7a-130">Wenn Sie eine Höchstdauer für die Wartezeit eines Anrufers festlegen möchten, bevor ein Agent den Anruf entgegennimmt, aktivieren Sie das Kontrollkästchen **Timeout für Warteschleife aktivieren** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="35a7a-131">a.</span><span class="sxs-lookup"><span data-stu-id="35a7a-131">a.</span></span> <span data-ttu-id="35a7a-132">Geben Sie in **Timeout (Sekunden)** die maximale Anzahl von Sekunden an, die ein Anrufer auf die Entgegennahme des Anrufs durch einen Agent wartet.</span><span class="sxs-lookup"><span data-stu-id="35a7a-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="35a7a-133">b.</span><span class="sxs-lookup"><span data-stu-id="35a7a-133">b.</span></span> <span data-ttu-id="35a7a-134">Wählen Sie in **Anrufaktion** die Aktion aus, die bei einem Timeout für einen Anruf durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="35a7a-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
     - <span data-ttu-id="35a7a-135">Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
     - <span data-ttu-id="35a7a-136">So leiten Sie den Anruf an Voicemail, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie im Feld **SIP-Adresse** eine Voicemail-Adresse im Format Sip weiter: _ \<Username\>_@ _\<Domainname\> _ (für Beispiel, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="35a7a-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: _\<username\>_@ _\<domainname\>_ (for example, sip:bob@contoso.com).</span></span>
    
     - <span data-ttu-id="35a7a-137">Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie im Feld **SIP-Adresse** die Telefonnummer im Format Sip: _ \<Anzahl\>_@ _\<Domainname\>_ (beispielsweise sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="35a7a-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: _\<number\>_@ _\<domainname\>_ (for example, sip:+14255550121@contoso.com).</span></span>
    
     - <span data-ttu-id="35a7a-138">Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie im Feld **SIP-Adresse** den URI für den Benutzer im Format Sip: _ \<Username\>_@ _\<Domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="35a7a-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="35a7a-139">Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="35a7a-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="35a7a-140">Um eine maximale Anzahl der Anrufe anzugeben, die in der Warteschleife enthalten sein können, aktivieren Sie das Kontrollkästchen **Warteschleifenüberlauf aktivieren** und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="35a7a-141">a.</span><span class="sxs-lookup"><span data-stu-id="35a7a-141">a.</span></span> <span data-ttu-id="35a7a-142">Wählen Sie im Feld **Maximale Anzahl von Anrufen** die maximale Anzahl von Anrufen aus, die die Warteschleife enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="35a7a-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="35a7a-143">b.</span><span class="sxs-lookup"><span data-stu-id="35a7a-143">b.</span></span> <span data-ttu-id="35a7a-144">Wählen Sie in **Anruf weiterleiten** aus, welcher Anruf weitergeleitet werden soll, wenn die Warteschleife voll ist: **Neuester Anruf** oder **Ältester Anruf**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="35a7a-145">c.</span><span class="sxs-lookup"><span data-stu-id="35a7a-145">c.</span></span> <span data-ttu-id="35a7a-146">Wählen Sie in **Anrufaktion** die Aktion aus, die bei Erreichen des Schwellenwerts für den Überlauf durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="35a7a-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
     - <span data-ttu-id="35a7a-147">Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
     - <span data-ttu-id="35a7a-148">So leiten Sie den Anruf an Voicemail, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie im Feld **SIP-Adresse** eine Voicemail-Adresse im Format Sip weiter: _ \<Username\>_@ _\<Domainname\> _ (für Beispiel, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="35a7a-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: _\<username\>_@ _\<domainname\>_ (for example, sip:bob@contoso.com).</span></span>
    
     - <span data-ttu-id="35a7a-149">Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie im Feld **SIP-Adresse** die Telefonnummer im Format Sip: _ \<Anzahl\>_@ _\<Domainname\>_ (beispielsweise sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="35a7a-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: _\<number\>_@ _\<domainname\>_ (for example, sip:+14255550121@contoso.com).</span></span>
    
     - <span data-ttu-id="35a7a-150">Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie im Feld **SIP-Adresse** den URI für den Benutzer im Format Sip: _ \<Username\>_@ _\<Domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="35a7a-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="35a7a-151">Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="35a7a-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="35a7a-152">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="35a7a-153">Verwenden Sie zum Erstellen oder Ändern einer Warteschleife Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="35a7a-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="35a7a-154">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35a7a-155">Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen und Warteschleifen erstellen und Warteschleifen Agentgruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="35a7a-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="35a7a-156">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="35a7a-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="35a7a-p112">Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="35a7a-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35a7a-159">For example:</span></span>
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="35a7a-160">Um eine Audiodatei für die Aufforderung zur verwenden möchten, verwenden Sie das Cmdlet **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="35a7a-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="35a7a-161">Weitere Informationen hierzu finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35a7a-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="35a7a-p114">Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="35a7a-164">Ausführliche Informationen zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35a7a-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="35a7a-165">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35a7a-165">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="35a7a-p115">Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   <span data-ttu-id="35a7a-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35a7a-168">For example:</span></span>
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > <span data-ttu-id="35a7a-169">Um eine Audiodatei für die Aufforderung zur verwenden möchten, verwenden Sie das Cmdlet **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="35a7a-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="35a7a-170">Weitere Informationen hierzu finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35a7a-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="35a7a-p117">Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > <span data-ttu-id="35a7a-173">Ausführliche Informationen zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35a7a-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="35a7a-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35a7a-174">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="35a7a-p118">Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="35a7a-p119">Identität einer Agentgruppe abrufen, die der Warteschleife zugeordnet werden soll. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="35a7a-179">Ausführliche Informationen zum Erstellen der agentgruppe finden Sie unter [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="35a7a-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="35a7a-p120">Die Warteschleife erstellen. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p120">Create the queue. At the command line, run:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="35a7a-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35a7a-182">For example:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="35a7a-p121">Bestätigen Sie, dass die Warteschleife erstellt wurde. Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="35a7a-p121">Confirm that the queue is created. Run:</span></span>
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="35a7a-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35a7a-185">See also</span></span>

[<span data-ttu-id="35a7a-186">Mit New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="35a7a-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="35a7a-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="35a7a-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="35a7a-188">Neue CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="35a7a-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="35a7a-189">Mit New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="35a7a-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="35a7a-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="35a7a-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="35a7a-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="35a7a-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="35a7a-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="35a7a-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)