---
title: 'Lync Server 2013: Windows PowerShell-und lync Server-Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24a94bf74b2ecf911179d64691e95153acceeeb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="abc00-102">Windows PowerShell-und lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="abc00-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abc00-103">_**Letztes Änderungsstand des Themas:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="abc00-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="abc00-104">In Microsoft lync Server 2013 werden Verwaltungstools mithilfe von Windows PowerShell implementiert.</span><span class="sxs-lookup"><span data-stu-id="abc00-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="abc00-105">Windows PowerShell bietet eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="abc00-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="abc00-106">Lync Server 2013 Tools, die mit Windows PowerShell implementiert werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="abc00-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="abc00-107">**Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="abc00-107">**Topology Builder**.</span></span> <span data-ttu-id="abc00-108">Mithilfe des Topologie-Generators können Sie die geplante Topologie erstellen, anpassen und veröffentlichen und Ihre Topologie überprüfen, bevor Sie mit der Server Installation beginnen.</span><span class="sxs-lookup"><span data-stu-id="abc00-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="abc00-109">Wenn Sie lync Server 2013 auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server wie in der Topologie weitergeleitet bereit.</span><span class="sxs-lookup"><span data-stu-id="abc00-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="abc00-110">Nach dem Setup werden Konfigurationsinformationen automatisch auf alle Server repliziert.</span><span class="sxs-lookup"><span data-stu-id="abc00-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="abc00-111">Komponenten können nur mithilfe des Topologie-Generators zur Bereitstellung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="abc00-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="abc00-112">**Lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="abc00-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="abc00-113">Sie können lync Server-Verwaltungsshell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="abc00-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="abc00-114">**Lync Server-Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="abc00-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="abc00-115">Sie können die Benutzeroberfläche der Microsoft lync Server 2013 Systemsteuerung verwenden, um die am häufigsten verwendeten Aufgaben in Ihrer Bereitstellung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="abc00-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="abc00-116">In diesen Tools werden Windows PowerShell-Cmdlets für die Verwaltung einer Bereitstellung verwendet, darunter fast 550 produktspezifische Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="abc00-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="abc00-117">Die in lync Server 2013 enthaltenen Sicherheits-Cmdlets dienen in erster Linie zum Verwalten der Authentifizierung sowie von Benutzerrechten und-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="abc00-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="abc00-118">Zum Verwalten der Authentifizierung stehen zahlreiche Cmdlets zur Verfügung, darunter Cmdlets für die Authentifizierung unter Verwendung von Zertifikaten oder einer persönlichen Identifikationsnummer (PIN).</span><span class="sxs-lookup"><span data-stu-id="abc00-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="abc00-119">Darüber hinaus können Sie mit einer Reihe von Cmdlets die neue Funktion für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwenden, um die administrative Steuerung von lync Server 2013 zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="abc00-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="abc00-120">Ausführliche Informationen zu den lync Server-Cmdlets finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="abc00-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="abc00-121">Die skriptbezogenen Sicherheitsfeatures für Windows PowerShell wurden speziell entwickelt, um einige der mit Skripts zusammenhängenden Sicherheitsprobleme in älteren Technologien zu vermeiden, z, B. in Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="abc00-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="abc00-122">Die Windows PowerShell-Sicherheitsfeatures sollen Ihnen helfen, eine Umgebung aufzubauen, in der es den Benutzern nicht möglich ist, auf einfache Weise oder unwissentlich Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="abc00-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="abc00-123">Standardmäßig sind Windows PowerShell-Sicherheitsfeatures aktiviert.</span><span class="sxs-lookup"><span data-stu-id="abc00-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="abc00-124">Sie können den Status dieser Features ändern, um Ihren Anforderungen in Bezug auf Skripts und Ihren individuellen Sicherheitszielen Rechnung zu tragen.</span><span class="sxs-lookup"><span data-stu-id="abc00-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="abc00-125">Das bedeutet nicht, dass Windows PowerShell den Benutzern die Ausführung von Skripts unmöglich macht.</span><span class="sxs-lookup"><span data-stu-id="abc00-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="abc00-126">Vielmehr erschwert sie es den Benutzern, Skripts auszuführen, ohne dass Sie sich dessen bewusst sind.</span><span class="sxs-lookup"><span data-stu-id="abc00-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="abc00-127">Ausführliche Informationen finden Sie unter Windows PowerShell Script Security [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145)in.</span><span class="sxs-lookup"><span data-stu-id="abc00-127">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

