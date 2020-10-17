---
title: 'Lync Server 2013: Wählpläne und Normalisierungsregeln'
description: 'Lync Server 2013: Wählpläne und Normalisierungsregeln.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559741"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="e674e-103">Wählpläne und Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e674e-103">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e674e-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e674e-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e674e-105">Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-105">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="e674e-106">Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt.</span><span class="sxs-lookup"><span data-stu-id="e674e-106">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="e674e-107">Die gleiche Wählzeichenfolge kann unterschiedlich interpretiert und übersetzt werden, je nach Standort, von dem Sie gewählt wird, und der Person oder dem Kontaktobjekt, die den Anruf tätigen.</span><span class="sxs-lookup"><span data-stu-id="e674e-107">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="e674e-108">Wähl Plan Bereich</span><span class="sxs-lookup"><span data-stu-id="e674e-108">Dial Plan Scope</span></span>

<span data-ttu-id="e674e-109">Der *Bereich* eines Wähl Plans bestimmt die hierarchische Ebene, auf der die Wähleinstellungen angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e674e-109">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="e674e-110">In lync Server kann ein Benutzer einen bestimmten Wählplan für einzelne Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e674e-110">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="e674e-111">Wenn kein Benutzer Wähl Plan zugewiesen ist, wird der Wählplan für den registrierungsstellenpool angewendet.</span><span class="sxs-lookup"><span data-stu-id="e674e-111">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="e674e-112">Wenn kein Wählplan für einen registrierungsstellenpool vorhanden ist, wird der Standort Wähl Plan angewendet.</span><span class="sxs-lookup"><span data-stu-id="e674e-112">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="e674e-113">Wenn keine anderen Wähleinstellungen für den Benutzer gelten, wird der globale Wählplan angewendet.</span><span class="sxs-lookup"><span data-stu-id="e674e-113">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="e674e-114">Clients erhalten Wähl planbereichs Ebenen durch in-Band-Bereitstellung Einstellungen, die bereitgestellt werden, wenn sich Benutzer bei lync Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="e674e-114">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="e674e-115">Als Administrator können Sie Bereichsebenen für Wähleinstellungen mithilfe von lync Server-Systemsteuerung verwalten und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e674e-115">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e674e-116">Die Wähleinstellungen für das öffentliche Telefonnetz (PSTN) auf Dienstebene werden auf eingehende Anrufe von einem bestimmten Gateway angewendet.</span><span class="sxs-lookup"><span data-stu-id="e674e-116">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="e674e-117">Bereichsebenen für Wähleinstellungen sind wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="e674e-117">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="e674e-118">**Benutzerwähleinstellungen:** Kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-118">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="e674e-119">VoIP-Anwendungen können einen benutzerbezogenen Wählplan nachschlagen, wenn ein Anruf mit dem auf Benutzer Standard festgelegten Telefonkontext empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="e674e-119">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="e674e-120">Für den Zweck der Zuweisung eines Wählplans wird ein Kontaktobjekt als einzelner Benutzer behandelt.</span><span class="sxs-lookup"><span data-stu-id="e674e-120">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="e674e-121">**Pool Wähl Plan:** Kann auf Dienstebene für ein beliebiges PSTN-Gateway oder eine Registrierungsstelle in Ihrer Topologie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-121">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="e674e-122">Um einen Wählplan für einen Pool zu definieren, müssen Sie den jeweiligen Dienst (PSTN-Gateway oder registrierungsstellenpool) angeben, auf den der Wählplan angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e674e-122">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="e674e-123">**Website Wähl Plan:** Kann für eine gesamte Website erstellt werden, mit Ausnahme von Benutzern, Gruppen oder Kontaktobjekten, denen ein Pool Wähl Plan oder Benutzer Wähl Plan zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e674e-123">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="e674e-124">Zum Definieren eines Website Wähl Plans müssen Sie den Standort angeben, auf den der Wählplan angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e674e-124">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="e674e-125">**Globale Wähleinstellungen:** Die Standard Wähleinstellungen, die mit dem Produkt installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e674e-125">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="e674e-126">Sie können die globalen Wähleinstellungen bearbeiten, jedoch nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="e674e-126">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="e674e-127">Dieser Wählplan gilt für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen einen Wählplan mit einem spezifischeren Bereich zu.</span><span class="sxs-lookup"><span data-stu-id="e674e-127">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="e674e-128">Planen von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="e674e-128">Planning for Dial Plans</span></span>

