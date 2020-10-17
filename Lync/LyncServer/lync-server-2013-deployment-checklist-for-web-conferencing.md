---
title: Prüfliste für lync Server 2013-Bereitstellung für Webkonferenzen
description: Lync Server 2013-Bereitstellungsprüfliste für Webkonferenzen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562181"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="2246a-103">Prüfliste für die Bereitstellung von Webkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2246a-103">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2246a-104">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="2246a-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="2246a-105">Wie bei der Bereitstellung Ihrer anderen lync Server 2013 Komponenten erfordert die Bereitstellung von Webkonferenzen die Verwendung des Topologie-Generators zum Erstellen und Veröffentlichen einer Topologie, in der Konferenzen integriert werden.</span><span class="sxs-lookup"><span data-stu-id="2246a-105">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="2246a-106">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="2246a-106">Deployment Sequence</span></span>

<span data-ttu-id="2246a-107">Sie können Konferenzen gleichzeitig bereitstellen, wenn Sie die anfängliche Topologie bereitstellen oder nachdem Sie mindestens eine Front-End-Pool oder Standard Edition-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="2246a-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="2246a-108">Bereitstellungsverfahren für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="2246a-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="2246a-109">Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung von Konferenzen in einer vorhandenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="2246a-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2246a-110">Phase</span><span class="sxs-lookup"><span data-stu-id="2246a-110">Phase</span></span></th>
<th><span data-ttu-id="2246a-111">Schritte</span><span class="sxs-lookup"><span data-stu-id="2246a-111">Steps</span></span></th>
<th><span data-ttu-id="2246a-112">Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="2246a-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="2246a-113">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="2246a-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2246a-114"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="2246a-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="2246a-115">Konferenzen werden auf Front-End-Servern auf einem Front-End-Pool-und Standard Edition-Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2246a-115">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="2246a-116">Es bestehen keine zusätzlichen Hardware- oder Softwareanforderungen, die die Installationsanforderungen für diese Server übersteigen.</span><span class="sxs-lookup"><span data-stu-id="2246a-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2246a-117">Lync Server 2013 verwendet Office-Webanwendungen und den Office-webapps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2246a-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="2246a-118">Informationen zum Installieren und Konfigurieren des Office-webapps-Servers finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2246a-118">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="2246a-119">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</span><span class="sxs-lookup"><span data-stu-id="2246a-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="2246a-120"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="2246a-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="2246a-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software-und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="2246a-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="2246a-122"><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2246a-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="2246a-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2246a-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2246a-124"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung von Konferenzen</strong></span><span class="sxs-lookup"><span data-stu-id="2246a-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="2246a-125">Führen Sie den Topologie-Generator aus, um der Topologie Konferenzen hinzuzufügen, und veröffentlichen Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="2246a-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="2246a-126">Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</span><span class="sxs-lookup"><span data-stu-id="2246a-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="2246a-127">So veröffentlichen Sie die Topologie, ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und die über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die Dateifreigabe verfügt, die für den lync Server 2013 Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann)</span><span class="sxs-lookup"><span data-stu-id="2246a-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="2246a-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2246a-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2246a-129"><strong>Konfigurieren von Konferenzrichtlinien und -unterstützung</strong></span><span class="sxs-lookup"><span data-stu-id="2246a-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="2246a-130">Verwenden Sie die lync Server 2013-Systemsteuerung oder lync Server-Verwaltungsshell, um Konferenzeinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2246a-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="2246a-131">RTCUniversalServerAdmins-Gruppe (nur Windows PowerShell) oder Zuweisen von Benutzern zur Rolle "[]" oder "CSAdministrator"</span><span class="sxs-lookup"><span data-stu-id="2246a-131">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="2246a-132"><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</a> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2246a-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2246a-133">Lync Server 2013 enthält jetzt die **MaxUploadFileSizeMb** -Einstellung, die die Größe von Dateien beschränkt, die während einer Besprechung hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="2246a-133">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="2246a-134">Der Standardwert für diese Einstellung ist "500 MB".</span><span class="sxs-lookup"><span data-stu-id="2246a-134">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="2246a-135">**MaxUploadFileSizeMb** kann mit dem **Set-CsConferencingConfiguration**-Cmdlet angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2246a-135">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="2246a-136">**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein.</span><span class="sxs-lookup"><span data-stu-id="2246a-136">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="2246a-137">Der Grenzwert für die Dateigrößen Uploads für lync Web App wird auf ungefähr 30 MB festgelegt und wird von der IIS-web.config Datei gesteuert:/DataCollabWeb/int \[ Ext \] /Handler/web.config. Um den Upload-Grenzwert für die Dateigröße für lync Web App zu konfigurieren, aktualisieren Sie `maxRequestLength` und `maxAllowedContentLength` in der web.config Datei, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2246a-137">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="2246a-138">Sie müssen die web.config Datei für jeden Front-End-Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2246a-138">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

