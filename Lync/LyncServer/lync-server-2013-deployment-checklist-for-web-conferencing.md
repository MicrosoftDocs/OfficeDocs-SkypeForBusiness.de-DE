---
title: Checkliste für die lync Server 2013-Bereitstellung für Webkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f845fd57846d7f9b58351d1cb77f3f1c0142ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="74689-102">Bereitstellungscheckliste für Webkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74689-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74689-103">_**Letztes Änderungsdatum des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="74689-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="74689-104">Wie bei der Bereitstellung Ihrer anderen lync Server 2013-Komponenten erfordert die Bereitstellung von Webkonferenzen, dass Sie den Topologie-Generator verwenden, um eine Topologie zu erstellen und zu veröffentlichen, in der Konferenzen integriert sind.</span><span class="sxs-lookup"><span data-stu-id="74689-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="74689-105">Bereitstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="74689-105">Deployment Sequence</span></span>

<span data-ttu-id="74689-106">Sie können Konferenzen gleichzeitig bereitstellen, indem Sie Ihre anfängliche Topologie bereitstellen oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="74689-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="74689-107">Konferenz Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="74689-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="74689-108">Die folgende Tabelle enthält eine Übersicht über die erforderlichen Schritte zum Bereitstellen von Konferenzen in einer vorhandenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="74689-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74689-109">Phase</span><span class="sxs-lookup"><span data-stu-id="74689-109">Phase</span></span></th>
<th><span data-ttu-id="74689-110">Schritte</span><span class="sxs-lookup"><span data-stu-id="74689-110">Steps</span></span></th>
<th><span data-ttu-id="74689-111">Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="74689-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="74689-112">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="74689-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74689-113"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="74689-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="74689-114">Konferenzen werden auf Front-End-Servern in einem Front-End-Pool und auf Standard Edition-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74689-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="74689-115">Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.</span><span class="sxs-lookup"><span data-stu-id="74689-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="74689-116">In lync Server 2013 werden Office Web Apps und der Office Web Apps-Server verwendet, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="74689-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="74689-117">Informationen zum Installieren und Konfigurieren von Office Web Apps Server finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration in Office Web Apps Server und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="74689-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="74689-118">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</span><span class="sxs-lookup"><span data-stu-id="74689-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="74689-119"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Dokumentation zur Unterstützung</span><span class="sxs-lookup"><span data-stu-id="74689-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="74689-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung für Server Software und-Infrastruktur in lync Server 2013</a> in der Dokumentation zur Unterstützung</span><span class="sxs-lookup"><span data-stu-id="74689-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="74689-121"><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln der Systemanforderungen für lync Server 2013</a> in der Planungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="74689-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="74689-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="74689-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74689-123"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung von Konferenzen</strong></span><span class="sxs-lookup"><span data-stu-id="74689-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="74689-124">Führen Sie den Topologie-Generator aus, um der Topologie Konferenzen hinzuzufügen, und veröffentlichen Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="74689-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="74689-125">Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</span><span class="sxs-lookup"><span data-stu-id="74689-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="74689-126">So veröffentlichen Sie die Topologie: ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und das Vollzugriffsberechtigungen (Lesen/Schreiben/ändern) für die Dateifreigabe hat, die für den lync Server 2013-Dateispeicher verwendet werden soll (damit der Topologie-Generator Konfigurieren der erforderlichen DACLs</span><span class="sxs-lookup"><span data-stu-id="74689-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="74689-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und konfigurieren Sie eine Topologie im Topologie-Generator für lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="74689-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74689-128"><strong>Konfigurieren von Konferenzrichtlinien und-Support</strong></span><span class="sxs-lookup"><span data-stu-id="74689-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="74689-129">Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell, um Konferenzeinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="74689-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="74689-130">RTCUniversalServerAdmins-Gruppe (nur Windows PowerShell) oder Zuweisen von Benutzern zur []-oder CSAdministrator-Rolle</span><span class="sxs-lookup"><span data-stu-id="74689-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="74689-131"><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</a> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="74689-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74689-132">Lync Server 2013 enthält jetzt die **MaxUploadFileSizeMb** -Einstellung, die die Größe von Dateien begrenzt, die während einer Besprechung hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="74689-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="74689-133">Der Standardwert für diese Einstellung ist 500 MB.</span><span class="sxs-lookup"><span data-stu-id="74689-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="74689-134">Sie können **MaxUploadFileSizeMb** mit dem Cmdlet " **Satz-CsConferencingConfiguration** " anpassen.</span><span class="sxs-lookup"><span data-stu-id="74689-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="74689-135">**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein.</span><span class="sxs-lookup"><span data-stu-id="74689-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="74689-136">Der Grenzwert für die Upload-Dateigröße für lync Web App ist auf ungefähr 30 MB festgesetzt und wird von der IIS Web.\[config\]-Datei gesteuert:/DataCollabWeb/int ext/Handler/Web.config. Zum Konfigurieren des Upload-Grenzwerts für die Dateigröße für lync `maxRequestLength` Web `maxAllowedContentLength` APP aktualisieren Sie die Datei Web. config wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="74689-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="74689-137">Sie müssen die Datei Web. config für jeden Front-End-Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="74689-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

