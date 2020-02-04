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
ms.openlocfilehash: 1460699b6516ab4e510c9715b2464ce442466faa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Der zentralisierte Protokollierungsdienst bietet eine Möglichkeit zur kontrollierten Datensammlung – mit einem breiten oder engen Bereich. Sie können gleichzeitig Daten von allen Servern in der Bereitstellung sammeln, bestimmte zu ablaufende Elemente definieren, Ablaufverfolgungsflags festlegen und Suchergebnisse von einem einzelnen Computer oder einer Aggregation aller Daten von allen Servern zurückgeben. Der zentralisierte Protokollierungsdienst wird auf allen Servern in Ihrer Bereitstellung ausgeführt. Die Architektur des zentralen Protokollierungsdiensts umfasst die folgenden Agents und Dienste:

  - *Der zentralisierte Protokollierungsdienst-Agent*   ClsAgent. exe ist die ausführbare Dienstdatei, die mit dem Controller kommuniziert und die Befehle empfängt, die vom Administrator vom Controller ausgestellt werden. Der Agent wird auf jedem lync Server-Computer als Dienst ausgeführt. Wenn der Agent einen Befehl erhält, führt er den Befehl aus, sendet Nachrichten an die definierten Komponenten für die Ablaufverfolgung und schreibt die Ablaufverfolgungsprotokolle auf die Festplatte. Er liest auch die Ablaufverfolgungsprotokolle für seinen Computer und sendet die Ablaufverfolgungsdaten auf Anforderung an den Controller zurück. Der ClsAgent überwacht Befehle auf den folgenden Ports: **TCP 50001**, **TCP 50002**und **TCP 50003**.

  - *Zentralisierter Protokollierungsdienst Controller*   ClsControllerLib. dll ist das Befehls Ausführungsmodul für die lync Server-Verwaltungsshell und für ClsController. exe. CLSControllerLib. dll sendet Start-, Stopp-, Flush-und Suchbefehle an das ClsAgent. Wenn Suchbefehle gesendet werden, werden die resultierenden Protokolle an die ClsControllerLib. dll zurückgegeben und aggregiert. Der Controller ist für das Senden von Befehlen an den Agenten, das Empfangen des Status dieser Befehle und die Verwaltung der Suchprotokoll Dateidaten verantwortlich, wie Sie von allen Agents auf einem beliebigen Computer im Suchbereich zurückgegeben werden, und Aggregieren der Protokolldaten in einer aussagekräftigen und geordneten Ausgabesatz. Die Informationen in den folgenden Themen konzentrieren sich auf die Verwendung der lync Server-Verwaltungsshell. ClsController. exe ist auf eine Teilmenge der Features und Funktionen, die in der lync Server-Verwaltungsshell verfügbar sind, limitiert. Hilfe zu ClsController. exe finden Sie in der Befehlszeile, indem `ClsController` Sie das Standardverzeichnis C:\\Programmdateien\\allgemeine Dateien\\Microsoft lync Server 2013\\ClsAgent eingeben.

**Kommunikation zwischen ClsController und ClsAgent**

