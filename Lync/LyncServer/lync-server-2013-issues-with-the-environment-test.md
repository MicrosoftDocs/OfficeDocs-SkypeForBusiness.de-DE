---
title: 'Lync Server 2013: Probleme mit dem Umgebungs Test'
description: 'Lync Server 2013: Probleme mit dem Umgebungs Test.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551d7e914480e178e0558c1d17eefcf060c0688e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574971"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="8d716-103">Probleme mit dem Umgebungs Test in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d716-103">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d716-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8d716-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8d716-105">Best Practices Analyzer bietet Ihnen die Möglichkeit, zu überprüfen, ob Ihre lync Server 2013 Umgebung eine unterstützte Konfiguration ist.</span><span class="sxs-lookup"><span data-stu-id="8d716-105">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="8d716-106">Im Rahmen der Active Directory-Domänendienste Überprüfung führt Best Practices Analyzer folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8d716-106">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="8d716-107">Überprüft die Active Directory-Domänendienste Gesamtstruktur und Schemavorbereitung.</span><span class="sxs-lookup"><span data-stu-id="8d716-107">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="8d716-108">Gibt die Anzahl der Active Directory-Domänendienste Websites und Domänen in der Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8d716-108">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="8d716-109">Überprüft die Gesamtstruktur-und Domänenebenen.</span><span class="sxs-lookup"><span data-stu-id="8d716-109">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="8d716-110">Überprüft die Version des Domänencontrollers.</span><span class="sxs-lookup"><span data-stu-id="8d716-110">Checks the domain controller version.</span></span>

  - <span data-ttu-id="8d716-111">Gibt den Domänen-, Konfigurations-und Schemanamenskontext an.</span><span class="sxs-lookup"><span data-stu-id="8d716-111">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="8d716-112">Gibt die Anzahl der aktivierten Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="8d716-112">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="8d716-113">Überprüft, wo die globalen Active Directory-Domänendienste Einstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8d716-113">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="8d716-114">Überprüft, ob die Dienstverbindungspunkte (SKP) für lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d716-114">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="8d716-115">Gibt die Datenbankversion an.</span><span class="sxs-lookup"><span data-stu-id="8d716-115">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="8d716-116">Beheben von Problemen mit der Umgebung</span><span class="sxs-lookup"><span data-stu-id="8d716-116">Resolving Issues with the Environment</span></span>

<span data-ttu-id="8d716-117">Wenn der Umgebungs Test Probleme mit Ihrer Umgebung festgestellt hat, werden diese Probleme möglicherweise durch Probleme mit Ihrer Active Directory Konfiguration oder durch die auf bestimmten Servern ausgeführten Softwareebenen verursacht.</span><span class="sxs-lookup"><span data-stu-id="8d716-117">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="8d716-118">Wenn Best Practices Analyzer beispielsweise Domänencontroller in Ihrer Umgebung identifiziert, auf denen Windows Server 2000 ausgeführt wird, wird eine Warnung ausgegeben, und Sie müssen diese Domänencontroller auf eine unterstützte Version von Windows Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8d716-118">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

