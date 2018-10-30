---
title: 'Lync Server 2013: Entwerfen von Anrufflüssen für interaktive Sprachantwort'
TOCTitle: Entwerfen von Anrufflüssen für interaktive Sprachantwort
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413020(v=OCS.15)
ms:contentKeyID: 49295885
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entwerfen von Anrufflüssen für interaktive Sprachantwort in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Sie können die interaktive Sprachantwort (Interactive Voice Response, IVR) verwenden, um Informationen bei Anrufern abzufragen und den Anruf an die richtige Warteschleife zu leiten. Frage/Antwort-Paare bestimmten, welche Warteschleife verwendet wird. Je nach Antwort des Anrufers hört dieser entweder eine weitere Frage oder wird an die geeignete Warteschleife weitergeleitet. Die IVR-Fragen und die Antworten des Anrufers werden dem zuständigen Agent angezeigt, der den Anruf annimmt, sodass dem Agent wertvolle Informationen bereitgestellt werden.

## Übersicht über die Funktionen der interaktiven Sprachantwort (IVR)

Die Reaktionsgruppenanwendung bietet Spracherkennung und Text-zu-Sprache-Funktionen in 26 Sprachen. Sie können IVR-Fragen eingeben, indem Sie die Text-zu-Sprache-Funktion oder eine WAV- oder WMA-Datei (Windows Media Audio) verwenden. Anrufer können per Spracheingabe oder Tastendruck (MFV) antworten.

Interaktive Workflows unterstützen bis zu zwei Frageebenen mit jeweils vier möglichen Antworten. Dem Anrufer wird vom interaktiven Sprachantwortsystem eine Frage gestellt. Je nachdem, wie der Anrufer die Frage beantwortet, wird er entweder in einer Warteschleife platziert, oder es wird ihm eine zweite Frage gestellt. Die zweite Frage kann ebenfalls vier mögliche Antworten haben. Abhängig von der Antwort auf die Frage der zweiten Ebene wird der Anrufer an die geeignete Warteschleife weitergeleitet.


> [!NOTE]
> Wenn Sie Anrufflüsse mithilfe der Lync Server-Verwaltungsshell entwerfen, können Sie eine beliebige Anzahl von Ebenen für IVR-Fragen und eine beliebige Anzahl von Antworten definieren. Aus Gründen der Benutzerfreundlichkeit wird jedoch empfohlen, nicht mehr als drei Frageebenen und pro Ebene nicht mehr als fünf Antworten zu definieren. Darüber hinaus kann ein Anruffluss, der über mehr als zwei Frageebenen und pro Ebene über mehr als vier Antworten verfügt, nicht mithilfe der Systemsteuerung für Lync Server 2013 bearbeitet werden.



Die IVR-Fragen und die Antworten des Anrufers werden dem zuständigen Agent angezeigt, der den Anruf annimmt.

## Arbeiten mit Sprachtechnologien

Sprachtechnologien, wie beispielsweise Spracherkennung und Text-zu-Sprache (Sprachsynthese), können die Benutzerfreundlichkeit verbessern und Benutzern einen intuitiveren und einfacheren Zugriff auf Informationen bieten. Es kann jedoch vorkommen, dass der angegebene Text oder die Sprachantwort des Benutzers vom Sprachmodul nicht richtig erkannt wird. Das Symbol "\#" wird vom Text-zu-Sprache-Modul z. B. als das Wort "Nummer" übersetzt. Diesem Problem kann wie folgt entgegengewirkt werden:

  - Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten. Wenn der Anrufer die Frage falsch beantwortet (die Antwort also keiner der angegebenen Antworten entspricht) oder keine Antwort gibt, erhält er eine weitere Möglichkeit, die Frage zu beantworten. Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor die Verbindung getrennt wird. Sie können das interaktive Sprachantwortsystem so konfigurieren, dass nach einem Anruferfehler eine benutzerdefinierte Nachricht wiedergegeben wird. Die Frage wird jedes Mal wiederholt.

  - Um zu vermeiden, dass Hintergrundgeräusche vom Sprachmodul als Antwort erkannt werden, sollten Sie längere Antworten verwenden. Antworten sollten beispielsweise mehr als eine Silbe umfassen und sich deutlich voneinander unterscheiden.

  - Wenn für Fragen sowohl eine Antwort per Spracheingabe als auch per Tastendruck möglich ist, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept widerspiegeln, statt auf die Taste zu verweisen. Verwenden Sie beispielsweise anstelle von "Drücken oder sagen Sie 1" die Ansage "Drücken Sie die 1, oder sagen Sie Rechnung".

  - Rufen Sie den Workflow nach dem Entwerfen der interaktiven Sprachantwort an, hören Sie sich die Ansagen an, reagieren Sie auf alle Ansagen per Spracheingabe, und überprüfen Sie, ob die interaktive Sprachantwort (IVR) sich wie gewünscht anhört und verhält. Anschließend können Sie den Workflow bearbeiten, um etwaige Interpretationsfehler zu beheben. Wenn Sie wie im vorgenannten Beispiel auf die Taste "\#" verweisen müssen, können Sie die IVR-Ansage so umschreiben, dass der Name der Taste und nicht das Symbol "\#" verwendet wird. Beispiel: "Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die Rautetaste."

