---
title: 'Lync Server 2013: Vorbereiten des Active Directory Schemas'
description: 'Lync Server 2013: Vorbereiten des Active Directory Schemas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df7533dcbabe278fd366b441cfd8daa83f54b23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560311"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="e9243-103">Vorbereiten des Active Directory Schemas in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9243-103">Preparing the Active Directory schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9243-104">_**Letztes Änderungsstand des Themas:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="e9243-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="e9243-105">Bevor Sie mit der Vorbereitung Active Directory-Domänendienste beginnen, können Sie die Schemadateien mithilfe eines Text-Editors wie Windows Notepad öffnen oder sich [Active Directory Schemaerweiterungen, Klassen und Attribute ansehen, die von lync Server 2013 verwendet](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) werden, um alle Active Directory-Domänendienste Schemaerweiterungen zu überprüfen, die für lync Server 2013 geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e9243-105">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="e9243-106">Lync Server verwendet vier Schemadateien:</span><span class="sxs-lookup"><span data-stu-id="e9243-106">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="e9243-107">ExternalSchema. ldf, die für die Interoperabilität mit Exchange Server verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e9243-107">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="e9243-108">ServerSchema. ldf, bei dem es sich um die primäre lync Server 2013 Schemadatei handelt</span><span class="sxs-lookup"><span data-stu-id="e9243-108">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="e9243-109">BackCompatSchema.ldf, verwendet zur Interoperabilität mit allen Komponenten aus vorherigen Versionen</span><span class="sxs-lookup"><span data-stu-id="e9243-109">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="e9243-110">VersionSchema.ldf, verwendet für Versionsinformationen des vorbereiteten Schemas</span><span class="sxs-lookup"><span data-stu-id="e9243-110">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="e9243-111">Alle LDF-Dateien werden während der Schemavorbereitung installiert – unabhängig davon, ob Sie eine Migration von einer vorherigen Version oder eine Neuinstallation durchführen.</span><span class="sxs-lookup"><span data-stu-id="e9243-111">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="e9243-112">Diese Schemadateien werden in der in der obigen Liste aufgeführten Reihenfolge installiert und befinden sich im \\ \\ Ordner Support Schema auf dem Installationsmedium.</span><span class="sxs-lookup"><span data-stu-id="e9243-112">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="e9243-113">Die lync Server Schemaerweiterungen werden in allen Domänen repliziert, was sich auf den Netzwerkdatenverkehr auswirkt.</span><span class="sxs-lookup"><span data-stu-id="e9243-113">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="e9243-114">Führen Sie die Schemavorbereitung zu einem Zeitpunkt aus, zu dem die Netzwerkauslastung möglichst gering ist.</span><span class="sxs-lookup"><span data-stu-id="e9243-114">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9243-115">Wenn Sie Unterstützung für Microsoft® Office Communicator Mobile 2007 R2 für Java und Microsoft® Office Communicator Mobile für Nokia 1,0 Mobile Clients zu ihrer lync Server 2013-Bereitstellung hinzufügen müssen, müssen Sie das Active Directory Schema für Microsoft Office Communications Server 2007 R2 während der Installation von lync Server 2013 vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="e9243-115">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="e9243-116">Die erforderliche Software und Dokumentation finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .</span><span class="sxs-lookup"><span data-stu-id="e9243-116">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="e9243-117">ADSI-Editor</span><span class="sxs-lookup"><span data-stu-id="e9243-117">ADSI Edit</span></span>

<span data-ttu-id="e9243-118">Der ADSI-Editor (Active Directory Services Interfaces Editor) ist ein AD DS-Verwaltungstool, mit dem Sie die Schemavorbereitung und -replikation überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="e9243-118">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="e9243-119">Die ADSI-Bearbeitung wird standardmäßig installiert, wenn Sie die AD DS Rolle installieren, um einen Server als Domänencontroller zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9243-119">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="e9243-120">Für Windows Server 2008 und Windows Server 2008 R2 ist ADSI Edit (AdsiEdit. msc) in den Remote Server-Verwaltungs Tools enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9243-120">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="e9243-121">Sie können die Remote Dienstprogrammsoftware auch auf Domänenmitgliedsservern oder eigenständigen Servern installieren.</span><span class="sxs-lookup"><span data-stu-id="e9243-121">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="e9243-122">Das Remote dienstprogrammor-Paket wird bei der Installation von Windows standardmäßig auf diese Server kopiert, wird jedoch nicht standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="e9243-122">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="e9243-123">Sie installieren einzelne Tools mithilfe des Server-Managers.</span><span class="sxs-lookup"><span data-stu-id="e9243-123">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="e9243-124">ADSI-Bearbeitung ist unter **Rollenverwaltungstools**, **Active Directory-Domänendienste Tools**, **Active Directory Domänen Controller Tools**enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9243-124">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="e9243-125">Für Windows Server 2003 ist die ADSI-Bearbeitung in den Support Tools enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9243-125">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="e9243-126">Die Support Tools stehen auf der Windows Server 2003-CD im \\ Ordner Support Tools zur Verfügung \\ , oder Sie können Sie unter "Windows Server 2003 Service Pack 2 32-Bit Support Tools" unter herunterladen [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) .</span><span class="sxs-lookup"><span data-stu-id="e9243-126">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="e9243-127">Anleitungen zum Installieren der Support Tools auf der Produkt-CD finden Sie unter "Install Windows Support Tools" unter [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) .</span><span class="sxs-lookup"><span data-stu-id="e9243-127">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="e9243-128">Adsiedit.dll wird automatisch registriert, wenn Sie die Support Tools installieren.</span><span class="sxs-lookup"><span data-stu-id="e9243-128">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="e9243-129">Wenn Sie die Dateien jedoch auf Ihren Computer kopiert haben, müssen Sie den Befehl " **regsvr32** " ausführen, um die adsiedit.dll Datei zu registrieren, bevor Sie das Tool ausführen können.</span><span class="sxs-lookup"><span data-stu-id="e9243-129">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9243-130">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9243-130">In This Section</span></span>

  - [<span data-ttu-id="e9243-131">Durchführen Active Directory Schemavorbereitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9243-131">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="e9243-132">Überprüfen Active Directory Schemareplikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9243-132">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9243-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9243-133">See Also</span></span>


[<span data-ttu-id="e9243-134">Vorbereiten der Gesamtstruktur auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9243-134">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="e9243-135">Vorbereiten von Domänen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9243-135">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

