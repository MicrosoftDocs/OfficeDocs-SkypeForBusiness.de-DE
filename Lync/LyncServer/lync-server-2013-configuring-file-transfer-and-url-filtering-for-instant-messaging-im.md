---
title: Konfigurieren der Dateiübertragung und der URL-Filterung für Chat
TOCTitle: Konfigurieren der Dateiübertragung und der URL-Filterung für Chat
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520952(v=OCS.15)
ms:contentKeyID: 49293214
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Dateiübertragung und der URL-Filterung für Chat

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit dem Tool für intelligente Sofortnachrichtenfilter können Sie die Lync Server 2013-Bereitstellung mit minimaler Beeinträchtigung der Benutzerfreundlichkeit vor den häufigsten Formen von Viren schützen. Konfigurieren Sie mit dem intelligenten Sofortnachrichtenfilter Filter zum Blockieren unerwünschter oder potenziell schädlicher Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall. Zum Konfigurieren von Filtern geben Sie die Kriterien an, anhand derer die zu blockierenden Elemente (z. B. Sofortnachrichten mit Links, die bestimmte Präfixe enthalten, und Dateien mit bestimmten Erweiterungen) ermittelt werden sollen.

Der intelligente Sofortnachrichtenfilter bietet folgende Funktionen:

  - Verbesserte URL-Filterung.

  - Verbesserte Filterung von Dateiübertragungen.

Die Konfiguration des intelligenten Sofortnachrichtenfilters umfasst Folgendes:

  - Konfigurieren der URL-Filterung.

  - Konfigurieren der Filterung von Dateiübertragungen.

## So werden Filteroptionen auf Sofortnachrichten angewendet

Vor dem Bereitstellen des Tools für intelligente Sofortnachrichtenfilter müssen Sie verstehen, wie Filteroptionen auf Nachrichten angewendet werden, die von einem Server mit Lync Server 2013 an einen anderen Server weitergeleitet werden. Die Art der Anwendung von Filteroptionen ist konsistent. Dabei spielt es keine Rolle, ob die Server sich in einer einzigen Organisation oder in mehreren Organisationen befinden. Die Konsistenz betrifft die Art und Weise, wie benutzerdefinierte Hinweise und Warntexte in Nachrichten eingefügt und an Server gesendet werden.


> [!NOTE]
> Der Sofortnachrichtenfilter erhöht den Umfang der zum Verarbeiten von URLs in einer Nachricht erforderlichen CPU-Ressourcen. Diese erhöhten CPU-Anforderungen wirken sich auch auf die Leistung von Lync Server aus.



Auf der Seite **URL-Filter** der Gruppe **Chat und Anwesenheit** in der Lync Server-Systemsteuerung können Sie einige oder alle Links blockieren oder eine Warnung konfigurieren. Bei Auswahl der Option **Warnmeldung senden** für das **Linkpräfix** wird die Warnung am Anfang von Sofortnachrichten eingefügt, die einen Link enthalten.

Wenn eine Sofortnachricht zwischen Servern übermittelt wird, gelten die folgenden Grundsätze:

  - Wenn Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** auf der Seite **URL-Filter** aktivieren oder die Option **Links blockieren** für das Linkpräfix wählen, wird eine Fehlermeldung an den Client zurückgegeben, wenn ein Server eine Sofortnachricht blockiert. Nachfolgende Server empfangen diese Sofortnachricht nicht.

  - Wenn ein Server (Server1) eine Warnung zu einer Sofortnachricht mit einem aktiven Link hinzufügt, kann ein nachfolgender Server (Server2), der diese Sofortnachricht empfängt, eine andere Aktion für diesen aktiven Link in der Sofortnachricht ausführen und die Nachricht z. B. blockieren oder eine Warnung hinzufügen. Wenn Server2 so konfiguriert ist, dass er lediglich eine Warnung für diese URL hinzufügt, wird die frühere, von Server1 hinzugefügte Warnung entfernt, und die auf Server2 konfigurierte Warnung wird am Anfang der Sofortnachricht eingefügt.


