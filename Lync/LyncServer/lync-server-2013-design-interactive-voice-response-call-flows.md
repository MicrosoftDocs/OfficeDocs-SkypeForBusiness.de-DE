---
title: 'Lync Server 2013: entwerfen interaktiver VoIP-Antwort-Anruf Flüsse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649d085253610002e7623872012a400ac0a1f079
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498942"
---
# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="c2f5e-102">Entwerfen von interaktiven Anrufflüssen für Sprachantworten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f5e-102">Design interactive voice response call flows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2f5e-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c2f5e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c2f5e-104">Sie können die interaktive Sprachantwort (IVR) verwenden, um Informationen von Anrufern zu erhalten und den Anruf an die entsprechende Warteschlange weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-104">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="c2f5e-105">Fragen-und-Antwort-Paare bestimmen, welche Warteschlange verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-105">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="c2f5e-106">Je nach Antwort des Anrufers hört der Anrufer entweder eine Folgefrage oder wird an die entsprechende Warteschlange weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-106">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="c2f5e-107">Die IVR-Fragen und die Antworten des Anrufers werden dem antwortenden Agent zur Verfügung gestellt, der den Anruf annimmt und dem Agent wertvolle Informationen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-107">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="c2f5e-108">Übersicht über IVR-Features</span><span class="sxs-lookup"><span data-stu-id="c2f5e-108">Overview of IVR Features</span></span>

<span data-ttu-id="c2f5e-109">Das Reaktionsgruppenanwendung bietet Spracherkennung und Text-zu-Sprache-Funktionen in 26 Sprachen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="c2f5e-110">Sie können IVR-Fragen mithilfe von Text-zu-Sprache-oder einer Wave (WAV)-oder Windows Media-Audiodatei (WMA) eingeben.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="c2f5e-111">Anrufer können mit Sprach-oder DTMF-Antworten (Dual-Tone MultiFrequency) Antworten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="c2f5e-112">Interaktive Workflows unterstützen bis zu zwei Ebenen von Fragen, wobei jede Frage bis zu vier mögliche Antworten enthält.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-112">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="c2f5e-113">Die IVR fragt den Anrufer eine Frage ab und leitet den Anrufer in Abhängigkeit von der Antwort des Anrufers an eine Warteschleife weiter oder fragt eine zweite Frage.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-113">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="c2f5e-114">Die zweite Frage kann auch vier mögliche Antworten haben.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-114">The second question can also have four possible answers.</span></span> <span data-ttu-id="c2f5e-115">Je nach Antwort auf die Frage der zweiten Ebene wird der Anrufer an die entsprechende Warteschlange weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-115">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2f5e-116">Wenn Sie Anruf Flüsse mithilfe von lync Server-Verwaltungsshell entwerfen, können Sie beliebige Nummern Ebenen für IVR-Fragen und eine beliebige Anzahl von Antworten definieren.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="c2f5e-117">Für die Benutzerfreundlichkeit wird jedoch empfohlen, dass Sie nicht mehr als drei Fragen Ebenen mit jeweils nicht mehr als fünf Antworten verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="c2f5e-118">Wenn Sie darüber hinaus einen Anruffluss mit mehr als zwei Fragen Ebenen mit jeweils mehr als vier Antworten entwerfen, können Sie den Anruffluss nicht mithilfe lync Server 2013 Systemsteuerung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="c2f5e-119">Die IVR-Fragen und die Antworten des Anrufers werden dem antwortenden Agent zur Verfügung gestellt, der den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="c2f5e-120">Arbeiten mit Sprachtechnologien</span><span class="sxs-lookup"><span data-stu-id="c2f5e-120">Working with Speech Technologies</span></span>

