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

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Entwerfen von Anrufflüssen für interaktive Sprachantwort in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Sie können die interaktive Sprachantwort (Interactive Voice Response, IVR) verwenden, um Informationen bei Anrufern abzufragen und den Anruf an die richtige Warteschleife zu leiten. Frage/Antwort-Paare bestimmten, welche Warteschleife verwendet wird. Je nach Antwort des Anrufers hört dieser entweder eine weitere Frage oder wird an die geeignete Warteschleife weitergeleitet. Die IVR-Fragen und die Antworten des Anrufers werden dem zuständigen Agent angezeigt, der den Anruf annimmt, sodass dem Agent wertvolle Informationen bereitgestellt werden.

<div>

## <a name="overview-of-ivr-features"></a>Übersicht über die Funktionen der interaktiven Sprachantwort (IVR)

Die reaktionsgruppenanwendung bietet Spracherkennung und Text-zu-Sprache-Funktionen in 26 Sprachen. Sie können IVR-Fragen mithilfe von Text-zu-Sprache-oder einer Wave-Datei (WAV) oder Windows Media Audio (WMA) eingeben. Anrufer können mithilfe von Sprach-oder Dual-Tone-mehr Frequenz-Antworten (DTMF) Antworten.

Interaktive Workflows unterstützen bis zu zwei Frageebenen mit jeweils vier möglichen Antworten. Dem Anrufer wird vom interaktiven Sprachantwortsystem eine Frage gestellt. Je nachdem, wie der Anrufer die Frage beantwortet, wird er entweder in einer Warteschleife platziert oder es wird ihm eine zweite Frage gestellt. Die zweite Frage kann ebenfalls vier mögliche Antworten haben. Abhängig von der Antwort auf die Frage der zweiten Ebene wird der Anrufer an die geeignete Warteschleife weitergeleitet.

<div>


> [!NOTE]  
> Wenn Sie Anruf Flüsse mithilfe der lync Server-Verwaltungsshell entwerfen, können Sie beliebige Anzahl Ebenen von IVR-Fragen und eine beliebige Anzahl von Antworten definieren. Aus Gründen der Benutzerfreundlichkeit wird jedoch empfohlen, nicht mehr als drei Frageebenen und pro Ebene nicht mehr als fünf Antworten zu definieren. Wenn Sie einen Anruffluss entwerfen, der über mehr als zwei Fragen Ebenen mit jeweils mehr als vier Antworten verfügt, können Sie den Anruffluss nicht mithilfe der lync Server 2013-Systemsteuerung bearbeiten.



</div>

Die IVR-Fragen und die Antworten des Anrufers werden dem zuständigen Agent angezeigt, der den Anruf annimmt.

</div>

<div>

## <a name="working-with-speech-technologies"></a>Arbeiten mit Sprachtechnologien

Sprachtechnologien, wie beispielsweise Spracherkennung und Text-zu-Sprache (Sprachsynthese), können die Benutzerfreundlichkeit verbessern und Benutzern einen intuitiveren und einfacheren Zugriff auf Informationen bieten. Es kann jedoch vorkommen, dass der angegebene Text oder die Sprachantwort des Benutzers vom Sprachmodul nicht richtig erkannt wird. So wird beispielsweise das\#Symbol "" vom Text-zu-Sprache-Modul als Wort "Zahl" übersetzt. Diesem Problem kann wie folgt entgegengewirkt werden:

  - Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten. Wenn der Anrufer die Frage falsch beantwortet (die Antwort also keiner der angegebenen Antworten entspricht) oder keine Antwort gibt, erhält er eine weitere Möglichkeit, die Frage zu beantworten. Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor die Verbindung getrennt wird. Sie können das interaktive Sprachantwortsystem so konfigurieren, dass nach einem Anruferfehler eine benutzerdefinierte Nachricht wiedergegeben wird. Die Frage wird jedes Mal wiederholt.

  - Um zu vermeiden, dass Hintergrundgeräusche vom Sprachmodul als Antwort erkannt werden, sollten Sie längere Antworten verwenden. Antworten sollten beispielsweise mehr als eine Silbe umfassen und sich deutlich voneinander unterscheiden.

  - Wenn für Fragen sowohl eine Antwort per Spracheingabe als auch per Tastendruck (MFV) möglich ist, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept widerspiegeln, statt auf die Taste zu verweisen. Verwenden Sie beispielsweise anstelle von „Drücken oder sagen Sie 1“ die Eingabeaufforderung „Drücken Sie die 1 oder sagen Sie Rechnung“.

  - Rufen Sie den Workflow nach dem Entwerfen der interaktiven Sprachantwort an, hören Sie sich die Eingabeaufforderungen an, reagieren Sie auf alle Eingabeaufforderungen per Spracheingabe und überprüfen Sie, ob die interaktive Sprachantwort (IVR) sich wie gewünscht anhört und verhält. Anschließend können Sie den Workflow bearbeiten, um etwaige Interpretationsfehler zu beheben. Wenn Sie nach dem vorherigen Beispiel auf den \# Schlüssel verweisen müssen, können Sie die IVR-Eingabeaufforderung neu schreiben, um den Schlüsselnamen anstelle des \# Symbols zu verwenden. Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die Rautetaste.“

