---
title: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0a690d38d6f7d348cdaf12503b08027bc4c0f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="6bb3d-102">Veröffentlichen der aktualisierten Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bb3d-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bb3d-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6bb3d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6bb3d-104">Nach dem Aktualisieren der Topologie im Topologie-Generator müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie den Server für beständigen Chat Konfigurieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="6bb3d-105">Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="6bb3d-106">So veröffentlichen Sie eine aktualisierte Topologie</span><span class="sxs-lookup"><span data-stu-id="6bb3d-106">To publish an updated topology</span></span>

<span data-ttu-id="6bb3d-107">Installieren Sie vor dem Veröffentlichen der Topologie die Datenbanken für den Server für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="6bb3d-108">Verwenden Sie den Topologie-Generator, um Datenbanken zu installieren, indem Sie **Aktion** auswählen und **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="6bb3d-109">Melden Sie sich auf einem Computer, auf dem lync Server 2013 oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der Gruppe " **Domänen-Admins** " und der **RTCUniversalServerAdmins** -Gruppe ist. und verfügt über Vollzugriff auf den Dateispeicher, der für den Dateispeicher für persistent Chat Server verwendet werden kann (also Lese-, Schreib-und Änderungsberechtigungen), sodass der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) oder ein Konto mit gleichwertigen Benutzerrechten konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="6bb3d-110">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-110">Start Topology Builder.</span></span> <span data-ttu-id="6bb3d-111">Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen** oder, wenn Sie die Topologie lokal gespeichert haben, **Topologie aus einer lokalen Datei öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="6bb3d-112">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="6bb3d-113">Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="6bb3d-114">Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6bb3d-115">Nach dem Veröffentlichen der Topologie müssen Sie die Unterstützung für den Server für beständigen Chat konfigurieren, bevor Inhalte archiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="6bb3d-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

