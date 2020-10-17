---
title: 'Lync Server 2013: Active Directory-Domänendienste für lync Server'
description: 'Lync Server 2013: Active Directory-Domänendienste für lync Server.'
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
ms.openlocfilehash: 50c7460daa312daf5fb857f51fe1acb78972447c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571071"
---
# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="b2225-103">Active Directory-Domänendienste für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2225-103">Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2225-104">_**Letztes Änderungsstand des Themas:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="b2225-104">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="b2225-105">Active Directory-Domänendienste fungiert als Verzeichnisdienst für Windows Server 2003-, Windows Server 2008-, Windows Server 2012-und Windows Server 2012 R2-Netzwerke.</span><span class="sxs-lookup"><span data-stu-id="b2225-105">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="b2225-106">Active Directory-Domänendienste dient auch als Grundlage, auf der die Microsoft lync Server 2013 Sicherheitsinfrastruktur aufgebaut ist.</span><span class="sxs-lookup"><span data-stu-id="b2225-106">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="b2225-107">In diesem Abschnitt wird beschrieben, wie lync Server 2013 Active Directory-Domänendienste verwendet, um eine vertrauenswürdige Umgebung für Chat, Webkonferenzen, Medien und VoIP zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b2225-107">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="b2225-108">Ausführliche Informationen zu lync Server Erweiterungen für Active Directory-Domänendienste und zur Vorbereitung Ihrer Umgebung auf Active Directory-Domänendienste finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-108">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="b2225-109">Ausführliche Informationen zur Rolle der Active Directory-Domänendienste in Windows Server-Netzwerken finden Sie in der Dokumentation für die Version des von Ihnen verwendeten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="b2225-109">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="b2225-110">Lync Server 2013 verwendet Active Directory-Domänendienste zum Speichern von:</span><span class="sxs-lookup"><span data-stu-id="b2225-110">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="b2225-111">Globale Einstellungen, die alle lync Server 2013 in einer Gesamtstruktur ausgeführten Server benötigen.</span><span class="sxs-lookup"><span data-stu-id="b2225-111">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="b2225-112">Dienstinformationen, mit denen die Rollen aller Server identifiziert werden, auf denen lync Server 2013 in einer Gesamtstruktur ausführt.</span><span class="sxs-lookup"><span data-stu-id="b2225-112">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="b2225-113">Einige Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="b2225-113">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="b2225-114">Active Directory-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="b2225-114">Active Directory Infrastructure</span></span>

<span data-ttu-id="b2225-115">Für Active Directory gelten die folgenden Infrastrukturanforderungen:</span><span class="sxs-lookup"><span data-stu-id="b2225-115">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="b2225-116">Betriebssystemanforderungen für Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="b2225-116">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="b2225-117">Anforderungen bezüglich der Funktionsebene der Domäne und der Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="b2225-117">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="b2225-118">Domänenanforderungen bezüglich des globalen Katalogs</span><span class="sxs-lookup"><span data-stu-id="b2225-118">Global catalog domain requirements</span></span>

