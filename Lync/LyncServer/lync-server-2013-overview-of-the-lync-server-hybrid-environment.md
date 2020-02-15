---
title: 'Lync Server 2013: Übersicht über die lync Server-Hybridumgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32132faee3b52140d20a7f01e6a0bad0e88c620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="d8a63-102">Übersicht über die lync Server 2013 Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="d8a63-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8a63-103">_**Letztes Änderungsstand des Themas:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="d8a63-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="d8a63-104">Lync Server 2013 Hybridumgebung bezieht sich auf eine Bereitstellung, in der einige Benutzer mit der lokalen lync Server 2013 und anderen Benutzern in lync online verwaltet werden, aber Benutzer dieselbe Domäne wie user@contoso.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8a63-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="d8a63-105">Informationen zu diesem Leitfaden</span><span class="sxs-lookup"><span data-stu-id="d8a63-105">About this Guide</span></span>

<span data-ttu-id="d8a63-106">In diesem Leitfaden werden die Aufgaben beschrieben, die erforderlich sind, um die lync Server 2013 Umgebung für die Interoperabilität mit lync online zu konfigurieren und dann Benutzer aus Ihrer lokalen Bereitstellung zur Verwendung von lync online zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="d8a63-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="d8a63-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d8a63-107">Prerequisites</span></span>

<span data-ttu-id="d8a63-108">Sie müssen die folgenden Anwendungen und Dienstprogramme installiert haben, um die Aufgaben zum Konfigurieren einer Bereitstellung für Hybrid auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8a63-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="d8a63-109">Die Installationsprogramme für diese Dateien sind auf den für Ihre Bereitstellung bereitgestellten Installationsmedien sowie auf den in der folgenden Liste aufgeführten Links enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8a63-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="d8a63-110">Active Directory-Verbunddienste (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="d8a63-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="d8a63-111">Microsoft-Verzeichnis Synchronisierungs Tool 9,1</span><span class="sxs-lookup"><span data-stu-id="d8a63-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="d8a63-112">Installieren von Windows PowerShell für einmaliges Anmelden mit AD FS</span><span class="sxs-lookup"><span data-stu-id="d8a63-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="d8a63-113">Der Microsoft Online Services-Anmelde Assistent (msoidcli-7.0. msi) ist in der Desktop Einrichtung für Office 365 enthalten, die von der Seite mit den Downloads abgerufen werden kann, die über das Office 365-Verwaltungsportal verlinkt ist.</span><span class="sxs-lookup"><span data-stu-id="d8a63-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="d8a63-114">Administrator Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="d8a63-114">Administrator Credentials</span></span>

<span data-ttu-id="d8a63-115">Wenn Sie aufgefordert werden, Ihre Administratoranmeldeinformationen anzugeben, verwenden Sie den Benutzernamen und das Kennwort für das Administratorkonto für den Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="d8a63-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="d8a63-116">Diese Anmeldeinformationen werden auch beim Konfigurieren von Active Directory-Verbunddienste (AD FS) 2.0, Verzeichnissynchronisierung, einmaliges Anmelden, Verbund und Verschieben von Benutzern zu lync Online verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8a63-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="d8a63-117">Herstellen einer Verbindung mit lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8a63-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="d8a63-118">Administratoren haben jetzt die Möglichkeit, lync Online und deren lync Online Benutzerkonten mit Windows PowerShell zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d8a63-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="d8a63-119">Hierzu müssen Sie zuerst das lync Online-Connector-Modul aus dem Microsoft Download Center herunterladen und installieren (http://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="d8a63-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="d8a63-120">Weitere Informationen zum herunterladen, installieren und Verwenden des lync Online-Connector-Moduls sowie ausführliche Informationen zur Verwendung von Windows PowerShell zum Verwalten von lync Online finden Sie unter [using Windows PowerShell to manage lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8a63-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