<span data-ttu-id="e674e-129">Führen Sie die folgenden Schritte aus, um einen Wählplan zu planen:</span><span class="sxs-lookup"><span data-stu-id="e674e-129">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="e674e-130">Auflisten aller Gebietsschemas, in denen Ihre Organisation über ein Office verfügt.</span><span class="sxs-lookup"><span data-stu-id="e674e-130">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="e674e-131">Die Liste muss auf dem neuesten Stand und vollständig sein.</span><span class="sxs-lookup"><span data-stu-id="e674e-131">The list must be up-to-date and complete.</span></span> <span data-ttu-id="e674e-132">Es muss überarbeitet werden, wenn sich die Unternehmensorganisation entwickelt.</span><span class="sxs-lookup"><span data-stu-id="e674e-132">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="e674e-133">In einem großen multinationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann dies eine zeitaufwändige Aufgabe sein.</span><span class="sxs-lookup"><span data-stu-id="e674e-133">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="e674e-134">Identifizieren gültiger Zahlenmuster für jede Website.</span><span class="sxs-lookup"><span data-stu-id="e674e-134">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="e674e-135">Der zeitaufwändigste Teil der Planung Ihrer Wählpläne ist die Ermittlung gültiger Nummernmuster für jeden Standort.</span><span class="sxs-lookup"><span data-stu-id="e674e-135">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="e674e-136">In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan geschrieben haben, in andere Wählpläne kopieren, insbesondere dann, wenn sich die entsprechenden Standorte innerhalb desselben Landes/einer Region oder sogar eines Kontinents befinden.</span><span class="sxs-lookup"><span data-stu-id="e674e-136">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="e674e-137">In anderen Fällen können kleine Änderungen an Zahlen in einem Wählplan ausreichen, um Sie in anderen Wählplänen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e674e-137">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="e674e-138">Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.</span><span class="sxs-lookup"><span data-stu-id="e674e-138">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="e674e-139">Durch die Einführung eines Standardbenennungsschemas wird die Konsistenz in einer Organisation gewährleistet, und Wartungs-und Aktualisierungsvorgänge werden vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e674e-139">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="e674e-140">Entscheiden Sie, ob mehrere Wählpläne für einen einzelnen Standort erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e674e-140">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="e674e-141">Wenn Ihre Organisation einen einzelnen Wählplan über mehrere Standorte hinweg verwaltet, müssen Sie möglicherweise dennoch einen separaten Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer Nebenstellenanlage migrieren und die vorhandenen Erweiterungen beibehalten müssen.</span><span class="sxs-lookup"><span data-stu-id="e674e-141">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="e674e-142">Entscheiden Sie, ob benutzerspezifische Wählpläne erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e674e-142">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="e674e-143">Wenn Sie beispielsweise über Benutzer an einem Zweigstellenstandort verfügen, die beim zentralen Standort registriert sind oder wenn Sie über Benutzer verfügen, die in einem Survivable Branch Appliance registriert sind, können Sie spezielle Wähl Szenarien für solche Benutzer verwenden, die benutzerspezifische Wählpläne und Normalisierungsregeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="e674e-143">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="e674e-144">Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e674e-144">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="e674e-145">Bestimmen des Wähl planbereichs (wie zuvor in diesem Thema beschrieben).</span><span class="sxs-lookup"><span data-stu-id="e674e-145">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="e674e-146">Zum Erstellen eines Wählplans geben Sie bei Bedarf Werte in den folgenden Feldern an, indem Sie lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="e674e-146">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="e674e-147">Name und einfacher Name</span><span class="sxs-lookup"><span data-stu-id="e674e-147">Name and Simple Name</span></span>

