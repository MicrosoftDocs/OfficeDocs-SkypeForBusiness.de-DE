---
title: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5834c6c7d0386f7943c523a184ea63f8ba129a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512242"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="4b821-102">Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b821-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b821-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4b821-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4b821-104">Nach dem Aktualisieren der Topologie im Topologie-Generator müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie die Archivierung konfigurieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4b821-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="4b821-105">Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="4b821-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="4b821-106">So veröffentlichen Sie Ihre aktualisierte Topologie</span><span class="sxs-lookup"><span data-stu-id="4b821-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="4b821-107">Melden Sie sich auf einem Computer, auf dem lync Server 2013 läuft oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).</span><span class="sxs-lookup"><span data-stu-id="4b821-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b821-108">Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die erforderlich ist, um der Topologie einen Server hinzuzufügen. Sie müssen ein Konto verwenden, das Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der <STRONG>RTCUniversalServerAdmins</STRONG> -Gruppe ist und das über die Berechtigung "Vollzugriff" (lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den lync Server 2013 Dateispeicher verwenden (damit der Topologie-Generator die erforderliche DACL (Discretionary Access Control List) oder ein Konto mit gleichwertigen Rechten konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="4b821-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="4b821-109">Öffnen Sie die Topologie, die Sie im vorherigen Abschnitt mithilfe des Topologie-Generators erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4b821-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="4b821-110">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="4b821-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="4b821-111">Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4b821-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="4b821-112">Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4b821-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b821-113">Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="4b821-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="4b821-114">Ausführliche Informationen zu den erforderlichen Administratorrechten und-Berechtigungen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4b821-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="4b821-115">Mithilfe des Topologie-Generators können nur Datenbanken auf dedizierten SQL Server Servern installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4b821-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="4b821-116">Datenbanken auf SQL Server Servern, die mit anderen Server Komponenten zusammenhängen, müssen installiert werden, indem das lokale Setup auf diesem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b821-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="4b821-117">Überprüfen Sie auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, ob die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4b821-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b821-118">Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="4b821-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="4b821-119">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4b821-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

