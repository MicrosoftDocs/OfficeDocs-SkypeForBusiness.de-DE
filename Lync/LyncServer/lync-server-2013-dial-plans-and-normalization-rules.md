---
title: 'Lync Server 2013: Wählpläne und Normalisierungsregeln'
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
ms.openlocfilehash: d4f1cc8221281502487a8f58e1562674432ea29d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="cf1a3-102">Wählpläne und Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf1a3-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf1a3-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cf1a3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cf1a3-104">Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="cf1a3-p101">Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für benannte Standorte, Benutzer oder Kontaktobjekte. Ein und dieselbe Wählzeichenfolge kann je nach dem Standort, an dem sie gewählt wurde, und je nach der anrufenden Person bzw. dem anrufenden Kontaktobjekt unterschiedlich interpretiert und übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p101">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="cf1a3-107">Wählplanbereich</span><span class="sxs-lookup"><span data-stu-id="cf1a3-107">Dial Plan Scope</span></span>

<span data-ttu-id="cf1a3-108">Der *Bereich* eines Wählplans bestimmt die Hierarchieebene, auf der der Wählplan angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="cf1a3-109">In lync Server kann einem Benutzer ein bestimmter benutzerspezifischer Wählplan zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="cf1a3-110">Wenn kein Benutzer Wählplan zugewiesen ist, wird der Wählplan für den Registrar-Pool angewendet.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="cf1a3-111">Wenn kein Wählplan für den Registrar-Pool vorhanden ist, wird der Standort Wähl Plan angewendet.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="cf1a3-112">Wenn für den Benutzer keine bestimmten Wählpläne gelten, wird der globale Wählplan angewendet.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="cf1a3-113">Clients erhalten Wähl Plan-Bereichsebenen über in-Band-Bereitstellungseinstellungen, die bereitgestellt werden, wenn sich Benutzer bei lync Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="cf1a3-114">Als Administrator können Sie die Bereichsebenen für Wähleinstellungen mithilfe der lync Server-Systemsteuerung verwalten und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf1a3-115">Der PSTN-Gateway-Wählplan auf Dienstebene wird auf eingehende Anrufe von einem bestimmten Gateway angewendet.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="cf1a3-116">Bereichsebenen für Wählpläne werden wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="cf1a3-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="cf1a3-117">**Benutzerwähleinstellungen:** Kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="cf1a3-118">Sprachanwendungen können einen Wählplan pro Benutzer suchen und verwenden, wenn für „phone-context“ der Wert „user-default“ empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="cf1a3-119">Damit ein Wählplan zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="cf1a3-120">**Pool-Wählplan:** Kann auf Dienstebene für alle PSTN-Gateways oder Registrierungsstellen in Ihrer Topologie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="cf1a3-121">Zum Definieren eines Poolwählplans müssen Sie den Dienst (PSTN-Gateway oder Registrierungsstellenpool) angeben, auf den der Wählplan angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="cf1a3-122">**Website Wähl Plan:** Kann für eine gesamte Website erstellt werden, mit Ausnahme von Benutzern, Gruppen oder Kontaktobjekten, denen ein Pool-Wählplan oder Benutzer Wähl Plan zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="cf1a3-123">Zum Definieren eines Standortwählplans müssen Sie den Standort angeben, auf den der Wählplan angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="cf1a3-124">**Globaler Wählplan:** Der Standard-Wählplan, der mit dem Produkt installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="cf1a3-125">Sie können den globalen Wählplan bearbeiten, aber nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="cf1a3-126">Diese Wähleinstellungen gelten für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen einen Wählplan mit einem spezifischeren Bereich zu.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="cf1a3-127">Planen eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="cf1a3-127">Planning for Dial Plans</span></span>

