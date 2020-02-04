---
title: 'Lync Server 2013: Installieren der Standard Edition-Serverdatenbank'
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
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="b757d-102">Installieren der Standard Edition-Serverdatenbank für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b757d-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b757d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b757d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b757d-104">Wenn Sie einen Standard Edition-Server als einzigen Server in Ihrer Infrastruktur einrichten, der sich von anderen Server Installationen unterscheidet, gibt es im **Bereitstellungs-Assistenten** eine Auswahl, die speziell für das Einrichten des ursprünglichen Servers vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="b757d-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="b757d-105">So installieren Sie einen Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="b757d-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="b757d-106">Melden Sie sich bei dem Server an, auf dem Sie den Standard Edition-Server als lokalen Administrator oder als Domänen Entsprechung installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b757d-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="b757d-107">Wenn Sie die Active Directory-Domänendienste nicht vorbereitet haben, führen Sie zuerst diese Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="b757d-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="b757d-108">Ausführliche Informationen finden Sie unter [Vorbereiten von Active Directory-Domänendiensten für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="b757d-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="b757d-109">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="b757d-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="b757d-110">Klicken Sie auf der Seite **Single Standard Edition-Server vorbereiten** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b757d-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="b757d-111">Auf der Seite **Ausführungsbefehle** wird SQL Server 2012 Express als zentraler Verwaltungsspeicher installiert.</span><span class="sxs-lookup"><span data-stu-id="b757d-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="b757d-112">Es werden erforderliche Firewallregeln erstellt.</span><span class="sxs-lookup"><span data-stu-id="b757d-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="b757d-113">Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b757d-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b757d-114">Die anfängliche Installation kann einige Zeit in Anspruch nehmen, ohne dass die Anzeige des Befehlsausgabe Zusammenfassungsbildschirms sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="b757d-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="b757d-115">Dies ist auf die Installation von SQL Server Express zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="b757d-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="b757d-116">Wenn Sie die Installation der Datenbank überwachen müssen, verwenden Sie den Task-Manager, um das Setup zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="b757d-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="b757d-117">Klicken Sie auf der Seite mit dem lync Server-Bereitstellungs-Assistenten auf **Topologie-Generator installieren** , wenn Sie die Verwaltungstools zuvor noch nicht installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b757d-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="b757d-118">Ausführliche Informationen finden Sie unter [Installieren von lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b757d-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="b757d-119">Vergewissern Sie sich, dass neben "Active Directory vorbereiten", "Vorbereiten des ersten Standard Edition-Servers" und "Installieren des Topologie-Generators" grüne Häkchen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b757d-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

