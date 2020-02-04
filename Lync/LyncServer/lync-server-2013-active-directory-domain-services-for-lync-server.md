---
title: 'Lync Server 2013: Active Directory-Domänendienste für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="e43cb-102">Active Directory-Domänendienste für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e43cb-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e43cb-103">_**Letztes Änderungsdatum des Themas:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="e43cb-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="e43cb-104">Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003, Windows Server 2008, Windows Server 2012 und Windows Server 2012 R2-Netzwerke.</span><span class="sxs-lookup"><span data-stu-id="e43cb-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="e43cb-105">Active Directory-Domänendienste dient auch als Grundlage für die Erstellung der Microsoft lync Server 2013-Sicherheitsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e43cb-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="e43cb-106">In diesem Abschnitt wird beschrieben, wie lync Server 2013 die Active Directory-Domänendienste zum Erstellen einer vertrauenswürdigen Umgebung für Chats, Webkonferenzen, Medien und Sprachanrufe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e43cb-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="e43cb-107">Details zu den lync-Server Erweiterungen für Active Directory-Domänendienste und zum Vorbereiten Ihrer Umgebung für Active Directory-Domänendienste finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="e43cb-108">Details zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation zur Version des verwendeten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="e43cb-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="e43cb-109">Lync Server 2013 verwendet die Active Directory-Domänendienste zum Speichern von:</span><span class="sxs-lookup"><span data-stu-id="e43cb-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="e43cb-110">Globale Einstellungen, die auf allen Servern mit lync Server 2013 in einer Gesamtstruktur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e43cb-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="e43cb-111">Dienstinformationen, die die Rollen aller Server mit lync Server 2013 in einer Gesamtstruktur identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e43cb-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="e43cb-112">Einige Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="e43cb-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="e43cb-113">Active Directory-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="e43cb-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="e43cb-114">Zu den Infrastrukturanforderungen für Active Directory gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="e43cb-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="e43cb-115">Betriebssystemanforderungen für Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="e43cb-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="e43cb-116">Anforderungen für die Domänen- und Gesamtstrukturfunktionsebene</span><span class="sxs-lookup"><span data-stu-id="e43cb-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="e43cb-117">Anforderungen für die globale Katalogdomäne</span><span class="sxs-lookup"><span data-stu-id="e43cb-117">Global catalog domain requirements</span></span>

