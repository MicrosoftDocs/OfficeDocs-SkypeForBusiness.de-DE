---
title: 'Lync Server 2013: Bereitstellen von lync-Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af989286dad9c0c8bba38f61b17b606e758dcd15
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="4e379-102">Bereitstellen von lync-Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e379-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4e379-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4e379-104">In lync 2013 wird ein anderer Ansatz für die Clientbereitstellung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4e379-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="4e379-105">Bei einer Abweichung aus früheren Versionen verfügt lync 2013 nicht mehr über ein eigenes Installationsprogramm.</span><span class="sxs-lookup"><span data-stu-id="4e379-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="4e379-106">Stattdessen ist lync im Office 2013-Setupprogramm enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e379-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="4e379-107">Um lync 2013 für Ihre Benutzer bereitzustellen, können Sie Office 2013 Installationsmethoden und Anpassungstools verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e379-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="4e379-108">**Office 2013 Windows Installer** ist ein Windows Installer-basiertes Installationspaket, das aus mehreren MSI-Dateien besteht.</span><span class="sxs-lookup"><span data-stu-id="4e379-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="4e379-109">Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert.</span><span class="sxs-lookup"><span data-stu-id="4e379-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="4e379-110">Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="4e379-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="4e379-111">In den Themen in diesem Abschnitt wird beschrieben, wie Sie die Office 2013 Windows Installer verwenden und anpassen, um lync 2013 bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4e379-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="4e379-112">**Office 2013 Klick-und-Los** ist ein Installationsprogramm, das Office-Setupdateien aus dem Microsoft 365 Admin Center an den Benutzer streamt.</span><span class="sxs-lookup"><span data-stu-id="4e379-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft 365 admin center.</span></span> <span data-ttu-id="4e379-113">Administratoren können die Installation mithilfe des Office-Bereitstellungstools für Klick-und-Los anpassen.</span><span class="sxs-lookup"><span data-stu-id="4e379-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="4e379-114">Da Office 2013 Klick-und-Los in erster Linie in der Microsoft 365-Umgebung verwendet wird, wird diese Installationsmethode in diesem Abschnitt nicht ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e379-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="4e379-115">Ausführliche Informationen zur Verwendung und Anpassung der Klick-und-Los-Installation finden Sie in der Dokumentation zum Office 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="4e379-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="4e379-116">Administratoren können auch die Office 2013 Klick-und-Los-Programm-und sprach Quelldateien an einen lokalen Speicherort herunterladen, was nützlich ist, wenn Sie die Netzwerkanforderungen minimieren oder verhindern möchten, dass Benutzer Software aus dem Internet installieren, da die Sicherheitsanforderungen für Unternehmen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="4e379-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="4e379-117">Die Themen in diesem Abschnitt konzentrieren sich auf die Bereitstellung von Clients mithilfe des Office 2013 MSI-basierten Installationsprogramms.</span><span class="sxs-lookup"><span data-stu-id="4e379-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="4e379-118">Ihr primärer Verweis sollte die Office 2013 Resource Kit-Dokumentation sein, in der ausführlich erläutert wird, wie Sie Ihre Infrastruktur vorbereiten, Setup anpassen und Office 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e379-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="4e379-119">Sie sollten jedoch die Office-Dokumentation in Verbindung mit Themen in diesem Abschnitt verwenden, die auf Bereitstellungsüberlegungen hinweisen, die spezifisch für lync 2013 sind.</span><span class="sxs-lookup"><span data-stu-id="4e379-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="4e379-120">Das Online Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung im Outlook-Client für Messaging und Zusammenarbeit unterstützt, wird automatisch mit lync 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="4e379-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="4e379-121">Mit dem Setupprogramm für Office 2013 werden frühere Versionen von lync oder Office Communicator nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="4e379-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="4e379-122">Der lync 2013 Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert.</span><span class="sxs-lookup"><span data-stu-id="4e379-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e379-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4e379-123">In This Section</span></span>

  - [<span data-ttu-id="4e379-124">Anpassen der Clientinstallation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="4e379-125">Anpassen von lync-Verhalten und der Benutzeroberfläche in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="4e379-126">Anpassen des Online Besprechungs-Add-Ins in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="4e379-127">Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="4e379-128">Konfigurieren unterstützter Clientversionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="4e379-129">Konfigurieren des Datenschutzmodus für erweiterte Anwesenheitsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e379-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

