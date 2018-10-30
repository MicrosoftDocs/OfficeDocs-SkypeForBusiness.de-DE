---
title: Webkonferenzanforderungen
TOCTitle: Webkonferenzanforderungen
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49293237
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Webkonferenzanforderungen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

  - Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

  - Integration mit Office Web Apps-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.

## Dateispeicher

Der Lync Server 2013-Webkonferenzdienst speichert bei Besprechungen freigegebene Inhalte im Dateispeicher. Im Rahmen der Bereitstellung müssen Sie eine Dateifreigabe festlegen, die als Dateispeicher für Standard Edition-Server oder den Enterprise Edition-Front-End-Pool verwendet wird. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben. Weitere Informationen finden Sie unter "Topologie-Generator – Definieren des Dateispeichers für das Front-End". Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Lync Server 2013 unterstützt die Verwendung von Dateifreigaben auf DAS (Direct Attached Storage)- oder SAN-Lösungen (Storage Area Network), einschließlich DFS (Distributed File System), sowie RAID-Komponenten (Redundant Array of Independent Disks) für Dateispeicher. Nachdem der Lync Server-Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt Lync Server innerhalb der Dateifreigabe eine ähnliche Ordnerstruktur wie die Folgende:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern "CollabContent" und "CollabMetadata", die sich wiederum im Ordner "WebServices" befinden.

Der Administrator muss Berechtigungen für die Dateifreigabe festlegen, um RTC-Gruppen den erforderlichen Lese- und Schreibzugriff zu gewähren.


> [!WARNING]
> Wenn bei den Berechtigungen Fehler auftreten, öffnen Sie den Topologie-Generator und veröffentlichen die vorhandene Topologie erneut. Durch das Veröffentlichen der Topologie werden die Dateifreigabeberechtigungen überprüft und ggf. zurückgesetzt.



Sie können die folgenden Einstellungen verwenden, um das Speichern von Inhalten für eine Besprechung zu verwalten:

  - Mit der Einstellung **ContentGracePeriod** in [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration) wird festgelegt, wie lange Webkonferenzinhalte nach dem Ende der Besprechung auf dem Server verbleiben.

  - Mit der Einstellung **MaxContentStorageMb** in [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration) wird die Höchstmenge an , zulässigem Dateispeicherplatz für das Speichern von Inhalten während einer einzelnen Besprechung festgelegt.

Mit **MaxUploadFileSizeMb** wird nicht die Einstellung für den Dateiupload für Lync Web App beschränkt. Der Grenzwert für die Uploaddateigröße für Lync Web App ist auf ca. 30 MB festgelegt und wird von der IIS-Datei "web.config" gesteuert: "/DataCollabWeb/Int\[Ext\]/Handler/web.config". Zum Konfigurieren des Grenzwerts für die Uploaddateigröße für Lync Web App aktualisieren Sie wie unten dargestellt in der Datei "web.config" `maxRequestLength` und `maxAllowedContentLength`.

    <system.web>
        <!-- Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Sie müssen die Datei "web.config" für jeden Front-End-Server aktualisieren.

## Office Web Apps-Server

Um diese neuen Funktionen nutzen zu können, müssen Administratoren Office Web Apps-Server installieren und Lync Server 2013 für die Kommunikation mit Office Web Apps-Server konfigurieren. Diese Dokumentation enthält Informationen zur Konfiguration von Lync Server 2013 für die Verwendung mit Office Web Apps-Server. Sie enthält jedoch keine Informationen zur Installation von Office Web Apps-Server. Informationen zur Installation finden Sie auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <http://go.microsoft.com/fwlink/?linkid=257525>. Dieses Handbuch enthält vollständige Informationen zu den Voraussetzungen für Office Web Apps-Server. Beachten Sie, dass Office Web Apps-Server auf einem eigenständigen Computer ohne Lync Server, SQL Server oder einer anderen Serveranwendung installiert werden sollte. (Auf dem Computer darf keine Version von Office installiert sein.) Auf dem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch bestimmte Software installiert sein (darunter .NET Framework 4.5 und Windows PowerShell 3.0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internetinformationsdienste (Internet Information Services, IIS) sind auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <http://go.microsoft.com/fwlink/?linkid=257525> ausführlich erläutert.

## Siehe auch

#### Konzepte

[Übersicht über Webkonferenzen in Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Prüfliste zur Bereitstellung für Webkonferenzen in Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)