<span data-ttu-id="e674e-148">Für Benutzer Wähl Pläne sollten Sie einen beschreibenden Namen angeben, der die Benutzer, Gruppen oder Kontaktobjekte identifiziert, denen der Wählplan zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e674e-148">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="e674e-149">Für Standortwählpläne wird das Feld Name mit dem Namen des Standorts vorausgefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-149">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="e674e-150">Bei Pool Wählplänen wird das Feld Name mit dem PSTN-Gateway oder Front-End-Pool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aufgefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-150">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="e674e-151">Der *einfache Name* des Wählplans wird mit einer Zeichenfolge aufgefüllt, die vom Namen des Wählplans abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="e674e-151">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="e674e-152">Das Feld einfacher Name ist bearbeitbar, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e674e-152">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="e674e-153">Der Wert des *einfachen namens* darf nicht leer sein und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e674e-153">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="e674e-154">Eine bewährte Methode besteht darin, eine Benennungskonvention für Ihre gesamte Organisation zu entwickeln und diese Konvention dann einheitlich für alle Websites und Benutzer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e674e-154">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="e674e-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e674e-155">Description</span></span>

<span data-ttu-id="e674e-156">Es wird empfohlen, den allgemeinen, erkennbaren Namen des geografischen Standorts einzugeben, auf den die entsprechenden Wähleinstellungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-156">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="e674e-157">Wenn der Name des Wählplans beispielsweise London.contoso.com lautet, lautet die empfohlene Beschreibung London.</span><span class="sxs-lookup"><span data-stu-id="e674e-157">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="e674e-158">Region für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="e674e-158">Dial-in Conferencing Region</span></span>

<span data-ttu-id="e674e-159">Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Einwahlkonferenz Region angeben, um Zugriffsnummern für Einwahlkonferenzen mit Wähleinstellungen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e674e-159">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="e674e-160">Präfix für externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="e674e-160">External Access Prefix</span></span>