> [!NOTE]
> Bei Ausführung von Lync Server 2013 in einer gemischten Umgebung ist mindestens Live Communications Server&nbsp;2005 mit SP1 erforderlich, um den intelligenten Sofortnachrichtenfilter zu verwenden. Der intelligente Sofortnachrichtenfilter wird in Live Communications Server&nbsp;2005 ohne SP1 nicht unterstützt.



## URL-Filterung

URLs werden basierend auf ihrem Linkpräfix gefiltert. Im Folgenden sind gültige Präfixe aufgeführt:

  - www\*.

  - ftp.

  - http:

Wenn Sie keinen Sofortnachrichtenfilter für die URL-Filterung konfigurieren, werden alle URLs in Sofortnachrichten unverändert über den Server übermittelt. Bei Konfiguration des Sofortnachrichtenfilters für die URL-Filterung werden URLs in Sofortnachrichten gemäß den Optionen gefiltert, die Sie im Dialogfeld **URL-Filter bearbeiten** oder **Neuer URL-Filter** auswählen.

  - **URL-Filter aktivieren**   Diese Option aktiviert die URL-Filterung für die globale Bereitstellung oder für den ausgewählten Standort.

  - **URLs mit Dateierweiterung blockieren**   Der Sofortnachrichtenfilter blockiert aktive Intranet- oder Internet-URLs mit Dateien, deren Erweiterungen im Dialogfeld **Dateifilter bearbeiten** unter **Dateityperweiterungen, die blockiert werden sollen** aufgeführt sind. Beim Blockieren einer URL wird dem Absender eine Fehlermeldung angezeigt. Bei Auswahl hat diese Option Vorrang vor allen anderen Filteroptionen für Dateierweiterungen, die unter **Dateityperweiterungen, die blockiert werden sollen** definiert sind.
    

    > [!IMPORTANT]
    > Die Filterung nach Dateierweiterungen ist auf Standarddateinamen beschränkt. Die Filterung funktioniert möglicherweise nicht, wenn Dateierweiterungen in anderen Namen enthalten sind.



Wählen Sie eine der folgenden Optionen unter **Linkpräfix** aus, um zu konfigurieren, wie Links in Sofortnachrichtenunterhaltungen behandelt werden:

  - **Kein Filter**   URLs in Nachrichten werden über den Server übermittelt. Bei Auswahl dieser Option wird das Feld **Nachricht zulassen** angezeigt. Geben Sie im Feld **Nachricht zulassen** den Hinweis ein, der am Anfang von Sofortnachrichten mit Links eingefügt werden soll. Dieser Hinweis darf maximal 65535 Zeichen umfassen.

  - **Links blockieren**   Die Übermittlung von Sofortnachrichten mit aktiven Links wird von Lync Server blockiert, und dem Absender wird eine Fehlermeldung angezeigt.

  - **Warnmeldung senden**   Aktive Links in Sofortnachrichten sind zulässig, Lync Server fügt jedoch eine Warnung ein. Bei Auswahl dieser Option wird das Feld **Warnmeldung** angezeigt. Geben Sie im Feld **Warnmeldung** die Warnung ein, die in Sofortnachrichten mit gültigen Links eingefügt werden soll. In dieser Warnung kann z. B. auf die potenziellen Gefahren beim Klicken auf einen unbekannten Link hingewiesen werden, oder die Warnung kann auf die relevanten Richtlinien und Anforderungen Ihrer Organisation verweisen. Die Warnung darf maximal 65535 Zeichen umfassen.

