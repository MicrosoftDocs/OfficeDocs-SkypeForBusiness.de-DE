---
title: Konfigurieren der Dateiübertragung und der URL-Filterung für Sofortnachrichten (im)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Das intelligente Chat-Filter Tool schützt Ihre lync Server 2013-Bereitstellung vor der Verbreitung der häufigsten Virenarten mit minimalem Abbau der Benutzerfreundlichkeit. Verwenden Sie den intelligenten Chatfilter, um Filter so zu konfigurieren, dass unerwünschte oder potenziell schädliche Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall blockiert werden. Sie konfigurieren Filter, indem Sie die Kriterien angeben, die verwendet werden sollen, um zu bestimmen, was blockiert werden soll, beispielsweise Sofortnachrichten, die Links mit bestimmten Präfixen und Dateien mit bestimmten Erweiterungen enthalten.

Der intelligente Chat Filter bietet die folgenden Optionen:

  - Erweiterte URL-Filterung.

  - Erweiterte Dateiübertragungsfilterung.

Das Konfigurieren intelligenter Chat Filter umfasst Folgendes:

  - Konfigurieren der URL-Filterung

  - Konfigurieren der Dateiübertragungsfilterung

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Anwenden von Filteroptionen auf Sofortnachrichten

Bevor Sie das intelligente Chatnachrichten Filter Tool bereitstellen, müssen Sie wissen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013-Server an einen anderen weitergeleitet werden. Die Art und Weise, wie diese Filteroptionen angewendet werden, ist konsistent, unabhängig davon, ob sich die Server in einer einzelnen Organisation oder unternehmensübergreifend befinden. Diese Konsistenz bezieht sich auf die Art und Weise, wie angepasste Benachrichtigungs-und Warnungstexte in Nachrichten eingefügt und serverübergreifend gesendet werden.

<div>


> [!NOTE]
> Der Sofortnachrichtenfilter erhöht die Anzahl der CPU-Ressourcen, die für die Verarbeitung von URLs in einer Nachricht erforderlich sind. Dieser Anstieg der CPU-Nachfrage wirkt sich auch auf die Leistung von lync Server aus.



</div>

Mithilfe der Seite " **URL-Filter** " in der **Chat-und Anwesenheits** Gruppe in der lync Server-Systemsteuerung können Sie einige oder alle Links blockieren oder eine Warnung konfigurieren. Die Warnung wird am Anfang einer Sofortnachricht eingefügt, die einen Link enthält, wenn Sie die Option " **Hyperlink-Präfix** " auf " **Warnmeldung senden**" auswählen.

Wenn eine Sofortnachricht von einem Server zu einem anderen reist, gelten die folgenden allgemeinen Richtlinien:

  - Wenn ein Server eine Chatnachricht blockiert (weil Sie auf der Seite **URL-Filter** das Kontrollkästchen **URLs mit Dateierweiterung blockieren** aktiviert haben oder wenn Sie die Option **Hyperlink-Präfix** - **Links blockieren**ausgewählt haben), wird eine Fehlermeldung an gesendet. der Client. Nachfolgende Server empfangen diese Sofortnachricht nicht.

  - Wenn ein Server (Server1) eine Warnung zu einer Sofortnachricht hinzufügt, die einen aktiven Link enthält, kann ein nach folgender Server (Server2), der diese Sofortnachricht empfängt, weiterhin eine andere Aktion auf der Grundlage dieses aktiven Links in der Chatnachricht durchführen und die Sofortnachricht oder eine Warnung hinzufügen. Wenn Server2 nur zum Hinzufügen einer Warnung für diese URL konfiguriert ist, wird die zuvor von Server1 hinzugefügte Warnung entfernt, und die auf Server2 konfigurierte Warnung wird am Anfang der Sofortnachricht hinzugefügt.

<div>