<span data-ttu-id="e674e-161">Sie können ein externes Zugriffs Präfix mit bis zu vier Zeichen ( \# , \* und 0-9) angeben, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (beispielsweise 9) zum Abrufen einer externen Leitung wählen müssen.</span><span class="sxs-lookup"><span data-stu-id="e674e-161">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e674e-162">Wenn Sie ein externes Zugriffs Präfix angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix anzupassen.</span><span class="sxs-lookup"><span data-stu-id="e674e-162">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="e674e-163">Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="e674e-163">Normalization Rules</span></span>

<span data-ttu-id="e674e-164">Normalisierungsregeln definieren, wie Telefonnummern, die in verschiedenen Formaten ausgedrückt werden, für den benannten Standort weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e674e-164">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="e674e-165">Die gleiche Nummernzeichenfolge kann je nach Gebietsschema, aus dem Sie gewählt wird, unterschiedlich interpretiert und übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-165">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="e674e-166">Normalisierungsregeln sind für das Anrufrouting erforderlich, da Benutzer unterschiedliche Formate bei der Eingabe von Telefonnummern in ihren Kontaktlisten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e674e-166">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="e674e-167">Durch die Normalisierung der von Benutzern bereitgestellten Telefonnummern wird ein konsistentes Format bereitgestellt, das die folgenden Aufgaben unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e674e-167">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="e674e-168">Entspricht einer gewählten Nummer dem SIP-URI des beabsichtigten Empfängers.</span><span class="sxs-lookup"><span data-stu-id="e674e-168">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="e674e-169">Wenden Sie Wähl Autorisierungsregeln auf den anrufenden Teilnehmer an.</span><span class="sxs-lookup"><span data-stu-id="e674e-169">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="e674e-170">Die folgenden Zahlenfelder gehören zu denen, die ihre Normalisierungsregeln möglicherweise berücksichtigen müssen:</span><span class="sxs-lookup"><span data-stu-id="e674e-170">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="e674e-171">Wählplan</span><span class="sxs-lookup"><span data-stu-id="e674e-171">Dial plan</span></span>

  - <span data-ttu-id="e674e-172">Landeskennzahl</span><span class="sxs-lookup"><span data-stu-id="e674e-172">Country code</span></span>

  - <span data-ttu-id="e674e-173">Vorwahl</span><span class="sxs-lookup"><span data-stu-id="e674e-173">Area code</span></span>

  - <span data-ttu-id="e674e-174">Länge der Erweiterung</span><span class="sxs-lookup"><span data-stu-id="e674e-174">Length of extension</span></span>

  - <span data-ttu-id="e674e-175">Standortpräfix</span><span class="sxs-lookup"><span data-stu-id="e674e-175">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="e674e-176">Erstellen von Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="e674e-176">Creating Normalization Rules</span></span>

<span data-ttu-id="e674e-177">Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um numerische Übereinstimmungsmuster anzugeben, die der Server verwendet, um Wählzeichenfolgen in das E. 164-Format zu übersetzen, um eine umgekehrte Nummernsuche durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="e674e-177">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="e674e-178">Normalisierungsregeln werden im lync Server-Systemsteuerung entweder durch manuelles Eingeben der Ausdrücke oder durch Eingeben der Start Ziffern und der Länge der zu entgegen gebenden Wählzeichenfolgen und dem lync Server-Systemsteuerung generieren des entsprechenden regulären Ausdrucks für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="e674e-178">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="e674e-179">In beiden Fällen können Sie, wenn Sie fertig sind, eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e674e-179">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="e674e-180">Ausführliche Informationen zur Verwendung .NET Framework reguläre Ausdrücke finden Sie unter ".NET Framework reguläre Ausdrücke" unter [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="e674e-180">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="e674e-181">Beispiele für Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="e674e-181">Sample Normalization Rules</span></span>

<span data-ttu-id="e674e-182">Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als .NET Framework reguläre Ausdrücke geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e674e-182">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="e674e-183">Die Beispiele sind nur Beispiele und sollen keine normative Referenz für die Erstellung eigener Normalisierungsregeln sein.</span><span class="sxs-lookup"><span data-stu-id="e674e-183">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="e674e-184">Tabelle 1. Normalisierungsregeln, die .NET Framework reguläre Ausdrücke verwenden</span><span class="sxs-lookup"><span data-stu-id="e674e-184">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e674e-185">Regelname</span><span class="sxs-lookup"><span data-stu-id="e674e-185">Rule name</span></span></th>
<th><span data-ttu-id="e674e-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e674e-186">Description</span></span></th>
<th><span data-ttu-id="e674e-187">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="e674e-187">Number pattern</span></span></th>
<th><span data-ttu-id="e674e-188">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="e674e-188">Translation</span></span></th>
<th><span data-ttu-id="e674e-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e674e-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e674e-190">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="e674e-190">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="e674e-191">Übersetzt vierstellige Durchwahlnummern</span><span class="sxs-lookup"><span data-stu-id="e674e-191">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="e674e-192">^(\d{4})$</span><span class="sxs-lookup"><span data-stu-id="e674e-192">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-193">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-193">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-194">0100 wird in + 14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-194">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-195">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="e674e-195">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="e674e-196">Übersetzt fünfstellige Durchwahlnummern</span><span class="sxs-lookup"><span data-stu-id="e674e-196">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="e674e-197">^ 5 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="e674e-197">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-198">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-198">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-199">50100 wird in + 14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-199">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-200">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="e674e-200">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="e674e-201">Übersetzt 7-stellige Nummern in lokale Redmond-Nummern.</span><span class="sxs-lookup"><span data-stu-id="e674e-201">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="e674e-202">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="e674e-202">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-203">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-203">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-204">5550100 wird in + 14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-204">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-205">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="e674e-205">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="e674e-206">Übersetzt siebenstellige Nummern in lokale Dallas-Nummern</span><span class="sxs-lookup"><span data-stu-id="e674e-206">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="e674e-207">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="e674e-207">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-208">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-208">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-209">5550100 wird in + 19725550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-209">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-210">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="e674e-210">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="e674e-211">Übersetzt 10-stellige Zahlen in den USA</span><span class="sxs-lookup"><span data-stu-id="e674e-211">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="e674e-212">^(\d{10})$</span><span class="sxs-lookup"><span data-stu-id="e674e-212">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-213">+1$1</span><span class="sxs-lookup"><span data-stu-id="e674e-213">+1$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-214">2065550100 wird in + 12065550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-214">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-215">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="e674e-215">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="e674e-216">Übersetzt Nummern mit Präfixen für Ferngespräche in den Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="e674e-216">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="e674e-217">^ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="e674e-217">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-218">+ $1</span><span class="sxs-lookup"><span data-stu-id="e674e-218">+$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-219">12145550100 wird in + 2145550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-219">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-220">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="e674e-220">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="e674e-221">Übersetzt Nummern mit internationalen Präfixen in den Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="e674e-221">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="e674e-222">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="e674e-222">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="e674e-223">+ $1</span><span class="sxs-lookup"><span data-stu-id="e674e-223">+$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-224">01191445550100 wird in + 91445550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-224">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-225">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="e674e-225">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="e674e-226">Übersetzt 0 nach Redmond-Operator</span><span class="sxs-lookup"><span data-stu-id="e674e-226">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="e674e-227">↑ $0</span><span class="sxs-lookup"><span data-stu-id="e674e-227">^0$</span></span></p></td>
<td><p><span data-ttu-id="e674e-228">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="e674e-228">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="e674e-229">0 wird in + 14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-229">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-230">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e674e-230">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="e674e-231">Übersetzt Nummern mit on-net prefix (6) und Redmond Site Code (222)</span><span class="sxs-lookup"><span data-stu-id="e674e-231">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="e674e-232">^ 6222 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="e674e-232">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-233">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-233">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-234">62220100 wird in + 14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-234">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-235">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e674e-235">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="e674e-236">Übersetzt Nummern mit on-net prefix (6) und NY Site Code (333)</span><span class="sxs-lookup"><span data-stu-id="e674e-236">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="e674e-237">^ 6333 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="e674e-237">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-238">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-238">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-239">63330100 wird in + 12025550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-239">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-240">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e674e-240">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="e674e-241">Übersetzt Nummern mit on-net prefix (6) und Dallas Site Code (444)</span><span class="sxs-lookup"><span data-stu-id="e674e-241">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="e674e-242">^ 6444 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="e674e-242">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="e674e-243">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="e674e-243">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="e674e-244">64440100 wird in + 19725550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="e674e-244">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e674e-245">Die folgende Tabelle zeigt einen beispielhaften Wählplan für Redmond, Washington, USA, basierend auf den Normalisierungsregeln in der vorherigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e674e-245">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="e674e-246">Tabelle 2.</span><span class="sxs-lookup"><span data-stu-id="e674e-246">Table 2.</span></span> <span data-ttu-id="e674e-247">Auf der Grundlage von Normalisierungsregeln in Tabelle 1 angezeigte Redmond-Wähleinstellungen</span><span class="sxs-lookup"><span data-stu-id="e674e-247">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e674e-248">Redmond. FQDN festgelegt</span><span class="sxs-lookup"><span data-stu-id="e674e-248">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e674e-249">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="e674e-249">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-250">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="e674e-250">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-251">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="e674e-251">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-252">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="e674e-252">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-253">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e674e-253">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-254">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e674e-254">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e674e-255">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e674e-255">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e674e-256">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="e674e-256">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e674e-257">Die Namen der Normalisierungsregeln, die in der obigen Tabelle angezeigt werden, enthalten keine Leerzeichen, dies ist jedoch eine Frage der Wahl.</span><span class="sxs-lookup"><span data-stu-id="e674e-257">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="e674e-258">Der erste Name in der Tabelle könnte beispielsweise als "5-stellige Durchwahl" oder "5-stellige Durchwahlnummer" geschrieben worden sein und trotzdem gültig sein.</span><span class="sxs-lookup"><span data-stu-id="e674e-258">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

