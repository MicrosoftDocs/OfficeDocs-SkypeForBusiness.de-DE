---
title: Meinen Anruf in Skype for Business Server bewerten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Zusammenfassung: erfahren Sie mehr über die Funktion "meine Anrufe bewerten" in Skype for Business Server.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902219"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="5b121-103">Meinen Anruf in Skype for Business Server bewerten</span><span class="sxs-lookup"><span data-stu-id="5b121-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="5b121-104">**Zusammenfassung:** Erfahren Sie mehr über die Funktion "meinen Anruf bewerten" in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b121-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="5b121-105">"Mein Anruf bewerten" war ein neues Feature in Skype for Business 2015-und 2016-Clients unter Windows, das Unternehmen eine Möglichkeit bietet, Feedback von Ihren Endbenutzern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5b121-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="5b121-106">Das Fenster "mein Anruf bewerten" bietet ein Bewertungssystem für "Sterne" und vordefinierte Token für Audio-und Videoanrufe.</span><span class="sxs-lookup"><span data-stu-id="5b121-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="5b121-107">Darüber hinaus können Administratoren ein benutzerdefiniertes Feld zur Bereitstellung von Feedback aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b121-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="5b121-108">Gesammelte Rate meine Anrufdaten sind derzeit nicht in einem vorhandenen Überwachungsbericht enthalten, es gibt jedoch einen separaten Überwachungsbericht.</span><span class="sxs-lookup"><span data-stu-id="5b121-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="5b121-109">Daten werden in SQL-Tabellen erfasst, auf die durch die Ausführung von SQL-Abfragen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5b121-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="5b121-110">Meine Voraussetzungen für Anrufe bewerten</span><span class="sxs-lookup"><span data-stu-id="5b121-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="5b121-111">Bevor die Benutzer in Ihrer Skype for Business Server-Bereitstellung auf die Funktion "meine Anrufe bewerten" zugreifen können, müssen die folgenden Komponenten bereitgestellt und konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="5b121-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="5b121-112">Sie müssen Skype for Business Server installiert haben (Version 9160 oder höher).</span><span class="sxs-lookup"><span data-stu-id="5b121-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="5b121-113">Lassen Sie die Benutzer die neueste Version von Skype for Business installieren und aktualisieren, und fordern Sie Sie außerdem auf, die Skype for Business Benutzeroberfläche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b121-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="5b121-114">Benutzer müssen im Skype for Business Server Front-End-Pool verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5b121-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="5b121-115">Sie müssen über eine Skype for Business Server Überwachungsdatenbank verfügen, die Ihren Skype for Business Server-Pools bereitgestellt und zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5b121-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="5b121-116">Es wird empfohlen, das Anruf Qualitäts Dashboard (CQD) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5b121-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="5b121-117">Konfigurieren von "mein Anruf bewerten"</span><span class="sxs-lookup"><span data-stu-id="5b121-117">Configure Rate my Call</span></span>

