---
title: 'Lync Server 2013: Übersicht über die Vorbereitung der Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51d0fec8f36749f52acf3272bf83dee3170da8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="5e546-102">Übersicht über die Vorbereitung der Active Directory-Domänendienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e546-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e546-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5e546-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5e546-104">Wenn Sie die Active Directory-Domänendienste für Ihre lync Server 2013-Bereitstellung vorbereiten möchten, müssen Sie drei Schritte in einer bestimmten Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="5e546-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="5e546-105">In der folgenden Tabelle werden die Schritte beschrieben, die zum Vorbereiten von AD DS für lync Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5e546-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="5e546-106">Vorbereitungsschritte für Active Directory</span><span class="sxs-lookup"><span data-stu-id="5e546-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5e546-107">Schritt</span><span class="sxs-lookup"><span data-stu-id="5e546-107">Step</span></span></th>
<th><span data-ttu-id="5e546-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e546-108">Description</span></span></th>
<th><span data-ttu-id="5e546-109">Wo ausführen</span><span class="sxs-lookup"><span data-stu-id="5e546-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="5e546-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Vorbereiten des Active Directory-Schemas in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e546-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5e546-111">Erweitert das Active Directory-Schema durch Hinzufügen neuer Klassen und Attribute, die von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e546-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="5e546-112">Einmaliges ausführen für jede Gesamtstruktur in Ihrer Bereitstellung, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e546-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="5e546-113">Für den Schemamaster in der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e546-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5e546-114">Sie müssen diesen Schritt nicht in der Stammdomäne ausführen, wenn Sie über Berechtigungen für den Schemamaster verfügen, aber Sie müssen Mitglied der Gruppe "Schemaadministratoren" in der Stammdomäne und ein Mitglied der Gruppe "Organisations-Admins" auf dem Schemamaster sein.</span><span class="sxs-lookup"><span data-stu-id="5e546-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="5e546-115">Führen Sie in einer Ressourcengesamtstruktur-Topologie diesen Schritt nur in der Ressourcengesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="5e546-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="5e546-116">Führen Sie in einer zentralen Gesamtstrukturtopologie diesen Schritt nur in der zentralen Gesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="5e546-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="5e546-117"><a href="lync-server-2013-preparing-the-forest.md">Vorbereiten der Gesamtstruktur für Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e546-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5e546-118">Erstellt globale Einstellungen und universelle Gruppen, die von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e546-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="5e546-119">Einmaliges ausführen für jede Gesamtstruktur in Ihrer Bereitstellung, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e546-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="5e546-120">In der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e546-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="5e546-121">Damit Sie diesen Schritt ausführen können, müssen Sie Mitglied der Gruppe Organisations-Admins sein.</span><span class="sxs-lookup"><span data-stu-id="5e546-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5e546-122">Führen Sie in einer Ressourcengesamtstruktur-Topologie diesen Schritt nur in der Ressourcengesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="5e546-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="5e546-123">Führen Sie in einer zentralen Gesamtstrukturtopologie diesen Schritt nur in der zentralen Gesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.</span><span class="sxs-lookup"><span data-stu-id="5e546-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="5e546-124"><a href="lync-server-2013-preparing-domains.md">Vorbereiten von Domänen für Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5e546-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5e546-125">Fügt Berechtigungen für Objekte hinzu, die von Mitgliedern universeller Gruppen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5e546-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="5e546-126">Einmal pro Benutzerdomäne oder Server Domäne ausführen.</span><span class="sxs-lookup"><span data-stu-id="5e546-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5e546-127">Wenn Sie von lync Server 2010 zu lync Server 2013 migrieren, zeigt der Bereitstellungs-Assistent möglicherweise an, dass die Domänenvorbereitung bereits abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5e546-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="5e546-128">Sie müssen die Domänenvorbereitung nicht erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="5e546-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="5e546-129">Es wurden keine Berechtigungen von lync Server 2010 zu lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="5e546-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="5e546-130">Auf einem Mitgliedsserver in jeder Domäne, in der lync Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e546-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="5e546-131">Damit Sie diesen Schritt ausführen können, müssen Sie Mitglied der Gruppe der Domänenadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="5e546-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="5e546-132">Lync Server 2013 speichert ähnlich wie lync Server 2010 einen Großteil der Konfigurationsinformationen im zentralen Verwaltungsspeicher statt in AD DS, wie dies bei Office Communications Server 2007 R2 der Fall war.</span><span class="sxs-lookup"><span data-stu-id="5e546-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5e546-133">Die folgenden Informationen werden jedoch in AD DS gespeichert:</span><span class="sxs-lookup"><span data-stu-id="5e546-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="5e546-134">**Schema Erweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="5e546-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5e546-135">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="5e546-135">User object extensions</span></span>
    
      - <span data-ttu-id="5e546-136">Erweiterungen für Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="5e546-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="5e546-137">**Daten** (im erweiterten lync Server-Schema und in vorhandenen Schemaklassen gespeichert):</span><span class="sxs-lookup"><span data-stu-id="5e546-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5e546-138">Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="5e546-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5e546-139">Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="5e546-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5e546-140">Ein Zeiger auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="5e546-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5e546-141">Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="5e546-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5e546-142">In lync Server 2013 delegieren Sie Setup und Verwaltung, indem Sie der universellen RTCUniversalServerAdmins-Gruppe Setup Berechtigungen erteilen, damit Mitglieder dieser Gruppe lync Server 2013 auf einem lokalen Server installieren und aktivieren können (nachdem der Server dem Topologie, veröffentlicht und aktiviert).</span><span class="sxs-lookup"><span data-stu-id="5e546-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="5e546-143">Die Delegierten Benutzer müssen lokale Administratoren auf dem Computer sein, auf dem Sie lync Server 2013 installieren und aktivieren, aber Sie müssen nicht Mitglieder der Gruppe der Domänenadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="5e546-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="5e546-144">Sie können auch Berechtigungen für Objekte in angegebenen Organisationseinheiten (Organizational Units, OUs) erteilen, damit Mitglieder der universellen Gruppen, die während der Gesamtstrukturvorbereitung erstellt wurden, auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.</span><span class="sxs-lookup"><span data-stu-id="5e546-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="5e546-145">Bei neuen Bereitstellungen von lync Server 2013 müssen die globalen Einstellungen im Container Konfiguration gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5e546-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="5e546-146">Wenn Ihre Organisation ein Upgrade von einer früheren Version durchläuft und Sie weiterhin über globale Einstellungen im Systemcontainer verfügen, wird der Systemcontainer weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e546-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e546-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e546-147">See Also</span></span>


[<span data-ttu-id="5e546-148">Vorbereiten des Active Directory-Schemas in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e546-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="5e546-149">Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server 2013 verwendet werden</span><span class="sxs-lookup"><span data-stu-id="5e546-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="5e546-150">Vorbereiten der Gesamtstruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e546-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="5e546-151">Vorbereiten von Domänen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e546-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

