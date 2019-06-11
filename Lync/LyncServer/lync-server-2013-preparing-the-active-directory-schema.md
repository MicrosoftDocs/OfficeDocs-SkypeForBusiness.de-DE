---
title: 'Lync Server 2013: Vorbereiten des Active Directory-Schemas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="f794e-102">Vorbereiten des Active Directory-Schemas in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f794e-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f794e-103">_**Letztes Änderungsdatum des Themas:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="f794e-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="f794e-104">Bevor Sie mit dem Vorbereiten der Active Directory-Domänendienste beginnen, können Sie die Schemadateien mit einem Text-Editor wie Windows Notepad öffnen oder die [Active Directory-Schemaerweiterungen,-Klassen und-Attribute anzeigen, die von lync Server 2013 verwendet](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) werden, um alle aktiven zu überprüfen. Verzeichnis-Domänendienste-Schemaerweiterungen, die für lync Server 2013 geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f794e-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="f794e-105">Lync Server verwendet vier Schemadateien:</span><span class="sxs-lookup"><span data-stu-id="f794e-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="f794e-106">ExternalSchema. ldf, das für die Interoperabilität mit Microsoft Exchange Server verwendet wird</span><span class="sxs-lookup"><span data-stu-id="f794e-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="f794e-107">ServerSchema. ldf, die primäre lync Server 2013-Schemadatei</span><span class="sxs-lookup"><span data-stu-id="f794e-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="f794e-108">BackCompatSchema. ldf, das für die Interoperabilität mit Komponenten aus früheren Versionen verwendet wird</span><span class="sxs-lookup"><span data-stu-id="f794e-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="f794e-109">VersionSchema. ldf, das für Versionsinformationen des vorbereiteten Schemas verwendet wird</span><span class="sxs-lookup"><span data-stu-id="f794e-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="f794e-110">Alle LDF-Dateien werden während der Schemavorbereitung installiert, unabhängig davon, ob Sie von einer früheren Version migrieren oder eine Neuinstallation durchführen.</span><span class="sxs-lookup"><span data-stu-id="f794e-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="f794e-111">Diese Schemadateien werden in der in der obigen Liste aufgeführten Reihenfolge installiert und befinden sich im \\Ordner\\"Support Schema" auf dem Installationsmedium.</span><span class="sxs-lookup"><span data-stu-id="f794e-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="f794e-112">Die lync Server-Schemaerweiterungen werden über alle Domänen repliziert, was Auswirkungen auf den Netzwerkverkehr hat.</span><span class="sxs-lookup"><span data-stu-id="f794e-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="f794e-113">Führen Sie die Schemavorbereitung zu einem Zeitpunkt aus, an dem die Netzwerkauslastung gering ist.</span><span class="sxs-lookup"><span data-stu-id="f794e-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f794e-114">Wenn Sie Unterstützung für Microsoft® Office Communicator Mobile 2007 R2 für Java und Microsoft® Office Communicator Mobile für Nokia 1,0 für mobile Clients zu ihrer lync Server 2013-Bereitstellung hinzufügen müssen, müssen Sie das Active Directory-Schema für Microsoft Office vorbereiten. Communications Server 2007 R2 während der Installation von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f794e-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="f794e-115">Die erforderlichen Software-und Dokumentationsinformationen <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="f794e-115">For the necessary software and documentation, see <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="f794e-116">ADSI-Bearbeitung</span><span class="sxs-lookup"><span data-stu-id="f794e-116">ADSI Edit</span></span>

<span data-ttu-id="f794e-117">Der Active Directory Service Interfaces-Editor (ADSI-Bearbeitung) ist ein AD DS-Verwaltungstool, mit dem Sie die Schemavorbereitung und-Replikation überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="f794e-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="f794e-118">Die ADSI-Bearbeitung wird standardmäßig installiert, wenn Sie die AD DS-Rolle installieren, um einen Server zu einem Domänencontroller zu machen.</span><span class="sxs-lookup"><span data-stu-id="f794e-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="f794e-119">Für Windows Server 2008 und Windows Server 2008 R2 ist die ADSI-Bearbeitung (AdsiEdit. msc) in den Remote Server-Verwaltungs Tools enthalten.</span><span class="sxs-lookup"><span data-stu-id="f794e-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="f794e-120">Sie können die Remoteserver-Server auch auf Domänenmitgliedsservern oder eigenständigen Servern installieren.</span><span class="sxs-lookup"><span data-stu-id="f794e-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="f794e-121">Wenn Sie Windows installieren, wird das Remoteserver-Paket standardmäßig auf diese Server kopiert, aber nicht standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="f794e-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="f794e-122">Sie installieren einzelne Tools mithilfe des Server-Managers.</span><span class="sxs-lookup"><span data-stu-id="f794e-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="f794e-123">Die ADSI-Bearbeitung ist unter **Rollenverwaltungstools**, **Active Directory-Domänendienst Tools**, **Active Directory-Domänen Controller Tools**enthalten.</span><span class="sxs-lookup"><span data-stu-id="f794e-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="f794e-124">Für Windows Server 2003 ist die ADSI-Bearbeitung in den Support Tools enthalten.</span><span class="sxs-lookup"><span data-stu-id="f794e-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="f794e-125">Die Support Tools stehen auf der Windows Server 2003-CD im Ordner \\Support\\Tools zur Verfügung, oder Sie können Sie unter "Windows Server 2003 Service Pack 2 32-Bit-Support Tools [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)" herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f794e-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="f794e-126">Anweisungen zum Installieren der Support Tools auf der Produkt-CD finden Sie unter "Installieren von Windows-Support [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)Tools" unter.</span><span class="sxs-lookup"><span data-stu-id="f794e-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="f794e-127">Adsiedit. dll wird automatisch registriert, wenn Sie die Support Tools installieren.</span><span class="sxs-lookup"><span data-stu-id="f794e-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="f794e-128">Wenn Sie die Dateien jedoch auf Ihren Computer kopiert haben, müssen Sie den Befehl **regsvr32** ausführen, um die Datei "Adsiedit. dll" zu registrieren, bevor Sie das Tool ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f794e-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f794e-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f794e-129">In This Section</span></span>

  - [<span data-ttu-id="f794e-130">Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f794e-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="f794e-131">Überprüfen der Active Directory-Schemareplikation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f794e-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f794e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f794e-132">See Also</span></span>


[<span data-ttu-id="f794e-133">Vorbereiten der Gesamtstruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f794e-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="f794e-134">Vorbereiten von Domänen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f794e-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

