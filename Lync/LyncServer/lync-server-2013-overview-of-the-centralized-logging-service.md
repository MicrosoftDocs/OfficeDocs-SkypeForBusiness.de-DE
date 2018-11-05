---
title: Übersicht über den zentralisierten Protokollierungsdienst
TOCTitle: Übersicht über den zentralisierten Protokollierungsdienst
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49890853
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über den zentralisierten Protokollierungsdienst

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Der Zentraler Protokollierungsdienst dient zur Steuerung der Datenerfassung über einen breit oder eng gefassten Bereich. Sie können Daten von allen Servern in der Bereitstellung gleichzeitig erfassen, spezifische Elemente definieren, die nachverfolgt werden, Nachverfolgungsflags festlegen und Suchergebnisse von einem einzelnen Computer zurückgeben oder eine Zusammenfassung aller Daten von allen Servern. Der Zentraler Protokollierungsdienst wird auf allen Servern in Ihrer Bereitstellung ausgeführt. Die Architektur des Zentraler Protokollierungsdiensts umfasst folgende Agents und Dienste:

  - *Zentraler Protokollierungsdienst-Agent*   ClsAgent.exe ist das Dienstprogramm, das mit dem Controller kommuniziert und Befehle empfängt, die der Controller vom Administrator erhält. Der Agent wird auf allen Lync Server-Computern als Dienst ausgeführt. Wenn der Agent einen Befehl empfängt, führt er diesen aus, sendet Nachrichten an die für die Nachverfolgung definierten Komponenten und schreibt die Nachverfolgungsprotokolle auf die Festplatte. Er liest außerdem die Nachverfolgungsprotokolle für seine Computer und sendet die Nachverfolgungsdaten auf Anfrage zurück an den Controller. Der ClsAgent überwacht folgende Ports auf Befehle: **TCP 50001**, **TCP 50002** und **TCP 50003**.

  - *Zentraler Protokollierungsdienst-Controller*   ClsControllerLib.dll ist das Befehlsausführungsmodul für die Lync Server-Verwaltungsshell und für ClsController.exe. CLSControllerLib.dll sendet Start-, Stopp-, Leerungs- und Suchbefehle an den ClsAgent. Wenn Suchbefehle gesendet werden, werden die sich daraus ergebenden Protokolle an die ClsControllerLib.dll zurückgesendet und zusammengefasst. Der Controller ist zuständig für das Senden von Befehlen an den Agent, das Empfangen des Status dieser Befehle, das Verwalten der Suchprotokolldateidaten, die von allen Agents auf allen Computern im Suchbereich zurückgegeben werden, und das Zusammenfassen der Protokolldaten zu einem aussagekräftigen und sortierten Ausgabesatz. Die in den folgenden Themen enthaltenen Informationen beziehen sich auf die Verwendung der Lync Server-Verwaltungsshell. ClsController.exe ist auf einen Teil der in der Lync Server-Verwaltungsshell verfügbaren Funktionen beschränkt. Hilfe zum ClsController.exe erhalten Sie, wenn in der Befehlszeile `ClsController` im Standardverzeichnis "C:\\Programme\\Gemeinsame Dateien\\Microsoft Lync Server 2013\\ClsAgent" eingeben

**Kommunikation zwischen ClsController und ClsAgent**

