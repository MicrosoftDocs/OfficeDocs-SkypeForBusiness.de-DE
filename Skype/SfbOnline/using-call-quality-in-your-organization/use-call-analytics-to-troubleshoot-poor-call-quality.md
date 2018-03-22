---
title: "Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings.
ms.openlocfilehash: cbb728c14c58393a5ec71cc538ad958ba58fb947
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="ffca8-103">Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ffca8-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="ffca8-p101">Mithilfe der Anrufanalyse können Sie Probleme im Zusammenhang mit Anrufen oder Verbindungen in Skype for Business behandeln. Die Anrufanalyse zeigt detaillierte Informationen zu den Geräten und Netzwerken sowie zur Konnektivität für die Anrufe und Besprechungen der einzelnen Benutzer in Ihrem Skype for Business-Konto. Wenn Informationen zu Gebäuden, Standorten und Mandanten zur Anrufanalyse hinzugefügt wurden, werden auch diese für jeden Anruf und jede Sitzung angezeigt. Anhand der über die Anrufanalyse verfügbaren Informationen können Sie herausfinden, warum bestimmte Benutzer eine schlechte Anruf- oder Besprechungsqualität wahrnehmen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-p101">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business. Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account. If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session. Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="ffca8-108">Behandeln von Problemen mit der Anrufqualität mithilfe der Anrufanalyse</span><span class="sxs-lookup"><span data-stu-id="ffca8-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="ffca8-109">Die Ihnen zugewiesene Berechtigungsstufe entscheidet, auf welche Informationen Sie in der Anrufanalyse zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="ffca8-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="ffca8-110">**Skype for Business-Administrator**: Sie können auf alle Informationen in der Anrufanalyse und im Skype for Business Admin Center zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="ffca8-p102">**Helpdesk-Agent mit Berechtigungen der Stufe 1**: Sie sehen in der Anrufanalyse begrenzte Daten. Sie können Problembehandlungen für Anrufe ausführen, geben aber Probleme mit Besprechungen an einen Agent der Stufe 2 weiter. Auf die übrigen Funktionen im Skype for Business Admin Center können Sie nicht zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-p102">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics. You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent. You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="ffca8-p103">**Helpdesk-Agent mit Berechtigungen der Stufe 2**: Sie sehen in der Anrufanalyse alle verfügbaren Daten und können bei Problembehandlungen für Anrufe und Besprechungen helfen. Auf die übrigen Funktionen im Skype for Business Admin Center können Sie nicht zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-p103">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings. You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="ffca8-116">Wenden Sie sich an Ihren Skype for Business-Administrator, wenn Sie Hilfe im Zusammenhang mit Berechtigungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="ffca8-117">**Öffnen der Anrufanalyse als Helpdesk-Agent der Stufe 1 oder 2**</span><span class="sxs-lookup"><span data-stu-id="ffca8-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="ffca8-118">Besuchen Sie das Office 365 Administrationscenter, und melden Sie sich mit Ihrem Konto arbeiten oder Schule.</span><span class="sxs-lookup"><span data-stu-id="ffca8-118">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="ffca8-119">Wechseln Sie in Ihrem Webbrowser zu *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="ffca8-119">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="ffca8-120">Beginnen Sie in **Benutzersuche**, den Namen oder die SIP-Adresse des Benutzers einzugeben, für dessen Anrufe Sie eine Problembehandlung ausführen möchten. Wählen Sie dann den Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ffca8-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="ffca8-122">Wählen Sie in **Call history** (Anrufliste) den Anruf oder die Besprechung aus, für den bzw. für die Sie eine Problembehandlung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ffca8-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="ffca8-124">Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="ffca8-p105">In den Sitzungsdetails für die einzelnen Anrufe oder Besprechungen werden geringfügige Probleme gelb dargestellt. (Im folgenden Screenshot zum Beispiel werden die Werte für „Durchschnittlicher Jitter", „Max. Jitter" und „Durchschnittliche Paketverlustrate" in Gelb angezeigt.) Gelbe Elemente befinden sich außerhalb des normalen Bereichs und können zum Problem beitragen. Sie sind aber wahrscheinlich nicht die Hauptursache des Problems. Rote Elemente weisen auf ein wichtiges Problem hin und stellen wahrscheinlich die Hauptursache für die schlechte Anrufqualität in dieser Sitzung dar.</span><span class="sxs-lookup"><span data-stu-id="ffca8-p105">In the session details for each call or meeting, minor issues appear in yellow. (For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem. If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="ffca8-129">In seltenen Fällen ist nicht für audiositzungen Daten Quality of Experience empfangen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-129">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="ffca8-130">Häufig ist dies durch den Aufruf ablegen und Verbindung mit dem Client beenden verursacht.</span><span class="sxs-lookup"><span data-stu-id="ffca8-130">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="ffca8-131">In diesem Fall ist die Sitzung Bewertung "nicht verfügbar".</span><span class="sxs-lookup"><span data-stu-id="ffca8-131">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="ffca8-132">Für audio-Sitzungen, die Daten Quality of Experience (QoE) verfügen, wird beschrieben, in der folgenden Tabelle Hauptprobleme, die für die Verwendung eine Sitzung als "schlecht".</span><span class="sxs-lookup"><span data-stu-id="ffca8-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="ffca8-133">**Problem**</span><span class="sxs-lookup"><span data-stu-id="ffca8-133">**Issue**</span></span>|<span data-ttu-id="ffca8-134">**Bereich**</span><span class="sxs-lookup"><span data-stu-id="ffca8-134">**Area**</span></span>|<span data-ttu-id="ffca8-135">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ffca8-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ffca8-136">Verbindungsaufbau</span><span class="sxs-lookup"><span data-stu-id="ffca8-136">Call setup</span></span>  <br/> |<span data-ttu-id="ffca8-137">Sitzung</span><span class="sxs-lookup"><span data-stu-id="ffca8-137">Session</span></span>  <br/> |<span data-ttu-id="ffca8-138">Der Fehlercode 20-29 Ms-Diagnose zeigt den Anruf ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ffca8-138">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="ffca8-139">Der Benutzer konnte nicht dem Anruf oder der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-139">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="ffca8-140">Audio Netzwerk klassifiziert Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="ffca8-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="ffca8-141">Sitzung</span><span class="sxs-lookup"><span data-stu-id="ffca8-141">Session</span></span>  <br/> |<span data-ttu-id="ffca8-142">Qualität Netzwerkprobleme aufgetreten in Bereichen wie Paketverlust, Jitter, NMOS-Beeinträchtigung, Zeit, oder Verhältnis verborgen.</span><span class="sxs-lookup"><span data-stu-id="ffca8-142">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="ffca8-143">Weitere Informationen über die Bedingungen, die zum Klassifizieren von schlechter Anrufe verwendet finden Sie unter in diesem [Blogbeitrag Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="ffca8-143">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="ffca8-144">Gerät nicht funktionsfähig</span><span class="sxs-lookup"><span data-stu-id="ffca8-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="ffca8-145">Gerät</span><span class="sxs-lookup"><span data-stu-id="ffca8-145">Device</span></span>  <br/> | <span data-ttu-id="ffca8-146">Ein Gerät ist nicht ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ffca8-146">A device isn't functioning correctly.</span></span> <span data-ttu-id="ffca8-147">Gerät nicht funktioniert Verhältnisse verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ffca8-147">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="ffca8-148">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="ffca8-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="ffca8-149">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="ffca8-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="ffca8-150">See Also</span><span class="sxs-lookup"><span data-stu-id="ffca8-150">Related topics</span></span>
[<span data-ttu-id="ffca8-151">Einrichten der Anrufanalyse von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ffca8-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="ffca8-152">Was ist der Unterschied zwischen der Anrufanalyse und dem Anrufqualitätsdashboard?</span><span class="sxs-lookup"><span data-stu-id="ffca8-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

## <a name="feedback"></a><span data-ttu-id="ffca8-153">Feedback?</span><span class="sxs-lookup"><span data-stu-id="ffca8-153">Feedback?</span></span>
<span data-ttu-id="ffca8-154">Geben Sie Feedback zu Produkten oder uns Ihre Meinung kennen, finden Sie unter [Skype für Business Feedback](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="ffca8-154">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>