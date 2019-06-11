---
title: 'Lync Server 2013: Anforderungen für Webkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="9180b-102">Webkonferenz Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9180b-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9180b-103">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9180b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9180b-104">Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:</span><span class="sxs-lookup"><span data-stu-id="9180b-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="9180b-105">Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9180b-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="9180b-106">Integration mit dem Office Web App-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9180b-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="9180b-107">Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="9180b-107">File Store</span></span>

<span data-ttu-id="9180b-108">Der lync Server 2013-Webkonferenzdienst speichert während Besprechungen im Dateispeicher freigegebene Inhalte.</span><span class="sxs-lookup"><span data-stu-id="9180b-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="9180b-109">Als Teil der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Enterprise Edition-Front-End-Pool verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9180b-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="9180b-110">Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.</span><span class="sxs-lookup"><span data-stu-id="9180b-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="9180b-111">Weitere Informationen finden Sie unter Topologie-Generator – definieren Sie den Dateispeicher für das Front-End.</span><span class="sxs-lookup"><span data-stu-id="9180b-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="9180b-112">Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="9180b-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="9180b-113">Lync Server 2013 unterstützt die Verwendung von Dateifreigaben entweder in Direct Attached Storage (das) oder in einem SAN (Storage Area Network), einschließlich DFS (Distributed File System) und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="9180b-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="9180b-114">Nachdem der lync Server-Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt lync Server eine Ordnerstruktur innerhalb der Dateifreigabe ähnlich wie:</span><span class="sxs-lookup"><span data-stu-id="9180b-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="9180b-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="9180b-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="9180b-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="9180b-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="9180b-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="9180b-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="9180b-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="9180b-118">CollabContent</span></span>
    
      - <span data-ttu-id="9180b-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="9180b-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="9180b-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="9180b-120">DataConf</span></span>

<span data-ttu-id="9180b-121">Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern „CollabContent“ und „CollabMetadata“, die sich wiederum im Ordner „WebServices“ befinden.</span><span class="sxs-lookup"><span data-stu-id="9180b-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="9180b-122">Der Administrator muss Berechtigungen für die Dateifreigabe einrichten, damit RTC-Gruppen über den erforderlichen Lese-und Schreibzugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="9180b-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9180b-123">Wenn Fehler mit den Berechtigungen auftreten, öffnen Sie den Topologie-Generator, laden Sie die vorhandene Topologie herunter, und veröffentlichen Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="9180b-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="9180b-124">Beim Veröffentlichen der Topologie werden die Dateifreigabeberechtigungen überprüft und bei Bedarf zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9180b-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="9180b-125">Sie können die folgenden Einstellungen verwenden, um zu verwalten, wie Inhalte für eine Besprechung gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="9180b-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="9180b-126">In **ContentGracePeriod**, das sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, wird festgelegt, wie lange Webkonferenzinhalte auf dem Server verbleiben, nachdem die Besprechung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9180b-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="9180b-127">**MaxContentStorageMb**, das sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, legt die maximale Menge an Dateispeicherplatz fest, die für die Speicherung von Inhalten während einer einzelnen Besprechung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9180b-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="9180b-128">**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein.</span><span class="sxs-lookup"><span data-stu-id="9180b-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="9180b-129">Der Grenzwert für die Upload-Dateigröße für lync Web App ist auf ungefähr 30 MB festgesetzt und wird von der IIS Web.\[config\]-Datei gesteuert:/DataCollabWeb/int ext/Handler/Web.config. Zum Konfigurieren des Upload-Grenzwerts für die Dateigröße für lync `maxRequestLength` Web `maxAllowedContentLength` APP aktualisieren Sie die Datei Web. config wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9180b-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="9180b-130">Sie müssen die Datei Web. config für jeden Front-End-Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9180b-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="9180b-131">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="9180b-131">Office Web Apps Server</span></span>

<span data-ttu-id="9180b-132">Um diese neuen Funktionen verwenden zu können, müssen Administratoren Office Web Apps Server installieren und lync Server 2013 für die Kommunikation mit Office Web Apps Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9180b-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="9180b-133">Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="9180b-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="9180b-134">In dieser Dokumentation werden keine Informationen zur Installation von Office Web Apps Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9180b-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="9180b-135">Einzelheiten zur Installation finden Sie auf <http://go.microsoft.com/fwlink/p/?linkid=257525>der Microsoft Office Web Apps-Bereitstellungswebsite unter.</span><span class="sxs-lookup"><span data-stu-id="9180b-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="9180b-136">Dieser Leitfaden enthält alle erforderlichen Informationen für Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="9180b-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="9180b-137">Beachten Sie, dass der Office Web Apps-Server auf einem eigenständigen Computer installiert sein sollte, auf dem lync Server, SQL Server oder eine andere Serveranwendung nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9180b-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="9180b-138">(Auf diesem Computer darf keine Office-Version installiert sein.) Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Softwaregruppe installiert sein (einschließlich .NET Framework 4,5 und Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="9180b-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="9180b-139">Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Informationsdienste (IIS) werden ausführlich auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <http://go.microsoft.com/fwlink/p/?linkid=257525>erläutert.</span><span class="sxs-lookup"><span data-stu-id="9180b-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9180b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9180b-140">See Also</span></span>


[<span data-ttu-id="9180b-141">Übersicht über Webkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9180b-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="9180b-142">Bereitstellungscheckliste für Webkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9180b-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