> [!NOTE]
> Wenn Sie lync Server 2013 in einer gemischten Umgebung ausführen, ist Live Communications Server 2005 mit SP1 die Mindestversion, die für die Verwendung der intelligenten Chat Filter-Anwendung erforderlich ist. Der intelligente Chat-Filter wird auf Live Communications Server 2005 ohne SP1 nicht unterstützt.



</div>

<div>

## <a name="url-filtering"></a>URL-Filterung

URLs werden gemäß Ihrem Link Präfix gefiltert. Die folgenden Beispiele sind gültige Präfixe:

  - www\*.

  - FTP.

  - http

Wenn Sie den Sofortnachrichtenfilter nicht so konfigurieren, dass eine URL-Filterung durchgeführt wird, werden alle URLs, die in Sofortnachrichten enthalten sind, über den Server unverändert übergeben. Wenn Sie den Sofortnachrichtenfilter so konfigurieren, dass URL-Filterung durchgeführt wird, werden URLs in Sofortnachrichten entsprechend den Optionen gefiltert, die Sie im Dialogfeld **URL-Filter bearbeiten** oder **neuer URL-Filter** ausgewählt haben.

  - **URL-Filter**   aktivieren diese Option aktiviert die URL-Filterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website.

  - **Blockieren von URLs mit Dateierweiterung**   der Sofortnachrichtenfilter blockiert alle aktiven Intranet-oder Internet-URLs, die eine Datei mit einer Erweiterung enthalten, die im Dialogfeld **Dateifilter bearbeiten** unter **zu blockierende Dateityperweiterungen** aufgeführt ist. Wenn eine URL blockiert ist, wird dem Absender eine Fehlermeldung angezeigt. Wenn diese Option ausgewählt ist, hat diese Option Vorrang vor allen anderen Filteroptionen für alle Dateierweiterungen, **die unter zu blockierende Dateityperweiterungen**definiert sind.
    
    <div>
    

    > [!IMPORTANT]
    > Das Filtern von Dateierweiterungen ist auf standardmäßige Dateinamen limitiert. Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in anderen Namen eingebettet sind.

    
    </div>

Wenn Sie konfigurieren möchten, wie Hyperlinks in Sofortnachrichtenunterhaltungen gehandhabt werden, wählen Sie eine der folgenden Optionen unter **Link-Präfix**aus:

  - **Sie können keine**   URLs in Nachrichten filtern, die über den Server gesendet werden. Wenn Sie diese Option auswählen, wird das Feld **Nachricht zulassen** angezeigt. Geben Sie im Feld **Nachricht zulassen** den Hinweis an, den Sie am Anfang jeder Sofortnachricht mit Links einfügen möchten. Dieser Hinweis kann aus maximal 65535 Zeichen bestehen.

  - **Blockieren von Links**   die Zustellung von Sofortnachrichten mit aktiven Links wird von lync Server blockiert, und dem Absender wird eine Fehlermeldung angezeigt.

  - **Warnungsnachricht**   senden lync Server erlaubt aktive Links in Sofortnachrichten, enthält aber eine Warnung. Wenn Sie diese Option auswählen, wird das Dialogfeld **Warnmeldung** angezeigt. Im Feld **Warnung** müssen Sie die Warnung eingeben, die Sie in Sofortnachrichten mit gültigen Hyperlinks einbeziehen möchten. Mit dieser Warnung können Sie beispielsweise die möglichen Gefahren für das Klicken auf einen unbekannten Link angeben, oder es kann auf die relevanten Richtlinien und Anforderungen Ihrer Organisation verweisen. Die Warnung darf maximal 65535 Zeichen lang sein.