<span data-ttu-id="c2f5e-121">Sprachtechnologien wie Spracherkennung und Text-zu-Sprache können die Benutzerfreundlichkeit verbessern und den Zugriff auf Informationen auf natürliche und effektive Weise ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="c2f5e-122">Es kann jedoch vorkommen, dass der angegebene Text oder die Benutzer Sprachantwort vom Sprachmodul nicht ordnungsgemäß erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="c2f5e-123">Beispielsweise \# wird das Symbol "" vom Text-zu-Sprache-Modul als Wort "Number" übersetzt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="c2f5e-124">Dieses Problem kann durch folgende Maßnahmen gemindert werden:</span><span class="sxs-lookup"><span data-stu-id="c2f5e-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="c2f5e-125">Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-125">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="c2f5e-126">Wenn der Anrufer die Frage falsch beantwortet (das heißt, dass die Antwort nicht eine der angegebenen Antworten ist) oder überhaupt keine Antwort gibt, erhält der Anrufer eine weitere Chance, die Frage zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-126">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="c2f5e-127">Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor er getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-127">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="c2f5e-128">Sie können die IVR so konfigurieren, dass eine benutzerdefinierte Nachricht nach jedem Fehler des Anrufers wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-128">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="c2f5e-129">Die Frage wird jedes Mal wiederholt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-129">The question is repeated each time.</span></span>

  - <span data-ttu-id="c2f5e-130">Verwenden Sie längere Antworten, um das Potenzial für Umgebungsgeräusche, die vom Sprachmodul als Antwort interpretiert werden, möglichst gering zu halten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-130">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="c2f5e-131">Antworten sollten beispielsweise mehr als eine Silbe haben und sich deutlich voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-131">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="c2f5e-132">Wenn Ihre Fragen sowohl sprach-als auch DTMF-Antworten haben, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept anstelle der DTMF-Antwort darstellen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-132">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="c2f5e-133">Verwenden Sie beispielsweise anstelle von "drücken oder sagen Sie eine" Verwendung "1 drücken oder sagen Sie Abrechnung."</span><span class="sxs-lookup"><span data-stu-id="c2f5e-133">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="c2f5e-134">Nachdem Sie Ihre IVR entworfen haben, rufen Sie den Workflow auf, hören Sie die Eingabeaufforderungen an, reagieren Sie auf alle Eingabeaufforderungen mit Voice, und überprüfen Sie, dass die IVR wie erwartet klingt und sich verhält.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="c2f5e-135">Anschließend können Sie die IVR so ändern, dass etwaige Interpretationsprobleme behoben werden.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="c2f5e-136">Wenn Sie sich im vorherigen Beispiel auf den Schlüssel berufen müssen \# , können Sie Ihre IVR-Ansage umschreiben, um anstelle des Symbols den Schlüsselnamen zu verwenden \# .</span><span class="sxs-lookup"><span data-stu-id="c2f5e-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="c2f5e-137">Wenn Sie beispielsweise "mit Vertrieb sprechen möchten, drücken Sie die Taste Pound".</span><span class="sxs-lookup"><span data-stu-id="c2f5e-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="c2f5e-138">IVR-Entwurfsbeispiele</span><span class="sxs-lookup"><span data-stu-id="c2f5e-138">IVR Design Examples</span></span>

