---
title: 'Lync Server 2013: Entwerfen von Anrufflüssen für interaktive Sprachantwort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487fa3d4842ad67f3433966a08a889e454450351
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="0c7be-102">Entwerfen von Anrufflüssen für interaktive Sprachantwort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c7be-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7be-103">_**Letztes Änderungsdatum des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0c7be-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0c7be-p101">Sie können die interaktive Sprachantwort (Interactive Voice Response, IVR) verwenden, um Informationen bei Anrufern abzufragen und den Anruf an die richtige Warteschleife zu leiten. Frage/Antwort-Paare bestimmten, welche Warteschleife verwendet wird. Je nach Antwort des Anrufers hört dieser entweder eine weitere Frage oder wird an die geeignete Warteschleife weitergeleitet. Die IVR-Fragen und die Antworten des Anrufers werden dem zuständigen Agent angezeigt, der den Anruf annimmt, sodass dem Agent wertvolle Informationen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="0c7be-108">Übersicht über die Funktionen der interaktiven Sprachantwort (IVR)</span><span class="sxs-lookup"><span data-stu-id="0c7be-108">Overview of IVR Features</span></span>

<span data-ttu-id="0c7be-109">Die reaktionsgruppenanwendung bietet Spracherkennung und Text-zu-Sprache-Funktionen in 26 Sprachen.</span><span class="sxs-lookup"><span data-stu-id="0c7be-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="0c7be-110">Sie können IVR-Fragen mithilfe von Text-zu-Sprache-oder einer Wave-Datei (WAV) oder Windows Media Audio (WMA) eingeben.</span><span class="sxs-lookup"><span data-stu-id="0c7be-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="0c7be-111">Anrufer können mithilfe von Sprach-oder Dual-Tone-mehr Frequenz-Antworten (DTMF) Antworten.</span><span class="sxs-lookup"><span data-stu-id="0c7be-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="0c7be-p103">Interaktive Workflows unterstützen bis zu zwei Frageebenen mit jeweils vier möglichen Antworten. Dem Anrufer wird vom interaktiven Sprachantwortsystem eine Frage gestellt. Je nachdem, wie der Anrufer die Frage beantwortet, wird er entweder in einer Warteschleife platziert oder es wird ihm eine zweite Frage gestellt. Die zweite Frage kann ebenfalls vier mögliche Antworten haben. Abhängig von der Antwort auf die Frage der zweiten Ebene wird der Anrufer an die geeignete Warteschleife weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c7be-116">Wenn Sie Anruf Flüsse mithilfe der lync Server-Verwaltungsshell entwerfen, können Sie beliebige Anzahl Ebenen von IVR-Fragen und eine beliebige Anzahl von Antworten definieren.</span><span class="sxs-lookup"><span data-stu-id="0c7be-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="0c7be-117">Aus Gründen der Benutzerfreundlichkeit wird jedoch empfohlen, nicht mehr als drei Frageebenen und pro Ebene nicht mehr als fünf Antworten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0c7be-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="0c7be-118">Wenn Sie einen Anruffluss entwerfen, der über mehr als zwei Fragen Ebenen mit jeweils mehr als vier Antworten verfügt, können Sie den Anruffluss nicht mithilfe der lync Server 2013-Systemsteuerung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0c7be-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="0c7be-119">Die IVR-Fragen und die Antworten des Anrufers werden dem zuständigen Agent angezeigt, der den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="0c7be-120">Arbeiten mit Sprachtechnologien</span><span class="sxs-lookup"><span data-stu-id="0c7be-120">Working with Speech Technologies</span></span>

