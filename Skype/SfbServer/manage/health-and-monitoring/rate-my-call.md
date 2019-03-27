---
title: Bewerten von Meine Anruf in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Zusammenfassung: Informationen Sie zum Feature Rate Meine Aufrufen in Skype für Business Server.'
ms.openlocfilehash: 61aaff26c5786cd8574b7277ed600da75c3679ce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886303"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="a329d-103">Bewerten von Meine Anruf in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a329d-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="a329d-104">**Zusammenfassung:** Lernen Sie das Feature Rate Meine Aufrufen in Skype für Business Server aus.</span><span class="sxs-lookup"><span data-stu-id="a329d-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="a329d-105">Rate Meine aufrufen, wurde ein neues Feature in Skype für Business 2015 und 2016 Clients unter Windows, das Unternehmen eine Möglichkeit zum Abrufen von Feedback von ihren Endbenutzern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a329d-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="a329d-106">Das Fenster Rate Meine aufrufen bietet einen "Stern" Bewertungssystem und vordefinierten Token für Audio-und Videoanrufe.</span><span class="sxs-lookup"><span data-stu-id="a329d-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="a329d-107">Darüber hinaus können Administratoren ein benutzerdefiniertes Feld Ihr Feedback übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="a329d-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="a329d-108">Erfasste Daten aus „Meinen Anruf bewerten“ sind derzeit nicht in einem vorhandenen Überwachungsbericht enthalten, es gibt jedoch einen separaten Überwachungsbericht.</span><span class="sxs-lookup"><span data-stu-id="a329d-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="a329d-109">Daten werden in der SQL-Tabellen, die durch Ausführen von SQL-Abfragen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a329d-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="a329d-110">Voraussetzungen für „Meinen Anruf bewerten“</span><span class="sxs-lookup"><span data-stu-id="a329d-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="a329d-111">Bevor die Benutzer in Ihrer Skype für Business Server-Bereitstellung Rate Meine aufrufen Funktionalität zugreifen können, muss die folgende Gruppe von Komponenten bereitgestellt und konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="a329d-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="a329d-112">Skype benötigen Sie für Business Server installiert (Version 9160 oder höher).</span><span class="sxs-lookup"><span data-stu-id="a329d-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="a329d-113">Müssen Sie sich die Benutzer installieren und aktualisieren Sie auf die neueste Version von Skype für Unternehmen und auch bitten, der Skype für Business-Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="a329d-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="a329d-114">Benutzer müssen auf die Skype für Business Server-Front-End-Pool befinden.</span><span class="sxs-lookup"><span data-stu-id="a329d-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="a329d-115">Sie benötigen einen Skype für Business Server Überwachungsdatenbank bereitgestellt und auf Ihrer Skype für Business Server-Pools verknüpft.</span><span class="sxs-lookup"><span data-stu-id="a329d-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="a329d-116">Die Bereitstellung des Anrufqualitäts-Dashboards (CQD) wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a329d-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="a329d-117">„Meinen Anruf bewerten“ konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a329d-117">Configure Rate my Call</span></span>

