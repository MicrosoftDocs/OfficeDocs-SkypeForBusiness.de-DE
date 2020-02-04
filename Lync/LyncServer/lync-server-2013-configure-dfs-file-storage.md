---
title: 'Lync Server 2013: Konfigurieren des Dateispeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb932a602ad1fc49907be9c5ab2777bc7a415f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="f0de4-102">Konfigurieren des Dateispeichers für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0de4-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0de4-103">_**Letztes Änderungsdatum des Themas:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="f0de4-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="f0de4-104">Lync Server 2013 unterstützt die Verwendung von Dateifreigaben in einem verteilten Datei System (DFS).</span><span class="sxs-lookup"><span data-stu-id="f0de4-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="f0de4-105">Ausführliche Informationen zu DFS für Windows Server 2008 finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)der schrittweisen Anleitung zu DFS für Windows Server 2008 unter. Um ein DFS zu verwenden, benötigt lync Server 2013 Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f0de4-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="f0de4-106">Namespaces sind Domänen basiert</span><span class="sxs-lookup"><span data-stu-id="f0de4-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="f0de4-107">Auf allen Namespaceservern wird ein minimales Windows 2008 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0de4-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="f0de4-108">Das Setup von lync Server 2013 erfordert, dass Berechtigungen für den freigegebenen Ordner den vollständigen Zugriff auf den Administrator ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f0de4-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="f0de4-109">Lync Server 2013 verwendet dann NTFS-Dateiberechtigungen, um die Ordner zu ACL.</span><span class="sxs-lookup"><span data-stu-id="f0de4-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="f0de4-110">Geerbte DFS-Freigabeberechtigungen werden nicht verwendet, um den Zugriff zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="f0de4-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="f0de4-111">Weitere Informationen zu den Anforderungen an Dateifreigaben finden Sie unter unter [Stützung von Dateispeicher in lync Server 2013](lync-server-2013-file-storage-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="f0de4-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0de4-112">Möglicherweise suchen Sie nach Informationen zum Konfigurieren einer nicht DFS-Freigabe.</span><span class="sxs-lookup"><span data-stu-id="f0de4-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="f0de4-113">Wenn dies der Fall ist, lesen Sie <A href="lync-server-2013-hardware-setup.md">Hardware-Setup für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f0de4-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f0de4-114">Im folgenden Verfahren wird beschrieben, wie Sie die Berechtigungen für freigegebene Ordner mithilfe des DFS-Namespace-Assistenten richtig konfigurieren (wie im DFS-Setup Handbuch beschrieben).</span><span class="sxs-lookup"><span data-stu-id="f0de4-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="f0de4-115">So konfigurieren Sie Berechtigungen für freigegebene Ordner</span><span class="sxs-lookup"><span data-stu-id="f0de4-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="f0de4-116">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **DFS-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="f0de4-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="f0de4-117">Klicken Sie in der Konsolenstruktur des DFS-Verwaltungs-Snap-Ins mit der rechten Maustaste auf den Namespaceserver (beispielsweise filesrv1.contoso.com), und klicken Sie dann auf **Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f0de4-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="f0de4-118">Wählen Sie **Berechtigungen für freigegebene Ordner**aus.</span><span class="sxs-lookup"><span data-stu-id="f0de4-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="f0de4-119">Wählen Sie **benutzerdefinierte Berechtigungen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="f0de4-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="f0de4-120">Wählen Sie für die Gruppe Administratoren unter **zulassen**die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f0de4-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="f0de4-121">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="f0de4-121">**Full Control**</span></span>
    
      - <span data-ttu-id="f0de4-122">**Änderung**</span><span class="sxs-lookup"><span data-stu-id="f0de4-122">**Change**</span></span>
    
      - <span data-ttu-id="f0de4-123">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="f0de4-123">**Read**</span></span>

6.  <span data-ttu-id="f0de4-124">Klicken Sie auf über **nehmen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0de4-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