<span data-ttu-id="5b121-118">Das Feature Meine Anruf Rate bewerten ist in der Client Richtlinie standardmäßig mit den folgenden Einstellungen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="5b121-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="5b121-119">Mein Anruf anzeigen: Prozentsatz-10%</span><span class="sxs-lookup"><span data-stu-id="5b121-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="5b121-120">Bewerten von "meine Anrufe erlauben"-Benutzer Feedback – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="5b121-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="5b121-121">Es ist keine Aktion erforderlich, um das Basis Feature zu aktivieren, aber wenn Sie ein benutzerdefiniertes Feedback wünschen, müssen Sie es separat aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b121-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="5b121-122">Das folgende Windows PowerShell-Cmdlets ist ein Beispiel für die Aktivierung benutzerdefinierter Endbenutzer Feedbacks und das Ändern des Intervalls von 10% auf 80%.</span><span class="sxs-lookup"><span data-stu-id="5b121-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="5b121-123">Zugreifen auf meine Anrufdaten bewerten</span><span class="sxs-lookup"><span data-stu-id="5b121-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="5b121-124">Daten von Benutzern werden in zwei Tabellen in der Überwachungsdatenbank gesammelt.</span><span class="sxs-lookup"><span data-stu-id="5b121-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="5b121-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** – Diese Tabelle enthält Ergebnisse von Token Polling durch Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="5b121-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="5b121-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** – Diese Tabelle enthält Token-Definitionen.</span><span class="sxs-lookup"><span data-stu-id="5b121-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="5b121-127">Token-Definitionen werden wie folgt codiert:</span><span class="sxs-lookup"><span data-stu-id="5b121-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5b121-128">1 </span><span class="sxs-lookup"><span data-stu-id="5b121-128">1</span></span>  <br/> |<span data-ttu-id="5b121-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="5b121-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="5b121-130">2 </span><span class="sxs-lookup"><span data-stu-id="5b121-130">2</span></span>  <br/> | <span data-ttu-id="5b121-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="5b121-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="5b121-132">3 </span><span class="sxs-lookup"><span data-stu-id="5b121-132">3</span></span>  <br/> | <span data-ttu-id="5b121-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="5b121-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="5b121-134">4 </span><span class="sxs-lookup"><span data-stu-id="5b121-134">4</span></span>  <br/> |<span data-ttu-id="5b121-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="5b121-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="5b121-136">5 </span><span class="sxs-lookup"><span data-stu-id="5b121-136">5</span></span>  <br/> |<span data-ttu-id="5b121-137">Echo</span><span class="sxs-lookup"><span data-stu-id="5b121-137">Echo</span></span>  <br/> |
|<span data-ttu-id="5b121-138"> 21</span><span class="sxs-lookup"><span data-stu-id="5b121-138">21</span></span>  <br/> | <span data-ttu-id="5b121-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="5b121-140">22</span><span class="sxs-lookup"><span data-stu-id="5b121-140">22</span></span>  <br/> | <span data-ttu-id="5b121-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="5b121-142">23</span><span class="sxs-lookup"><span data-stu-id="5b121-142">23</span></span>  <br/> | <span data-ttu-id="5b121-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="5b121-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="5b121-144">24</span><span class="sxs-lookup"><span data-stu-id="5b121-144">24</span></span>  <br/> | <span data-ttu-id="5b121-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="5b121-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="5b121-146">25</span><span class="sxs-lookup"><span data-stu-id="5b121-146">25</span></span>  <br/> | <span data-ttu-id="5b121-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="5b121-148">101</span><span class="sxs-lookup"><span data-stu-id="5b121-148">101</span></span>  <br/> |<span data-ttu-id="5b121-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="5b121-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="5b121-150">102</span><span class="sxs-lookup"><span data-stu-id="5b121-150">102</span></span>  <br/> |<span data-ttu-id="5b121-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="5b121-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="5b121-152">103</span><span class="sxs-lookup"><span data-stu-id="5b121-152">103</span></span>  <br/> |<span data-ttu-id="5b121-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="5b121-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="5b121-154">104</span><span class="sxs-lookup"><span data-stu-id="5b121-154">104</span></span>  <br/> |<span data-ttu-id="5b121-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="5b121-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="5b121-156">105</span><span class="sxs-lookup"><span data-stu-id="5b121-156">105</span></span>  <br/> |<span data-ttu-id="5b121-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="5b121-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="5b121-158">106</span><span class="sxs-lookup"><span data-stu-id="5b121-158">106</span></span>  <br/> |<span data-ttu-id="5b121-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="5b121-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="5b121-160">107</span><span class="sxs-lookup"><span data-stu-id="5b121-160">107</span></span>  <br/> |<span data-ttu-id="5b121-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="5b121-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="5b121-162">108</span><span class="sxs-lookup"><span data-stu-id="5b121-162">108</span></span>  <br/> |<span data-ttu-id="5b121-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="5b121-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="5b121-164">109</span><span class="sxs-lookup"><span data-stu-id="5b121-164">109</span></span>  <br/> |<span data-ttu-id="5b121-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="5b121-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="5b121-166">201</span><span class="sxs-lookup"><span data-stu-id="5b121-166">201</span></span>  <br/> |<span data-ttu-id="5b121-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="5b121-168">202</span><span class="sxs-lookup"><span data-stu-id="5b121-168">202</span></span>  <br/> |<span data-ttu-id="5b121-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="5b121-170">203</span><span class="sxs-lookup"><span data-stu-id="5b121-170">203</span></span>  <br/> |<span data-ttu-id="5b121-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="5b121-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="5b121-172">204</span><span class="sxs-lookup"><span data-stu-id="5b121-172">204</span></span>  <br/> |<span data-ttu-id="5b121-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="5b121-174">205</span><span class="sxs-lookup"><span data-stu-id="5b121-174">205</span></span>  <br/> |<span data-ttu-id="5b121-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="5b121-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="5b121-176">206</span><span class="sxs-lookup"><span data-stu-id="5b121-176">206</span></span>  <br/> |<span data-ttu-id="5b121-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="5b121-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="5b121-178">207</span><span class="sxs-lookup"><span data-stu-id="5b121-178">207</span></span>  <br/> |<span data-ttu-id="5b121-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="5b121-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="5b121-180">208</span><span class="sxs-lookup"><span data-stu-id="5b121-180">208</span></span>  <br/> |<span data-ttu-id="5b121-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="5b121-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="5b121-182">301</span><span class="sxs-lookup"><span data-stu-id="5b121-182">301</span></span>  <br/> |<span data-ttu-id="5b121-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="5b121-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="5b121-184">401</span><span class="sxs-lookup"><span data-stu-id="5b121-184">401</span></span>  <br/> |<span data-ttu-id="5b121-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="5b121-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="5b121-186">402</span><span class="sxs-lookup"><span data-stu-id="5b121-186">402</span></span>  <br/> |<span data-ttu-id="5b121-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="5b121-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="5b121-188">403</span><span class="sxs-lookup"><span data-stu-id="5b121-188">403</span></span>  <br/> |<span data-ttu-id="5b121-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="5b121-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="5b121-190">404</span><span class="sxs-lookup"><span data-stu-id="5b121-190">404</span></span>  <br/> |<span data-ttu-id="5b121-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="5b121-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="5b121-192">405</span><span class="sxs-lookup"><span data-stu-id="5b121-192">405</span></span>  <br/> |<span data-ttu-id="5b121-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="5b121-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="5b121-194">406</span><span class="sxs-lookup"><span data-stu-id="5b121-194">406</span></span>  <br/> |<span data-ttu-id="5b121-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="5b121-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="5b121-196">407</span><span class="sxs-lookup"><span data-stu-id="5b121-196">407</span></span>  <br/> |<span data-ttu-id="5b121-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="5b121-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="5b121-198">408</span><span class="sxs-lookup"><span data-stu-id="5b121-198">408</span></span>  <br/> |<span data-ttu-id="5b121-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="5b121-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="5b121-200">501</span><span class="sxs-lookup"><span data-stu-id="5b121-200">501</span></span>  <br/> |<span data-ttu-id="5b121-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="5b121-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="5b121-202">502</span><span class="sxs-lookup"><span data-stu-id="5b121-202">502</span></span>  <br/> |<span data-ttu-id="5b121-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="5b121-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="5b121-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Diese Tabelle enthält Polling-Ergebnisse aus "Sterne"-Abstimmungen und Kundenfeedback, falls aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b121-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="5b121-205">Daten aus Tabellen können mithilfe einer **Select \* from [Table.Name]** -Abfrage oder mithilfe von Microsoft SQL Server Management Studio aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5b121-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="5b121-206">Die folgenden SQL-Abfragen können verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5b121-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="5b121-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="5b121-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="5b121-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="5b121-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="5b121-209">Aktualisieren von Token-Definitionen</span><span class="sxs-lookup"><span data-stu-id="5b121-209">Updating Token Definitions</span></span>

<span data-ttu-id="5b121-210">Die neuesten Skype for Business Clients melden neue Problemtoken-IDs ( \> 100), die möglicherweise nicht in Ihrem [QoeMetrics] vorhanden sind. [ dbo]. [CallQualityFeedbackTokenDef]-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5b121-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="5b121-211">Um die Datenbanktabelle mit den neuesten Token-Definitionen zu aktualisieren, kann der folgende SQL-Befehl in der Überwachungsdatenbank mit Microsoft SQL Server Management Studio ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b121-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="5b121-212">Mit diesem Befehl werden alle Einträge im [QoeMetrics] ersetzt. [dbo]. [CallQualityFeedbackTokenDef]-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5b121-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


