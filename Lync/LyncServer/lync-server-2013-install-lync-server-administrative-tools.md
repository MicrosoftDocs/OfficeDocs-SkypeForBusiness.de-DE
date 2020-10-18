---
title: 'Lync Server 2013: Installieren von lync Server Verwaltungstools'
description: 'Lync Server 2013: Installieren von lync Server Verwaltungstools.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1ad96299197c3339d06c4f094784edc632e6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574171"
---
# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="bcffb-103">Installieren von lync Server 2013 Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="bcffb-103">Install Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcffb-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bcffb-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bcffb-105">In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie für die Bereitstellung und Verwaltung von lync Server 2013 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="bcffb-105">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="bcffb-106">Die Verwaltungstools werden auf jedem Server mit lync Server 2013 standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="bcffb-106">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="bcffb-107">Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren.</span><span class="sxs-lookup"><span data-stu-id="bcffb-107">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="bcffb-108">Es wird dringend empfohlen, dass Sie die Verwaltungstools auf einem Computer installieren, der sich in der gleichen Domäne oder Gesamtstruktur wie die lync Server 2013 Bereitstellung befindet, die Sie erstellen, da Sie dadurch sicherstellen, dass Active Directory-Domänendienste Vorbereitungsschritte bereits abgeschlossen sind, sodass Sie später die Verwaltungstools auf diesem Computer zum Veröffentlichen Ihrer Topologie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bcffb-108">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="bcffb-109">Stellen Sie sicher, dass Sie die Anforderungen an Infrastruktur, Betriebssystem, Software und Administratorrechte überprüfen, bevor Sie die lync Server 2013 Verwaltungstools installieren oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcffb-109">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="bcffb-110">Ausführliche Informationen zu den Infrastrukturanforderungen finden Sie unter [Administrative Tools Infrastructure Requirements in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcffb-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="bcffb-111">Ausführliche Informationen zu den Betriebssystem-und Softwareanforderungen für die Installation der lync Server 2013 Verwaltungstools finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)sowie [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcffb-111">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="bcffb-112">Ausführliche Informationen zu den Benutzerrechten und-Berechtigungen, die für die Installation und Verwendung der Tools erforderlich sind, finden Sie unter [Administrator Rechte und-Berechtigungen, die für die Einrichtung und Verwaltung von lync Server 2013 erforderlich](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)sind.</span><span class="sxs-lookup"><span data-stu-id="bcffb-112">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bcffb-113">Wenn die Internetinformationsdienste (IIS) und alle Webdienste in Ihrer Organisation auf einem anderen Laufwerk als auf dem Systemlaufwerk platziert werden müssen, können Sie das Installationsverzeichnis für die Lync Server-Dateien im Setupdialogfeld ändern.</span><span class="sxs-lookup"><span data-stu-id="bcffb-113">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="bcffb-114">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bcffb-114">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="bcffb-115">So installieren Sie die lync Server 2013 Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="bcffb-115">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="bcffb-p104">Melden Sie sich mindestens als lokaler Administrator auf dem Computer an, auf dem der fea-cs-topo-tool und die Verwaltungstools installiert werden sollen. Wenn Sie als Standardbenutzer bei einem Windows Vista- oder Windows 7-Betriebssystem angemeldet sind und die Benutzerkontensteuerung aktiviert ist, werden Sie zur Eingabe von Name und Kennwort für den lokalen Administrator oder für ein gleichwertiges Domänenbenutzerkonto aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bcffb-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="bcffb-118">Suchen Sie das Installationsmedium auf Ihrem Computer, und doppelklicken Sie dann auf \\ Setup \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="bcffb-118">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="bcffb-119">Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ 2008 Distributable aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="bcffb-119">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="bcffb-120">Klicken Sie auf der Seite **Installationsspeicherort für Microsoft lync Server 2013** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcffb-120">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="bcffb-121">Ändern Sie diesen Pfad in einen anderen Speicherort oder ein anderes Laufwerk, wenn Sie die Dateien an einem anderen Speicherort installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="bcffb-121">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bcffb-122">Wenn in Ihrer Organisation Internet Information Services (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk gefunden werden müssen, können Sie den Pfad für den Installationspfad für die lync Server 2013 Dateien im Dialogfeld Setup ändern.</span><span class="sxs-lookup"><span data-stu-id="bcffb-122">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="bcffb-123">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bcffb-123">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="bcffb-p107">Lesen Sie die Lizenzbedingungen auf der Seite **Endbenutzer-Lizenzvertrag**, klicken Sie auf **Ich stimme zu** und anschließend auf **OK**. Dieser Schritt ist erforderlich, um fortfahren zu können.</span><span class="sxs-lookup"><span data-stu-id="bcffb-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="bcffb-126">Klicken Sie auf der Seite **Microsoft lync Server 2013-Bereitstellungs-Assistenten** auf **Administrator Tools installieren**.</span><span class="sxs-lookup"><span data-stu-id="bcffb-126">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="bcffb-127">Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="bcffb-127">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bcffb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcffb-128">See Also</span></span>


[<span data-ttu-id="bcffb-129">Öffnen lync Server 2013 Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="bcffb-129">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="bcffb-130">Lync Server 2013 Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="bcffb-130">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