## IVR-Entwurfsbeispiele

Die folgenden Abschnitte zeigen Beispiele für unterschiedliche IVR-Szenarien und Frage/Antwort-Paare.

## IVR mit einer Frageebene

Das folgende Beispiel zeigt einen IVR-Entwurf mit einer Frageebene. Dabei wird die Spracherkennung verwendet, um die Antwort des Anrufers zu erfassen.

**Frage:** "Willkommen bei der Personalabteilung. Falls Sie mit der Lohnbuchhaltung sprechen möchten, sagen Sie 'Lohnbuchhaltung'. Sagen Sie andernfalls 'Personalabteilung'".

  - **Option 1 wurde gewählt:** Der Anrufer wird an das Team der Lohnbuchhaltung weitergeleitet.

  - **Option 2 wurde gewählt:** Der Anrufer wird an das Team der Personalabteilung weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

**Interaktiver Anruffluss mit einer Ebene**

![Entwerfen von Anrufflüssen per interaktiver Sprachantwort (IVR)](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Entwerfen von Anrufflüssen per interaktiver Sprachantwort (IVR)")

## IVR mit zwei Frageebenen

Das folgende Beispiel zeigt einen IVR-Entwurf mit zwei Frageebenen. Dabei können Anrufer entweder per Spracheingabe oder per Tastendruck (MFV) antworten.

**Frage:** "Willkommen beim IT-Helpdesk. Wenn Sie ein Problem mit dem Netzwerkzugriff haben, drücken Sie 1 oder sagen Sie "Netzwerk". Wenn Sie ein Softwareproblem haben, drücken Sie 2 oder sagen Sie "Software". Wenn Sie ein Hardwareproblem haben, drücken Sie 3 oder sagen Sie "Hardware"."

  - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Netzwerksupport weitergeleitet.

  - **Option 2 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.
    
    **Frage:** "Wenn Sie ein Problem mit dem Betriebssystem haben, drücken Sie 1 oder sagen Sie "Betriebssystem". Wenn Sie ein Problem mit einer internen Anwendung haben, drücken Sie 2 oder sagen Sie "interne Anwendung". Andernfalls drücken Sie 3 oder sagen Sie "Sonstiges"."
    
      - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Betriebssystemsupport weitergeleitet.
    
      - **Option 2 wurde gewählt:** Der Anrufer wird an das Supportteam für interne Anwendungen weitergeleitet.
    
      - **Option 3 wurde gewählt:** Der Anrufer wird an das Team für den Softwaresupport weitergeleitet.

  - **Option 3 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.
    
    **Frage:** "Wenn Sie ein Problem mit dem Drucker haben, drücken Sie die 1. Andernfalls drücken Sie die 2."
    
      - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Druckersupport weitergeleitet.
    
      - **Option 2 wurde gewählt:** Der Anrufer wird an das Team für den Hardwaresupport weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

**Interaktiver Anruffluss mit zwei Ebenen**

![Entwerfen von Anrufflüssen per interaktiver Sprachantwort (IVR)](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Entwerfen von Anrufflüssen per interaktiver Sprachantwort (IVR)")

## Bewährte Methoden

In der folgenden Liste werden einige bewährte Methoden für das Entwerfen der interaktiven Sprachantwort beschrieben:

  - Leiten Sie den Anrufer schnell an die gewünschte Kontaktperson weiter. Vermeiden Sie interaktive Sprachantworten mit zu vielen Informationen und langen Marketingbotschaften.

  - Wenn Sie eine lange Nachricht verwenden möchten, hängen Sie diese eher an die erste Frage statt an die Willkommensnachricht an. Anrufer können die Nachricht durch Beantwortung der Frage umgehen, wenn sie Teil der ersten Frage ist. Eine Umgehung der Willkommensnachricht ist jedoch nicht möglich.

  - Sprechen Sie die Sprache des Anrufers. Vermeiden Sie eine gestelzte Ausdrucksweise. Sprechen Sie natürlich.

  - Formulieren Sie effiziente und effektive Anweisungen. Entfernen Sie unnötige Optionen. Achten Sie beim Strukturieren der Informationen darauf, dass die erwartete Antwort des Anrufers am Ende des Satzes genannt wird. Beispiel: "Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1."

  - Gestalten Sie Sprachantworten benutzerfreundlich. Wenn beispielsweise sowohl eine Antwort per Spracheingabe als auch eine Antwort per Tastendruck zulässig ist, verwenden Sie eine Formulierung wie diese: "Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1, oder sagen Sie 'Vertrieb'".

  - Testen Sie den IVR-Workflow in einer Gruppe von Benutzern, bevor Sie ihn in Ihrer Organisation bereitstellen.

