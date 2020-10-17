---
title: 'Lync Server 2013: Installieren der Operations Manager-Agent-Dateien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0216c05dd039f907d0ac54ff8afa13f6015a923d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534802"
---
# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="25f56-102">Installieren der Operations Manager-Agent-Dateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25f56-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25f56-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="25f56-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="25f56-104">Führen Sie die folgenden Schritte aus, um die Operations Manager-Agentdateien auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="25f56-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="25f56-105">Doppelklicken Sie auf den System Center-Setupmedien auf **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="25f56-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="25f56-106">Klicken Sie im System Center Operations Manager-Setupprogramm auf **Operations Manager-Agent installieren**.</span><span class="sxs-lookup"><span data-stu-id="25f56-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="25f56-107">Klicken Sie im System Center-Setup-Assistenten auf der Willkommensseite\*\*\*\* des Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="25f56-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="25f56-108">Wählen Sie auf der Seite **Zielordner** den Ordner aus, in dem die Operations Manager-Agentdateien installiert werden sollen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="25f56-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="25f56-109">Wählen Sie auf der Seite **Verwaltungsgruppenkonfiguration** die Option **Verwaltungsgruppeninformationen angeben** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="25f56-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="25f56-110">Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** in das Feld **Verwaltungsgruppenname** den Namen Ihrer Operations Manager-Verwaltungsgruppe ein, und geben Sie dann den Hostnamen Ihres Operations Manager-Servers (beispielsweise ATL-SCOM-001) in das Feld **Verwaltungsserver** ein.</span><span class="sxs-lookup"><span data-stu-id="25f56-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="25f56-111">Wenn Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer in das Feld Verwaltungs Server Port ein.</span><span class="sxs-lookup"><span data-stu-id="25f56-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="25f56-112">Belassen Sie andernfalls den Port mit dem Standardwert 5723, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="25f56-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="25f56-113">Wählen Sie auf der Seite **Agentaktionskonto** die Option **Lokales System** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="25f56-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="25f56-114">Wählen Sie auf der Seite **Microsoft Update** die Option **Ich möchte Microsoft Update nicht verwenden** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="25f56-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="25f56-115">Klicken Sie auf der Seite **Bereit zum Installieren** auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="25f56-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="25f56-116">Klicken Sie auf der Seite **Fertigstellen des System Center Operations Manager-Setup-Assistenten** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="25f56-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="25f56-117">Klicken Sie auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="25f56-117">Click **Exit**.</span></span>

<span data-ttu-id="25f56-118">Wenn Sie System Center 2007 R2 verwenden, können Sie überprüfen, ob der Agent erstellt wurde, indem Sie auf **Start**, auf **Alle Programme**, auf **System Center Operations Manager 2007 R2**und dann auf **Operations Manager-Shell**klicken.</span><span class="sxs-lookup"><span data-stu-id="25f56-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="25f56-119">Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="25f56-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="25f56-120">Eine Liste aller Operations Manager-Agents wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25f56-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="25f56-121">Falls Sie System Center 2012 verwenden, führen Sie den folgenden Befehl in der Operations Manager 2012-Shell aus:</span><span class="sxs-lookup"><span data-stu-id="25f56-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