Bei Auswahl von **Links blockieren** oder **Warnmeldung senden** sind die folgenden Optionen verfügbar:

  - **Lokale Intranetlinks ausschließen**   Der Sofortnachrichtenfilter blockiert lediglich Internet-URLs. URLs für Seiten innerhalb Ihres Intranets werden unverändert über den Server übermittelt. Die Intranet-URLs, die einzelne Server mit Lync Server weiterleiten, hängen jedoch davon ab, welche Typen lokaler Websites als Teil der Intranetzone betrachtet werden. Anleitungen zum Überprüfen der Intranetzoneneinstellungen eines Servers finden Sie im Verfahren "So konfigurieren Sie Ihre Intraneteinstellungen in Internet Explorer" in [Ändern des URL-Standardfilters](lync-server-2013-modify-the-default-url-filter.md).

  - **Diese Linkpräfixe filtern**   Zur Auswahl der zu blockierenden Präfixe klicken Sie auf **Auswählen**, und fügen Sie in **Linkpräfix auswählen** die gewünschten Präfixe zur Liste **Linkpräfixe** hinzu.
    
    Mit Ausnahme von **href** müssen alle Präfixe auf einen Punkt oder Doppelpunkt oder auf ein Sternchen vor einem Punkt enden. Gültige Präfixe können beliebige Zeichen aus dem Satz gültiger URL-Zeichen mit Ausnahme des Sternchens (\*) enthalten. Der Satz gültiger URL-Zeichen lautet: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~

## Dateiübertragungsfilterung

Die Filterung bei der Dateiübertragung wirkt sich sowohl auf Sofortnachrichten als auch auf Konferenzen aus. Für Konferenzen wirken sich diese Einstellungen auf die Handzettelfunktion im Office Live Meeting 2007-Client und auf die Multimediawiedergabefunktionen aus.


> [!NOTE]
> In Lync Server können zudem Optionen für die Dateiübertragung festgelegt werden. Diese serverseitigen Optionen werden zusätzlich zu den in Lync Server verfügbaren clientseitigen Steuerelementen bereitgestellt.



Sie können Dateiübertragungen während Sofortnachrichtenunterhaltungen filtern, wenn Sie die Handzettelfunktion im Office Live Meeting 2007-Client verwenden, sowie bei Multimediawiedergabefunktionen für alle Dateitypen. Zur Steuerung von Dateiübertragungen können die folgenden Optionen festgelegt werden:

  - **Dateifilter aktivieren**   Diese Option aktiviert die Dateifilterung für die globale Bereitstellung oder für den ausgewählten Standort.
    
    Bei Aktivierung des Dateifilters können Sie in **Dateiübertragung** eine der folgenden Optionen auswählen:
    
      - **Bestimmte Dateitypen blockieren**   Geben Sie in einer Liste mit zu blockierenden Dateierweiterungen an, welche Dateiübertragungsanforderungen vom Server gefiltert werden sollen. Die Einträge in der Liste können alle Standardzeichen enthalten, nicht jedoch das Platzhalterzeichen (\*). Im Office Live Meeting 2007-Client ist die Handzettelfunktion aktiviert, Dateien mit dieser Erweiterung können jedoch nicht hochgeladen oder heruntergeladen werden. Bei Aktivierung des Kontrollkästchens **URLs mit Dateierweiterung blockieren** in den Einstellungen für einen URL-Filter auf der Registerkarte **URL-Filter** verwendet der URL-Filter dieselbe Liste, um aktive Links mit diesen Dateierweiterungen zu blockieren. Zur Auswahl der zu blockierenden Dateitypen klicken Sie auf **Auswählen**, und fügen Sie in **Dateityp auswählen** die Dateityperweiterungen zur Liste **Ausgewählte Dateityperweiterungen** hinzu.
    
      - **Alle blockieren**   Der Server löscht alle Sofortnachrichten, die Dateiübertragungsanforderungen enthalten, und sendet eine Fehlermeldung an den Absender der Anforderung. Die Handzettelfunktion im Office Live Meeting 2007-Client wird deaktiviert.


> [!IMPORTANT]
> Die Filterung nach Dateierweiterungen ist auf Standarddateinamen beschränkt. Die Filterung funktioniert möglicherweise nicht, wenn Dateierweiterungen in anderen Namen enthalten sind.



## In diesem Abschnitt

  - [Ändern des standardmäßigen Dateiübertragungsfilters](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Erstellen eines neuen Dateiübertragungsfilters für einen bestimmten Standort](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Ändern des URL-Standardfilters](lync-server-2013-modify-the-default-url-filter.md)

  - [Erstellen eines neuen URL-Filters für die Verarbeitung von Links in Sofortnachrichtenunterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Einstellungen für Chat und Anwesenheit in Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)