<span data-ttu-id="cf1a3-128">Führen Sie folgende Schritte aus, um einen Wählplan zu planen:</span><span class="sxs-lookup"><span data-stu-id="cf1a3-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="cf1a3-129">Listen Sie alle Standorte auf, an denen sich eine Niederlassung Ihrer Organisation befindet.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="cf1a3-p108">Die Liste muss aktuell und vollständig sein. Sie muss immer wieder überprüft werden, wenn sich die Unternehmensorganisation weiterentwickelt. Bei einem großen internationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann diese Aufgabe sehr zeitaufwendig sein.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p108">The list must be up-to-date and complete. It will need to be revised as company organization evolves. In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="cf1a3-133">Identifizieren Sie gültige Rufnummernmuster für jeden Standort.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="cf1a3-p109">Der zeitaufwendigste Teil der Planung von Wählplänen besteht darin, die gültigen Rufnummernmuster für jeden Standort zu identifizieren. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan erstellt haben, in einen anderen Wählplan kopieren, insbesondere dann, wenn sich die zugehörigen Standorte auf demselben Kontinent oder sogar im selben Land bzw. in derselben Region befinden. In anderen Fällen genügt es möglicherweise, die Rufnummern in einem Wählplan geringfügig zu ändern, um sie auch in anderen Wählplänen verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="cf1a3-137">Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="cf1a3-138">Das Erstellen eines Standardbenennungsschemas stellt die Konsistenz innerhalb der gesamten Organisation sicher und vereinfacht Wartung und Updates.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="cf1a3-139">Entscheiden Sie, ob für einen einzelnen Standort mehrere Wählpläne erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="cf1a3-140">Wenn in Ihrer Organisation ein einzelner Wählplan an mehreren Standorten verwaltet wird, müssen Sie möglicherweise dennoch einen separaten Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer PBX-Anlage (Private Branch Exchange) migrieren und deren vorhandene Erweiterungen beibehalten werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="cf1a3-141">Entscheiden Sie, ob Wählpläne auf Benutzerebene erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="cf1a3-142">Wenn Sie beispielsweise über Benutzer an einer Zweigstelle verfügen, die bei der zentralen Website registriert sind, oder wenn Sie über Benutzer verfügen, die auf einer überlebensfähigen Branch-Appliance registriert sind, können Sie spezielle Wähl Szenarien für diese Benutzer unter Verwendung von Wählplänen und Normalisierungsregeln für einzelne Benutzer in Frage stellen. .</span><span class="sxs-lookup"><span data-stu-id="cf1a3-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="cf1a3-143">Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit von Zweigstellen für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf1a3-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="cf1a3-144">Ermitteln Sie den Bereich für den Wählplan (wie weiter oben in diesem Thema beschrieben).</span><span class="sxs-lookup"><span data-stu-id="cf1a3-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="cf1a3-145">Zum Erstellen eines Wählplans geben Sie bei Bedarf Werte in den folgenden Feldern mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell an.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="cf1a3-146">Name und einfacher Name</span><span class="sxs-lookup"><span data-stu-id="cf1a3-146">Name and Simple Name</span></span>

<span data-ttu-id="cf1a3-147">Bei Benutzerwählplänen sollten Sie einen beschreibenden Namen für die Benutzer, Gruppen oder Kontaktobjekte angeben, denen der Wählplan zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="cf1a3-148">Bei Website Wählplänen ist das Feld Name mit dem Websitenamen gefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="cf1a3-149">Für Pool-Wählpläne ist das Feld "Name" mit dem PSTN-Gateway oder dem Front-End-Pool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) gefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="cf1a3-150">Der *einfache Name* des Wählplans ist mit einer Zeichenfolge gefüllt, die vom Namen des Wählplans abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="cf1a3-151">Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="cf1a3-152">Der Wert *Einfacher Name* darf nicht leer und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="cf1a3-153">Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="cf1a3-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf1a3-154">Description</span></span>

