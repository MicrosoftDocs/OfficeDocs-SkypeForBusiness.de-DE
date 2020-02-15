---
title: 'Lync Server 2013: Übersicht über den zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c485293fe747a16cc9c2b392d053137105306da4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Der zentralisierte Protokollierungsdienst bietet eine Möglichkeit zur kontrollierten Sammlung von Daten – mit einem breiten oder engen Bereich. Sie können Daten von allen Servern in der Bereitstellung gleichzeitig erfassen, spezifische Elemente definieren, die nachverfolgt werden, Nachverfolgungsflags festlegen und Suchergebnisse von einem einzelnen Computer zurückgeben oder eine Zusammenfassung aller Daten von allen Servern. Der zentralisierte Protokollierungsdienst wird auf allen Servern in der Bereitstellung ausgeführt. Die Architektur des zentralisierten Protokollierungsdiensts umfasst die folgenden Agents und Dienste:

  - *Der Agent*   für den zentralisierten Protokollierungsdienst ClsAgent. exe ist die ausführbare Dienstdatei, die mit dem Controller kommuniziert und die Befehle empfängt, die der Controller vom Administrator ausgestellt wird. Der Agent wird auf jedem lync Server Computer als Dienst ausgeführt. Wenn der Agent einen Befehl empfängt, führt er diesen aus, sendet Nachrichten an die für die Nachverfolgung definierten Komponenten und schreibt die Nachverfolgungsprotokolle auf die Festplatte. Er liest außerdem die Nachverfolgungsprotokolle für seine Computer und sendet die Nachverfolgungsdaten auf Anfrage zurück an den Controller. Der ClsAgent überwacht folgende Ports auf Befehle: **TCP 50001**, **TCP 50002** und **TCP 50003**.

  - *Der zentralisierte Protokollierungsdienst-Controller*   ClsControllerLib. dll ist das Befehls Ausführungsmodul für die lync Server-Verwaltungsshell und für ClsController. exe. CLSControllerLib. dll sendet Befehle zum Starten, beenden, leeren und suchen an das ClsAgent-Steuerfeld. Wenn Suchbefehle gesendet werden, werden die resultierenden Protokolle an die ClsControllerLib. dll zurückgegeben und aggregiert. Der Controller ist für das Senden von Befehlen an den Agent verantwortlich, wobei der Status dieser Befehle erhalten und die Daten der Suchprotokoll Datei verwaltet werden, wenn Sie von allen Agents auf einem beliebigen Computer im Suchbereich zurückgegeben werden, und die Protokolldaten in eine sinnvolle und geordnete Aggregation Ausgabemenge. Die Informationen in den folgenden Themen konzentrieren sich auf die Verwendung des lync Server-Verwaltungsshell. ClsController. exe ist auf eine Teilmenge der Features und Funktionen eingeschränkt, die in der lync Server-Verwaltungsshell verfügbar sind. Hilfe für ClsController. exe steht an der Befehlszeile zur Verfügung `ClsController` , indem Sie das Standardverzeichnis\\C:\\allgemeine Dateien\\für\\Programmdateien Microsoft lync Server 2013 ClsAgent eingeben.

**Kommunikation zwischen ClsController und ClsAgent**

