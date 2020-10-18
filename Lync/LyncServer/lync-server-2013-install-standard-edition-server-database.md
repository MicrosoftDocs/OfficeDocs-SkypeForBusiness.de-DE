---
title: 'Lync Server 2013: Installieren Standard Edition-Server Datenbank'
description: 'Lync Server 2013: Installieren Sie Standard Edition-Server Datenbank.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a20d2c01de94ad88960555db78c57c6b79d92f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574081"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="ff34e-103">Installieren Standard Edition-Server Datenbank für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff34e-103">Install Standard Edition server database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff34e-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ff34e-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ff34e-105">Das Einrichten eines Standard Edition-Server als einziger Server in Ihrer Infrastruktur, der von den Heimbenutzern unterschiedlich ist, unterscheidet sich von anderen Server Installationen dadurch, dass eine Auswahl im **Bereitstellungs-Assistenten** speziell für das Einrichten des ursprünglichen Servers vorliegt.</span><span class="sxs-lookup"><span data-stu-id="ff34e-105">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="ff34e-106">So installieren Sie einen Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="ff34e-106">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="ff34e-107">Melden Sie sich an dem Server an, auf dem Standard Edition-Server als lokaler Administrator oder als Domänen Äquivalent installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff34e-107">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="ff34e-108">Wenn Sie Active Directory-Domänendienste nicht vorbereitet haben, führen Sie zunächst diese Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="ff34e-108">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="ff34e-109">Ausführliche Informationen finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff34e-109">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="ff34e-110">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="ff34e-110">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="ff34e-111">Klicken Sie auf der Seite **Einzelnen Standard Edition-Server vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ff34e-111">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="ff34e-112">Auf der Seite **Befehle werden ausgeführt** wird der SQL Server 2012 Express als zentraler Verwaltungsspeicher installiert.</span><span class="sxs-lookup"><span data-stu-id="ff34e-112">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="ff34e-113">Die erforderlichen Firewallregeln werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff34e-113">Necessary firewall rules are created.</span></span> <span data-ttu-id="ff34e-114">Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ff34e-114">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff34e-115">Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff34e-115">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="ff34e-116">Dies ist auf die Installation des SQL Server Express zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-116">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="ff34e-117">Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-117">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="ff34e-118">Klicken Sie auf der Seite lync Server-Bereitstellungs-Assistenten auf **Topologie-Generator installieren** , wenn Sie die Verwaltungstools nicht zuvor installiert haben.</span><span class="sxs-lookup"><span data-stu-id="ff34e-118">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="ff34e-119">Ausführliche Informationen finden Sie unter [install lync Server 2013 Administration Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ff34e-119">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="ff34e-120">Vergewissern Sie sich, dass neben "Vorbereiten von Active Directory", "Vorbereiten des ersten Standard Edition-Servers" und "Installieren des Topologie-Generators" grüne Häkchen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff34e-120">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