<span data-ttu-id="a329d-118">Das Feature Rate Meine aufrufen, ist standardmäßig in die Clientrichtlinie mit den folgenden Einstellungen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="a329d-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="a329d-119">Bewerten von Meine Prozentsatz der Anzeige - 10 %</span><span class="sxs-lookup"><span data-stu-id="a329d-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="a329d-120">Bewerten von Meine Anruf zulassen benutzerdefinierte Benutzerfeedback - deaktiviert</span><span class="sxs-lookup"><span data-stu-id="a329d-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="a329d-121">Wenn Sie benutzerdefinierte Feedback möchten, müssen separat aktivieren, aber es ist keine Aktion erforderlich, um die Basis Feature jedoch aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a329d-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="a329d-122">Die folgenden Windows PowerShell-Cmdlets ist ein Beispiel des benutzerdefinierten Endbenutzer Feedback aktivieren und das Intervall von 10 % auf 80 % ändern.</span><span class="sxs-lookup"><span data-stu-id="a329d-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="a329d-123">Zugriff auf die Daten von „Meinen Anruf bewerten“</span><span class="sxs-lookup"><span data-stu-id="a329d-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="a329d-124">Daten von Benutzern werden in zwei Tabellen in der Überwachungsdatenbank erfasst.</span><span class="sxs-lookup"><span data-stu-id="a329d-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="a329d-125">**[QoeMetrics]. [Dbo]. [CallQualityFeedbackToken]** -Die folgende Tabelle enthält die Ergebnisse der token Abruf durch Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="a329d-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="a329d-126">**[QoeMetrics]. [Dbo]. [CallQualityFeedbackTokenDef]** -Die folgende Tabelle enthält Definitionen für token.</span><span class="sxs-lookup"><span data-stu-id="a329d-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="a329d-127">Token-Definitionen sind folgendermaßen codiert:</span><span class="sxs-lookup"><span data-stu-id="a329d-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a329d-128">1</span><span class="sxs-lookup"><span data-stu-id="a329d-128">1</span></span>  <br/> |<span data-ttu-id="a329d-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="a329d-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="a329d-130">2</span><span class="sxs-lookup"><span data-stu-id="a329d-130">2</span></span>  <br/> | <span data-ttu-id="a329d-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="a329d-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="a329d-132">3</span><span class="sxs-lookup"><span data-stu-id="a329d-132">3</span></span>  <br/> | <span data-ttu-id="a329d-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="a329d-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="a329d-134">4</span><span class="sxs-lookup"><span data-stu-id="a329d-134">4</span></span>  <br/> |<span data-ttu-id="a329d-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="a329d-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="a329d-136">5</span><span class="sxs-lookup"><span data-stu-id="a329d-136">5</span></span>  <br/> |<span data-ttu-id="a329d-137">Echo</span><span class="sxs-lookup"><span data-stu-id="a329d-137">Echo</span></span>  <br/> |
|<span data-ttu-id="a329d-138">21</span><span class="sxs-lookup"><span data-stu-id="a329d-138">21</span></span>  <br/> | <span data-ttu-id="a329d-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="a329d-140">22</span><span class="sxs-lookup"><span data-stu-id="a329d-140">22</span></span>  <br/> | <span data-ttu-id="a329d-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="a329d-142">23</span><span class="sxs-lookup"><span data-stu-id="a329d-142">23</span></span>  <br/> | <span data-ttu-id="a329d-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="a329d-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="a329d-144">24</span><span class="sxs-lookup"><span data-stu-id="a329d-144">24</span></span>  <br/> | <span data-ttu-id="a329d-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="a329d-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="a329d-146">25</span><span class="sxs-lookup"><span data-stu-id="a329d-146">25</span></span>  <br/> | <span data-ttu-id="a329d-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="a329d-148">101</span><span class="sxs-lookup"><span data-stu-id="a329d-148">101</span></span>  <br/> |<span data-ttu-id="a329d-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="a329d-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="a329d-150">102</span><span class="sxs-lookup"><span data-stu-id="a329d-150">102</span></span>  <br/> |<span data-ttu-id="a329d-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="a329d-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="a329d-152">103</span><span class="sxs-lookup"><span data-stu-id="a329d-152">103</span></span>  <br/> |<span data-ttu-id="a329d-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="a329d-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="a329d-154">104</span><span class="sxs-lookup"><span data-stu-id="a329d-154">104</span></span>  <br/> |<span data-ttu-id="a329d-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="a329d-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="a329d-156">105</span><span class="sxs-lookup"><span data-stu-id="a329d-156">105</span></span>  <br/> |<span data-ttu-id="a329d-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="a329d-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="a329d-158">106</span><span class="sxs-lookup"><span data-stu-id="a329d-158">106</span></span>  <br/> |<span data-ttu-id="a329d-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="a329d-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="a329d-160">107</span><span class="sxs-lookup"><span data-stu-id="a329d-160">107</span></span>  <br/> |<span data-ttu-id="a329d-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="a329d-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="a329d-162">108</span><span class="sxs-lookup"><span data-stu-id="a329d-162">108</span></span>  <br/> |<span data-ttu-id="a329d-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="a329d-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="a329d-164">109</span><span class="sxs-lookup"><span data-stu-id="a329d-164">109</span></span>  <br/> |<span data-ttu-id="a329d-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="a329d-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="a329d-166">201</span><span class="sxs-lookup"><span data-stu-id="a329d-166">201</span></span>  <br/> |<span data-ttu-id="a329d-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="a329d-168">202</span><span class="sxs-lookup"><span data-stu-id="a329d-168">202</span></span>  <br/> |<span data-ttu-id="a329d-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="a329d-170">203</span><span class="sxs-lookup"><span data-stu-id="a329d-170">203</span></span>  <br/> |<span data-ttu-id="a329d-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="a329d-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="a329d-172">204</span><span class="sxs-lookup"><span data-stu-id="a329d-172">204</span></span>  <br/> |<span data-ttu-id="a329d-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="a329d-174">205</span><span class="sxs-lookup"><span data-stu-id="a329d-174">205</span></span>  <br/> |<span data-ttu-id="a329d-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="a329d-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="a329d-176">206</span><span class="sxs-lookup"><span data-stu-id="a329d-176">206</span></span>  <br/> |<span data-ttu-id="a329d-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="a329d-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="a329d-178">207</span><span class="sxs-lookup"><span data-stu-id="a329d-178">207</span></span>  <br/> |<span data-ttu-id="a329d-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="a329d-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="a329d-180">208</span><span class="sxs-lookup"><span data-stu-id="a329d-180">208</span></span>  <br/> |<span data-ttu-id="a329d-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="a329d-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="a329d-182">301</span><span class="sxs-lookup"><span data-stu-id="a329d-182">301</span></span>  <br/> |<span data-ttu-id="a329d-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="a329d-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="a329d-184">401</span><span class="sxs-lookup"><span data-stu-id="a329d-184">401</span></span>  <br/> |<span data-ttu-id="a329d-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="a329d-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="a329d-186">402</span><span class="sxs-lookup"><span data-stu-id="a329d-186">402</span></span>  <br/> |<span data-ttu-id="a329d-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="a329d-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="a329d-188">403</span><span class="sxs-lookup"><span data-stu-id="a329d-188">403</span></span>  <br/> |<span data-ttu-id="a329d-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="a329d-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="a329d-190">404</span><span class="sxs-lookup"><span data-stu-id="a329d-190">404</span></span>  <br/> |<span data-ttu-id="a329d-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="a329d-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="a329d-192">405</span><span class="sxs-lookup"><span data-stu-id="a329d-192">405</span></span>  <br/> |<span data-ttu-id="a329d-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="a329d-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="a329d-194">406</span><span class="sxs-lookup"><span data-stu-id="a329d-194">406</span></span>  <br/> |<span data-ttu-id="a329d-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="a329d-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="a329d-196">407</span><span class="sxs-lookup"><span data-stu-id="a329d-196">407</span></span>  <br/> |<span data-ttu-id="a329d-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="a329d-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="a329d-198">408</span><span class="sxs-lookup"><span data-stu-id="a329d-198">408</span></span>  <br/> |<span data-ttu-id="a329d-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="a329d-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="a329d-200">501</span><span class="sxs-lookup"><span data-stu-id="a329d-200">501</span></span>  <br/> |<span data-ttu-id="a329d-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="a329d-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="a329d-202">502</span><span class="sxs-lookup"><span data-stu-id="a329d-202">502</span></span>  <br/> |<span data-ttu-id="a329d-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="a329d-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="a329d-204">**[QoeMetrics]. [Dbo]. [CallQualityFeedback]** Die folgende Tabelle enthält Abrufergebnisse aus "Stern" Stimmabgabe und Customer Feedback aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a329d-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="a329d-205">Daten von Tabellen mithilfe von aufgerufen werden können ein **auswählen \* aus [Table.Name]** Abfrage oder mithilfe von Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a329d-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="a329d-206">Die folgenden SQL-Abfragen können verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a329d-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="a329d-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="a329d-207">**Audio**</span></span>

```
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

 <span data-ttu-id="a329d-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="a329d-208">**Video**</span></span>

```
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

## <a name="updating-token-definitions"></a><span data-ttu-id="a329d-209">Aktualisieren von Token Definitionen</span><span class="sxs-lookup"><span data-stu-id="a329d-209">Updating Token Definitions</span></span>

<span data-ttu-id="a329d-210">Die neuesten Skype für Business Clients melden neues Problem Token IDs (\> 100), die möglicherweise nicht in Ihrer [QoeMetrics] vorhanden sein. [Dbo]. [CallQualityFeedbackTokenDef]-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a329d-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="a329d-211">So aktualisieren Sie die Datenbanktabelle mit den neuesten token Definitionen, die unter SQL-Befehl kann auf die Überwachungsdatenbank mit Microsoft SQL Server Management Studio ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a329d-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="a329d-212">Mit diesem Befehl werden alle Einträge in der [QoeMetrics] ersetzt. [Dbo]. [CallQualityFeedbackTokenDef]-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a329d-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```
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


