---
title: 'Lync Server 2013: Verschieben von Benutzern zu Enterprise-VoIP'
description: 'Lync Server 2013: Verschieben von Benutzern zu Enterprise-VoIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542011"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d0899-103">Verschieben von Benutzern zu Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0899-103">Moving users to Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0899-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d0899-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d0899-105">Wenn Sie Benutzer von einer vorhandenen PBX-Telefonie-Infrastruktur zu Enterprise-VoIP verschieben, enthält der Bereitstellungsprozess einige Schritte, die nicht Teil des Planungsprozesses sind, der bereits unter [Planning for Enterprise Voice in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md)beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="d0899-105">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="d0899-106">Informationen zur Migration von Benutzern aus einer früheren Enterprise-VoIP-Bereitstellung finden Sie in den Migrationsdokumenten, die den Installationsdatenträgern beiliegen.</span><span class="sxs-lookup"><span data-stu-id="d0899-106">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="d0899-107">Um Benutzer von einer vorhandenen Telefonieinfrastruktur zu Enterprise-VoIP zu migrieren, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d0899-107">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="d0899-108">Festlegen primärer Rufnummern</span><span class="sxs-lookup"><span data-stu-id="d0899-108">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="d0899-109">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d0899-109">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="d0899-110">Vorbereiten von Wähleinstellungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d0899-110">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="d0899-111">Planen von VoIP-Richtlinien für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d0899-111">Plan user voice policies.</span></span>

5.  <span data-ttu-id="d0899-112">Planen von Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="d0899-112">Plan call routes.</span></span>

