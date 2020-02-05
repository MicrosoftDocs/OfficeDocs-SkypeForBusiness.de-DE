---
title: Erstellen oder Ändern einer Warteschlange in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Erstellen oder Ändern einer Reaktionsgruppen Warteschlange in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 8cd306e849eeddd8a11b76604826084c0eb9b41d
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767868"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="850eb-103">Erstellen oder Ändern einer Warteschlange in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="850eb-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="850eb-104">Erstellen oder Ändern einer Reaktionsgruppen Warteschlange in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="850eb-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="850eb-105">Warteschlangen halten Anrufer, bis ein Agent den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="850eb-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="850eb-106">Wenn die reaktionsgruppenanwendung nach einem verfügbaren Agenten sucht, durchsucht Sie die Agentengruppen in der Reihenfolge, in der Sie Sie auflisten.</span><span class="sxs-lookup"><span data-stu-id="850eb-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="850eb-107">Sie können die Agents auswählen, die der Warteschlange zugewiesen sind, und das Warteschlangenverhalten angeben, beispielsweise das Einschränken der Anzahl von anrufen, die in der Warteschlange gespeichert werden können, und die Zeitspanne, die ein Anruf wartet, bis ein Agent den Anruf beantwortet.</span><span class="sxs-lookup"><span data-stu-id="850eb-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="850eb-108">Verwenden Sie eines der folgenden Verfahren, um eine Warteschleife zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="850eb-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="850eb-109">So verwenden Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="850eb-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="850eb-110">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="850eb-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="850eb-111">Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Reaktionsgruppen-Warteschleifen erstellen und ändern und diese den von Ihnen verwalteten Workflows zuweisen.</span><span class="sxs-lookup"><span data-stu-id="850eb-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="850eb-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="850eb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="850eb-113">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife**.</span><span class="sxs-lookup"><span data-stu-id="850eb-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="850eb-114">Führen Sie auf der Seite **Warteschleife** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="850eb-115">Klicken Sie zum Erstellen einer neuen Warteschleife auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="850eb-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="850eb-116">Geben Sie in **Dienst auswählen** den Namen des **ApplicationServer**-Diensts, zu dem Sie die Warteschleife hinzufügen möchten, vollständig oder teilweise in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="850eb-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="850eb-117">Klicken Sie in der Dienstliste auf den gewünschten Dienst und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="850eb-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="850eb-p103">Geben Sie den Warteschleifennamen vollständig oder teilweise in das Suchfeld ein, um eine vorhandene Warteschleife zu ändern. Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="850eb-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="850eb-120">Geben Sie bei **Name** einen Namen ein, mit dem die Warteschleife bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="850eb-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="850eb-121">Geben Sie in **Beschreibung** eine Beschreibung für die Warteschleife ein.</span><span class="sxs-lookup"><span data-stu-id="850eb-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="850eb-p104">Geben Sie in **Gruppen** die Gruppen an, die Sie der Warteschleife zuweisen möchten. Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="850eb-p105">Klicken Sie auf **Auswählen**, um eine Gruppe zu der Warteschleife hinzuzufügen. Geben Sie im Suchfeld **Gruppen auswählen** den Namen der Agentgruppe, die Sie der Warteschleife zuweisen möchten, teilweise oder vollständig ein, klicken Sie auf die gewünschte Agentgruppe und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="850eb-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="850eb-126">Um eine Gruppe aus der Warteschleife zu entfernen, klicken Sie in der Liste der Agentgruppen auf die Gruppe, die Sie entfernen möchten und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="850eb-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="850eb-127">Um die Reihenfolge zu ändern, in der Agents durchsucht werden, klicken Sie in der Liste der Agentgruppen auf eine Gruppe und klicken Sie dann auf den Pfeil nach oben oder nach unten.</span><span class="sxs-lookup"><span data-stu-id="850eb-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="850eb-p106">Bei der Suche des Servers nach einem verfügbaren Agent werden Gruppen in der vorhandenen Reihenfolge durchlaufen. Die erste Gruppe in der Liste wird also zuerst durchsucht, dann die zweite Gruppe in der Liste usw.</span><span class="sxs-lookup"><span data-stu-id="850eb-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="850eb-130">Wenn Sie eine Höchstdauer für die Wartezeit eines Anrufers festlegen möchten, bevor ein Agent den Anruf entgegennimmt, aktivieren Sie das Kontrollkästchen **Timeout für Warteschleife aktivieren** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="850eb-131">a.</span><span class="sxs-lookup"><span data-stu-id="850eb-131">a.</span></span> <span data-ttu-id="850eb-132">Geben Sie in **Timeout (Sekunden)** die maximale Anzahl von Sekunden an, die ein Anrufer auf die Entgegennahme des Anrufs durch einen Agent wartet.</span><span class="sxs-lookup"><span data-stu-id="850eb-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="850eb-133">b.</span><span class="sxs-lookup"><span data-stu-id="850eb-133">b.</span></span> <span data-ttu-id="850eb-134">Wählen Sie in **Anrufaktion** die Aktion aus, die bei einem Timeout für einen Anruf durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="850eb-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="850eb-135">Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="850eb-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="850eb-136">Um den Anruf an die Voicemail weiterzuleiten, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** eine Voicemail-Adresse im Format SIP: \* \<\>username\**\<\> Domain* Name@ ein (beispielsweise SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="850eb-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="850eb-137">Wenn Sie den Anruf an eine andere Telefonnummer weiterleiten möchten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** die Telefonnummer im Format SIP: \* \<Number\>\*@ \*\<Domain Name\> \* ein (beispielsweise SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="850eb-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="850eb-138">Wenn Sie den Anruf an einen anderen Benutzer weiterleiten möchten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** den URI für den Benutzer im Format SIP: _ \<\>username__\<\>Domain_Name@ ein.</span><span class="sxs-lookup"><span data-stu-id="850eb-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="850eb-139">Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="850eb-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="850eb-140">Um eine maximale Anzahl der Anrufe anzugeben, die in der Warteschleife enthalten sein können, aktivieren Sie das Kontrollkästchen **Warteschleifenüberlauf aktivieren** und führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="850eb-141">a.</span><span class="sxs-lookup"><span data-stu-id="850eb-141">a.</span></span> <span data-ttu-id="850eb-142">Wählen Sie im Feld **Maximale Anzahl von Anrufen** die maximale Anzahl von Anrufen aus, die die Warteschleife enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="850eb-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="850eb-143">b.</span><span class="sxs-lookup"><span data-stu-id="850eb-143">b.</span></span> <span data-ttu-id="850eb-144">Wählen Sie in **Anruf weiterleiten** aus, welcher Anruf weitergeleitet werden soll, wenn die Warteschleife voll ist: **Neuester Anruf** oder **Ältester Anruf**.</span><span class="sxs-lookup"><span data-stu-id="850eb-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="850eb-145">c.</span><span class="sxs-lookup"><span data-stu-id="850eb-145">c.</span></span> <span data-ttu-id="850eb-146">Wählen Sie in **Anrufaktion** die Aktion aus, die bei Erreichen des Schwellenwerts für den Überlauf durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="850eb-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="850eb-147">Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="850eb-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="850eb-148">Um den Anruf an die Voicemail weiterzuleiten, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** eine Voicemail-Adresse im Format SIP: \* \<\>username\**\<\> Domain* Name@ ein (beispielsweise SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="850eb-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="850eb-149">Wenn Sie den Anruf an eine andere Telefonnummer weiterleiten möchten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** die Telefonnummer im Format SIP: \* \<Number\>\*@ \*\<Domain Name\> \* ein (beispielsweise SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="850eb-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="850eb-150">Wenn Sie den Anruf an einen anderen Benutzer weiterleiten möchten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie dann im Feld **SIP-Adresse** den URI für den Benutzer im Format SIP: _ \<\>username__\<\>Domain_Name@ ein.</span><span class="sxs-lookup"><span data-stu-id="850eb-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="850eb-151">Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="850eb-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="850eb-152">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="850eb-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="850eb-153">So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="850eb-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="850eb-154">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="850eb-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="850eb-155">Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen und Warteschleifen erstellen und Warteschleifen Agentgruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="850eb-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="850eb-156">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="850eb-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="850eb-p112">Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="850eb-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="850eb-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="850eb-160">Verwenden Sie das **Import-CsRgsAudioFile**-Cmdlet, um eine Audiodatei als Ansage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="850eb-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="850eb-161">Ausführliche Informationen finden Sie unter [importieren-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="850eb-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="850eb-p114">Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="850eb-164">Details zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="850eb-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="850eb-165">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="850eb-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="850eb-p115">Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="850eb-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="850eb-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="850eb-169">Verwenden Sie das **Import-CsRgsAudioFile**-Cmdlet, um eine Audiodatei als Ansage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="850eb-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="850eb-170">Ausführliche Informationen finden Sie unter [importieren-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="850eb-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="850eb-p117">Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="850eb-173">Details zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="850eb-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="850eb-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="850eb-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="850eb-p118">Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="850eb-p119">Identität einer Agentgruppe abrufen, die der Warteschleife zugeordnet werden soll. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="850eb-179">Details zum Erstellen der Agentengruppe finden Sie unter [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="850eb-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="850eb-p120">Die Warteschleife erstellen. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="850eb-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="850eb-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="850eb-p121">Bestätigen Sie, dass die Warteschleife erstellt wurde. Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="850eb-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="850eb-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="850eb-185">See also</span></span>

[<span data-ttu-id="850eb-186">Neu – CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="850eb-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="850eb-187">Satz-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="850eb-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="850eb-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="850eb-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="850eb-189">Neu – CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="850eb-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="850eb-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="850eb-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="850eb-191">Importieren-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="850eb-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="850eb-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="850eb-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