<span data-ttu-id="b2225-119">Ausführliche Informationen finden Sie unter [Active Directory Infrastrukturanforderungen für lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-119">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="b2225-120">Vorbereiten der Active Directory-Domänendienste</span><span class="sxs-lookup"><span data-stu-id="b2225-120">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2225-121">Es wird empfohlen, globale Einstellungen nicht im Systemcontainer, sondern im Konfigurationscontainer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b2225-121">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="b2225-122">Dadurch wird zwar die Sicherheit nicht optimiert, aber es kann zu Verbesserungen bei der Skalierbarkeit für einige Topologien der Active Directory-Domänendienste führen.</span><span class="sxs-lookup"><span data-stu-id="b2225-122">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="b2225-123">Wenn Sie von Microsoft Office Communications Server 2007 migrieren und den Systemcontainer verwendet haben, aber den Konfigurationscontainer verwenden möchten, müssen Sie die Einstellungen im Systemcontainer verschieben, bevor Sie ein Upgrade vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="b2225-123">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="b2225-124">Informationen zum Migrieren der System Container Einstellungen zum Konfigurationscontainer finden Sie unter Office Communications Server 2007 Migration Tool Global Settings unter <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> .</span><span class="sxs-lookup"><span data-stu-id="b2225-124">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="b2225-125">Bei der Bereitstellung von lync Server 2013 besteht der erste Schritt darin, Active Directory-Domänendienste vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="b2225-125">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="b2225-126">Das Vorbereiten Active Directory-Domänendienste für lync Server 2013 umfasst die folgenden drei Schritte:</span><span class="sxs-lookup"><span data-stu-id="b2225-126">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="b2225-127">**Vorbereiten des Schemas**.</span><span class="sxs-lookup"><span data-stu-id="b2225-127">**Prepare Schema**.</span></span> <span data-ttu-id="b2225-128">Diese Aufgabe erweitert das Schema in Active Directory-Domänendienste auf Klassen und Attribute, die spezifisch für lync Server 2013 sind.</span><span class="sxs-lookup"><span data-stu-id="b2225-128">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="b2225-129">Ausführliche Informationen zum Vorbereiten des Schemas finden Sie unter [Running Active Directory Schema Preparation in lync Server 2013](lync-server-2013-running-schema-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-129">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="b2225-130">Weitere Informationen finden Sie unter [Migration from Office Communications Server 2007 R2 to lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="b2225-130">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="b2225-131">**Vorbereiten der Gesamtstruktur**</span><span class="sxs-lookup"><span data-stu-id="b2225-131">**Prepare Forest**.</span></span> <span data-ttu-id="b2225-132">Mit dieser Aufgabe werden globale Einstellungen und Objekte in der Gesamtstruktur-Stammdomäne sowie der universelle Dienst und administrative Gruppen erstellt, die den Zugriff auf diese Einstellungen und Objekte steuern.</span><span class="sxs-lookup"><span data-stu-id="b2225-132">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="b2225-133">Ausführliche Informationen zum Vorbereiten der Gesamtstruktur finden Sie unter [Ausführung der Gesamtstrukturvorbereitung für lync Server 2013](lync-server-2013-running-forest-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-133">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="b2225-134">**Vorbereiten der Domäne**.</span><span class="sxs-lookup"><span data-stu-id="b2225-134">**Prepare Domain**.</span></span> <span data-ttu-id="b2225-135">Diese Aufgabe fügt universelle Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzu, die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne erteilen.</span><span class="sxs-lookup"><span data-stu-id="b2225-135">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="b2225-136">Diese Aufgabe muss in allen Domänen abgeschlossen sein, in denen Sie Server mit lync Server 2013 und Domänen bereitstellen möchten, in denen sich Ihre lync Server Benutzer befinden.</span><span class="sxs-lookup"><span data-stu-id="b2225-136">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="b2225-137">Ausführliche Informationen zum Vorbereiten der Domäne finden Sie unter [Ausführung der Domänenvorbereitung für lync Server 2013](lync-server-2013-running-domain-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-137">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b2225-138">Eine Übersicht über den vollständigen Prozess für die Vorbereitung Active Directory und die erforderlichen Rechte und Berechtigungen zum Ausführen der einzelnen Schritte finden Sie unter [Active Directory Infrastrukturanforderungen für lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-138">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="b2225-139">Universelle Gruppen</span><span class="sxs-lookup"><span data-stu-id="b2225-139">Universal Groups</span></span>

<span data-ttu-id="b2225-140">Während der Vorbereitung der Gesamtstruktur erstellt lync Server 2013 verschiedene universelle Gruppen in Active Directory-Domänendienste, die über die Berechtigung zum Zugreifen auf und Verwalten globaler Einstellungen und Dienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="b2225-140">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="b2225-141">Dazu gehören folgende universelle Gruppen:</span><span class="sxs-lookup"><span data-stu-id="b2225-141">These universal groups include:</span></span>

  - <span data-ttu-id="b2225-142">**Administrative Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="b2225-142">**Administrative groups**.</span></span> <span data-ttu-id="b2225-143">Diese Gruppen definieren die grundlegenden Administratorrollen für ein lync Server Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="b2225-143">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="b2225-144">Während der Gesamtstrukturvorbereitung werden diese Administratorgruppen zu lync Server-Infrastrukturgruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2225-144">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="b2225-145">**Dienstgruppen**.</span><span class="sxs-lookup"><span data-stu-id="b2225-145">**Service groups**.</span></span> <span data-ttu-id="b2225-146">Diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene von lync Server bereitgestellte Dienste erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2225-146">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="b2225-147">**Infrastrukturgruppen**.</span><span class="sxs-lookup"><span data-stu-id="b2225-147">**Infrastructure groups**.</span></span> <span data-ttu-id="b2225-148">Diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="b2225-148">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="b2225-149">Es sollten keine Infrastrukturgruppen geändert oder Benutzer direkt zu ihnen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b2225-149">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="b2225-150">Während der Gesamtstrukturvorbereitung werden bestimmte Dienst-und Verwaltungsgruppen zu den entsprechenden Infrastrukturgruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2225-150">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="b2225-151">Ausführliche Informationen zu den spezifischen universellen Gruppen, die beim Vorbereiten von AD für lync Server erstellt werden, sowie zu den Dienst-und Verwaltungsgruppen, die den Infrastrukturgruppen hinzugefügt werden, finden Sie unter Änderungen, die [von der Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b2225-151">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2225-152">Lync Server 2013 unterstützt die universellen Gruppen im Windows Server 2012 für Server, auf denen lync Server 2013 läuft, sowie Windows Server 2003 Betriebssysteme für Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="b2225-152">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="b2225-153">Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen.</span><span class="sxs-lookup"><span data-stu-id="b2225-153">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="b2225-154">Die universelle Gruppenunterstützung in Kombination mit der Administrator Delegierung vereinfacht die Verwaltung einer lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="b2225-154">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="b2225-155">Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen Domäne hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b2225-155">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="b2225-156">Rollenbasierte Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="b2225-156">Role-Based Access Control</span></span>

<span data-ttu-id="b2225-157">Neben dem Erstellen von universellen Dienst-und Verwaltungsgruppen und dem Hinzufügen von Dienst-und Verwaltungsgruppen zu den entsprechenden universellen Gruppen erstellt die Gesamtstrukturvorbereitung auch Role-Based Zugriffssteuerungsgruppen (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b2225-157">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="b2225-158">Ausführliche Informationen zu den spezifischen RBAC-Gruppen, die von der Gesamtstrukturvorbereitung erstellt werden, finden Sie unter Änderungen bei der [Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-158">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="b2225-159">Weitere Informationen zu RBAC-Gruppen finden Sie unter [Role-Based Access Control (RBAC) für lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="b2225-159">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="b2225-160">Zugriffssteuerungseinträge und Vererbung</span><span class="sxs-lookup"><span data-stu-id="b2225-160">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="b2225-161">Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche Zugriffssteuerungseinträge (Access Control Entries, ACEs) erstellt sowie ACEs für die erstellten universellen Gruppen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2225-161">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="b2225-162">Es werden bestimmte private ACEs im Container "globale Einstellungen" erstellt, der von lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2225-162">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="b2225-163">Dieser Container wird nur von lync Server verwendet und befindet sich in Abhängigkeit davon, wo Sie globale Einstellungen speichern, entweder im Konfigurationscontainer oder im System Container in der Stammdomäne.</span><span class="sxs-lookup"><span data-stu-id="b2225-163">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="b2225-p114">Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="b2225-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="b2225-166">Ausführliche Informationen zu den öffentlichen ACEs, die von der Gesamtstrukturvorbereitung und der Domänenvorbereitung erstellt und hinzugefügt wurden, finden Sie unter Änderungen bei der [Gesamtstrukturvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) und Änderungen, die [von der Domänenvorbereitung in lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in der Bereitstellungsdokumentation vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b2225-166">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b2225-167">In Organisationen werden die Active Directory-Domänendienste (Active Directory Domain Services, AD DS) häufig gesperrt, um Sicherheitsrisiken nach Möglichkeit auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="b2225-167">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="b2225-168">Eine gesperrte Active Directory Umgebung kann jedoch die Berechtigungen einschränken, die lync Server 2013 erfordert.</span><span class="sxs-lookup"><span data-stu-id="b2225-168">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="b2225-169">Dies kann das Entfernen von ACEs aus Containern und Organisationseinheiten (Organizational Units, OUs) und das Deaktivieren der Vererbung von Berechtigungen für Benutzer-, Kontakt-, InetOrgPerson- oder Computerobjekte beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b2225-169">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="b2225-170">In einer gesperrten Active Directory-Umgebung müssen Berechtigungen manuell für die entsprechenden Container und Organisationseinheiten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b2225-170">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="b2225-171">Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b2225-171">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="b2225-172">Serverinformationen</span><span class="sxs-lookup"><span data-stu-id="b2225-172">Server Information</span></span>

<span data-ttu-id="b2225-173">Während der Aktivierung veröffentlicht lync Server 2013 Server Informationen an den drei folgenden Speicherorten in Active Directory-Domänendienste:</span><span class="sxs-lookup"><span data-stu-id="b2225-173">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="b2225-174">Einen Dienstverbindungspunkt (Service Connection Points, SCP) auf jedem Active Directory Computerobjekt, das einem physischen Computer entspricht, auf dem lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b2225-174">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="b2225-175">Serverobjekte, die im Container der **msRTCSIP-Pools**-Klasse erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="b2225-175">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="b2225-176">Im Topologie-Generator angegebene vertrauenswürdige Server.</span><span class="sxs-lookup"><span data-stu-id="b2225-176">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="b2225-177">Dienstverbindungspunkte</span><span class="sxs-lookup"><span data-stu-id="b2225-177">Service Connection Points</span></span>

<span data-ttu-id="b2225-178">Jedes lync Server 2013-Objekt in Active Directory-Domänendienste verfügt über einen SCP namens RTC Services, der wiederum eine Reihe von Attributen enthält, mit denen jeder Computer identifiziert und die bereitgestellten Dienste angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2225-178">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="b2225-179">Zu den wichtigsten SCP-Attributen gehören *servicednsname*, *serviceDNSNameType*, *serviceClassName*und *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="b2225-179">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="b2225-180">Asset Management-Anwendungen von Drittanbietern können Server Informationen in einer Bereitstellung abrufen, indem Sie diese und andere SCP-Attribute Abfragen.</span><span class="sxs-lookup"><span data-stu-id="b2225-180">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="b2225-181">Active Directory-Serverobjekte</span><span class="sxs-lookup"><span data-stu-id="b2225-181">Active Directory Server Objects</span></span>

<span data-ttu-id="b2225-182">Jede lync Server 2013 Server Rolle verfügt über ein entsprechendes Active Directory-Objekt, dessen Attribute die von dieser Rolle bereitgestellten Dienste definieren.</span><span class="sxs-lookup"><span data-stu-id="b2225-182">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="b2225-183">Wenn ein Standard Edition-Server aktiviert wird oder ein Enterprise Edition-Pool erstellt wird, erstellt lync Server 2013 außerdem ein neues **msRTCSIP-** Objekt im **msRTCSIP-Pool-** Container.</span><span class="sxs-lookup"><span data-stu-id="b2225-183">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="b2225-184">In der **msRTCSIP-Pool**-Klasse werden der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools und die Zuordnung zwischen Front-End- und Back-End-Komponenten des Pools festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b2225-184">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="b2225-185">(Ein Standard Edition-Server wird als logischer Pool betrachtet, dessen Front- und Back-Ends gemeinsam auf einem einzigen Computer ausgeführt werden.)</span><span class="sxs-lookup"><span data-stu-id="b2225-185">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="b2225-186">Vertrauenswürdige Server</span><span class="sxs-lookup"><span data-stu-id="b2225-186">Trusted Servers</span></span>

<span data-ttu-id="b2225-187">In lync Server 2013 sind vertrauenswürdige Server diejenigen, die beim Ausführen des Topologie-Generators und Veröffentlichen Ihrer Topologie angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2225-187">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="b2225-188">Die veröffentlichte Topologie, einschließlich aller Serverinformationen, wird im zentralen Verwaltungsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b2225-188">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="b2225-189">Nur im zentralen Verwaltungsspeicher definierte Server sind vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="b2225-189">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="b2225-190">In lync Server 2013 ist ein vertrauenswürdiger Server einer, der die folgenden Kriterien erfüllt:</span><span class="sxs-lookup"><span data-stu-id="b2225-190">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="b2225-191">Der vollqualifizierte Domänenname (FQDN) des Servers ist in der im zentralen Verwaltungsspeicher gespeicherten Topologie vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b2225-191">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="b2225-192">Der Server verfügt über ein gültiges Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="b2225-192">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="b2225-193">Ausführliche Informationen finden Sie unter [Certificate Infrastructure Requirements for lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2225-193">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="b2225-p120">Wenn eines dieser Kriterien nicht zutrifft, gilt der Server nicht als vertrauenswürdig und es wird keine Verbindung damit hergestellt. Diese doppelte Anforderung soll einen möglichen, wenn auch unwahrscheinlichen Angriff ausschließen, bei dem ein nicht autorisierter Server versucht, den FQDN eines gültigen Servers zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b2225-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="b2225-196">Um Microsoft Office Communications Server 2007 R2-und Microsoft Office Communications Server 2007-Bereitstellungen mit lync Server 2013-Servern zu kommunizieren, erstellt lync Server 2013 außerdem Container während der Gesamtstrukturvorbereitung für die Aufbewahrung von Listen vertrauenswürdiger Server für frühere Versionen.</span><span class="sxs-lookup"><span data-stu-id="b2225-196">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="b2225-197">In der folgenden Tabelle werden die Container beschrieben, die erstellt werden, um die Kompatibilität mit früheren Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b2225-197">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="b2225-198">Listen mit vertrauenswürdigen Servern und ihre entsprechenden Active Directory-Container für die Kompatibilität mit vorherigen Versionen</span><span class="sxs-lookup"><span data-stu-id="b2225-198">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2225-199">Listen mit vertrauenswürdigen Servern</span><span class="sxs-lookup"><span data-stu-id="b2225-199">Trusted server list</span></span></th>
<th><span data-ttu-id="b2225-200">Active Directory-Container</span><span class="sxs-lookup"><span data-stu-id="b2225-200">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2225-201">Standard Edition-Server und Front End-Server von Enterprise-Pools</span><span class="sxs-lookup"><span data-stu-id="b2225-201">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b2225-202">RTC-Dienst/Globale Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b2225-202">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2225-203">Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="b2225-203">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="b2225-204">RTC-Dienst/Vertrauenswürdige MCUs</span><span class="sxs-lookup"><span data-stu-id="b2225-204">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2225-205">Webkomponentenserver</span><span class="sxs-lookup"><span data-stu-id="b2225-205">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="b2225-206">RTC-Dienst/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="b2225-206">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2225-207">Vermittlungsserver und Communicator Web Access-Server, Anwendungsserver, Registrierungsstelle mit QoE, A/V-Konferenzdienst (auch SIP-Server von Drittanbietern)</span><span class="sxs-lookup"><span data-stu-id="b2225-207">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="b2225-208">RTC-Dienst/Vertrauenswürdige Dienste</span><span class="sxs-lookup"><span data-stu-id="b2225-208">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2225-209">Proxyserver</span><span class="sxs-lookup"><span data-stu-id="b2225-209">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="b2225-210">Lync Server 2013 unterstützt keine Abwärtskompatibilität für Proxy Server</span><span class="sxs-lookup"><span data-stu-id="b2225-210">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b2225-211">Um vertrauenswürdige Server früherer Versionen zu unterstützen, müssen Sie das Tool Best Practices Analyzer ausführen.</span><span class="sxs-lookup"><span data-stu-id="b2225-211">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="b2225-212">Ausführliche Informationen zum Durchführen von Best Practices Analyzer finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) .</span><span class="sxs-lookup"><span data-stu-id="b2225-212">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

