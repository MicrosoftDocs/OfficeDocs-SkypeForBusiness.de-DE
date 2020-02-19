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
ms.openlocfilehash: 428d1d40b32c8dfaec3b897549409016f2cb6984
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Entwerfen von interaktiven Anrufflüssen für Sprachantworten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Sie können die interaktive Sprachantwort (IVR) verwenden, um Informationen von Anrufern zu erhalten und den Anruf an die entsprechende Warteschlange weiterzuleiten. Fragen-und-Antwort-Paare bestimmen, welche Warteschlange verwendet werden soll. Je nach Antwort des Anrufers hört der Anrufer entweder eine Folgefrage oder wird an die entsprechende Warteschlange weitergeleitet. Die IVR-Fragen und die Antworten des Anrufers werden dem antwortenden Agent zur Verfügung gestellt, der den Anruf annimmt und dem Agent wertvolle Informationen zur Verfügung stellt.

<div>

## <a name="overview-of-ivr-features"></a>Übersicht über IVR-Features

Das Reaktionsgruppenanwendung bietet Spracherkennung und Text-zu-Sprache-Funktionen in 26 Sprachen. Sie können IVR-Fragen mithilfe von Text-zu-Sprache-oder einer Wave (WAV)-oder Windows Media-Audiodatei (WMA) eingeben. Anrufer können mit Sprach-oder DTMF-Antworten (Dual-Tone MultiFrequency) Antworten.

Interaktive Workflows unterstützen bis zu zwei Ebenen von Fragen, wobei jede Frage bis zu vier mögliche Antworten enthält. Die IVR fragt den Anrufer eine Frage ab und leitet den Anrufer in Abhängigkeit von der Antwort des Anrufers an eine Warteschleife weiter oder fragt eine zweite Frage. Die zweite Frage kann auch vier mögliche Antworten haben. Je nach Antwort auf die Frage der zweiten Ebene wird der Anrufer an die entsprechende Warteschlange weitergeleitet.

<div>


> [!NOTE]  
> Wenn Sie Anruf Flüsse mithilfe von lync Server-Verwaltungsshell entwerfen, können Sie beliebige Nummern Ebenen für IVR-Fragen und eine beliebige Anzahl von Antworten definieren. Für die Benutzerfreundlichkeit wird jedoch empfohlen, dass Sie nicht mehr als drei Fragen Ebenen mit jeweils nicht mehr als fünf Antworten verwenden. Wenn Sie darüber hinaus einen Anruffluss mit mehr als zwei Fragen Ebenen mit jeweils mehr als vier Antworten entwerfen, können Sie den Anruffluss nicht mithilfe lync Server 2013 Systemsteuerung bearbeiten.



</div>

Die IVR-Fragen und die Antworten des Anrufers werden dem antwortenden Agent zur Verfügung gestellt, der den Anruf annimmt.

</div>

<div>

## <a name="working-with-speech-technologies"></a>Arbeiten mit Sprachtechnologien

Sprachtechnologien wie Spracherkennung und Text-zu-Sprache können die Benutzerfreundlichkeit verbessern und den Zugriff auf Informationen auf natürliche und effektive Weise ermöglichen. Es kann jedoch vorkommen, dass der angegebene Text oder die Benutzer Sprachantwort vom Sprachmodul nicht ordnungsgemäß erkannt wird. Beispielsweise wird das Symbol\#"" vom Text-zu-Sprache-Modul als Wort "Number" übersetzt. Dieses Problem kann durch folgende Maßnahmen gemindert werden:

  - Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten. Wenn der Anrufer die Frage falsch beantwortet (das heißt, dass die Antwort nicht eine der angegebenen Antworten ist) oder überhaupt keine Antwort gibt, erhält der Anrufer eine weitere Chance, die Frage zu beantworten. Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor er getrennt wird. Sie können die IVR so konfigurieren, dass eine benutzerdefinierte Nachricht nach jedem Fehler des Anrufers wiedergegeben wird. Die Frage wird jedes Mal wiederholt.

  - Verwenden Sie längere Antworten, um das Potenzial für Umgebungsgeräusche, die vom Sprachmodul als Antwort interpretiert werden, möglichst gering zu halten. Antworten sollten beispielsweise mehr als eine Silbe haben und sich deutlich voneinander unterscheiden.

  - Wenn Ihre Fragen sowohl sprach-als auch DTMF-Antworten haben, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept anstelle der DTMF-Antwort darstellen. Verwenden Sie beispielsweise anstelle von "drücken oder sagen Sie eine" Verwendung "1 drücken oder sagen Sie Abrechnung."

  - Nachdem Sie Ihre IVR entworfen haben, rufen Sie den Workflow auf, hören Sie die Eingabeaufforderungen an, reagieren Sie auf alle Eingabeaufforderungen mit Voice, und überprüfen Sie, dass die IVR wie erwartet klingt und sich verhält. Anschließend können Sie die IVR so ändern, dass etwaige Interpretationsprobleme behoben werden. Wenn Sie sich im vorherigen Beispiel auf den \# Schlüssel berufen müssen, können Sie Ihre IVR-Ansage umschreiben, um anstelle des \# Symbols den Schlüsselnamen zu verwenden. Wenn Sie beispielsweise "mit Vertrieb sprechen möchten, drücken Sie die Taste Pound".

