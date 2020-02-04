---
title: 'Lync Server 2013: Konfigurieren der Standortdatenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="2aa7e-102">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aa7e-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aa7e-103">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2aa7e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2aa7e-104">Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="2aa7e-105">Wenn Sie eine Standortdatenbank nicht konfigurieren und der Standort, der in der Standortrichtlinie **erforderlich** ist, auf **Ja** oder **Disclaimer**eingestellt ist, wird der Benutzer aufgefordert, einen Standort manuell einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="2aa7e-106">Um die Standortdatenbank zu konfigurieren, führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2aa7e-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="2aa7e-107">Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="2aa7e-108">Wenn Sie ein Elin-Gateway (Notfall Standort-Identifikationsnummer) verwenden, müssen Sie Elin in das \<Feld\> "CompanyName" einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="2aa7e-109">Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="2aa7e-110">Veröffentlichen Sie die aktualisierte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2aa7e-111">Alternativ können Sie eine sekundäre Standort Quelldatenbank definieren, die für die Position der Standortdatenbank verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="2aa7e-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2aa7e-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2aa7e-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2aa7e-113">In This Section</span></span>

  - [<span data-ttu-id="2aa7e-114">Auffüllen der Standortdatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aa7e-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="2aa7e-115">Überprüfen von Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aa7e-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="2aa7e-116">Veröffentlichen der Standortdatenbank aus lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aa7e-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

