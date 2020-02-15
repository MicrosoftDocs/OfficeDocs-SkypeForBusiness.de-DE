---
title: Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b741418790c5faf11c566afb27a477a67beb71ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Mit dem intelligenten Sofortnachrichten-Filter Tool können Sie Ihre lync Server 2013-Bereitstellung vor der Verbreitung der häufigsten Virenarten mit minimaler Beeinträchtigung der Benutzerfreundlichkeit schützen. Konfigurieren Sie mit dem intelligenten Sofortnachrichtenfilter Filter zum Blockieren unerwünschter oder potenziell schädlicher Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall. Sie konfigurieren Filter, indem Sie die Kriterien angeben, die verwendet werden sollen, um zu bestimmen, was blockiert werden soll, beispielsweise Sofortnachrichten mit Hyperlinks mit bestimmten Präfixen und Dateien mit bestimmten Erweiterungen.

Der intelligente Chat Filter bietet Folgendes:

  - Erweiterte URL-Filterung.

  - Erweiterte Dateiübertragungsfilterung.

Das Konfigurieren eines intelligenten Sofortnachrichtenfilters umfasst Folgendes:

  - Konfigurieren der URL-Filterung

  - Konfigurieren der Dateiübertragungsfilterung.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Anwenden von Filteroptionen auf Chatnachrichten

Vor dem Bereitstellen des intelligenten Chatnachrichten Filter-Tools müssen Sie verstehen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013 Server an einen anderen weitergeleitet werden. Die Art der Anwendung von Filteroptionen ist konsistent, unabhängig davon, ob die Server sich in einer einzigen Organisation oder in mehreren Organisationen befinden. Diese Konsistenz gilt für die Art und Weise, in der die benutzerdefinierten Benachrichtigungs-und Warn Texte in Nachrichten eingefügt und über Server gesendet werden.

<div>


> [!NOTE]
> Der Instant Messaging-Filter erhöht die Menge an CPU-Ressourcen, die zum Verarbeiten von URLs in einer Nachricht erforderlich sind. Dieser Anstieg der CPU-Nachfrage wirkt sich auch auf die Leistung von lync Server aus.



</div>

Mithilfe der Seite **URL-Filter** in der **Chat-und Anwesenheits** Gruppe in lync Server-Systemsteuerung können Sie einige oder alle Hyperlinks blockieren oder eine Warnung konfigurieren. Die Warnung wird am Anfang einer Sofortnachricht eingefügt, die einen Hyperlink enthält, wenn Sie die Option **Hyperlink** -Präfix **senden Warnmeldung**auswählen.

Wenn eine Sofortnachricht von einem Server auf einen anderen übertragen wird, gelten die folgenden allgemeinen Richtlinien:

  - Wenn ein Server eine Sofortnachricht blockiert (da Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** auf der Seite **URL-Filter** aktiviert haben oder wenn Sie die Option Hyperlinks für **Hyperlink-Präfix** **blockieren**ausgewählt haben), wird eine Fehlermeldung an den Client zurückgegeben. Nachfolgende Server erhalten diese Sofortnachricht nicht.

  - Wenn ein Server (Server1) eine Warnung zu einer Sofortnachricht hinzufügt, die einen aktiven Hyperlink enthält, kann ein folgender Server (Server2), der diese Sofortnachricht empfängt, nach wie vor eine andere Aktion basierend auf diesem in der Sofortnachricht vorhandenen aktiven Hyperlink ausführen und den Block Sofortnachricht oder Warnung hinzufügen. Wenn Server2 nur zum Hinzufügen einer Warnung für diese URL konfiguriert ist, wird die zuvor von Server1 hinzugefügte Warnung entfernt, und die auf Server2 konfigurierte Warnung wird am Anfang der Sofortnachricht hinzugefügt.

<div>