<span data-ttu-id="e43cb-118">Ausführliche Informationen finden Sie unter Anforderungen an die [Active Directory-Infrastruktur für lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="e43cb-119">Vorbereitung der Active Directory-Domänendienste</span><span class="sxs-lookup"><span data-stu-id="e43cb-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e43cb-120">Wir empfehlen, dass Sie die globalen Einstellungen für den Konfigurationscontainer anstelle des System Containers bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="e43cb-121">Dies verbessert nicht die Sicherheit, kann aber zu Verbesserungen bei der Skalierbarkeit einiger Active Directory-Domänendienste-Topologien führen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="e43cb-122">Wenn Sie von Microsoft Office Communications Server 2007 migrieren und den Systemcontainer verwendet haben, aber den Konfigurationscontainer verwenden möchten, müssen Sie die Einstellungen im Systemcontainer verschieben, bevor Sie ein Upgrade vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="e43cb-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="e43cb-123">Informationen zum Migrieren der System Container Einstellungen zum Konfigurationscontainer finden Sie unter Office Communications Server 2007-Migrations Tool für <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>globale Einstellungen unter.</span><span class="sxs-lookup"><span data-stu-id="e43cb-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="e43cb-124">Beim Bereitstellen von lync Server 2013 besteht der erste Schritt darin, Active Directory-Domänendienste vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="e43cb-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="e43cb-125">Das Vorbereiten der Active Directory-Domänendienste für lync Server 2013 umfasst die folgenden drei Schritte:</span><span class="sxs-lookup"><span data-stu-id="e43cb-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="e43cb-126">**Schema vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="e43cb-126">**Prepare Schema**.</span></span> <span data-ttu-id="e43cb-127">Mit dieser Aufgabe wird das Schema in den Active Directory-Domänendiensten so erweitert, dass es Klassen und Attribute enthält, die für lync Server 2013 spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="e43cb-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="e43cb-128">Details zum Vorbereiten des Schemas finden Sie unter [Ausführen der Active Directory-Schemavorbereitung in lync Server 2013](lync-server-2013-running-schema-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="e43cb-129">Weitere Informationen finden Sie unter [Migration von Office Communications Server 2007 R2 zu lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e43cb-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="e43cb-130">**Vorbereiten der Gesamtstruktur**</span><span class="sxs-lookup"><span data-stu-id="e43cb-130">**Prepare Forest**.</span></span> <span data-ttu-id="e43cb-131">Mit dieser Aufgabe werden globale Einstellungen und Objekte in der Gesamtstruktur-Stammdomäne sowie der universelle Dienst und administrative Gruppen erstellt, die den Zugriff auf diese Einstellungen und Objekte Regeln.</span><span class="sxs-lookup"><span data-stu-id="e43cb-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="e43cb-132">Details zum Vorbereiten der Gesamtstruktur finden Sie unter [Ausführen der Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-running-forest-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e43cb-133">**Domäne vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="e43cb-133">**Prepare Domain**.</span></span> <span data-ttu-id="e43cb-134">Mit dieser Aufgabe werden universelle Gruppen, die Berechtigungen zum Hosten und Verwalten von Benutzern innerhalb der Domäne erteilen, die erforderlichen Zugriffssteuerungseinträge (ACEs) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e43cb-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="e43cb-135">Diese Aufgabe muss in allen Domänen ausgeführt werden, in denen Sie Server mit lync Server 2013 und alle Domänen bereitstellen möchten, in denen sich Ihre lync Server-Benutzer befinden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="e43cb-136">Details zum Vorbereiten der Domäne finden Sie unter [Ausführen der Domänenvorbereitung für lync Server 2013](lync-server-2013-running-domain-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e43cb-137">Eine Übersicht über den vollständigen Prozess zum Vorbereiten von Active Directory sowie über die für die einzelnen Schritte erforderlichen Rechte und Berechtigungen finden Sie unter [Active Directory Infrastructure Requirements for lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="e43cb-138">Universelle Gruppen</span><span class="sxs-lookup"><span data-stu-id="e43cb-138">Universal Groups</span></span>

<span data-ttu-id="e43cb-139">Während der Vorbereitung der Gesamtstruktur erstellt lync Server 2013 verschiedene universelle Gruppen in Active Directory-Domänendiensten, die über die Berechtigung zum Zugriff auf und Verwalten globaler Einstellungen und Dienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="e43cb-140">Zu diesen Gruppen zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="e43cb-140">These universal groups include:</span></span>

  - <span data-ttu-id="e43cb-141">**Administrative Gruppen:**</span><span class="sxs-lookup"><span data-stu-id="e43cb-141">**Administrative groups**.</span></span> <span data-ttu-id="e43cb-142">Diese Gruppen definieren die grundlegenden Administratorrollen für ein lync Server-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e43cb-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="e43cb-143">Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen den lync Server-Infrastrukturgruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e43cb-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="e43cb-144">**Dienstgruppen:**</span><span class="sxs-lookup"><span data-stu-id="e43cb-144">**Service groups**.</span></span> <span data-ttu-id="e43cb-145">Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene Dienste erforderlich sind, die von lync Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="e43cb-146">**Infrastrukturgruppen:**</span><span class="sxs-lookup"><span data-stu-id="e43cb-146">**Infrastructure groups**.</span></span> <span data-ttu-id="e43cb-147">Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e43cb-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="e43cb-148">Sie dienen als Komponenten von administrativen Gruppen und Sie sollten sie weder ändern noch ihnen direkt Nutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="e43cb-149">Während der Gesamtstrukturvorbereitung werden den entsprechenden Infrastrukturgruppen bestimmte Dienst- und Administrationsgruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e43cb-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="e43cb-150">Details zu den bei der Vorbereitung von AD für lync Server erstellten universellen Gruppen sowie zu den Dienst-und Verwaltungsgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e43cb-151">Lync Server 2013 unterstützt die universellen Gruppen in Windows Server 2012 für Server, auf denen lync Server 2013 ausgeführt wird, sowie Windows Server 2003-Betriebssysteme für Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="e43cb-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="e43cb-152">Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="e43cb-153">Die Unterstützung für universelle Gruppen in Verbindung mit der Administrator Delegierung vereinfacht die Verwaltung einer lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e43cb-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="e43cb-154">Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="e43cb-155">Rollenbasierte Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="e43cb-155">Role-Based Access Control</span></span>

<span data-ttu-id="e43cb-156">Zusätzlich zum Erstellen von Gruppen für universelle Dienste und Administratoren sowie zum Hinzufügen von Dienst-und Verwaltungsgruppen zu den entsprechenden universellen Gruppen erstellt die Gesamtstrukturvorbereitung auch Rollenbasierte Zugriffssteuerungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="e43cb-157">Details zu den von der Gesamtstrukturvorbereitung erstellten speziellen RBAC-Gruppen finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="e43cb-158">Weitere Informationen zu RBAC-Gruppen finden Sie unter [rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="e43cb-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="e43cb-159">Zugriffssteuerungseinträge (Access Control Entries,ACEs) und Vererbung</span><span class="sxs-lookup"><span data-stu-id="e43cb-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="e43cb-160">Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt und ACEs zu den erstellten universellen Gruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e43cb-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="e43cb-161">Es werden bestimmte private ACEs im Container für globale Einstellungen erstellt, der von lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e43cb-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="e43cb-162">Dieser Container wird nur von lync Server verwendet und befindet sich entweder im Konfigurationscontainer oder im System Container in der Stammdomäne, je nachdem, wo Sie die globalen Einstellungen speichern.</span><span class="sxs-lookup"><span data-stu-id="e43cb-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="e43cb-p114">Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="e43cb-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="e43cb-165">Details zu den öffentlichen ACEs, die von der Gesamtstrukturvorbereitung und Domänenvorbereitung erstellt und hinzugefügt wurden, finden Sie unter [Änderungen der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) und Änderungen, die [von der Domänenvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e43cb-166">Organisationen Sperren häufig Active Directory-Domänendienste (AD DS), um Sicherheitsrisiken zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="e43cb-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="e43cb-167">Eine gesperrte Active Directory-Umgebung kann jedoch die von lync Server 2013 erforderlichen Berechtigungen einschränken.</span><span class="sxs-lookup"><span data-stu-id="e43cb-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="e43cb-168">Dazu kann das Entfernen von ACEs aus Containern und Organisationseinheiten und das Deaktivieren der Vererbung von Berechtigungen für Nutzer-, Kontakt-, InetOrgPerson- oder Computerobjekten gehören.</span><span class="sxs-lookup"><span data-stu-id="e43cb-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="e43cb-169">In einer gesperrten Active Directory-Umgebung müssen Berechtigungen für Container und OUs, für die Sie erforderlich sind, manuell festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="e43cb-170">Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e43cb-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="e43cb-171">Serverinformationen</span><span class="sxs-lookup"><span data-stu-id="e43cb-171">Server Information</span></span>

<span data-ttu-id="e43cb-172">Während der Aktivierung veröffentlicht lync Server 2013 Server Informationen an den drei folgenden Speicherorten in den Active Directory-Domänendiensten:</span><span class="sxs-lookup"><span data-stu-id="e43cb-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="e43cb-173">Einen Dienstverbindungspunkt (Service Connection Point, SCP) für jedes Active Directory-Computerobjekt, das einem physikalischen Computer entspricht, auf dem lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e43cb-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="e43cb-174">Serverobjekte, die im Container der Klasse **msRTCSIP-Pools** erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="e43cb-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="e43cb-175">Im Topologie-Generator angegebene vertrauenswürdige Server.</span><span class="sxs-lookup"><span data-stu-id="e43cb-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="e43cb-176">Dienstverbindungspunkte</span><span class="sxs-lookup"><span data-stu-id="e43cb-176">Service Connection Points</span></span>

<span data-ttu-id="e43cb-177">Jedes lync Server 2013-Objekt in den Active Directory-Domänendiensten verfügt über einen SCP namens RTC Services, der wiederum eine Reihe von Attributen enthält, die jeden Computer identifizieren und die bereitgestellten Dienste angeben.</span><span class="sxs-lookup"><span data-stu-id="e43cb-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="e43cb-178">Zu den wichtigeren Attributen der Dienstverbindungspunkte zählen \*serviceDNSName \*, *serviceDNSNameType*, *serviceClassname* und \*serviceBindingInformation \*.</span><span class="sxs-lookup"><span data-stu-id="e43cb-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="e43cb-179">Asset Management-Anwendungen von Drittanbietern können Serverinformationen bereitstellungsübergreifend abrufen, indem sie diese und andere Attribute von Dienstverbindungspunkten anfragen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="e43cb-180">Active Directory-Server Objekte</span><span class="sxs-lookup"><span data-stu-id="e43cb-180">Active Directory Server Objects</span></span>

<span data-ttu-id="e43cb-181">Jede lync Server 2013-Serverrolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute die von dieser Rolle bereitgestellten Dienste definieren.</span><span class="sxs-lookup"><span data-stu-id="e43cb-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="e43cb-182">Wenn ein Standard Edition-Server aktiviert ist oder wenn ein Enterprise Edition-Pool erstellt wird, erstellt lync Server 2013 ein neues **Attribut msRTCSIP-** Objekt im Container **Attribut msRTCSIP-Pools** .</span><span class="sxs-lookup"><span data-stu-id="e43cb-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="e43cb-183">Die **msRTCSIP-Pool**-Klasse gibt den vollständig qualifizierten Domänennamen (FQDN) des Pools sowie die Verbindung zwischen den Front-End- und Back-End-Komponenten des Pools an.</span><span class="sxs-lookup"><span data-stu-id="e43cb-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="e43cb-184">(Ein Standard Edition-Server wird als logischer Pool angesehen, dessen Front-und Back-Ends auf einem einzelnen Computer angeordnet sind.)</span><span class="sxs-lookup"><span data-stu-id="e43cb-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="e43cb-185">Vertrauenswürdige Server</span><span class="sxs-lookup"><span data-stu-id="e43cb-185">Trusted Servers</span></span>

<span data-ttu-id="e43cb-186">In lync Server 2013 sind vertrauenswürdige Server diejenigen, die beim Ausführen des Topologie-Generators und Veröffentlichen Ihrer Topologie angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e43cb-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="e43cb-187">Die veröffentlichte Topologie wird einschließlich aller Serverinformationen im zentralen Verwaltungsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e43cb-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="e43cb-188">Nur die im zentralen Verwaltungsspeicher definierten Server sind vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="e43cb-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="e43cb-189">In lync Server 2013 ist ein vertrauenswürdiger Server einer, der die folgenden Kriterien erfüllt:</span><span class="sxs-lookup"><span data-stu-id="e43cb-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="e43cb-190">Der FQDN des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie enthalten.</span><span class="sxs-lookup"><span data-stu-id="e43cb-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="e43cb-191">Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="e43cb-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="e43cb-192">Ausführliche Informationen finden Sie unter Anforderungen an die [Zertifikatinfrastruktur für lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43cb-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="e43cb-p120">Wird eins dieser Kriterien nicht erfüllt, ist der Server nicht vertrauenswürdig, und die Verbindung mit ihm wird abgelehnt. Diese doppelte Anforderung verhindert einen möglichen, wenn auch unwahrscheinlichen, Angriff, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="e43cb-195">Damit Microsoft Office Communications Server 2007 R2 und Microsoft Office Communications Server 2007-Bereitstellungen mit lync Server 2013-Servern kommunizieren können, erstellt lync Server 2013 Container während der Gesamtstrukturvorbereitung für das halten von Listen von vertrauenswürdige Server für frühere Versionen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="e43cb-196">In der folgenden Tabelle sind die für die Kompatibilität mit früheren Bereitstellungen erstellten Container beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e43cb-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="e43cb-197">Vertrauenswürdige Server Listen und deren Active Directory-Container zur Kompatibilität mit früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="e43cb-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e43cb-198">Liste vertrauenswürdiger Server</span><span class="sxs-lookup"><span data-stu-id="e43cb-198">Trusted server list</span></span></th>
<th><span data-ttu-id="e43cb-199">Active Directory-Container</span><span class="sxs-lookup"><span data-stu-id="e43cb-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e43cb-200">Standard Edition-Server und Enterprise-Pool-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e43cb-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e43cb-201">RTC Service/Global Settings</span><span class="sxs-lookup"><span data-stu-id="e43cb-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43cb-202">Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="e43cb-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="e43cb-203">RTC Service/Trusted MCUs</span><span class="sxs-lookup"><span data-stu-id="e43cb-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43cb-204">Webkomponentenserver</span><span class="sxs-lookup"><span data-stu-id="e43cb-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="e43cb-205">RTC Service/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="e43cb-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43cb-206">Vermittlungsservers und Communicator Web Access-Server, Anwendungsserver, Registrierung mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)</span><span class="sxs-lookup"><span data-stu-id="e43cb-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="e43cb-207">RTC Service/Trusted Services</span><span class="sxs-lookup"><span data-stu-id="e43cb-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43cb-208">Proxyserver</span><span class="sxs-lookup"><span data-stu-id="e43cb-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="e43cb-209">Lync Server 2013 unterstützt keine Abwärtskompatibilität für Proxy Server</span><span class="sxs-lookup"><span data-stu-id="e43cb-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e43cb-210">Zur Unterstützung von vertrauenswürdigen Servern vorheriger Versionen müssen Sie das Tool bewährte Methoden Analyzer ausführen.</span><span class="sxs-lookup"><span data-stu-id="e43cb-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="e43cb-211">Details zum Ausführen des Best Practices Analyzer finden Sie [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)unter.</span><span class="sxs-lookup"><span data-stu-id="e43cb-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