<span data-ttu-id="c2f5e-139">Die folgenden Abschnitte enthalten Beispiele für unterschiedliche IVR-Szenarien und Frage-und-Antwort-Paare.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="c2f5e-140">IVR mit einer Frage Ebene</span><span class="sxs-lookup"><span data-stu-id="c2f5e-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="c2f5e-141">Das folgende Beispiel zeigt eine IVR, die eine Ebene mit Fragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-141">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="c2f5e-142">Es verwendet die Spracherkennung, um die Antwort des Anrufers zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-142">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="c2f5e-143">**Frage:** "Vielen Dank für den Aufruf der Personalabteilung.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-143">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="c2f5e-144">Wenn Sie mit der Gehaltsliste sprechen möchten, sagen Sie Payroll.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-144">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="c2f5e-145">Andernfalls sagen Sie HR. "</span><span class="sxs-lookup"><span data-stu-id="c2f5e-145">Otherwise, say HR."</span></span>

  - <span data-ttu-id="c2f5e-146">**Option 1 ist ausgewählt:** Der Anrufer wird an das Abrechnungsteam weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="c2f5e-147">**Option 2 ist ausgewählt:** Der Anrufer wird an das Team der Personalabteilung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="c2f5e-148">In der folgenden Abbildung ist der Anruffluss dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="c2f5e-149">**Interaktiver Anruffluss mit einer Ebene**</span><span class="sxs-lookup"><span data-stu-id="c2f5e-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="c2f5e-150">![Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.")</span><span class="sxs-lookup"><span data-stu-id="c2f5e-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="c2f5e-151">IVR mit zwei Ebenen von Fragen</span><span class="sxs-lookup"><span data-stu-id="c2f5e-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="c2f5e-152">Das folgende Beispiel zeigt eine IVR, die zwei Ebenen von Fragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-152">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="c2f5e-153">Anrufer können mit der Eingabe einer sprach-oder DTMF-Tastatur Antworten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-153">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="c2f5e-154">**Frage:** "Vielen Dank für Ihren Anruf beim IT-Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-154">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="c2f5e-155">Wenn Sie ein Netzwerkzugriffs Problem haben, drücken Sie die 1 oder sagen Sie "Netzwerk".</span><span class="sxs-lookup"><span data-stu-id="c2f5e-155">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="c2f5e-156">Wenn Sie ein Softwareproblem haben, drücken Sie die 2 oder sagen Sie Software.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-156">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="c2f5e-157">Wenn Sie ein Hardwareproblem haben, drücken Sie die 3 oder sagen Sie Hardware. "</span><span class="sxs-lookup"><span data-stu-id="c2f5e-157">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="c2f5e-158">**Option 1 ist ausgewählt:** Der Anrufer wird an das Netzwerk Support Team weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="c2f5e-159">**Option 2 ist ausgewählt:** Dem Anrufer wird eine weitere Frage gestellt:</span><span class="sxs-lookup"><span data-stu-id="c2f5e-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="c2f5e-160">**Frage:** "Wenn es sich um ein Betriebssystemproblem handelt, drücken Sie die 1 oder sagen Sie Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-160">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="c2f5e-161">Wenn es sich um ein Problem mit einer internen Anwendung handelt, drücken Sie die 2 oder sagen Sie die interne Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-161">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="c2f5e-162">Andernfalls drücken Sie die 3 oder sagen andere. "</span><span class="sxs-lookup"><span data-stu-id="c2f5e-162">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="c2f5e-163">**Option 1 ist ausgewählt:** Der Anrufer wird an das Support Team für Betriebssysteme weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="c2f5e-164">**Option 2 ist ausgewählt:** Der Anrufer wird an das Support Team für interne Anwendungen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="c2f5e-165">**Option 3 ist ausgewählt:** Der Anrufer wird an das Software Support Team weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="c2f5e-166">**Option 3 ist ausgewählt:** Dem Anrufer wird eine weitere Frage gestellt:</span><span class="sxs-lookup"><span data-stu-id="c2f5e-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="c2f5e-167">**Frage:** "Wenn es sich um ein Drucker Problem handelt, drücken Sie die 1.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-167">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="c2f5e-168">Drücken Sie andernfalls 2. "</span><span class="sxs-lookup"><span data-stu-id="c2f5e-168">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="c2f5e-169">**Option 1 ist ausgewählt:** Der Anrufer wird an das Support Team des Druckers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="c2f5e-170">**Option 2 ist ausgewählt:** Der Anrufer wird an das Team für den Hardware Support weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="c2f5e-171">In der folgenden Abbildung ist der Anruffluss dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="c2f5e-172">**Interaktiver Anruffluss mit zwei Ebenen**</span><span class="sxs-lookup"><span data-stu-id="c2f5e-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="c2f5e-173">![Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.")</span><span class="sxs-lookup"><span data-stu-id="c2f5e-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="c2f5e-174">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="c2f5e-174">Best Practices</span></span>

<span data-ttu-id="c2f5e-175">In der folgenden Liste werden einige bewährte Methoden für das Entwerfen Ihrer IVR beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c2f5e-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="c2f5e-176">Lassen Sie den Anrufer schnell zur Aufgabe gelangen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-176">Let the caller get to the task quickly.</span></span> <span data-ttu-id="c2f5e-177">Vermeiden Sie es, zu viele Informationen oder langwierige Marketingnachrichten in ihrer IVR bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-177">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="c2f5e-178">Wenn Sie eine lange Nachricht einbeziehen möchten, können Sie Sie an die erste Frage und nicht an die Willkommensnachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-178">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="c2f5e-179">Anrufer können die Nachricht umgehen, wenn Sie Teil der ersten Frage ist, indem Sie die Frage beantworten, aber die Willkommensnachricht kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-179">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="c2f5e-180">Sprechen Sie in der Sprache des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-180">Speak in the caller’s language.</span></span> <span data-ttu-id="c2f5e-181">Vermeiden Sie eine Gestelzte Sprache.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-181">Avoid stilted language.</span></span> <span data-ttu-id="c2f5e-182">Sprechen Sie natürlich.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-182">Speak naturally.</span></span>

  - <span data-ttu-id="c2f5e-183">Schreiben Sie effiziente und effektive Eingabeaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-183">Write efficient and effective prompts.</span></span> <span data-ttu-id="c2f5e-184">Entfernen Sie alle unnötigen Optionen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-184">Remove any unnecessary options.</span></span> <span data-ttu-id="c2f5e-185">Strukturieren Sie die Informationen so, dass die erwartete Antwort des Anrufers am Ende des Satzes liegt.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-185">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="c2f5e-186">Wenn Sie beispielsweise "mit dem Verkaufsteam sprechen möchten, drücken Sie die 1."</span><span class="sxs-lookup"><span data-stu-id="c2f5e-186">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="c2f5e-187">Sprachantworten benutzerfreundlich gestalten.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-187">Make voice responses user friendly.</span></span> <span data-ttu-id="c2f5e-188">Wenn Sie beispielsweise sowohl DTMF-als auch Sprachantworten angeben, verwenden Sie Folgendes wie: "um mit dem Vertriebsteam zu sprechen, drücken Sie die 1 oder sagen Sie" Umsatz ".</span><span class="sxs-lookup"><span data-stu-id="c2f5e-188">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="c2f5e-189">Testen Sie die IVR für eine Gruppe von Benutzern, bevor Sie Sie in Ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c2f5e-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