> [!NOTE]
> Wenn Sie lync Server 2013 in einer gemischten Umgebung verwenden, ist Live Communications Server 2005 mit SP1 die minimale Version, die für die Verwendung der intelligenten Chat Filter Anwendung erforderlich ist. Der intelligente Chat Filter wird auf Live Communications Server 2005 ohne SP1 nicht unterstützt.



</div>

<div>

## <a name="url-filtering"></a>URL-Filterung

URLs werden entsprechend Ihrem Hyperlink-Präfix gefiltert. Die folgenden Beispiele sind gültige Präfixe:

  - www\*.

  - FTP.

  - http

Wenn Sie den Instant Messaging-Filter nicht so konfigurieren, dass eine URL-Filterung durchgeführt wird, werden alle in Chatnachrichten enthaltenen URLs ohne Änderung über den Server übergeben. Wenn Sie den Instant Messaging-Filter so konfigurieren, dass die URL-Filterung durchgeführt wird, werden URLs in Chatnachrichten entsprechend den Optionen gefiltert, die Sie im Dialogfeld **URL-Filter bearbeiten** oder **neuer URL** -Filter ausgewählt haben.

  - **URL-Filter**   aktivieren mit dieser Option wird die URL-Filterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website aktiviert.

  - **Blockieren von URLs mit Dateierweiterung**   der Sofortnachrichtenfilter blockiert alle aktiven Intranet-oder Internet-URLs, die eine Datei mit einer im Dialogfeld **Dateifilter bearbeiten** unter **Dateityperweiterungen** aufgeführten Erweiterung enthalten. Wenn eine URL blockiert wird, wird dem Absender eine Fehlermeldung angezeigt. Wenn diese Option aktiviert ist, hat diese Option Vorrang vor allen anderen Filteroptionen für alle Dateierweiterungen, **die unter Dateityperweiterungen definiert sind, die blockiert werden sollen**.
    
    <div>
    

    > [!IMPORTANT]
    > Das Filtern von Dateierweiterungen ist auf Standarddatei Namen limitiert. Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in andere Namen eingebettet sind.

    
    </div>

Wählen Sie eine der folgenden Optionen unter **Link Prefix**aus, um zu konfigurieren, wie Hyperlinks in Sofortnachrichtenunterhaltungen behandelt werden:

  - ****   URLs in Nachrichten nicht Filtern werden über den Server gesendet. Wenn Sie diese Option auswählen, wird das Feld **Nachricht zulassen** angezeigt. Geben Sie im Feld **Nachricht zulassen** den Hinweis an, den Sie am Anfang jeder Sofortnachricht mit Hyperlinks einfügen möchten. Dieser Hinweis kann aus maximal 65535 Zeichen bestehen.

  - **Blockieren von Hyperlinks**   die Zustellung von Sofortnachrichten mit aktiven Hyperlinks wird von lync Server blockiert, und dem Absender wird eine Fehlermeldung angezeigt.

  - **Warnmeldung**   senden lync Server erlaubt aktive Hyperlinks in Chatnachrichten, enthält jedoch eine Warnung. Wenn Sie diese Option auswählen, wird das **Warn Meldungs** Feld angezeigt. Im **Warn Meldungs** Feld müssen Sie die Warnung eingeben, die in Chatnachrichten enthalten sein soll, die gültige Hyperlinks enthalten. Beispielsweise kann diese Warnung die potenziellen Gefahren für das Klicken auf einen unbekannten Link angeben oder sich auf die relevanten Richtlinien und Anforderungen Ihrer Organisation berufen. Die Warnung darf nicht mehr als 65535 Zeichen enthalten.