</div>

<div>

## <a name="ivr-design-examples"></a>IVR-Entwurfsbeispiele

Die folgenden Abschnitte zeigen Beispiele für unterschiedliche IVR-Szenarien und Frage/Antwort-Paare.

<div>

## <a name="ivr-with-one-level-of-questions"></a>IVR mit einer Frageebene

Das folgende Beispiel zeigt einen IVR-Entwurf mit einer Frageebene. Dabei wird die Spracherkennung verwendet, um die Antwort des Anrufers zu erfassen.

**Frage:** „Willkommen bei der Personalabteilung. Falls Sie mit der Lohnbuchhaltung sprechen möchten, sagen Sie ‚Lohnbuchhaltung‘ Sagen Sie andernfalls ‚Personalabteilung‘.“

  - **Option 1 wurde gewählt:** Der Anrufer wird an das Team der Lohnbuchhaltung weitergeleitet.

  - **Option 2 wurde gewählt:** Der Anrufer wird an das Team der Personalabteilung weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

**Interaktiver Anruffluss mit einer Ebene**

![Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw] . (images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw") .

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>IVR mit zwei Frageebenen

Das folgende Beispiel zeigt einen IVR-Entwurf mit zwei Frageebenen. Dabei können Anrufer entweder per Spracheingabe oder per Tastendruck (MFV) antworten.

**Frage:** „Willkommen beim IT-Helpdesk. Wenn Sie ein Problem mit dem Netzwerkzugriff haben, drücken Sie die 1 oder sagen Sie ‚Netzwerk‘. Wenn Sie ein Softwareproblem haben, drücken Sie die 2 oder sagen Sie ‚Software‘. Wenn Sie ein Hardwareproblem haben, drücken Sie die 3 oder sagen Sie ‚Hardware‘.“

  - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Netzwerksupport weitergeleitet.

  - **Option 2 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.
    
    **Frage:** „Wenn Sie ein Problem mit dem Betriebssystem haben, drücken Sie die 1 oder sagen Sie ‚Betriebssystem‘. Wenn Sie ein Problem mit einer internen Anwendung haben, drücken Sie die 2 oder sagen Sie ‚interne Anwendung‘. Andernfalls drücken Sie die 3 oder sagen Sie ‚Sonstiges‘.“
    
      - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Betriebssystemsupport weitergeleitet.
    
      - **Option 2 wurde gewählt:** Der Anrufer wird an das Supportteam für interne Anwendungen weitergeleitet.
    
      - **Option 3 wurde gewählt:** Der Anrufer wird an das Team für den Softwaresupport weitergeleitet.

  - **Option 3 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.
    
    **Frage:** „Wenn Sie ein Problem mit dem Drucker haben, drücken Sie die 1. Andernfalls drücken Sie die 2.“
    
      - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Druckersupport weitergeleitet.
    
      - **Option 2 wurde gewählt:** Der Anrufer wird an das Team für den Hardwaresupport weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

**Interaktiver Anruffluss mit zwei Ebenen**

![Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw] . (images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Entwerfen von Anruf strömen mithilfe von Interactive Voice bzw") .

</div>

</div>

<div>

## <a name="best-practices"></a>Bewährte Methoden

In der folgenden Liste werden einige bewährte Methoden für das Entwerfen der interaktiven Sprachantwort beschrieben:

  - Leiten Sie den Anrufer schnell an die gewünschte Kontaktperson weiter. Vermeiden Sie interaktive Sprachantworten mit zu vielen Informationen und langen Marketingbotschaften.

  - Wenn Sie eine lange Nachricht verwenden möchten, hängen Sie diese eher an die erste Frage statt an die Willkommensnachricht an. Anrufer können die Nachricht durch Beantwortung der Frage umgehen, wenn sie Teil der ersten Frage ist. Eine Umgehung der Willkommensnachricht ist jedoch nicht möglich.

  - Sprechen Sie die Sprache des Anrufers. Vermeiden Sie eine gestelzte Ausdrucksweise. Sprechen Sie natürlich.

  - Formulieren Sie effiziente und effektive Anweisungen. Entfernen Sie unnötige Optionen. Achten Sie beim Strukturieren der Informationen darauf, dass die erwartete Antwort des Anrufers am Ende des Satzes genannt wird. Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1.“

  - Gestalten Sie Sprachantworten benutzerfreundlich. Wenn beispielsweise sowohl eine Antwort per Spracheingabe als auch eine Antwort per Tastendruck (MFV) zulässig ist, verwenden Sie eine Formulierung wie diese: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1 oder sagen Sie ‚Vertrieb‘.“

  - Testen Sie den IVR-Workflow in einer Gruppe von Benutzern, bevor Sie ihn in Ihrer Organisation bereitstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

