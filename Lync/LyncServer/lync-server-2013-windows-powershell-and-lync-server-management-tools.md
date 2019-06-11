---
title: 'Lync Server 2013: Windows PowerShell und Lync Server-Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="315c3-102">Windows PowerShell und Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="315c3-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="315c3-103">_**Letztes Änderungsdatum des Themas:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="315c3-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="315c3-104">In Microsoft lync Server 2013 werden Verwaltungstools mithilfe von Windows PowerShell implementiert.</span><span class="sxs-lookup"><span data-stu-id="315c3-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="315c3-105">Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="315c3-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="315c3-106">Zu den lync Server 2013-Tools, die mit Windows PowerShell implementiert werden, gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="315c3-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="315c3-107">**Topologie-Generator**</span><span class="sxs-lookup"><span data-stu-id="315c3-107">**Topology Builder**.</span></span> <span data-ttu-id="315c3-108">Sie verwenden den Topologie-Generator zum Erstellen, anpassen und Veröffentlichen Ihrer geplanten Topologie, und Sie überprüft Ihre Topologie, bevor Sie mit Server Installationen beginnen.</span><span class="sxs-lookup"><span data-stu-id="315c3-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="315c3-109">Wenn Sie lync Server 2013 auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server gemäß den Anweisungen in der Topologie bereit.</span><span class="sxs-lookup"><span data-stu-id="315c3-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="315c3-110">After setup, configuration information is automatically replicated to all servers.</span><span class="sxs-lookup"><span data-stu-id="315c3-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="315c3-111">Components can be added to your deployment only by using Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="315c3-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="315c3-112">**Lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="315c3-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="315c3-113">Sie können die lync Server-Verwaltungsshell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="315c3-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="315c3-114">**Lync Server-System**Steuerung.</span><span class="sxs-lookup"><span data-stu-id="315c3-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="315c3-115">Sie können die Benutzeroberfläche der Microsoft lync Server 2013-Systemsteuerung verwenden, um die am häufigsten ausgeführten Aufgaben in Ihrer Bereitstellung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="315c3-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="315c3-116">Diese Tools verwenden Windows PowerShell-Cmdlets für die Verwaltung Ihrer Bereitstellung, einschließlich in der Nähe von 550-produktspezifischen Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="315c3-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="315c3-117">Die in lync Server 2013 enthaltenen Sicherheits-Cmdlets werden in erster Linie zum Verwalten der Authentifizierung und von Benutzerrechten und-Berechtigungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="315c3-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="315c3-118">Zum Verwalten der Authentifizierung stehen vielfältige Cmdlets zur Verfügung, darunter Cmdlets für die Zertifikat- und PIN-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="315c3-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="315c3-119">Darüber hinaus können Sie mithilfe einer Reihe von Cmdlets das neue Feature für die rollenbasierte Zugriffssteuerung verwenden, um die administrative Steuerung von lync Server 2013 zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="315c3-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="315c3-120">Details zu den lync Server-Cmdlets finden Sie unter [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="315c3-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="315c3-121">Die Skript Sicherheitsfeatures für Windows PowerShell wurden speziell entwickelt, um zu verhindern, dass einige der Skript bezogenen Sicherheitsprobleme älterer Technologien, einschließlich Microsoft Visual Basic Scripting Edition (VBScript), unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="315c3-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="315c3-122">Die Windows PowerShell-Sicherheitsfeatures sollen eine Umgebung erstellen, in der Benutzer keine einfachen oder unwissentlichen Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="315c3-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="315c3-123">Standardmäßig sind die Windows PowerShell-Sicherheitsfeatures aktiviert.</span><span class="sxs-lookup"><span data-stu-id="315c3-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="315c3-124">Sie können den Zustand dieser Features ändern, damit Sie Ihren Skriptanforderungen und einer Reihe von Sicherheitszielen gerecht werden.</span><span class="sxs-lookup"><span data-stu-id="315c3-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="315c3-125">Dies soll nicht heißen, dass die Shell es Benutzern unmöglich macht, Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="315c3-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="315c3-126">Stattdessen erschwert die Shell standardmäßig, dass Benutzer Skripts ausführen können, ohne dass dies zu erkennen ist.</span><span class="sxs-lookup"><span data-stu-id="315c3-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="315c3-127">Ausführliche Informationen finden Sie unter Windows PowerShell-Skript [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)Sicherheit unter.</span><span class="sxs-lookup"><span data-stu-id="315c3-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

