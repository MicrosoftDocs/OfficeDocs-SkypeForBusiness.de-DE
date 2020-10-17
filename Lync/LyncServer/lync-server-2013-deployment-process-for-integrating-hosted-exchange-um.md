---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration von gehosteten Exchange um'
description: 'Lync Server 2013: Bereitstellungsprozess für die Integration von gehosteten Exchange um.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542611"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="31100-103">Bereitstellungsprozess für die Integration gehosteter Exchange um mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31100-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31100-104">_**Letztes Änderungsstand des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="31100-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="31100-105">Für eine effektive Planung für die Integration von lync Server 2013 mit gehosteten Exchange Unified Messaging (um) müssen Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="31100-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="31100-106">Voraussetzungen für die Integration von lync Server 2013 mit gehosteten Exchange um</span><span class="sxs-lookup"><span data-stu-id="31100-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="31100-107">Erforderliche Schritte während des Integrationsprozesses</span><span class="sxs-lookup"><span data-stu-id="31100-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="31100-108">Bereitstellungsvoraussetzungen für die Integration in gehostete Exchange UM-Dienste</span><span class="sxs-lookup"><span data-stu-id="31100-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="31100-109">Bevor Sie mit dem Integrationsprozess beginnen können, müssen Sie bereits lync Server 2013 bereitgestellt haben (mindestens eine Front-End-Pool oder ein Standard Edition-Server), eine Edgeserver und lync 2013 oder lync 2010 Clients.</span><span class="sxs-lookup"><span data-stu-id="31100-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="31100-110">Integrationsprozess</span><span class="sxs-lookup"><span data-stu-id="31100-110">Integration Process</span></span>

<span data-ttu-id="31100-111">Die folgende Tabelle zeigt eine Übersicht über den Integrationsprozess der gehosteten Exchange Unified Messaging-Dienste.</span><span class="sxs-lookup"><span data-stu-id="31100-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="31100-112">Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [providing lync Server 2013 users Voice Mail on Hosted Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="31100-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31100-113">Phase</span><span class="sxs-lookup"><span data-stu-id="31100-113">Phase</span></span></th>
<th><span data-ttu-id="31100-114">Schritte</span><span class="sxs-lookup"><span data-stu-id="31100-114">Steps</span></span></th>
<th><span data-ttu-id="31100-115">Rechte und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="31100-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="31100-116">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="31100-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31100-117">Konfigurieren des Edgeservers</span><span class="sxs-lookup"><span data-stu-id="31100-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="31100-118">Konfigurieren Sie den Edgeserver für einen Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="31100-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="31100-119">Replizieren Sie die Daten manuell auf den Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="31100-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="31100-120">Konfigurieren Sie den Hostingprovider auf dem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="31100-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="31100-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="31100-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="31100-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Konfigurieren der Edgeserver für die Integration in gehostete Exchange um</a></span><span class="sxs-lookup"><span data-stu-id="31100-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31100-123">Konfigurieren der Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="31100-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="31100-124">Ändern Sie entweder die globale Richtlinie für gehostete Voicemail, oder erstellen Sie eine neue Richtlinie für gehostete Voicemail auf Standort- oder Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="31100-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="31100-125">Weisen Sie auf Benutzerebene erstellte Richtlinien den geeigneten Benutzern oder Gruppen zu.</span><span class="sxs-lookup"><span data-stu-id="31100-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="31100-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="31100-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="31100-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="31100-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31100-128">Aktivieren von Benutzerkonten für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="31100-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="31100-129">Konfigurieren Sie Benutzerkonten für Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="31100-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="31100-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="31100-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="31100-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Aktivieren von Benutzern für gehostete Voicemail in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="31100-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31100-132">Konfigurieren von gehosteten Kontaktobjekten</span><span class="sxs-lookup"><span data-stu-id="31100-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="31100-133">Erstellen Sie Kontaktobjekte für automatische Telefonzentralen für gehostete Exchange UM-Dienste.</span><span class="sxs-lookup"><span data-stu-id="31100-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="31100-134">Erstellen Sie Kontaktobjekte für den Teilnehmerzugriff für gehostete Exchange UM-Dienste.</span><span class="sxs-lookup"><span data-stu-id="31100-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="31100-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="31100-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="31100-136">Zum Erstellen, Ändern oder Entfernen von Kontaktobjekten muss der Benutzer, der das Cmdlet "New-CsExUmContact", "Set-CsExUmContact" oder "Remove-CsExUmContact" ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="31100-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="31100-137">Diese Berechtigungen können mit dem Cmdlet "Grant-CsOUPermission" gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="31100-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="31100-138">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="31100-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="31100-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Erstellen von Contact-Objekten für gehostete Exchange um in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="31100-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

