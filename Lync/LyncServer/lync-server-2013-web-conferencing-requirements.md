---
title: 'Lync Server 2013: Webkonferenz Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b75663f1e5bc51136ac0a2254944541716ad6f74
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Webkonferenz Anforderungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

  - <span></span>  
    Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

  - <span></span>  
    Integration mit Office webapps Server, die erforderlich ist, um PowerPoint-Dateien während einer Konferenz freizugeben.

<div>

## <a name="file-store"></a>Dateispeicher

Der lync Server 2013-Webkonferenzdienst speichert während Besprechungen im Dateispeicher freigegebene Inhalte. Im Rahmen der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für die Front-End-Pool Standard Edition-Server oder Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.Weitere Informationen finden Sie unter "Topologie-Generator – Definieren des Dateispeichers für das Front-End". Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Lync Server 2013 unterstützt die Verwendung von Dateifreigaben entweder im Direct Attached Storage (das) oder im San (Storage Area Network), einschließlich DFS (Distributed File System) und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Nachdem der lync Server-Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt lync Server eine Ordnerstruktur innerhalb der Dateifreigabe, die der folgenden ähnelt:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-Webservices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - Dataconf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern "CollabContent" und "CollabMetadata", die sich wiederum im Ordner "WebServices" befinden.

Der Administrator muss Berechtigungen für die Dateifreigabe festlegen, um RTC-Gruppen den erforderlichen Lese- und Schreibzugriff zu gewähren.

<div>


> [!WARNING]  
> Wenn bei den Berechtigungen Fehler auftreten, öffnen Sie den Topologie-Generator und veröffentlichen die vorhandene Topologie erneut. Durch das Veröffentlichen der Topologie werden die Dateifreigabeberechtigungen überprüft und ggf. zurückgesetzt.



</div>

Sie können die folgenden Einstellungen verwenden, um das Speichern von Inhalten für eine Besprechung zu verwalten:

  - **ContentGracePeriod**, die sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, legt fest, wie lange Webkonferenzinhalte auf dem Server verbleiben, nachdem die Besprechung beendet wurde.

  - **MaxContentStorageMb**, die sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, legt die maximale Menge an Dateispeicherplatz fest, die für die Speicherung von Inhalten während einer einzelnen Besprechung zulässig ist.

**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein. Der Grenzwert für die Dateigrößen Uploads für lync Web App wird auf ungefähr 30 MB festgelegt und wird von der IIS-Datei\["\]Internet. config" gesteuert:/DataCollabWeb/int ext/Handler/Web.config. Um den Upload-Grenzwert für die Dateigröße für lync Web App `maxRequestLength` zu `maxAllowedContentLength` konfigurieren, aktualisieren Sie und in der Datei "config" wie unten dargestellt.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
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

Sie müssen die Datei "Internet. config" für jede Front-End-Server aktualisieren.

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps-Server

Um diese neuen Funktionen nutzen zu können, müssen Administratoren Office-webapps Server installieren und lync Server 2013 für die Kommunikation mit Office-webapps-Server konfigurieren. Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Verwendung mit Office-webapps Server. In dieser Dokumentation werden Informationen zur Installation von Office-webapps Server nicht bereitgestellt. Weitere Informationen zur Installation finden Sie auf <https://go.microsoft.com/fwlink/p/?linkid=257525>der Microsoft Office Web Apps-Bereitstellungswebsite unter. Dieser Leitfaden enthält alle erforderlichen Informationen für Office-webapps Server. Beachten Sie, dass Office webapps Server auf einem eigenständigen Computer installiert werden sollte, auf dem lync Server, SQL Server oder eine andere Server Anwendung nicht aktiv ist. (Auf diesem Computer darf keine Version von Office installiert sein.) Auf jedem Computer, auf dem Office-webapps-Server ausgeführt wird, muss auch ein bestimmter Softwaresatz installiert sein (einschließlich .NET Framework 4.5 und Windows PowerShell 3,0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Information Services (IIS) werden ausführlich in der Microsoft Office Web Apps-Bereitstellungswebsite unter <https://go.microsoft.com/fwlink/p/?linkid=257525>beschrieben.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über Webkonferenzen in lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Prüfliste für die Bereitstellung von Webkonferenzen in lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