<span data-ttu-id="0c7be-121">Sprachtechnologien, wie beispielsweise Spracherkennung und Text-zu-Sprache (Sprachsynthese), können die Benutzerfreundlichkeit verbessern und Benutzern einen intuitiveren und einfacheren Zugriff auf Informationen bieten.</span><span class="sxs-lookup"><span data-stu-id="0c7be-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="0c7be-122">Es kann jedoch vorkommen, dass der angegebene Text oder die Sprachantwort des Benutzers vom Sprachmodul nicht richtig erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7be-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="0c7be-123">So wird beispielsweise das\#Symbol "" vom Text-zu-Sprache-Modul als Wort "Zahl" übersetzt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="0c7be-124">Diesem Problem kann wie folgt entgegengewirkt werden:</span><span class="sxs-lookup"><span data-stu-id="0c7be-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="0c7be-p106">Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten. Wenn der Anrufer die Frage falsch beantwortet (die Antwort also keiner der angegebenen Antworten entspricht) oder keine Antwort gibt, erhält er eine weitere Möglichkeit, die Frage zu beantworten. Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor die Verbindung getrennt wird. Sie können das interaktive Sprachantwortsystem so konfigurieren, dass nach einem Anruferfehler eine benutzerdefinierte Nachricht wiedergegeben wird. Die Frage wird jedes Mal wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="0c7be-p107">Um zu vermeiden, dass Hintergrundgeräusche vom Sprachmodul als Antwort erkannt werden, sollten Sie längere Antworten verwenden. Antworten sollten beispielsweise mehr als eine Silbe umfassen und sich deutlich voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="0c7be-p108">Wenn für Fragen sowohl eine Antwort per Spracheingabe als auch per Tastendruck (MFV) möglich ist, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept widerspiegeln, statt auf die Taste zu verweisen. Verwenden Sie beispielsweise anstelle von „Drücken oder sagen Sie 1“ die Eingabeaufforderung „Drücken Sie die 1 oder sagen Sie Rechnung“.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="0c7be-134">Rufen Sie den Workflow nach dem Entwerfen der interaktiven Sprachantwort an, hören Sie sich die Eingabeaufforderungen an, reagieren Sie auf alle Eingabeaufforderungen per Spracheingabe und überprüfen Sie, ob die interaktive Sprachantwort (IVR) sich wie gewünscht anhört und verhält.</span><span class="sxs-lookup"><span data-stu-id="0c7be-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="0c7be-135">Anschließend können Sie den Workflow bearbeiten, um etwaige Interpretationsfehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="0c7be-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="0c7be-136">Wenn Sie nach dem vorherigen Beispiel auf den \# Schlüssel verweisen müssen, können Sie die IVR-Eingabeaufforderung neu schreiben, um den Schlüsselnamen anstelle des \# Symbols zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c7be-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="0c7be-137">Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die Rautetaste.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="0c7be-138">IVR-Entwurfsbeispiele</span><span class="sxs-lookup"><span data-stu-id="0c7be-138">IVR Design Examples</span></span>