Wenn Sie **Links blockieren** oder **Warnmeldung senden**auswählen, stehen die folgenden Optionen zur Verfügung:

  - **Lokale Intranet-Links**   ausschließen der Sofortnachrichtenfilter blockiert nur Internet-URLs. URLs für Standorte innerhalb Ihres Intranets werden ungeändert über den Server weitergeleitet. Die Intranet-URLs, die von einzelnen Servern mit lync Server übertragen werden, hängen jedoch davon ab, welche Typen von lokalen Websites als Teil ihrer Intranetzone angesehen werden. Informationen zum Überprüfen der Intranet-Zoneneinstellungen eines Servers finden Sie unter [Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)unter "so konfigurieren Sie Ihre Intraneteinstellungen in Internet Explorer".

  - **Filtern Sie diese Link Präfixe**   , um auszuwählen, welche Präfixe blockiert werden sollen, klicken Sie auf **auswählen**, und fügen Sie dann im Feld **Link Präfix auswählen**die Präfixe der Liste **Hyperlink** -Präfixe hinzu.
    
    Alle Präfixe mit Ausnahme von **href** müssen mit einem Punkt oder einem Doppelpunkt oder einem Sternchen, gefolgt von einem Punkt, enden. Gültige Präfixe können alle Zeichen in der Gruppe gültiger URL-Zeichen mit Ausnahme des Sternchens\*() enthalten. Der Satz gültiger URL-Zeichen lautet: \# \*+/0123456789 = @abcdefghijklmnopqrstuvwxyz ^\_ \` abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Dateiübertragungsfilterung

Filter Übertragungsfilter wirken sich sowohl auf Sofortnachrichten als auch auf Konferenzen aus. Bei Konferenzen wirken sich diese Einstellungen auf das Handzettel Feature in den Office Live Meeting 2007-Client-und Multimedia-Wiedergabe Features aus.

<div>


> [!NOTE]
> Lync Server bietet außerdem Einstellungen für die Dateiübertragung. Diese serverseitige Option wird zusätzlich zu den in lync Server verfügbaren clientseitigen Steuerelementen angeboten.



</div>

Sie können Dateiübertragungen während Sofortnachrichtenunterhaltungen filtern, wenn Sie die handzettelfunktion im Office Live Meeting 2007-Client verwenden, und für Multimedia-Wiedergabe Features für alle Dateitypen. Sie können die folgenden Optionen festlegen, um Dateiübertragungen zu steuern:

  - **Dateifilter**   aktivieren mit dieser Option wird die Dateifilterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website aktiviert.
    
    Wenn Sie den Dateifilter aktivieren, können Sie eine der folgenden Optionen in **Dateiübertragung**auswählen:
    
      - **Blockieren bestimmter Dateitypen**   Sie geben an, welche Dateiübertragungsanforderungen vom Server gefiltert werden sollen, indem Sie eine Liste der zu blockierenden Dateierweiterungen angeben. Einträge in der Liste können alle Standardzeichen, aber nicht das Platzhalterzeichen (\*) enthalten. Im Office Live Meeting 2007-Client ist die handzettelfunktion aktiviert, aber jede Datei mit dieser Erweiterung kann nicht hochgeladen oder heruntergeladen werden. Wenn Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** in den Einstellungen für einen URL-Filter auswählen, der auf der Registerkarte **URL-Filter** aufgelistet ist, verwendet der URL-Filter dieselbe Liste, um aktive Hyperlinks zu blockieren, die eine dieser Dateierweiterungen enthalten. Wenn Sie auswählen möchten, welche Dateitypen blockiert werden sollen, klicken Sie auf **auswählen**, und fügen Sie dann im Feld **Dateityp**die Dateierweiterungen zur Liste **ausgewählte Dateityperweiterungen** hinzu.
    
      - **Blockieren der gesamte**   Server löscht alle Sofortnachrichten, die Dateiübertragungsanforderungen enthalten, und gibt eine Fehlermeldung an den Absender der Anforderung zurück. Das Handzettel Feature im Office Live Meeting 2007-Client ist deaktiviert.

<div>


> [!IMPORTANT]
> Das Filtern von Dateierweiterungen ist auf standardmäßige Dateinamen limitiert. Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in anderen Namen eingebettet sind.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für eine bestimmte Website](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Einstellungen für Chat und Anwesenheit in Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

