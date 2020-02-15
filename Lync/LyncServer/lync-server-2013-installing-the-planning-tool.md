---
title: 'Lync Server 2013: Installieren des Planungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792f72daac7eb1d7edb10087256bfda0912edfe9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="e5431-102">Installieren des Planungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5431-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5431-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e5431-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e5431-104">Bevor Sie mit dem Entwerfen und Planen Ihrer lync Server 2013 Infrastruktur mit dem Microsoft lync Server 2013, Planungstool beginnen, müssen Sie zuerst das Planungstool installieren.</span><span class="sxs-lookup"><span data-stu-id="e5431-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="e5431-105">Das Planungs Tool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie lync Server 2013 installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e5431-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="e5431-106">In der Readme-Datei zum Planungstool werden wichtige Informationen zum Installieren und Verwenden des Tools erläutert.</span><span class="sxs-lookup"><span data-stu-id="e5431-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="e5431-107">Einige der Informationen in der Readme-Datei werden hier aus Gründen der Übersichtlichkeit dupliziert.</span><span class="sxs-lookup"><span data-stu-id="e5431-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5431-108">Das Planungs Tool erfordert die Installation durch einen Benutzer mit Administratorrechten und-Berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5431-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="e5431-109">Die unterstützten Betriebssysteme für die Installation und den Betrieb des Planungstools sind:</span><span class="sxs-lookup"><span data-stu-id="e5431-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="e5431-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="e5431-110">Windows 8</span></span>

  - <span data-ttu-id="e5431-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e5431-111">Windows 8.1</span></span>

  - <span data-ttu-id="e5431-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e5431-112">Windows Server 2012</span></span>

  - <span data-ttu-id="e5431-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e5431-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="e5431-114">Windows 7, 32-Bit-Edition</span><span class="sxs-lookup"><span data-stu-id="e5431-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="e5431-115">Windows 7, 64-Bit-Edition mit Windows auf Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="e5431-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="e5431-116">Windows Server 2008 R2, mit wow</span><span class="sxs-lookup"><span data-stu-id="e5431-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="e5431-117">Darüber hinaus erfordert das Planungs Tool Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e5431-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="e5431-118">Nachdem die Voraussetzungen für die Vorinstallation erfüllt sind, können Sie das Planungs Tool installieren.</span><span class="sxs-lookup"><span data-stu-id="e5431-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="e5431-119">So installieren Sie das Planungs Tool</span><span class="sxs-lookup"><span data-stu-id="e5431-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="e5431-120">Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.</span><span class="sxs-lookup"><span data-stu-id="e5431-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="e5431-121">Suchen Sie im Windows-Explorer oder in einem Befehlsfenster nach dem Verzeichnis, in das Sie die Installationsdateien für das Planungs Tool heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="e5431-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="e5431-122">Suchen Sie nach der LyncPlanningTool. msi.</span><span class="sxs-lookup"><span data-stu-id="e5431-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="e5431-123">Doppelklicken Sie in Windows-Explorer auf die Datei.</span><span class="sxs-lookup"><span data-stu-id="e5431-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="e5431-124">Geben Sie im Befehlsfenster den Namen der Datei ein, und drücken Sie dann die **EINGABETASTE** , um die Datei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e5431-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="e5431-125">Klicken Sie auf der Willkommensseite des Setup-Assistenten für das **Microsoft lync Server 2013 des Planungstools**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5431-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="e5431-126">Lesen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags** zu, wenn Sie die Nutzungsbedingungen des Lizenzvertrags akzeptieren möchten, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5431-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="e5431-127">Wählen Sie aus, wo die Planungs Tool Dateien installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e5431-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="e5431-128">Der Standardspeicherort ist C:\\Programmdateien (x86)\\Microsoft lync Server 2013\\Planungs Tool.</span><span class="sxs-lookup"><span data-stu-id="e5431-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="e5431-129">Wenn Sie den Installationsspeicherort ändern möchten, klicken Sie auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="e5431-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="e5431-130">Klicken Sie unter **Zielordner ändern**auf Durchsuchen oder geben Sie den Speicherort zum Installieren der Dateien ein, klicken Sie auf **OK**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5431-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="e5431-131">Das Installationsprogramm ist nun für die Installation des Planungstools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5431-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="e5431-132">Klicken Sie auf **Installieren** , um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="e5431-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="e5431-133">Die Installation wird gestartet, und der Fortschritt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5431-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="e5431-134">Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e5431-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="e5431-135">Das Planungs Tool ist einsatzfähig.</span><span class="sxs-lookup"><span data-stu-id="e5431-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5431-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5431-136">See Also</span></span>


[<span data-ttu-id="e5431-137">Installieren von optionaler Software in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5431-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