<span data-ttu-id="0c7be-139">Die folgenden Abschnitte zeigen Beispiele für unterschiedliche IVR-Szenarien und Frage/Antwort-Paare.</span><span class="sxs-lookup"><span data-stu-id="0c7be-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="0c7be-140">IVR mit einer Frageebene</span><span class="sxs-lookup"><span data-stu-id="0c7be-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="0c7be-p110">Das folgende Beispiel zeigt einen IVR-Entwurf mit einer Frageebene. Dabei wird die Spracherkennung verwendet, um die Antwort des Anrufers zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="0c7be-p111">**Frage:** „Willkommen bei der Personalabteilung. Falls Sie mit der Lohnbuchhaltung sprechen möchten, sagen Sie ‚Lohnbuchhaltung‘ Sagen Sie andernfalls ‚Personalabteilung‘.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="0c7be-146">**Option 1 wurde gewählt:** Der Anrufer wird an das Team der Lohnbuchhaltung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="0c7be-147">**Option 2 wurde gewählt:** Der Anrufer wird an das Team der Personalabteilung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="0c7be-148">In der folgenden Abbildung ist der Anruffluss dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="0c7be-149">**Interaktiver Anruffluss mit einer Ebene**</span><span class="sxs-lookup"><span data-stu-id="0c7be-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="0c7be-150">![Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw] . (images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw") .</span><span class="sxs-lookup"><span data-stu-id="0c7be-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="0c7be-151">IVR mit zwei Frageebenen</span><span class="sxs-lookup"><span data-stu-id="0c7be-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="0c7be-p112">Das folgende Beispiel zeigt einen IVR-Entwurf mit zwei Frageebenen. Dabei können Anrufer entweder per Spracheingabe oder per Tastendruck (MFV) antworten.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="0c7be-p113">**Frage:** „Willkommen beim IT-Helpdesk. Wenn Sie ein Problem mit dem Netzwerkzugriff haben, drücken Sie die 1 oder sagen Sie ‚Netzwerk‘. Wenn Sie ein Softwareproblem haben, drücken Sie die 2 oder sagen Sie ‚Software‘. Wenn Sie ein Hardwareproblem haben, drücken Sie die 3 oder sagen Sie ‚Hardware‘.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="0c7be-158">**Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Netzwerksupport weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="0c7be-159">**Option 2 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="0c7be-p114">**Frage:** „Wenn Sie ein Problem mit dem Betriebssystem haben, drücken Sie die 1 oder sagen Sie ‚Betriebssystem‘. Wenn Sie ein Problem mit einer internen Anwendung haben, drücken Sie die 2 oder sagen Sie ‚interne Anwendung‘. Andernfalls drücken Sie die 3 oder sagen Sie ‚Sonstiges‘.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="0c7be-163">**Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Betriebssystemsupport weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="0c7be-164">**Option 2 wurde gewählt:** Der Anrufer wird an das Supportteam für interne Anwendungen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="0c7be-165">**Option 3 wurde gewählt:** Der Anrufer wird an das Team für den Softwaresupport weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="0c7be-166">**Option 3 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="0c7be-p115">**Frage:** „Wenn Sie ein Problem mit dem Drucker haben, drücken Sie die 1. Andernfalls drücken Sie die 2.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="0c7be-169">**Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Druckersupport weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="0c7be-170">**Option 2 wurde gewählt:** Der Anrufer wird an das Team für den Hardwaresupport weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c7be-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="0c7be-171">In der folgenden Abbildung ist der Anruffluss dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0c7be-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="0c7be-172">**Interaktiver Anruffluss mit zwei Ebenen**</span><span class="sxs-lookup"><span data-stu-id="0c7be-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="0c7be-173">![Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw] . (images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw") .</span><span class="sxs-lookup"><span data-stu-id="0c7be-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="0c7be-174">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="0c7be-174">Best Practices</span></span>

<span data-ttu-id="0c7be-175">In der folgenden Liste werden einige bewährte Methoden für das Entwerfen der interaktiven Sprachantwort beschrieben:</span><span class="sxs-lookup"><span data-stu-id="0c7be-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="0c7be-p116">Leiten Sie den Anrufer schnell an die gewünschte Kontaktperson weiter. Vermeiden Sie interaktive Sprachantworten mit zu vielen Informationen und langen Marketingbotschaften.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="0c7be-p117">Wenn Sie eine lange Nachricht verwenden möchten, hängen Sie diese eher an die erste Frage statt an die Willkommensnachricht an. Anrufer können die Nachricht durch Beantwortung der Frage umgehen, wenn sie Teil der ersten Frage ist. Eine Umgehung der Willkommensnachricht ist jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="0c7be-p118">Sprechen Sie die Sprache des Anrufers. Vermeiden Sie eine gestelzte Ausdrucksweise. Sprechen Sie natürlich.</span><span class="sxs-lookup"><span data-stu-id="0c7be-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="0c7be-p119">Formulieren Sie effiziente und effektive Anweisungen. Entfernen Sie unnötige Optionen. Achten Sie beim Strukturieren der Informationen darauf, dass die erwartete Antwort des Anrufers am Ende des Satzes genannt wird. Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="0c7be-p120">Gestalten Sie Sprachantworten benutzerfreundlich. Wenn beispielsweise sowohl eine Antwort per Spracheingabe als auch eine Antwort per Tastendruck (MFV) zulässig ist, verwenden Sie eine Formulierung wie diese: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1 oder sagen Sie ‚Vertrieb‘.“</span><span class="sxs-lookup"><span data-stu-id="0c7be-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="0c7be-189">Testen Sie den IVR-Workflow in einer Gruppe von Benutzern, bevor Sie ihn in Ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c7be-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