<span data-ttu-id="cf1a3-p113">Es wird empfohlen, den allgemeinen, wiedererkennbaren Namen des geografischen Standorts einzugeben, auf den der entsprechende Wählplan angewendet wird. Wenn der Name des Wählplans beispielsweise „London.Contoso.com“ lautet, wird für die Beschreibung der Eintrag „London“ empfohlen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="cf1a3-157">Region für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="cf1a3-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="cf1a3-158">Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Region angeben, um die Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="cf1a3-159">Vorwahl für externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="cf1a3-159">External Access Prefix</span></span>

<span data-ttu-id="cf1a3-160">Sie können ein externes Zugriffs Präfix mit bis zu vier Zeichen (\#, \*und 0-9) angeben, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (beispielsweise 9) wählen müssen, um eine externe Leitung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf1a3-161">Wenn Sie eine Vorwahl für den externen Zugriff eingeben, müssen Sie keine zusätzliche Normalisierungsregeln zur Unterstützung der Vorwahl erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="cf1a3-162">Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="cf1a3-162">Normalization Rules</span></span>

<span data-ttu-id="cf1a3-p114">Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort. Ein und dieselbe numerische Zeichenfolge wird möglicherweise unterschiedlich interpretiert und übersetzt, je nachdem, von welchem Standort aus sie gewählt wird. Normalisierungsregeln sind für das Anrufrouting notwendig, da Benutzer Rufnummern in unterschiedlichen Formaten in ihre Kontaktlisten eingeben.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p114">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="cf1a3-166">Die Normalisierung der von Benutzern eingegebenen Rufnummern stellt ein konsistentes Format bereit, das folgende Aufgaben vereinfacht:</span><span class="sxs-lookup"><span data-stu-id="cf1a3-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="cf1a3-167">Zuordnen einer gewählten Rufnummer zum SIP-URI des gewünschten Empfängers</span><span class="sxs-lookup"><span data-stu-id="cf1a3-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="cf1a3-168">Anwenden von Wählautorisierungsregeln auf den Anrufer</span><span class="sxs-lookup"><span data-stu-id="cf1a3-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="cf1a3-169">In Normalisierungsregeln müssen möglicherweise die folgenden numerischen Felder berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="cf1a3-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="cf1a3-170">Wählplan</span><span class="sxs-lookup"><span data-stu-id="cf1a3-170">Dial plan</span></span>

  - <span data-ttu-id="cf1a3-171">Landesvorwahl</span><span class="sxs-lookup"><span data-stu-id="cf1a3-171">Country code</span></span>

  - <span data-ttu-id="cf1a3-172">Ortsvorwahl</span><span class="sxs-lookup"><span data-stu-id="cf1a3-172">Area code</span></span>

  - <span data-ttu-id="cf1a3-173">Länge der Durchwahlnummer</span><span class="sxs-lookup"><span data-stu-id="cf1a3-173">Length of extension</span></span>

  - <span data-ttu-id="cf1a3-174">Standortvorwahl</span><span class="sxs-lookup"><span data-stu-id="cf1a3-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="cf1a3-175">Erstellen von Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="cf1a3-175">Creating Normalization Rules</span></span>

<span data-ttu-id="cf1a3-176">Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="cf1a3-177">Sie können Normalisierungsregeln in der lync Server-Systemsteuerung erstellen, indem Sie die Ausdrücke manuell eingeben, oder indem Sie die Anfangsziffern und die Länge der zu entgleichenden Wählzeichenfolgen eingeben und die lync Server-Systemsteuerung die entsprechenden regulärer Ausdruck für Sie.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="cf1a3-178">Unabhängig davon, welche Methode Sie anwenden, können Sie anschließend eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="cf1a3-179">Ausführliche Informationen zur Verwendung von regulären Ausdrücken in [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework finden Sie unter ".NET Framework-reguläre Ausdrücke" unter.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="cf1a3-180">Beispiele für Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="cf1a3-180">Sample Normalization Rules</span></span>

<span data-ttu-id="cf1a3-p116">Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre .NET Framework-Ausdrücke formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer Normalisierungsregeln dar.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="cf1a3-183">Tabelle 1: Normalisierungsregeln mit regulären .NET Framework-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="cf1a3-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="cf1a3-184">Regelname</span><span class="sxs-lookup"><span data-stu-id="cf1a3-184">Rule name</span></span></th>
<th><span data-ttu-id="cf1a3-185">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf1a3-185">Description</span></span></th>
<th><span data-ttu-id="cf1a3-186">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="cf1a3-186">Number pattern</span></span></th>
<th><span data-ttu-id="cf1a3-187">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="cf1a3-187">Translation</span></span></th>
<th><span data-ttu-id="cf1a3-188">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf1a3-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="cf1a3-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-190">Übersetzt vierstellige Durchwahlnummern</span><span class="sxs-lookup"><span data-stu-id="cf1a3-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-192">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-193">0100 wird in +14255550100 übersetzt.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="cf1a3-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-195">Übersetzt fünfstellige Durchwahlnummern</span><span class="sxs-lookup"><span data-stu-id="cf1a3-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-197">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-198">50100 wird in +14255550100 übersetzt.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="cf1a3-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-200">Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond</span><span class="sxs-lookup"><span data-stu-id="cf1a3-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-202">+1425$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-203">5550100 wird in +14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="cf1a3-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-205">Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Dallas</span><span class="sxs-lookup"><span data-stu-id="cf1a3-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-207">+1972$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-208">5550100 wird in +19725550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="cf1a3-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-210">Übersetzt zehnstellige Rufnummern in US-Rufnummern</span><span class="sxs-lookup"><span data-stu-id="cf1a3-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-212">+1$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-213">2065550100 wird in +12065550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="cf1a3-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-215">Übersetzt Rufnummern mit Vorwahlen für Ferngespräche in US-Rufnummern</span><span class="sxs-lookup"><span data-stu-id="cf1a3-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-217">+$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-218">12145550100 wird in +2145550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="cf1a3-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-220">Übersetzt Rufnummern mit internationalen Vorwahlen in US-Rufnummern</span><span class="sxs-lookup"><span data-stu-id="cf1a3-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-221">^011(\d\*)$</span><span class="sxs-lookup"><span data-stu-id="cf1a3-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-222">+$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-223">01191445550100 wird in +91445550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="cf1a3-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-225">Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond</span><span class="sxs-lookup"><span data-stu-id="cf1a3-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-226">^0$</span><span class="sxs-lookup"><span data-stu-id="cf1a3-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-227">+14255550100</span><span class="sxs-lookup"><span data-stu-id="cf1a3-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-228">0 wird in +14255550100 übersetzt.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="cf1a3-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-230">Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="cf1a3-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-232">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-233">62220100 wird in +14255550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="cf1a3-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-235">Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von New York (333)</span><span class="sxs-lookup"><span data-stu-id="cf1a3-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-237">+1202555$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-238">63330100 wird in +12025550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="cf1a3-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-240">Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Dallas-Vorwahl (444)</span><span class="sxs-lookup"><span data-stu-id="cf1a3-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="cf1a3-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-242">+1972555$1</span><span class="sxs-lookup"><span data-stu-id="cf1a3-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="cf1a3-243">64440100 wird in +19725550100 übersetzt</span><span class="sxs-lookup"><span data-stu-id="cf1a3-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf1a3-244">Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="cf1a3-p117">Tabelle 2: Wählplan für Redmond, basierend auf den in Tabelle 1 gezeigten Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf1a3-247">Redmond.forestFQDN</span><span class="sxs-lookup"><span data-stu-id="cf1a3-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="cf1a3-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="cf1a3-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="cf1a3-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="cf1a3-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="cf1a3-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="cf1a3-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf1a3-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="cf1a3-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf1a3-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="cf1a3-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="cf1a3-p118">Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen, aber dies ist nicht obligatorisch. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet.</span><span class="sxs-lookup"><span data-stu-id="cf1a3-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

