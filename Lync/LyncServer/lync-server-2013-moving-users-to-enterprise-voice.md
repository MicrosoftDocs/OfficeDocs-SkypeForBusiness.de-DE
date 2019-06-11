---
title: 'Lync Server 2013: Verschieben von Benutzern zu Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="65501-102">Verschieben von Benutzern zu Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65501-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65501-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="65501-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="65501-104">Wenn Sie Benutzer aus einer vorhandenen PBX-Telefonie-Infrastruktur in Enterprise-VoIP verschieben, enthält der Bereitstellungsprozess einige Schritte, die nicht Teil des Planungsprozesses sind, der in der [Planung für Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md)bereits beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="65501-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="65501-105">Informationen zum Migrieren von Benutzern aus einer früheren Enterprise-VoIP-Bereitstellung finden Sie in den Migrations Dokumenten, die in Ihren Installationsmedien enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="65501-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="65501-106">Der Vorgang zum Verschieben von Benutzern aus einer vorhandenen Telefonie-Infrastruktur in Enterprise-VoIP umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="65501-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="65501-107">Primäre Telefonnummern festlegen</span><span class="sxs-lookup"><span data-stu-id="65501-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="65501-108">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="65501-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="65501-109">Vorbereiten von Wählplänen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="65501-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="65501-110">Planen von Benutzer VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="65501-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="65501-111">Planen Sie Anrufrouten.</span><span class="sxs-lookup"><span data-stu-id="65501-111">Plan call routes.</span></span>

6.  <span data-ttu-id="65501-112">Konfigurieren Sie die Telefonanlage oder den SIP-Trunk, um Anrufe für für Enterprise-VoIP aktivierte Benutzer neu zu leiten.</span><span class="sxs-lookup"><span data-stu-id="65501-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="65501-113">Verschieben von Benutzern in Exchange Unified Messaging (um) (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="65501-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="65501-114">In diesem Thema wird die Planung beschrieben, die für jeden dieser Schritte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="65501-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="65501-115">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="65501-115">Step 1.</span></span> <span data-ttu-id="65501-116">Festlegen von primären Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="65501-116">Designate primary phone numbers</span></span>