![Beziehung zwischen CLSController und CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Beziehung zwischen CLSController und CLSAgent.")

Sie können Befehle über die Windows Server-Befehlszeilenschnittstelle oder mithilfe der lync Server-Verwaltungsshell ausgeben. Die Befehle werden auf dem Computer ausgeführt, bei dem Sie angemeldet sind, und an den lokalen ClsAgent oder an die anderen Computer und Pools in Ihrer Bereitstellung gesendet.

ClsAgent verwaltet eine Indexdatei aller .CACHE-Dateien, die auf dem lokalen Computer vorhanden sind. ClsAgent ordnet diese so zu, dass sie, entsprechend der Definition der Option „CacheFileLocalFolders“, gleichmäßig auf Volumes verteilt sind und nie mehr als 80 % eines Volumes belegen (der lokale Cachespeicherort und der Prozentsatz sind mit dem Cmdlet **Set-CsClsConfiguration** konfigurierbar). ClsAgent ist außerdem für die Cacheablaufzeiten alter gecachter Ereignisablaufprotokolldateien (ETL-Dateien) vom lokalen Computer zuständig. Nach zwei Wochen (der Zeitrahmen kann mit dem Cmdlet**Set-CsClsConfiguration** konfiguriert werden) werden diese Dateien in eine Dateifreigabe kopiert und vom lokalen Computer gelöscht. Ausführliche Informationen finden Sie unter [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Wenn eine Suchanfrage empfangen wird, werden die Suchkriterien verwendet, um die gecachten ETL-Dateien auszuwählen und die Suche anhand der Werte in dem vom Agent geführten Index durchzuführen.

<div>


> [!NOTE]  
> Dateien, die vom lokalen Computer in die Dateifreigabe verschoben wurden, können von ClsAgent durchsucht werden. Sobald ClsAgent die Dateien in die Dateifreigabe verschiebt, werden die Cacheablaufzeiten und das Entfernen von Dateien nicht mehr durch ClsAgent verwaltet. Sie sollten daher eine administrative Aufgabe definieren, die die Größe der Dateien in der Dateifreigabe überwacht und diese Dateien löscht oder archiviert.



</div>

Die resultierenden Protokolldateien können mithilfe einer Vielzahl von Tools, einschließlich **Snooper. exe** und jedem Tool, das eine Textdatei wie **Notepad. exe**lesen kann, gelesen und analysiert werden. Snooper. exe ist Teil der lync Server 2013-Debug-Tools und steht als Webdownload von [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)zur Verfügung.

Wie OCSLogger verfügt der zentralisierte Protokollierungsdienst über mehrere Komponenten, die verfolgt werden können, und bietet Optionen zum Auswählen von\_Flags wie TF\_Component und TF diag. Der zentralisierte Protokollierungsdienst behält auch die Protokollierungsstufen Optionen von OCSLogger bei.

Der wichtigste Vorteil bei der Verwendung der lync Server-Verwaltungsshell über die Befehlszeilen-ClsController besteht darin, dass Sie neue Szenarien mit ausgewählten Anbietern konfigurieren und definieren können, die auf den Problembereich, benutzerdefinierte Flags und Protokollierungsebenen ausgerichtet sind. Die für ClsController verfügbaren Szenarien sind auf die für das Programm definierten Szenarien beschränkt.

In früheren Versionen war OCSLogger.exe verfügbar, um Administratoren und Supportmitarbeitern das Erfassen von Nachverfolgungsdateien von Computern in der Bereitstellung zu ermöglichen. OCSLogger hatte bei all seinen Stärken einen Nachteil. Sie konnten damit nur jeweils auf einem Computer Protokolle erfassen. Sie konnten sich bei mehreren Computern anmelden, indem Sie separate Kopien von OCSLogger verwendeten, Sie erhielten jedoch mehrere Protokolle und es gab kein einfaches Verfahren, um die Ergebnisse zusammenzufassen.

Wenn ein Benutzer eine Protokollsuche anfordert, ermittelt der ClsController, an welche Computer die Anfrage gesendet werden muss (dies basiert auf den ausgewählten Szenarien). Er bestimmt außerdem, ob die Suche an die Dateifreigabe gesendet werden muss, in der sich die gespeicherten ETL-Dateien befinden. Wenn die Suchergebnisse an den ClsController zurückgegeben werden, fasst der Controller die Ergebnisse zu einem einzigen, zeitlich geordneten Ergebnissatz zusammen, der dem Benutzer angezeigt wird. Benutzer können die Suchergebnisse für weitere Analysen auf ihrem lokalen Computer speichern.

Wenn Sie eine Protokollierungssitzung starten, legen Sie Szenarien fest, die sich auf das Problem beziehen, das Sie beheben möchten. Sie können jederzeit zwei Szenarien gleichzeitig ausführen. Eines dieser beiden Szenarien sollte das Szenario „AlwaysOn“ sein. Dieses sollte in Ihrer Bereitstellung immer ausgeführt werden und Informationen von allen Computern, Pools und Komponenten erfassen.

<div>


> [!IMPORTANT]  
> Standardmäßig wird das AlwaysOn-Szenario nicht in Ihrer Bereitstellung ausgeführt. Sie müssen das Szenario explizit starten. Nachdem der Vorgang gestartet wurde, wird er weiterhin ausgeführt, bis er explizit angehalten wird, und der Ausführungszustand wird durch einen Neustart der Computer beibehalten. Details zum Starten und Beenden von Szenarien finden Sie unter <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Verwenden von Start für den zentralisierten Protokollierungsdienst zum Aufzeichnen von Protokollen in lync Server 2013</A> und <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Verwenden von Stopp für den zentralisierten Protokollierungsdienst in lync Server 2013</A>.



</div>

Wenn ein Problem auftritt, können Sie ein zweites Szenario starten, das sich auf dieses Problem bezieht. Reproduzieren Sie das Problem und beenden Sie dann die Protokollierung für das zweite Szenario. Beginnen Sie mit der Protokollsuche für das Problem. Die zusammengefassten Protokolle ergeben eine Protokolldatei, die Nachverfolgungsmeldungen von allen Computern des Standort- oder des globalen Bereichs Ihrer Bereitstellung enthält. Wenn die Suche mehr Daten zurückgibt, als Sie analysieren können (meist aufgrund von Störabstände, bei denen das Rauschen zu hoch ist), führen Sie eine weitere Suche mit enger gesteckten Parametern durch. An diesem Punkt können Sie gegebenenfalls auftretende Muster feststellen, die Ihnen helfen, das Problem genauer einzugrenzen. Letztlich finden Sie nach diversen verfeinerten Suchen Daten, die für das Problem relevant sind und die Hauptursache deutlich machen.

<div>


> [!TIP]  
> Wenn Sie mit einem Problemszenario in lync Server dargestellt werden, Fragen Sie sich zunächst, was ich bereits über das Problem weiß. Wenn Sie die Problem Grenzen quantifizieren, können Sie einen Großteil der operativen Entitäten in lync Server eliminieren.<BR>Stellen Sie sich ein Beispielszenario vor, in dem Sie wissen, dass Benutzer bei der Suche nach einem Kontakt keine aktuellen Ergebnisse erhalten. Es hat keinen Punkt, nach Problemen in den Medienkomponenten, Enterprise-VoIP, Konferenz und einer Reihe anderer Komponenten zu suchen. Was Sie nicht wissen, ist, wo das Problem tatsächlich auftritt: auf dem Client oder auf dem Server? Kontakte werden vom Benutzerreplikationsdienst aus Active Directory gesammelt und über den Adressbuch Server (AbServer) an den Client übermittelt. Der ABServer erhält seine Updates von der RTC-Datenbank (in die der User Replicator sie geschrieben hat) und erfasst diese Updates in Adressbuchdateien – standardmäßig um 1:30 Uhr. Die lync Server-Clients rufen das neue Adressbuch nach einem randomisierten Zeitplan ab. Da Sie wissen, wie der Prozess funktioniert, können Sie die Suche nach der potenziellen Ursache für ein Problem reduzieren, das mit Daten zusammenhängt, die von Active Directory vom Benutzerreplikationsdienst erfasst werden, die ABServer die Adressbuchdateien nicht abrufen und erstellen, oder die Clients, die nicht Herunterladen der Adressbuchdatei.



</div>

</div>

<span> </span>

</div>

</div>

</div>

