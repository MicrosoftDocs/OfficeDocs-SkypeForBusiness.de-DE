---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="6e85c-102">Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e85c-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e85c-103">_**Letztes Änderungsdatum des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="6e85c-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="6e85c-104">Bei der effektiven Planung für die Integration von lync Server 2013 in gehostete Exchange Unified Messaging (um) müssen Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="6e85c-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="6e85c-105">Voraussetzungen für die Integration von lync Server 2013 in Hosted Exchange um</span><span class="sxs-lookup"><span data-stu-id="6e85c-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="6e85c-106">Erforderliche Schritte während des Integrationsprozesses</span><span class="sxs-lookup"><span data-stu-id="6e85c-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="6e85c-107">Voraussetzungen für die Bereitstellung für die Integration in Hosted Exchange um</span><span class="sxs-lookup"><span data-stu-id="6e85c-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="6e85c-108">Bevor Sie mit dem Integrationsprozess beginnen können, müssen Sie bereits lync Server 2013 (mindestens einen Front-End-Pool oder einen Standard Edition-Server), einen Edgeserver und lync 2013-oder lync 2010-Clients bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6e85c-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="6e85c-109">Integrationsprozess</span><span class="sxs-lookup"><span data-stu-id="6e85c-109">Integration Process</span></span>

<span data-ttu-id="6e85c-110">Die folgende Tabelle enthält eine Übersicht über den gehosteten Exchange um-Integrationsprozess.</span><span class="sxs-lookup"><span data-stu-id="6e85c-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="6e85c-111">Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [Bereitstellen von lync Server 2013-Benutzern für Voicemail](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in der Bereitstellungsdokumentation für gehostete Exchange um.</span><span class="sxs-lookup"><span data-stu-id="6e85c-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e85c-112">Phase</span><span class="sxs-lookup"><span data-stu-id="6e85c-112">Phase</span></span></th>
<th><span data-ttu-id="6e85c-113">Schritte</span><span class="sxs-lookup"><span data-stu-id="6e85c-113">Steps</span></span></th>
<th><span data-ttu-id="6e85c-114">Rechte und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6e85c-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="6e85c-115">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6e85c-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e85c-116">Konfigurieren Sie den Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6e85c-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6e85c-117">Konfigurieren Sie den Edgeserver für einen Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="6e85c-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="6e85c-118">Manuelles Replizieren von Daten auf den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6e85c-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="6e85c-119">Konfigurieren Sie den Hostinganbieter auf dem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6e85c-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6e85c-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6e85c-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6e85c-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Konfigurieren des Edgeservers für die Integration in gehostete Exchange UM-Dienste</a></span><span class="sxs-lookup"><span data-stu-id="6e85c-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e85c-122">Konfigurieren der Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="6e85c-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6e85c-123">Ändern Sie entweder die Global Hosted Voicemail-Richtlinie, oder erstellen Sie eine neue gehostete Voicemail-Richtlinie mit Website-oder pro-Benutzer-Bereich.</span><span class="sxs-lookup"><span data-stu-id="6e85c-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="6e85c-124">Weisen Sie für Richtlinien mit benutzerspezifischem Bereich die Richtlinie Benutzern oder Gruppen zu.</span><span class="sxs-lookup"><span data-stu-id="6e85c-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6e85c-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6e85c-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6e85c-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6e85c-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e85c-127">Aktivieren von Benutzern für gehostete Voicemails</span><span class="sxs-lookup"><span data-stu-id="6e85c-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6e85c-128">Konfigurieren Sie Benutzerkonten für Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="6e85c-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6e85c-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="6e85c-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="6e85c-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Aktivieren von Benutzern für gehostete Voicemail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6e85c-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e85c-131">Konfigurieren von gehosteten Kontaktobjekten</span><span class="sxs-lookup"><span data-stu-id="6e85c-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6e85c-132">Erstellen Sie Kontaktobjekte für die automatische Telefonzentrale für gehostete Exchange um.</span><span class="sxs-lookup"><span data-stu-id="6e85c-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="6e85c-133">Erstellen von Kontaktobjekten für den Abonnenten Zugriff für gehostete Exchange um.</span><span class="sxs-lookup"><span data-stu-id="6e85c-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6e85c-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="6e85c-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6e85c-135">Zum Erstellen, ändern oder Entfernen von Kontaktobjekten muss der Benutzer, der das Cmdlet New-CsExUmContact, CsExUmContact oder Remove-CsExUmContact ausführt, über die richtige Berechtigung für die Active Directory-Organisationseinheit verfügen, in der die neuen Kontaktobjekte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6e85c-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="6e85c-136">Diese Berechtigungen können gewährt werden, indem das Cmdlet Grant-CsOUPermission ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e85c-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="6e85c-137">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="6e85c-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="6e85c-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6e85c-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