![Beziehung zwischen CLSController und CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Beziehung zwischen CLSController und CLSAgent.")

Sie geben Befehle über die Windows Server-Befehlszeilenschnittstelle oder die lync Server-Verwaltungsshell aus. Die Befehle werden auf dem Computer ausgeführt, bei dem Sie angemeldet sind, und an den lokalen ClsAgent oder an die anderen Computer und Pools in Ihrer Bereitstellung gesendet.

ClsAgent verwaltet eine Indexdatei aller .CACHE-Dateien, die auf dem lokalen Computer vorhanden sind. ClsAgent ordnet diese so zu, dass sie, entsprechend der Definition der Option "CacheFileLocalFolders", gleichmäßig auf Volumes verteilt sind und nie mehr als 80 % eines Volumes belegen (der lokale Cachespeicherort und der Prozentsatz sind mit dem **Set-CsClsConfiguration**-Cmdlet konfigurierbar). ClsAgent ist außerdem für die Cacheablaufzeiten alter gecachter Ereignisablaufprotokolldateien (.etl) vom lokalen Computer zuständig. Nach zwei Wochen (der Zeitrahmen kann mit dem **Set-CsClsConfiguration**-Cmdlet konfiguriert werden) werden diese Dateien in eine Dateifeigabe kopiert und vom lokalen Computer gelöscht. Ausführliche Informationen finden Sie unter [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Wenn eine Suchanfrage empfangen wird, werden die Suchkriterien verwendet, um die gecachten .etl-Dateien auszuwählen und die Suche anhand der Werte in dem vom Agent geführten Index durchzuführen.

<div>


> [!NOTE]  
> Dateien, die vom lokalen Computer in die Dateifreigabe verschoben wurden, können durch ClsAgent durchsucht werden. Sobald ClsAgent die Dateien in die Dateifreigabe verschiebt, werden die Cacheablaufzeiten und das Entfernen von Dateien nicht mehr durch ClsAgent verwaltet. Sie sollten daher eine administrative Aufgabe definieren, die die Größe der Dateien in der Dateifreigabe überwacht und diese löscht oder archiviert.



</div>

Die resultierenden Protokolldateien können mit einer Vielzahl von Tools, einschließlich **Snooper. exe** und allen Tools, die eine Textdatei wie **Notepad. exe**lesen können, gelesen und analysiert werden. Snooper. exe ist Teil der lync Server 2013 Debug-Tools und steht als Webdownload zur Verfügung [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).

Wie OCSLogger verfügt der zentralisierte Protokollierungsdienst über mehrere Komponenten, anhand derer nachverfolgt werden kann, und bietet Optionen zum\_auswählen von Flags\_wie TF Component und TF diag. Der zentralisierte Protokollierungsdienst behält auch die Protokollierungsgrad Optionen von OCSLogger bei.

Der wichtigste Vorteil bei der Verwendung der lync Server-Verwaltungsshell über das Befehlszeilen-ClsController ist, dass Sie neue Szenarien mithilfe ausgewählter Anbieter konfigurieren und definieren können, die auf Problembereich, benutzerdefinierte Flags und Protokollierungsstufen abzielen. Die für ClsController verfügbaren Szenarien sind auf die für das Programm definierten Szenarien beschränkt.

In früheren Versionen war OCSLogger.exe verfügbar, um Administratoren und Supportmitarbeitern das Erfassen von Nachverfolgungsdateien von Computern in der Bereitstellung zu ermöglichen. OCSLogger hatte bei all seinen Stärken einen Nachteil. Sie konnten damit nur jeweils auf einem Computer Protokolle erfassen. Sie konnten sich bei mehreren Computern anmelden, indem Sie separate Kopien von OCSLogger verwendeten, Sie erhielten aber mehrere Protokolle und hatten kein einfaches Verfahren, die Ergebnisse zusammenzufassen.

Wenn ein Benutzer eine Protokollsuche anfordert, ermittelt der ClsController, an welche Computer die Anfrage gesendet werden muss (dies basiert auf den ausgewählten Szenarien). Er bestimmt außerdem, ob die Suche an die Dateifreigabe gesendet werden muss, in der sich die gespeicherten .etl-Dateien befinden. Wenn die Suchergebnisse an den ClsController zurückgegeben werden, fasst der Controller die Ergebnisse zu einem einzigen, zeitlich geordneten Ergebnissatz zusammen, der an dem Benutzer angezeigt wird. Benutzer können die Suchergebnisse für weitere Analysen auf ihrem lokalen Computer speichern.

Wenn Sie eine Protokollierungssitzung starten, legen Sie Szenarien fest, die sich auf das Problem beziehen, das Sie beheben möchten. Sie können jederzeit zwei Szenarien gleichzeitig ausführen. Eines dieser beiden Szenarien sollte das Szenario "AlwaysOn" sein. Dieses sollte in Ihrer Bereitstellung immer ausgeführt werden und Informationen von allen Computern, Pools und Komponenten erfassen.

<div>


> [!IMPORTANT]  
> Das AlwaysOn-Szenario wird standardmäßig nicht in Ihrer Bereitstellung gestartet. Sie müssen das Szenario explizit starten. Nachdem der Vorgang gestartet wurde, wird er weiterhin ausgeführt, bis er explizit angehalten wurde, und der Ausführungsstatus wird durch einen Neustart der Computer beibehalten. Ausführliche Informationen zum Starten und Beenden von Szenarien finden Sie unter <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013</A> und <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Verwenden von Stop für den zentralisierten Protokollierungsdienst in lync Server 2013</A>.



</div>

Wenn ein Problem auftritt, können Sie ein zweites Szenario starten, das sich auf das Problem bezieht. Reproduzieren Sie das Problem, und beenden Sie dann die Protokollierung für das zweite Szenario. Beginnen Sie für das Problem mit der Protokollsuche. Die zusammengefassten Protokolle ergeben eine Protokolldatei, die Nachverfolgungsmeldungen von allen Computern des Standort- oder des globalen Bereichs Ihrer Bereitstellung enthält. Wenn die Suche mehr Daten zurückgibt, als Sie analysieren können (meist Störabstände, bei denen das Rauschen zu hoch ist), führen Sie eine weitere Suche mit enger gesteckten Parametern durch. An diesem Punkt können Sie gegebenenfalls auftretende Muster feststellen, die Ihnen helfen, das Problem genauer einzugrenzen. Letztlich finden Sie nach diversen verfeinerten Suchen Daten, die für das Problem relevant sind und die Hauptursache deutlich machen.

<div>


> [!TIP]  
> Wenn ein Problemszenario in lync Server angezeigt wird, Fragen Sie sich zunächst: "was weiß ich bereits über das Problem?" Wenn Sie die Problem Grenzen quantifizieren, können Sie einen großen Teil der Betriebs Entitäten in lync Server entfernen.<BR>Stellen Sie sich ein Beispielszenario vor, in dem Sie wissen, dass Benutzer bei der Suche nach einem Kontakt keine aktuellen Ergebnisse erhalten. Es hat keinen Sinn, nach Problemen in den Medienkomponenten, Enterprise-VoIP, Konferenzen und einer Reihe anderer Komponenten zu suchen. Was Sie nicht wissen, ist, wo das Problem tatsächlich auftritt: auf dem Client oder auf dem Server? Kontakte werden vom Benutzerreplikationsdienst aus Active Directory gesammelt und über den Adressbuch Server (AbServer) an den Client übermittelt. Der ABServer erhält seine Updates von der RTC-Datenbank (in die der User Replicator diese geschrieben hat) und erfasst diese in Adressbuchdateien – standardmäßig um 1:30 Uhr. Die lync Server Clients rufen das neue Adressbuch in einem randomisierten Zeitplan ab. Da Sie die Funktionsweise des Prozesses kennen, können Sie die Suche nach der potenziellen Ursache für ein Problem reduzieren, das sich auf Daten bezieht, die vom Benutzerreplikationsdienst aus Active Directory gesammelt werden, das ABServer nicht das Abrufen und Erstellen der Adressbuchdateien oder die Clients, die nicht Herunterladen der Adressbuchdatei.



</div>

</div>

<span> </span>

</div>

</div>

</div>