Wenn Sie **Hyperlinks blockieren** oder **Warnmeldung senden**auswählen, stehen die folgenden Optionen zur Verfügung:

  - **Lokale Intranet-Hyperlinks**   ausschließen der Sofortnachrichtenfilter blockiert nur Internet-URLs. URLs für Standorte in Ihrem Intranet werden unverändert über den Server übergeben. Die Intranet-URLs, die einzelne Server lync Server übergeben, hängen jedoch davon ab, welche Arten von lokalen Websites als Teil ihrer Intranetzone betrachtet werden. Informationen zum Überprüfen der Intranet-Zoneneinstellungen eines Servers finden Sie unter "so konfigurieren Sie die Einstellungen für Intraneteinstellungen in Internet Explorer" unter [Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtern Sie diese Verknüpfungs Präfixe**   , um auszuwählen, welche Präfixe Sie blockieren möchten, klicken Sie auf **auswählen**, und fügen Sie dann im Feld **Hyperlink-Präfix auswählen**die Präfixe zur Liste **Hyperlink-Präfixe** hinzu.
    
    Alle Präfixe mit Ausnahme von **href** müssen mit einem Punkt oder einem Doppelpunkt oder einem Sternchen, gefolgt von einem Punkt enden. Gültige Präfixe können beliebige Zeichen im Satz gültiger URL-Zeichen enthalten, außer dem Sternchen (\*). Die Gruppe gültiger URL-Zeichen lautet: \# \*+/0123456789 = @abcdefghijklmnopqrstuvwxyz ^\_ \` abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Dateiübertragungsfilterung

Filter Übertragungs Filterung wirkt sich sowohl auf Chatnachrichten als auch auf Konferenzen aus. Bei Konferenzen wirken sich diese Einstellungen auf die handzettelfunktion in den Features Office Live Meeting 2007 Client-und Multimedia-Wiedergabe aus.

<div>


> [!NOTE]
> Lync Server bietet auch Optionen zum Festlegen von Dateiübertragungen. Diese serverseitige Option wird zusätzlich zu den clientseitigen Steuerelementen angeboten, die in lync Server verfügbar sind.



</div>

Sie können Dateiübertragungen während Sofortnachrichtenunterhaltungen filtern, wenn Sie das Handzettel Feature im Office Live Meeting 2007-Client verwenden, sowie für Multimedia-Wiedergabefunktionen für alle Dateitypen. Sie können die folgenden Optionen festlegen, um Dateiübertragungen zu steuern:

  - **Dateifilter**   aktivieren mit dieser Option wird die Dateifilterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website aktiviert.
    
    Wenn Sie den Dateifilter aktivieren, können Sie eine der folgenden Optionen bei der **Dateiübertragung**auswählen:
    
      - **Blockieren bestimmter Dateitypen**   Sie geben an, welche Dateiübertragungsanforderungen vom Server gefiltert werden, indem Sie eine Liste der zu blockierenden Dateierweiterungen angeben. Einträge in der Liste können alle Standardzeichen enthalten, jedoch nicht das Platzhalterzeichen\*(). Im Office Live Meeting 2007-Client ist das Handzettel Feature aktiviert, aber jede Datei mit dieser Erweiterung kann nicht hochgeladen oder heruntergeladen werden. Wenn Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** für die Einstellungen für einen URL-Filter aktivieren, der auf der Registerkarte **URL-Filter** aufgeführt ist, verwendet der URL-Filter diese Liste, um aktive Hyperlinks zu blockieren, die eine dieser Dateierweiterungen enthalten. Um auszuwählen, welche Dateitypen Sie blockieren möchten, klicken Sie auf **auswählen**, und fügen Sie dann unter **Dateityp**die Dateierweiterungen der Liste **ausgewählte Dateitypen Erweiterungen** hinzu.
    
      - **Alle blockieren der**   Server löscht alle Sofortnachrichten, die Dateiübertragungsanforderungen enthalten, und gibt eine Fehlermeldung an den Absender der Anforderung zurück. Das Handzettel Feature im Office Live Meeting 2007-Client ist deaktiviert.

<div>


> [!IMPORTANT]
> Das Filtern von Dateierweiterungen ist auf Standarddatei Namen limitiert. Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in andere Namen eingebettet sind.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Ändern des standardmäßigen URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Chat-und Anwesenheitseinstellungen in lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

