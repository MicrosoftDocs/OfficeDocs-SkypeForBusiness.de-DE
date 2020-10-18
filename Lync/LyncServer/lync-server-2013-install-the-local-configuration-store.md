---
title: 'Lync Server 2013: Installieren des lokalen Konfigurationsspeichers'
description: 'Lync Server 2013: Installieren Sie den lokalen Konfigurationsspeicher.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf603704a8e1bdfbe71e0a9b064013d57bceda7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574061"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="dc299-103">Installieren des lokalen Konfigurationsspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc299-103">Install the Local Configuration store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc299-104">_**Letztes Änderungsstand des Themas:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="dc299-104">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="dc299-105">Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie bei dem Server mit einem Domänenbenutzerkonto angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der RTCUniversalReadOnlyAdmin-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="dc299-105">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="dc299-106">Um mit dem lync Server-Bereitstellungs-Assistenten etwas tun zu können, muss der lokale Konfigurationsspeicher auf einem Server vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="dc299-106">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="dc299-107">Der lokale Konfigurationsspeicher ist eine schreibgeschützte Kopie des zentralen Verwaltungsspeichers, der nach der lokalen Installation von SQL Server Express erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dc299-107">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="dc299-108">Der zentrale Verwaltungsspeicher selbst wird der vorhandenen SQL Server Datenbank hinzugefügt, die auf der Standard Edition-Server-oder SQL Server Express basierten Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="dc299-108">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dc299-109">Wenn Sie lync Server 2013-Setup noch nicht auf diesem Server ausgeführt haben, werden Sie aufgefordert, ein Laufwerk und einen Pfad einzugeben, um lync Server 2013 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="dc299-109">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="dc299-110">Auf diese Weise können Sie auf einem anderen Laufwerk als dem Systemlaufwerk installieren, wenn es für Ihre Organisation erforderlich ist, oder wenn Sie über Platzprobleme verfügen.</span><span class="sxs-lookup"><span data-stu-id="dc299-110">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="dc299-111">Sie können den Pfad der Installationspfade für die lync Server Dateien im Dialogfeld Setup einfach auf ein neues verfügbares Laufwerk ändern.</span><span class="sxs-lookup"><span data-stu-id="dc299-111">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="dc299-112">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dc299-112">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="dc299-113">So installieren Sie den lokalen Konfigurationsspeicher</span><span class="sxs-lookup"><span data-stu-id="dc299-113">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="dc299-114">Navigieren Sie auf den Installationsmedien zu \\ Setup \\ amd64 \\Setup.exe, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc299-114">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="dc299-115">Wenn Sie zur Installation von Microsoft Visual C++ 2012 Redistributable aufgefordert werden, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="dc299-115">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="dc299-116">Klicken Sie auf der Seite **Installationsspeicherort für lync Server 2013** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc299-116">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="dc299-117">Überprüfen Sie auf der Seite **Endbenutzer-Lizenzvertrag** die Lizenzbedingungen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags**zu, und klicken Sie dann auf **OK** , um den Vorgang fortsetzen zu können.</span><span class="sxs-lookup"><span data-stu-id="dc299-117">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="dc299-118">Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="dc299-118">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="dc299-119">Klicken Sie auf der Seite **lync Server 2013** neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dc299-119">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="dc299-120">Stellen Sie auf der Seite **lokalen Konfigurationsspeicher installieren** sicher, dass die Option **direkt aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc299-120">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="dc299-121">Wenn die Installation der lokalen Serverkonfiguration abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dc299-121">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