</div>

<div>

## <a name="ivr-design-examples"></a>IVR-Entwurfsbeispiele

Die folgenden Abschnitte enthalten Beispiele für unterschiedliche IVR-Szenarien und Frage-und-Antwort-Paare.

<div>

## <a name="ivr-with-one-level-of-questions"></a>IVR mit einer Frage Ebene

Das folgende Beispiel zeigt eine IVR, die eine Ebene mit Fragen verwendet. Es verwendet die Spracherkennung, um die Antwort des Anrufers zu erkennen.

**Frage:** "Vielen Dank für den Aufruf der Personalabteilung. Wenn Sie mit der Gehaltsliste sprechen möchten, sagen Sie Payroll. Andernfalls sagen Sie HR. "

  - **Option 1 ist ausgewählt:** Der Anrufer wird an das Abrechnungsteam weitergeleitet.

  - **Option 2 ist ausgewählt:** Der Anrufer wird an das Team der Personalabteilung weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

**Interaktiver Anruffluss mit einer Ebene**

![Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.")

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>IVR mit zwei Ebenen von Fragen

Das folgende Beispiel zeigt eine IVR, die zwei Ebenen von Fragen verwendet. Anrufer können mit der Eingabe einer sprach-oder DTMF-Tastatur Antworten.

**Frage:** "Vielen Dank für Ihren Anruf beim IT-Helpdesk. Wenn Sie ein Netzwerkzugriffs Problem haben, drücken Sie die 1 oder sagen Sie "Netzwerk". Wenn Sie ein Softwareproblem haben, drücken Sie die 2 oder sagen Sie Software. Wenn Sie ein Hardwareproblem haben, drücken Sie die 3 oder sagen Sie Hardware. "

  - **Option 1 ist ausgewählt:** Der Anrufer wird an das Netzwerk Support Team weitergeleitet.

  - **Option 2 ist ausgewählt:** Dem Anrufer wird eine weitere Frage gestellt:
    
    **Frage:** "Wenn es sich um ein Betriebssystemproblem handelt, drücken Sie die 1 oder sagen Sie Betriebssystem. Wenn es sich um ein Problem mit einer internen Anwendung handelt, drücken Sie die 2 oder sagen Sie die interne Anwendung. Andernfalls drücken Sie die 3 oder sagen andere. "
    
      - **Option 1 ist ausgewählt:** Der Anrufer wird an das Support Team für Betriebssysteme weitergeleitet.
    
      - **Option 2 ist ausgewählt:** Der Anrufer wird an das Support Team für interne Anwendungen weitergeleitet.
    
      - **Option 3 ist ausgewählt:** Der Anrufer wird an das Software Support Team weitergeleitet.

  - **Option 3 ist ausgewählt:** Dem Anrufer wird eine weitere Frage gestellt:
    
    **Frage:** "Wenn es sich um ein Drucker Problem handelt, drücken Sie die 1. Drücken Sie andernfalls 2. "
    
      - **Option 1 ist ausgewählt:** Der Anrufer wird an das Support Team des Druckers weitergeleitet.
    
      - **Option 2 ist ausgewählt:** Der Anrufer wird an das Team für den Hardware Support weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

**Interaktiver Anruffluss mit zwei Ebenen**

![Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Entwerfen von Anrufflüssen mithilfe von Interactive Voice resp.")

</div>

</div>

<div>

## <a name="best-practices"></a>Bewährte Methoden

In der folgenden Liste werden einige bewährte Methoden für das Entwerfen Ihrer IVR beschrieben:

  - Lassen Sie den Anrufer schnell zur Aufgabe gelangen. Vermeiden Sie es, zu viele Informationen oder langwierige Marketingnachrichten in ihrer IVR bereitzustellen.

  - Wenn Sie eine lange Nachricht einbeziehen möchten, können Sie Sie an die erste Frage und nicht an die Willkommensnachricht anfügen. Anrufer können die Nachricht umgehen, wenn Sie Teil der ersten Frage ist, indem Sie die Frage beantworten, aber die Willkommensnachricht kann nicht umgangen werden.

  - Sprechen Sie in der Sprache des Anrufers. Vermeiden Sie eine Gestelzte Sprache. Sprechen Sie natürlich.

  - Schreiben Sie effiziente und effektive Eingabeaufforderungen. Entfernen Sie alle unnötigen Optionen. Strukturieren Sie die Informationen so, dass die erwartete Antwort des Anrufers am Ende des Satzes liegt. Wenn Sie beispielsweise "mit dem Verkaufsteam sprechen möchten, drücken Sie die 1."

  - Sprachantworten benutzerfreundlich gestalten. Wenn Sie beispielsweise sowohl DTMF-als auch Sprachantworten angeben, verwenden Sie Folgendes wie: "um mit dem Vertriebsteam zu sprechen, drücken Sie die 1 oder sagen Sie" Umsatz ".

  - Testen Sie die IVR für eine Gruppe von Benutzern, bevor Sie Sie in Ihrer Organisation bereitstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

