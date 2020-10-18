---
title: 'Lync Server 2013: Webkonferenz Anforderungen'
description: 'Lync Server 2013: Webkonferenz Anforderungen.'
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
ms.openlocfilehash: 6c1fce932d3cc02ac29364d53d04ec336693e43b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576391"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="18daf-103">Webkonferenz Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18daf-103">Web conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18daf-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="18daf-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="18daf-105">Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:</span><span class="sxs-lookup"><span data-stu-id="18daf-105">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="18daf-106">Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="18daf-106">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="18daf-107">Integration mit Office webapps Server, die erforderlich ist, um PowerPoint-Dateien während einer Konferenz freizugeben.</span><span class="sxs-lookup"><span data-stu-id="18daf-107">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="18daf-108">Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="18daf-108">File Store</span></span>

<span data-ttu-id="18daf-109">Der lync Server 2013-Webkonferenzdienst speichert während Besprechungen im Dateispeicher freigegebene Inhalte.</span><span class="sxs-lookup"><span data-stu-id="18daf-109">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="18daf-110">Im Rahmen der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für die Front-End-Pool Standard Edition-Server oder Enterprise Edition verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="18daf-110">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="18daf-111">Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.</span><span class="sxs-lookup"><span data-stu-id="18daf-111">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="18daf-112">Weitere Informationen finden Sie unter "Topologie-Generator – Definieren des Dateispeichers für das Front-End".</span><span class="sxs-lookup"><span data-stu-id="18daf-112">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="18daf-113">Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="18daf-113">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="18daf-114">Lync Server 2013 unterstützt die Verwendung von Dateifreigaben entweder im Direct Attached Storage (das) oder im San (Storage Area Network), einschließlich DFS (Distributed File System) und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="18daf-114">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="18daf-115">Nachdem der lync Server-Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt lync Server eine Ordnerstruktur innerhalb der Dateifreigabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="18daf-115">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="18daf-116">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="18daf-116">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="18daf-117">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="18daf-117">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="18daf-118">1-Webservices-1</span><span class="sxs-lookup"><span data-stu-id="18daf-118">1-WebServices-1</span></span>
    
      - <span data-ttu-id="18daf-119">CollabContent</span><span class="sxs-lookup"><span data-stu-id="18daf-119">CollabContent</span></span>
    
      - <span data-ttu-id="18daf-120">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="18daf-120">CollabMetadata</span></span>
    
      - <span data-ttu-id="18daf-121">Dataconf</span><span class="sxs-lookup"><span data-stu-id="18daf-121">DataConf</span></span>

<span data-ttu-id="18daf-122">Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern "CollabContent" und "CollabMetadata", die sich wiederum im Ordner "WebServices" befinden.</span><span class="sxs-lookup"><span data-stu-id="18daf-122">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="18daf-123">Der Administrator muss Berechtigungen für die Dateifreigabe festlegen, um RTC-Gruppen den erforderlichen Lese- und Schreibzugriff zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="18daf-123">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="18daf-p103">Wenn bei den Berechtigungen Fehler auftreten, öffnen Sie den Topologie-Generator und veröffentlichen die vorhandene Topologie erneut. Durch das Veröffentlichen der Topologie werden die Dateifreigabeberechtigungen überprüft und ggf. zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="18daf-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="18daf-126">Sie können die folgenden Einstellungen verwenden, um das Speichern von Inhalten für eine Besprechung zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="18daf-126">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="18daf-127">**ContentGracePeriod**, die sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, legt fest, wie lange Webkonferenzinhalte auf dem Server verbleiben, nachdem die Besprechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="18daf-127">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="18daf-128">**MaxContentStorageMb**, die sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, legt die maximale Menge an Dateispeicherplatz fest, die für die Speicherung von Inhalten während einer einzelnen Besprechung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="18daf-128">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="18daf-129">**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein.</span><span class="sxs-lookup"><span data-stu-id="18daf-129">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="18daf-130">Der Grenzwert für die Dateigrößen Uploads für lync Web App wird auf ungefähr 30 MB festgelegt und wird von der IIS-web.config Datei gesteuert:/DataCollabWeb/int \[ Ext \] /Handler/web.config. Um den Upload-Grenzwert für die Dateigröße für lync Web App zu konfigurieren, aktualisieren Sie `maxRequestLength` und `maxAllowedContentLength` in der web.config Datei, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="18daf-130">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="18daf-131">Sie müssen die web.config Datei für jeden Front-End-Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="18daf-131">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="18daf-132">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="18daf-132">Office Web Apps Server</span></span>

<span data-ttu-id="18daf-133">Um diese neuen Funktionen nutzen zu können, müssen Administratoren Office-webapps Server installieren und lync Server 2013 für die Kommunikation mit Office-webapps-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="18daf-133">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="18daf-134">Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Verwendung mit Office-webapps Server.</span><span class="sxs-lookup"><span data-stu-id="18daf-134">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="18daf-135">In dieser Dokumentation werden Informationen zur Installation von Office-webapps Server nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="18daf-135">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="18daf-136">Weitere Informationen zur Installation finden Sie auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="18daf-136">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="18daf-137">Dieser Leitfaden enthält alle erforderlichen Informationen für Office-webapps Server.</span><span class="sxs-lookup"><span data-stu-id="18daf-137">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="18daf-138">Beachten Sie, dass Office webapps Server auf einem eigenständigen Computer installiert werden sollte, auf dem lync Server, SQL Server oder eine andere Server Anwendung nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="18daf-138">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="18daf-139">(Auf diesem Computer darf keine Version von Office installiert sein.) Auf jedem Computer, auf dem Office-webapps-Server ausgeführt wird, muss auch ein bestimmter Softwaresatz installiert sein (einschließlich .NET Framework 4.5 und Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="18daf-139">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="18daf-140">Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Information Services (IIS) werden ausführlich in der Microsoft Office Web Apps-Bereitstellungswebsite unter beschrieben <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="18daf-140">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18daf-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18daf-141">See Also</span></span>


[<span data-ttu-id="18daf-142">Übersicht über Webkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18daf-142">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="18daf-143">Prüfliste für die Bereitstellung von Webkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18daf-143">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

