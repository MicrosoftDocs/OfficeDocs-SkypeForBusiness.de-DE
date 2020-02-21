---
title: Verhindern von Sitzungen für Dienste
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed0ba62a3635d58d685668adc9cf3687609e4f49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="ad6da-102">Verhindern von Sitzungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="ad6da-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad6da-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ad6da-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ad6da-104">Sie können Microsoft lync Server 2010 Systemsteuerung verwenden, um neue Sitzungen für alle lync Server 2010-Dienste zu verhindern, die auf einem bestimmten Computer auszuführen sind, oder um neue Sitzungen für einen bestimmten lync Server 2010 Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ad6da-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="ad6da-105">So verhindern Sie neue Sitzungen für alle Lync Server-Dienste auf einem Computer</span><span class="sxs-lookup"><span data-stu-id="ad6da-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="ad6da-106">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ad6da-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ad6da-107">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ad6da-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="ad6da-108">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="ad6da-109">Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="ad6da-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="ad6da-110">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-110">Click **Action**.</span></span>

6.  <span data-ttu-id="ad6da-111">Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="ad6da-112">So verhindern Sie neue Sitzungen für einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="ad6da-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="ad6da-113">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ad6da-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ad6da-114">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ad6da-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="ad6da-115">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="ad6da-116">Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="ad6da-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="ad6da-117">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="ad6da-118">Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="ad6da-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="ad6da-119">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-119">Click **Action**.</span></span>

8.  <span data-ttu-id="ad6da-120">Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="ad6da-121">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ad6da-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

