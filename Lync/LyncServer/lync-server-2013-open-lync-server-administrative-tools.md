---
title: 'Lync Server 2013: Öffnen der lync Server-Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="199d7-102">Öffnen der lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="199d7-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="199d7-103">_**Letztes Änderungsdatum des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="199d7-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="199d7-104">Sie können die in diesem Thema beschriebenen Verfahren verwenden, um administrative Tools zum Bereitstellen, konfigurieren oder behandeln von Problemen mit der lync Server 2013-Topologie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="199d7-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="199d7-105">Bereitstellungs-Assistent</span><span class="sxs-lookup"><span data-stu-id="199d7-105">Deployment Wizard</span></span>

  - <span data-ttu-id="199d7-106">Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="199d7-106">Topology Builder</span></span>

  - <span data-ttu-id="199d7-107">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="199d7-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="199d7-108">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="199d7-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="199d7-109">Bereitstellungs-Assistent</span><span class="sxs-lookup"><span data-stu-id="199d7-109">Deployment Wizard</span></span>

<span data-ttu-id="199d7-110">Gehen Sie wie folgt vor, um den Bereitstellungs-Assistenten lokal zu starten, um lync Server 2013-Komponentendateien hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="199d7-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="199d7-111">So starten Sie den lync Server 2013-Bereitstellungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="199d7-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="199d7-112">Melden Sie sich bei dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.</span><span class="sxs-lookup"><span data-stu-id="199d7-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="199d7-113">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Bereitstellungs-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="199d7-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="199d7-114">Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="199d7-114">Topology Builder</span></span>

<span data-ttu-id="199d7-115">Gehen Sie wie folgt vor, um den Topologie-Generator zu öffnen, um die Server zu definieren, die in ihrer lync Server 2013-Topologie bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="199d7-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="199d7-116">So öffnen Sie den lync Server 2013-Topologie-Generator zum Entwerfen der Topologie</span><span class="sxs-lookup"><span data-stu-id="199d7-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="199d7-117">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="199d7-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="199d7-118">Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Lesen, veröffentlichen oder Aktivieren einer Topologie, die für die Installation von lync Server 2013 auf einem Server erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe der Domänenadministratoren und der RTCUniv ist. ersalServerAdmins-Gruppe, die über Vollzugriffsberechtigungen (also lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den Archivierungsdatei Speicher verwenden werden, damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control List) konfigurieren kann. oder ein Konto mit entsprechenden Benutzerrechten.</span><span class="sxs-lookup"><span data-stu-id="199d7-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="199d7-119">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="199d7-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="199d7-120">Systemsteuerung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="199d7-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="199d7-121">Führen Sie eines der folgenden Verfahren aus, um die lync Server 2013-Systemsteuerung zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="199d7-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="199d7-122">Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in der lync Server 2013-Systemsteuerung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="199d7-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="199d7-123">Sie können andere Rollen verwenden, um sich bei der lync Server 2013-Systemsteuerung anzumelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="199d7-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="199d7-124">So können Sie beispielsweise CSArchivingAdministrator verwenden, um die Archivierung in der lync Server 2013-Systemsteuerung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="199d7-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="199d7-125">Details zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="199d7-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="199d7-126">Details zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation der Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="199d7-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="199d7-127">So öffnen Sie die lync Server 2013-Systemsteuerung von einem beliebigen Computer in der Firewall Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="199d7-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="199d7-128">Melden Sie sich bei einem Benutzerkonto, das der Rolle CsAdministrator oder einer anderen Rolle zugewiesen ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei einem beliebigen Computer in ihrer internen Bereitstellung mit einer Mindestauflösung von 1024 x 768 an.</span><span class="sxs-lookup"><span data-stu-id="199d7-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="199d7-129">Wenn Sie eine einfache URL (Uniform Resource Locator) für die Verwaltung konfiguriert haben, können Sie von einem Internet Browser, der auf einem beliebigen Computer in der Firewall Ihrer Organisation ausgeführt wird, auf die lync Server 2013-Systemsteuerung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="199d7-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="199d7-130">Details zum Konfigurieren der einfachen URL für die Verwaltung finden Sie unter <A href="lync-server-2013-planning-for-simple-urls.md">Planen einfacher URLs in lync Server 2013</A> in der Planungsdokumentation und <A href="lync-server-2013-edit-or-configure-simple-urls.md">Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="199d7-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="199d7-131">Öffnen Sie ein Browserfenster, und geben Sie dann die für Ihre Organisation konfigurierte Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="199d7-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="199d7-132">So öffnen Sie die lync Server 2013-Systemsteuerung auf einem Computer mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="199d7-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="199d7-133">Melden Sie sich bei einem Benutzerkonto, das Mitglied der Rolle CsAdministrator oder einer anderen Rolle ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, an einem Computer an, auf dem Sie lync Server 2013 installiert haben, oder zumindest die lync Server 2013-Verwaltung. Ive-Tools.</span><span class="sxs-lookup"><span data-stu-id="199d7-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="199d7-134">Zum Konfigurieren der Einstellungen muss der Computer mindestens eine Bildschirmauflösung von 1024 x 768 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="199d7-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="199d7-135">Starten Sie die lync Server 2013-Systemsteuerung: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, zeigen Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server 2013-System**Steuerung.</span><span class="sxs-lookup"><span data-stu-id="199d7-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="199d7-136">Verwaltungsshell für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="199d7-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="199d7-137">Gehen Sie wie folgt vor, um die lync Server 2013-Verwaltungsshell zum Verwalten von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung über die Befehlszeile zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="199d7-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="199d7-138">Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in der lync Server 2013-Verwaltungsshell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="199d7-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="199d7-139">Sie können sich mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="199d7-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="199d7-140">So können Sie beispielsweise CSArchivingAdministrator verwenden, um Cmdlets für die Archivierungsverwaltung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="199d7-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="199d7-141">Details zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="199d7-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="199d7-142">Details zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="199d7-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="199d7-143">Sie können bestimmte Cmdlets auch ausführen, indem Sie je nach Cmdlet ein Benutzerkonto in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins verwenden.</span><span class="sxs-lookup"><span data-stu-id="199d7-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="199d7-144">So öffnen Sie die lync Server 2013-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="199d7-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="199d7-145">Wenn Sie ein Windows PowerShell-Fenster anstelle der lync Server 2013-Verwaltungsshell öffnen, können die lync Server 2013-Cmdlets standardmäßig nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="199d7-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="199d7-146">Wenn Sie die lync Server 2013-Cmdlets in Windows PowerShell ausführen möchten, geben Sie Folgendes an der Windows PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="199d7-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="199d7-147">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="199d7-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="199d7-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="199d7-148">See Also</span></span>


[<span data-ttu-id="199d7-149">Installieren von Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="199d7-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="199d7-150">Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="199d7-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