<span data-ttu-id="65501-117">Enterprise-VoIP integriert Sprache mit anderen Nachrichtenmedien, so dass der Server die Nummer dem SIP-URI des Benutzers zuordnet und dann den Anruf an alle Clientendpunkte abzweigt, die diesem SIP-URI zugeordnet sind, wenn ein eingehender Anruf am Server eintrifft.</span><span class="sxs-lookup"><span data-stu-id="65501-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="65501-118">Für diesen Vorgang muss jeder Benutzer einer primären Telefonnummer zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="65501-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="65501-119">Eine primäre Telefonnummer muss sein:</span><span class="sxs-lookup"><span data-stu-id="65501-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="65501-120">Global eindeutig oder, im Fall interner Erweiterungen, eindeutig im Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="65501-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="65501-121">Im Unternehmen im Besitz von und routingfähig.</span><span class="sxs-lookup"><span data-stu-id="65501-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="65501-122">Persönliche Nummern sollten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65501-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="65501-123">Für Unternehmensbenutzer können in den Active Directory-Domänendiensten zwei oder mehr Telefonnummern aufgelistet sein.</span><span class="sxs-lookup"><span data-stu-id="65501-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="65501-124">Alle Telefonnummern, die einem bestimmten Benutzer zugeordnet sind, können im Eigenschaftenfenster für diesen Benutzer im Snap-in Active Directory-Benutzer und-Computer angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="65501-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="65501-125">Das Feld " **Telefonnummer** " auf der Registerkarte " **Allgemein** " im Dialogfeld " **Benutzereigenschaften** " sollte die Haupt Arbeitsnummer des Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="65501-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="65501-126">Diese Nummer wird normalerweise als primäre Telefonnummer des Benutzers angegeben.</span><span class="sxs-lookup"><span data-stu-id="65501-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="65501-127">Einige Benutzer haben möglicherweise besondere Anforderungen (beispielsweise eine Führungskraft, die alle eingehenden Anrufe über einen administrativen Assistenten weiterleiten möchte), diese Ausnahmen sollten jedoch nur auf diejenigen begrenzt werden, in denen der Bedarf klar und kritisch ist.</span><span class="sxs-lookup"><span data-stu-id="65501-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="65501-128">Nachdem eine primäre Nummer ausgewählt wurde, muss Sie wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="65501-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="65501-129">Im E. 164-Format normalisiert, wo immer dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="65501-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="65501-130">In das Active Directory **-Attribut msRTCSIP-** Attribut kopiert.</span><span class="sxs-lookup"><span data-stu-id="65501-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65501-131"><STRONG>Mit Remoteanrufsteuerung (RCC) vorhanden</STRONG></span><span class="sxs-lookup"><span data-stu-id="65501-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="65501-132">RCC ist die Möglichkeit, lync Server zum Überwachen und Steuern eines Desktop-PBX-Telefons zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="65501-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="65501-133">Die Steuerung wird über den Server weitergeleitet, der als Gateway zur Telefonanlage fungiert.</span><span class="sxs-lookup"><span data-stu-id="65501-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="65501-134">Obwohl Sie keinen Benutzer für RCC und Enterprise-VoIP konfigurieren können, wird in beiden Fällen die Einstellung für den Leitungs-URI für die primäre Telefonnummer eines Benutzers bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="65501-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="65501-135">Wenn Sie über eine vorhandene PBX-Infrastruktur verfügen, die von ausgewählten Benutzern weiterhin verwendet werden soll, können Sie Enterprise-VoIP schrittweise in Ihre Organisation einführen.</span><span class="sxs-lookup"><span data-stu-id="65501-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="65501-136">Details zu diesem Bereitstellungsszenario finden Sie unter <A href="lync-server-2013-direct-sip-deployment-options.md">direkte SIP-Bereitstellungsoptionen in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="65501-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="65501-137">In früheren Versionen konnten Sie sowohl RCC als auch Enterprise-VoIP für einen Benutzer aktivieren, jedoch nur, wenn Sie den Benutzer auch für die Duale Verzweigung konfiguriert haben, ein Feature, bei dem ein eingehender Anruf die Telefonanlage und den Communicator eines Benutzers gleichzeitig klingelt.</span><span class="sxs-lookup"><span data-stu-id="65501-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="65501-138">In lync Server 2010 wird Dual-Forking nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65501-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="65501-139">Es gibt drei Methoden zum Auffüllen des **Attribut msRTCSIP-** Attributs:</span><span class="sxs-lookup"><span data-stu-id="65501-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="65501-140">Microsoft Identity Integration Server (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="65501-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="65501-141">Seite ' **Benutzer** ' in der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="65501-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="65501-142">Wo viele Telefonnummern verarbeitet werden müssen, ist ein von Ihrer Organisation entwickeltes benutzerdefiniertes Skript die bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="65501-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="65501-143">Je nachdem, wie Ihre Organisation Telefonnummern in den Active Directory-Domänendiensten darstellt, muss das Skript die primären Telefonnummern möglicherweise im E. 164-Format normalisieren, bevor Sie Sie in das **Attribut msRTCSIP-** Attribut kopieren.</span><span class="sxs-lookup"><span data-stu-id="65501-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="65501-144">Wenn in Ihrer Organisation alle Telefonnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden und das Format E. 164 ist, muss für Ihr Skript nur jede primäre Telefonnummer in das **Attribut msRTCSIP-** Attribut geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="65501-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="65501-145">Wenn in Ihrer Organisation alle Telefonnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden, das Format aber nicht E. 164 ist, sollte Ihr Skript eine geeignete Normalisierungsregel definieren, um primäre Telefonnummern aus Ihrem vorhandenen Format zu konvertieren. an E. 164, bevor Sie Sie in das **Attribut msRTCSIP-** Attribut schreiben.</span><span class="sxs-lookup"><span data-stu-id="65501-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="65501-146">Wenn in Ihrer Organisation kein Standardformat für Telefonnummern in den Active Directory-Domänendiensten erzwungen wird, sollte Ihr Skript geeignete Normalisierungsregeln definieren, um primäre Telefonnummern aus ihren unterschiedlichen Formaten in die E. 164-Konformität zu konvertieren, bevor Schreiben der primären Telefonnummern in das **Attribut msRTCSIP-** Attribut.</span><span class="sxs-lookup"><span data-stu-id="65501-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="65501-147">Ihr Skript muss auch das Präfix **Tel:** vor jeder primären Nummer einfügen, bevor es in das **Attribut msRTCSIP-** Attribut geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="65501-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="65501-148">Das erwartete Format der in diesem Attribut angegebenen Zahl lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="65501-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="65501-149">Tel: + 14255550100 übersetzt.; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="65501-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="65501-150">Tel: 5550100 (für eindeutige Enterprise Wide-Erweiterungen)</span><span class="sxs-lookup"><span data-stu-id="65501-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="65501-151">Die vom Adressbuchdienst (ABS) durchgeführte Normalisierung ersetzt oder beseitigt nicht die Notwendigkeit, die primäre Telefonnummer jedes Benutzers in Active Directory-Domänendiensten zu normalisieren, da ABS keinen Zugriff auf Active Directory-Domänendienste hat und Deshalb können keine primär Nummern in das <STRONG>Attribut msRTCSIP-</STRONG> Attribut kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="65501-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="65501-152">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="65501-152">Step 2.</span></span> <span data-ttu-id="65501-153">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="65501-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="65501-154">Außer der Identifizierung, welche Benutzer aktiviert werden sollen, ist keine spezielle Planung erforderlich, um diesen Schritt ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="65501-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="65501-155">Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="65501-155">Step 3.</span></span> <span data-ttu-id="65501-156">Vorbereiten von Wählplänen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="65501-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="65501-157">Benutzer, die für Enterprise-VoIP aktiviert sind, können keine Anrufe an das PSTN vornehmen, ohne dass Wählpläne vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="65501-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="65501-158">Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="65501-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="65501-159">Normalisierungsregeln definieren, wie Telefonnummern, die in verschiedenen Formaten ausgedrückt werden, für jeden angegebenen Speicherort, Benutzer oder Kontaktobjekt weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="65501-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="65501-160">Informationen zum Vorbereiten von Wählplänen finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="65501-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="65501-161">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="65501-161">Step 4.</span></span> <span data-ttu-id="65501-162">Planen von Richtlinien für Benutzer VoIP</span><span class="sxs-lookup"><span data-stu-id="65501-162">Plan user voice policies</span></span>

<span data-ttu-id="65501-163">Benutzer-Service-Einstellungen auf einer Legacy-Telefonanlage, wie etwa das Recht, Fern-oder Auslandsgespräche über Unternehmens Telefone zu führen, müssen als VoIP-Richtlinien für Benutzer neu konfiguriert werden, die in Enterprise-VoIP verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="65501-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="65501-164">Details zum Planen und Erstellen von Richtlinien für Enterprise-VoIP finden Sie unter [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="65501-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="65501-165">Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="65501-165">Step 5.</span></span> <span data-ttu-id="65501-166">Planen von ausgehenden Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="65501-166">Plan outbound call routes</span></span>

<span data-ttu-id="65501-167">Anrufrouten geben an, wie lync Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt.</span><span class="sxs-lookup"><span data-stu-id="65501-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="65501-168">Wenn ein Benutzer eine Nummer wählt, normalisiert der Server bei Bedarf die Wählzeichenfolge in das E. 164-Format und versucht, Sie mit einem SIP-URI zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="65501-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="65501-169">Wenn der Server nicht in der Lage ist, die Übereinstimmung zu erreichen, wendet er die Routinglogik für ausgehende Anrufe basierend auf der Nummer an.</span><span class="sxs-lookup"><span data-stu-id="65501-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="65501-170">Der letzte Schritt beim Definieren dieser Logik ist das Erstellen einer separaten benannten Anrufroute für jede Gruppe von Zielrufnummern, die in den einzelnen Wähleinstellungen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="65501-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="65501-171">Details zum Planen von Anrufrouten finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="65501-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="65501-172">Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="65501-172">Step 6.</span></span> <span data-ttu-id="65501-173">Konfigurieren von Telefonanlagen oder SIP-Stämmen zum Umleiten von Anrufen für Enterprise-VoIP-Benutzer</span><span class="sxs-lookup"><span data-stu-id="65501-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="65501-174">Benutzer, die früher in einer traditionellen Telefonanlage oder auf einer SIP-Trunk-Verbindung mit einem Internet-Telefoniedienstanbieter (ITSP) gehostet wurden, behalten ihre Telefonnummern nach dem Umzug.</span><span class="sxs-lookup"><span data-stu-id="65501-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="65501-175">Die einzige Voraussetzung ist, dass nach dem Umzug die Telefonanlage oder der SIP-Stamm neu konfiguriert werden muss, um eingehende Anrufe an Enterprise-VoIP-Benutzer an den Vermittlungs Server weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="65501-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="65501-176">Schritt 7.</span><span class="sxs-lookup"><span data-stu-id="65501-176">Step 7.</span></span> <span data-ttu-id="65501-177">Verschieben von Benutzern in Exchange Unified Messaging (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="65501-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="65501-178">Das Verschieben von Benutzern in Exchange Unified Messaging umfasst die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="65501-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="65501-179">Konfigurieren Sie Exchange Unified Messaging und lync Server für die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="65501-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="65501-180">Aktivieren von Benutzern für Exchange Unified Messaging-Anrufbeantwortung und Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="65501-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="65501-181">Diese Aufgabe wird auf dem Exchange Unified Messaging-Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65501-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="65501-182">Ausführliche Informationen finden Sie in [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)der TechNet-Bibliothek für Exchange Server 2010 unter.</span><span class="sxs-lookup"><span data-stu-id="65501-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

