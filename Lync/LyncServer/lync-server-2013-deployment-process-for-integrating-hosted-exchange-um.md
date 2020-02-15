---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration von gehosteten Exchange um'
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
ms.openlocfilehash: cdab3e470037780d871f9ac6a5eba549497cd23a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="29ff9-102">Bereitstellungsprozess für die Integration gehosteter Exchange um mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29ff9-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29ff9-103">_**Letztes Änderungsstand des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="29ff9-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="29ff9-104">Für eine effektive Planung für die Integration von lync Server 2013 mit gehosteten Exchange Unified Messaging (um) müssen Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="29ff9-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="29ff9-105">Voraussetzungen für die Integration von lync Server 2013 mit gehosteten Exchange um</span><span class="sxs-lookup"><span data-stu-id="29ff9-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="29ff9-106">Erforderliche Schritte während des Integrationsprozesses</span><span class="sxs-lookup"><span data-stu-id="29ff9-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="29ff9-107">Bereitstellungsvoraussetzungen für die Integration in gehostete Exchange UM-Dienste</span><span class="sxs-lookup"><span data-stu-id="29ff9-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="29ff9-108">Bevor Sie mit dem Integrationsprozess beginnen können, müssen Sie bereits lync Server 2013 bereitgestellt haben (mindestens eine Front-End-Pool oder ein Standard Edition-Server), eine Edgeserver und lync 2013 oder lync 2010 Clients.</span><span class="sxs-lookup"><span data-stu-id="29ff9-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="29ff9-109">Integrationsprozess</span><span class="sxs-lookup"><span data-stu-id="29ff9-109">Integration Process</span></span>

<span data-ttu-id="29ff9-110">Die folgende Tabelle zeigt eine Übersicht über den Integrationsprozess der gehosteten Exchange Unified Messaging-Dienste.</span><span class="sxs-lookup"><span data-stu-id="29ff9-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="29ff9-111">Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [providing lync Server 2013 users Voice Mail on Hosted Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="29ff9-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29ff9-112">Phase</span><span class="sxs-lookup"><span data-stu-id="29ff9-112">Phase</span></span></th>
<th><span data-ttu-id="29ff9-113">Schritte</span><span class="sxs-lookup"><span data-stu-id="29ff9-113">Steps</span></span></th>
<th><span data-ttu-id="29ff9-114">Rechte und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29ff9-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="29ff9-115">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="29ff9-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29ff9-116">Konfigurieren des Edgeservers</span><span class="sxs-lookup"><span data-stu-id="29ff9-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="29ff9-117">Konfigurieren Sie den Edgeserver für einen Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="29ff9-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="29ff9-118">Replizieren Sie die Daten manuell auf den Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="29ff9-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="29ff9-119">Konfigurieren Sie den Hostingprovider auf dem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="29ff9-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="29ff9-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="29ff9-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="29ff9-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Konfigurieren der Edgeserver für die Integration in gehostete Exchange um</a></span><span class="sxs-lookup"><span data-stu-id="29ff9-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29ff9-122">Konfigurieren der Richtlinie für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="29ff9-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="29ff9-123">Ändern Sie entweder die globale Richtlinie für gehostete Voicemail, oder erstellen Sie eine neue Richtlinie für gehostete Voicemail auf Standort- oder Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="29ff9-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="29ff9-124">Weisen Sie auf Benutzerebene erstellte Richtlinien den geeigneten Benutzern oder Gruppen zu.</span><span class="sxs-lookup"><span data-stu-id="29ff9-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="29ff9-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="29ff9-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="29ff9-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="29ff9-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29ff9-127">Aktivieren von Benutzerkonten für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="29ff9-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="29ff9-128">Konfigurieren Sie Benutzerkonten für Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="29ff9-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="29ff9-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29ff9-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="29ff9-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Aktivieren von Benutzern für gehostete Voicemail in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="29ff9-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29ff9-131">Konfigurieren von gehosteten Kontaktobjekten</span><span class="sxs-lookup"><span data-stu-id="29ff9-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="29ff9-132">Erstellen Sie Kontaktobjekte für automatische Telefonzentralen für gehostete Exchange UM-Dienste.</span><span class="sxs-lookup"><span data-stu-id="29ff9-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="29ff9-133">Erstellen Sie Kontaktobjekte für den Teilnehmerzugriff für gehostete Exchange UM-Dienste.</span><span class="sxs-lookup"><span data-stu-id="29ff9-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="29ff9-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="29ff9-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="29ff9-135">Zum Erstellen, Ändern oder Entfernen von Kontaktobjekten muss der Benutzer, der das Cmdlet "New-CsExUmContact", "Set-CsExUmContact" oder "Remove-CsExUmContact" ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="29ff9-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="29ff9-136">Diese Berechtigungen können mit dem Cmdlet "Grant-CsOUPermission" gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="29ff9-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="29ff9-137">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="29ff9-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="29ff9-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Erstellen von Contact-Objekten für gehostete Exchange um in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="29ff9-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