![Beziehung zwischen CLSController und CLSAgent](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Beziehung zwischen CLSController und CLSAgent")

Die Befehlseingabe erfolgt in der Windows Server-Befehlszeile oder mithilfe der Lync Server-Verwaltungsshell. Die Befehle werden auf dem Computer ausgeführt, bei dem Sie angemeldet sind, und an den lokalen ClsAgent oder an die anderen Computer und Pools in Ihrer Bereitstellung gesendet.

ClsAgent verwaltet eine Indexdatei aller .CACHE-Dateien, die auf dem lokalen Computer vorhanden sind. ClsAgent ordnet diese so zu, dass sie, entsprechend der Definition der Option "CacheFileLocalFolders", gleichmäßig auf Volumes verteilt sind und nie mehr als 80 % eines Volumes belegen (der lokale Cachespeicherort und der Prozentsatz sind mit dem **Set-CsClsConfiguration**-Cmdlet konfigurierbar). ClsAgent ist außerdem für die Cacheablaufzeiten alter gecachter Ereignisablaufprotokolldateien (.etl) vom lokalen Computer zuständig. Nach zwei Wochen (der Zeitrahmen kann mit dem **Set-CsClsConfiguration**-Cmdlet konfiguriert werden) werden diese Dateien in eine Dateifeigabe kopiert und vom lokalen Computer gelöscht. Ausführliche Informationen finden Sie unter [Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration). Wenn eine Suchanfrage empfangen wird, werden die Suchkriterien verwendet, um die gecachten .etl-Dateien auszuwählen und die Suche anhand der Werte in dem vom Agent geführten Index durchzuführen.


> [!NOTE]  
> Dateien, die vom lokalen Computer in die Dateifreigabe verschoben wurden, können durch ClsAgent durchsucht werden. Sobald ClsAgent die Dateien in die Dateifreigabe verschiebt, werden die Cacheablaufzeiten und das Entfernen von Dateien nicht mehr durch ClsAgent verwaltet. Sie sollten daher eine administrative Aufgabe definieren, die die Größe der Dateien in der Dateifreigabe überwacht und diese löscht oder archiviert.



Die daraus resultierenden Protokolldateien können mit einer Vielzahl von Tools gelesen und analysiert werden. Hierzu gehören auch **Snooper.exe** und alle Tools, die eine Textdatei lesen können, wie **Notepad.exe**. Snooper.exe ist Teil der Debugtools von Lync Server 2013 und ist als Webdownload verfügbar.

Wie OCSLogger kann der Zentraler Protokollierungsdienst verschiedene Komponenten nachverfolgen und bietet Optionen zur Auswahl von Flags, wie TF\_COMPONENT und TF\_DIAG. Zentraler Protokollierungsdienst behält außerdem die Protokollierungsebenenoptionen von OCSLogger bei.

Der wichtigste Vorteil bei der Verwendung der Windows PowerShell gegenüber der ClsController-Befehlszeile besteht darin, dass Sie neue Szenarien konfigurieren und definieren können, in denen Sie ausgewählte Anbieter, eigene Flags und Protokollierungsebenen verwenden, die auf den Problembereich abzielen. Die für ClsController verfügbaren Szenarien sind auf die für das Programm definierten Szenarien beschränkt.

In früheren Versionen war OCSLogger.exe verfügbar, um Administratoren und Supportmitarbeitern das Erfassen von Nachverfolgungsdateien von Computern in der Bereitstellung zu ermöglichen. OCSLogger hatte bei all seinen Stärken einen Nachteil. Sie konnten damit nur jeweils auf einem Computer Protokolle erfassen. Sie konnten sich bei mehreren Computern anmelden, indem Sie separate Kopien von OCSLogger verwendeten, Sie erhielten aber mehrere Protokolle und hatten kein einfaches Verfahren, die Ergebnisse zusammenzufassen.

Wenn ein Benutzer eine Protokollsuche anfordert, ermittelt der ClsController, an welche Computer die Anfrage gesendet werden muss (dies basiert auf den ausgewählten Szenarien). Er bestimmt außerdem, ob die Suche an die Dateifreigabe gesendet werden muss, in der sich die gespeicherten .etl-Dateien befinden. Wenn die Suchergebnisse an den ClsController zurückgegeben werden, fasst der Controller die Ergebnisse zu einem einzigen, zeitlich geordneten Ergebnissatz zusammen, der an dem Benutzer angezeigt wird. Benutzer können die Suchergebnisse für weitere Analysen auf ihrem lokalen Computer speichern.

Wenn Sie eine Protokollierungssitzung starten, legen Sie Szenarien fest, die sich auf das Problem beziehen, das Sie beheben möchten. Sie können jederzeit zwei Szenarien gleichzeitig ausführen. Eines dieser beiden Szenarien sollte das Szenario "AlwaysOn" sein. Dieses sollte in Ihrer Bereitstellung immer ausgeführt werden und Informationen von allen Computern, Pools und Komponenten erfassen.


> [!IMPORTANT]  
> Das Szenario "AlwaysOn" wird standardmäßig nicht in Ihrer Bereitstellung ausgeführt. Sie müssen das Szenario explizit starten. Nach dem Start wird es so lange ausgeführt, bis es explizit beendet wird. Der Ausführungsstatus ändert sich auch beim Neustart der Computer nicht. Ausführliche Informationen zum Starten und Beenden von Szenarien finden Sie unter <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Verwenden von "Start", damit der zentralisierte Protokollierungsdienst Protokolle erfasst</A> und <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Verwenden von "Stop" für den zentralisierten Protokollierungsdienst</A>.

Wenn ein Problem auftritt, können Sie ein zweites Szenario starten, das sich auf das Problem bezieht. Reproduzieren Sie das Problem, und beenden Sie dann die Protokollierung für das zweite Szenario. Beginnen Sie für das Problem mit der Protokollsuche. Die zusammengefassten Protokolle ergeben eine Protokolldatei, die Nachverfolgungsmeldungen von allen Computern des Standort- oder des globalen Bereichs Ihrer Bereitstellung enthält. Wenn die Suche mehr Daten zurückgibt, als Sie analysieren können (meist Störabstände, bei denen das Rauschen zu hoch ist), führen Sie eine weitere Suche mit enger gesteckten Parametern durch. An diesem Punkt können Sie gegebenenfalls auftretende Muster feststellen, die Ihnen helfen, das Problem genauer einzugrenzen. Letztlich finden Sie nach diversen verfeinerten Suchen Daten, die für das Problem relevant sind und die Hauptursache deutlich machen.

> [!TIP]  
> Wenn Ihnen in Lync Server ein Problemszenario vorgelegt wird, fragen Sie sich zuerst: "Was weiß ich bereits über das Problem?" Indem Sie die Grenzen des Problems quantifizieren, können Sie einen großen Teil der operativen Entitäten in Lync Server ausschließen.
> Stellen Sie sich ein Beispielszenario vor, in dem Sie wissen, dass Benutzer bei der Suche nach einem Kontakt keine aktuellen Ergebnisse erhalten. Hier ist es nicht erforderlich, in den Medienkomponenten, Enterprise-VoIP, dem Konferenzdienst und einer Vielzahl anderer Komponenten nach Problemen zu suchen. Was Sie nicht wissen, ist, wo das Problem tatsächlich auftritt: auf dem Client oder auf dem Server? Kontakte werden aus Active Directory durch den User Replicator erfasst und über den ABServer (Address Book Server) an den Client geliefert. Der ABServer erhält seine Updates von der RTC-Datenbank (in die der User Replicator diese geschrieben hat) und erfasst diese in Adressbuchdateien – standardmäßig um 1:30 Uhr. Die Lync Server-Clients rufen das neue Adressbuch nach einem zufallsgesteuerten Plan ab. Da Sie wissen, wie der Prozess arbeitet, können Sie Ihre Suche nach der potenziellen Ursache auf ein Problem einschränken, das mit dem Erfassen der Daten aus Active Directory durch den User Replicator zusammenhängt, damit, dass der ABServer die Daten nicht abruft und keine Adressbuchdateien erstellt, oder damit, dass die Clients die Adressbuchdatei nicht herunterladen.