6.  <span data-ttu-id="d0899-113">Konfigurieren der Nebenstellenanlage oder des SIP-Trunks zum Umleiten von Anrufen für Benutzer mit Enterprise-VoIP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="d0899-113">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="d0899-114">Benutzer zu Exchange Unified Messaging (um) umstellen (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="d0899-114">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="d0899-115">In diesem Thema wird beschrieben, welche Planungsaufgaben für jeden dieser Schritte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d0899-115">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="d0899-p102">Schritt 1: Festlegen primärer Rufnummern</span><span class="sxs-lookup"><span data-stu-id="d0899-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="d0899-p103">Enterprise VoIP integriert die Sprachtelefonie mit anderen Messagingmedien. Wenn also ein Anruf am Server eingeht, ordnet der Server die Rufnummer dem SIP-URI des Benutzers zu und verzweigt den Anruf dann an alle Clientendpunkte, die diesem SIP-URI zugeordnet sind. Für diesen Prozess muss jedem Benutzer eine primäre Rufnummer zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="d0899-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="d0899-120">Eine primäre Rufnummer muss folgende Eigenschaften aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d0899-120">A primary phone number must be:</span></span>

  - <span data-ttu-id="d0899-121">Sie muss global eindeutig oder (im Fall interner Durchwahlen) innerhalb des Unternehmens eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="d0899-121">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="d0899-p104">Sie muss im Besitz des Unternehmens sein und innerhalb des Unternehmens weitergeleitet werden können. Persönliche Rufnummern sollten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0899-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="d0899-124">Für Enterprise-Benutzer können in Active Directory-Domänendienste zwei oder mehr Telefonnummern aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="d0899-124">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="d0899-125">Alle Rufnummern, die einem bestimmten Benutzer zugeordnet sind, können auf der Eigenschaftenseite für diesen Benutzer im Snap-In "Active Directory-Benutzer und -Computer" angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d0899-125">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="d0899-p106">Das Feld **Rufnummer** auf der Registerkarte **Allgemein** des Dialogfelds **Benutzereigenschaften** sollte die primäre geschäftliche Rufnummer des Benutzers enthalten. Diese Nummer wird normalerweise als primäre Rufnummer des Benutzers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d0899-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="d0899-128">Einige Benutzer stellen möglicherweise besondere Anforderungen (z. B. eine Führungskraft, für die alle eingehenden Anrufe über das Sekretariat weitergeleitet werden sollen). Solche Ausnahmen sollten jedoch auf Fälle beschränkt werden, in denen die Anforderung klar und wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="d0899-128">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="d0899-129">Nach der Auswahl einer primären Rufnummer müssen folgende Aktionen für diese durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d0899-129">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="d0899-130">Normalisierung in das E.164-Format (wenn möglich)</span><span class="sxs-lookup"><span data-stu-id="d0899-130">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="d0899-131">Kopieren in das Active Directory-Attribut **msRTCSIP-line**</span><span class="sxs-lookup"><span data-stu-id="d0899-131">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0899-132"><STRONG>Verwendung neben der Remoteanrufsteuerung (Remote Call Control, RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="d0899-132"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="d0899-133">RCC ist die Möglichkeit, lync Server zum Überwachen und Steuern eines Desktop-PBX-Telefons zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0899-133">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="d0899-134">Die Steuerung wird über den Server geleitet, der als Gateway zur Nebenstellenanlage dient.</span><span class="sxs-lookup"><span data-stu-id="d0899-134">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="d0899-135">Auch wenn Sie einen Benutzer nicht sowohl für RCC als auch für Enterprise-VoIP konfigurieren können, stellt die Einstellung für den Anschluss-URI in beiden Fällen die primäre Rufnummer eines Benutzers dar.</span><span class="sxs-lookup"><span data-stu-id="d0899-135">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="d0899-136">Wenn Sie über eine vorhandene PBX-Infrastruktur verfügen, die bestimmte Benutzer weiterhin verwenden sollen, können Sie Enterprise-VoIP stufenweise in Ihrer Organisation einführen.</span><span class="sxs-lookup"><span data-stu-id="d0899-136">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="d0899-137">Ausführliche Informationen zu diesem Bereitstellungsszenario finden Sie unter <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP Deployment Options in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d0899-137">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="d0899-138">In früheren Versionen konnten Sie sowohl RCC als auch Enterprise-VoIP für einen Benutzer aktivieren, allerdings nur, wenn Sie den Benutzer auch für die Duale Verzweigung konfiguriert haben, ein Feature, bei dem ein eingehender Anruf das Nebenstellentelefon und den Communicator eines Benutzers gleichzeitig klingelt.</span><span class="sxs-lookup"><span data-stu-id="d0899-138">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="d0899-139">In lync Server 2010 wird die Duale Verzweigung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0899-139">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="d0899-140">Das Attribut **msRTCSIP-line** kann auf drei Arten aufgefüllt werden:</span><span class="sxs-lookup"><span data-stu-id="d0899-140">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="d0899-141">Microsoft Identity Integration Server (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="d0899-141">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="d0899-142">Die Seite " **Benutzer** " im lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d0899-142">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="d0899-143">Wenn viele Telefonnummern verarbeitet werden müssen, ist ein von Ihrer Organisation entwickeltes Skript die bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="d0899-143">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="d0899-144">Abhängig davon, wie in Ihrer Organisation Rufnummern in den Active Directory-Domänendiensten (Active Directory Domain Services, AD DS) dargestellt werden, muss das Skript die primären Rufnummern möglicherweise in das E.164-Format übertragen, bevor es sie in das Attribut **msRTCSIP-line** kopiert.</span><span class="sxs-lookup"><span data-stu-id="d0899-144">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="d0899-145">Wenn in Ihrer Organisation alle Rufnummern in den Active Directory-Domänendiensten im E.164-Format verwaltet werden, muss Ihr Skript lediglich jede primäre Rufnummer in das Attribut **msRTCSIP-line** schreiben.</span><span class="sxs-lookup"><span data-stu-id="d0899-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="d0899-146">Wenn in Ihrer Organisation alle Rufnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden, dieses Format jedoch nicht E.164 ist, muss Ihr Skript eine entsprechende Normalisierungsregel definieren, mit der primäre Rufnummern aus ihrem vorhandenen Format in E.164 konvertiert werden können, bevor sie in das Attribut **msRTCSIP-line** geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d0899-146">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="d0899-147">Wenn Ihre Organisation kein Standardformat für Rufnummern in den Active Directory-Domänendiensten erzwingt, muss Ihr Skript geeignete Normalisierungsregeln definieren, mit denen primäre Rufnummern aus ihren unterschiedlichen Formaten in E.164 konvertiert werden können, bevor sie in das Attribut **msRTCSIP-line** geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d0899-147">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="d0899-148">In Ihrem Skript muss außerdem das Präfix **Tel:** vor jeder primären Rufnummer eingefügt werden, bevor diese Nummern in das Attribut **msRTCSIP-line** geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d0899-148">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="d0899-149">Folgendes Format wird für die in diesem Attribut angegebene Nummer erwartet:</span><span class="sxs-lookup"><span data-stu-id="d0899-149">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="d0899-150">Tel: + 14255550100 übersetzt; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="d0899-150">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="d0899-151">Tel:5550100 (für unternehmensweit eindeutige Durchwahlen)</span><span class="sxs-lookup"><span data-stu-id="d0899-151">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d0899-152">Trotz der vom Adressbuchdienst (Address Book Service, ABS) durchgeführten Normalisierung muss die primäre Rufnummer jedes Benutzers in den Active Directory-Domänendiensten normalisiert werden, da ABS über keinen Zugriff auf die Active Directory-Domänendienste verfügt und daher keine primären Rufnummern in das Attribut <STRONG>msRTCSIP-line</STRONG> kopieren kann.</span><span class="sxs-lookup"><span data-stu-id="d0899-152">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="d0899-p111">Schritt 2: Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d0899-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="d0899-155">In diesem Schritt muss lediglich identifiziert werden, für welche Benutzer Enterprise-VoIP aktiviert werden soll. Es ist keine besondere Planung notwendig.</span><span class="sxs-lookup"><span data-stu-id="d0899-155">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="d0899-p112">Schritt 3: Vorbereiten von Wähleinstellungen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d0899-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="d0899-p113">Benutzer, die für Enterprise-VoIP aktiviert sind, können ohne festgelegte Wähleinstellungen keine Anrufe an das PSTN tätigen. Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden. Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt.</span><span class="sxs-lookup"><span data-stu-id="d0899-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="d0899-161">Informationen zum Vorbereiten von Wählplänen finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="d0899-161">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="d0899-162">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="d0899-162">Step 4.</span></span> <span data-ttu-id="d0899-163">Planen von Benutzer VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d0899-163">Plan user voice policies</span></span>

<span data-ttu-id="d0899-164">Einstellungen für Benutzerdienstklassen auf vorhandenen Nebenstellenanlagen (wie das Recht, Auslands- oder Ferngespräche von einem Unternehmenstelefon aus zu führen) müssen für Benutzer, die zu Enterprise-VoIP migriert werden, als VoIP-Richtlinien neu konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d0899-164">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="d0899-165">Ausführliche Informationen zum Planen und Erstellen von Richtlinien für Enterprise-VoIP finden Sie unter [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d0899-165">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="d0899-166">Schritt 5:</span><span class="sxs-lookup"><span data-stu-id="d0899-166">Step 5.</span></span> <span data-ttu-id="d0899-167">Planen von Routen für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="d0899-167">Plan outbound call routes</span></span>

<span data-ttu-id="d0899-168">Anrufrouten geben an, wie lync Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt.</span><span class="sxs-lookup"><span data-stu-id="d0899-168">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="d0899-169">Wenn ein Benutzer eine Nummer wählt, normalisiert der Server bei Bedarf die Wählzeichenfolge in das E. 164-Format und versucht, Sie einem SIP-URI zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d0899-169">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="d0899-170">Wenn der Server die Übereinstimmung nicht herstellen kann, wendet er die Routinglogik für ausgehende Anrufe basierend auf der Nummer an.</span><span class="sxs-lookup"><span data-stu-id="d0899-170">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="d0899-171">Der letzte Schritt beim Definieren dieser Logik ist das Erstellen einer separaten benannten Anrufroute für jeden Satz von Zielrufnummern, die in den einzelnen Wähleinstellungen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d0899-171">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="d0899-172">Ausführliche Informationen zum Planen von Anrufrouten finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="d0899-172">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="d0899-173">Schritt 6:</span><span class="sxs-lookup"><span data-stu-id="d0899-173">Step 6.</span></span> <span data-ttu-id="d0899-174">Konfigurieren von PBX-oder SIP-Trunks für die Umleitung von Anrufen für Enterprise-VoIP-Benutzer</span><span class="sxs-lookup"><span data-stu-id="d0899-174">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="d0899-175">Benutzer, die früher in einer herkömmlichen Nebenstellenanlage oder einer SIP-Trunk Verbindung mit einem Internet Telefonie-Dienstanbieter (ITSP) gehostet wurden, behalten ihre Telefonnummern nach dem Wechsel bei.</span><span class="sxs-lookup"><span data-stu-id="d0899-175">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="d0899-176">Die einzige Voraussetzung ist, dass nach dem Wechsel die Nebenstellenanlage oder der SIP-Trunk neu konfiguriert werden muss, um eingehende Anrufe für Enterprise-VoIP-Benutzer an die Vermittlungsserver weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="d0899-176">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="d0899-p120">Schritt 7: Migrieren von Benutzern zu Exchange Unified Messaging (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="d0899-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="d0899-179">Um Benutzer zu Exchange Unified Messaging zu migrieren, ist das Ausführen der folgenden Aufgaben erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d0899-179">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="d0899-180">Konfigurieren von Exchange Unified Messaging und lync Server zur Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="d0899-180">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="d0899-181">Aktivieren von Exchange Unified Messaging-Mailboxansagen und Outlook Voice Access für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d0899-181">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="d0899-182">Diese Aufgabe wird auf dem Exchange Unified Messaging-Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0899-182">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="d0899-183">Ausführliche Informationen finden Sie in der Exchange Server 2010 TechNet-Bibliothek unter [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .</span><span class="sxs-lookup"><span data-stu-id="d0899-183">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

