---
title: 'Lync Server 2013: Starten von lync aus einer anderen Anwendung'
description: 'Lync Server 2013: Starten von lync aus einer anderen Anwendung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd64b8b9f335638b54a0bf6473b5d159c97a0e7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562701"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="62e95-103">Starten von lync aus einer anderen Anwendung</span><span class="sxs-lookup"><span data-stu-id="62e95-103">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e95-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="62e95-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="62e95-105">Sie können Befehlszeilenparameter verwenden, um lync 2013 schnell zu starten.</span><span class="sxs-lookup"><span data-stu-id="62e95-105">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="62e95-106">Wenn ein Benutzer beispielsweise auf eine Telefonnummer in einer anderen Anwendung klickt, kann die Anwendung eine Instanz von lync 2013 starten und einen Anruf an diese Nummer initiieren.</span><span class="sxs-lookup"><span data-stu-id="62e95-106">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="62e95-107">Lync 2013 können auch eine durch Semikolons getrennte Liste von Kontaktnamen für Mehrparteienkonferenzen erkennen.</span><span class="sxs-lookup"><span data-stu-id="62e95-107">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="62e95-108">Wenn lync 2013 für die automatische Anmeldung beim Start konfiguriert ist, wird beim Starten von lync 2013 mit Befehlszeilenparametern das lync-Hauptfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="62e95-108">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="62e95-109">Wenn Lync nicht für die automatische Anmeldung beim Starten konfiguriert ist, wird das Anmeldefenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="62e95-109">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="62e95-110">Die folgende Tabelle zeigt die verfügbaren Parameter.</span><span class="sxs-lookup"><span data-stu-id="62e95-110">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="62e95-111">Lync 2013 Command-Line Parameter</span><span class="sxs-lookup"><span data-stu-id="62e95-111">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62e95-112">Erweiterung</span><span class="sxs-lookup"><span data-stu-id="62e95-112">Extension</span></span></th>
<th><span data-ttu-id="62e95-113">Datenformat</span><span class="sxs-lookup"><span data-stu-id="62e95-113">Format of Data</span></span></th>
<th><span data-ttu-id="62e95-114">Aktion</span><span class="sxs-lookup"><span data-stu-id="62e95-114">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62e95-115">Tel</span><span class="sxs-lookup"><span data-stu-id="62e95-115">tel:</span></span></p></td>
<td><p><span data-ttu-id="62e95-116">Tel-URI</span><span class="sxs-lookup"><span data-stu-id="62e95-116">tel URI</span></span></p></td>
<td><p><span data-ttu-id="62e95-117">Öffnet das Fenster "Unterhaltung" für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</span><span class="sxs-lookup"><span data-stu-id="62e95-117">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e95-118">callto</span><span class="sxs-lookup"><span data-stu-id="62e95-118">callto:</span></span></p></td>
<td><p><span data-ttu-id="62e95-119">"tel:", "sip:" oder Telefon-URI, der eingegeben werden kann</span><span class="sxs-lookup"><span data-stu-id="62e95-119">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="62e95-120">Öffnet das Fenster "Unterhaltung" für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</span><span class="sxs-lookup"><span data-stu-id="62e95-120">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e95-121">SIP</span><span class="sxs-lookup"><span data-stu-id="62e95-121">sip:</span></span></p></td>
<td><p><span data-ttu-id="62e95-122">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="62e95-122">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="62e95-123">Öffnet das Fenster "Unterhaltung" mit dem angegebenen SIP-URI (Uniform Resource Identifier) in der Teilnehmerliste.</span><span class="sxs-lookup"><span data-stu-id="62e95-123">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e95-124">SIPs</span><span class="sxs-lookup"><span data-stu-id="62e95-124">Sips:</span></span></p></td>
<td><p><span data-ttu-id="62e95-125">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="62e95-125">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="62e95-126">Wenn lync 2013 für die Verwendung des TLS-Protokolls (Transport Layer Security) konfiguriert ist, funktioniert genau wie bei SIP:.</span><span class="sxs-lookup"><span data-stu-id="62e95-126">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="62e95-127">Wenn TLS nicht verwendet wird, wird der Benutzer in einem Dialogfeld informiert, dass eine höhere Sicherheitsstufe erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="62e95-127">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e95-128">conf</span><span class="sxs-lookup"><span data-stu-id="62e95-128">conf:</span></span></p></td>
<td><p><span data-ttu-id="62e95-129">SIP-URI der Konferenz, an welcher der Benutzer teilnehmen möchte</span><span class="sxs-lookup"><span data-stu-id="62e95-129">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="62e95-p104">Bei Verwendung des URI-Werts "self" wird das Konferenzzustandsobjekt instanziiert, und es wird ausschließlich die Konferenzliste angezeigt. Andernfalls wird die Listenansicht geöffnet, eine INVITE-Anforderung wird jedoch nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="62e95-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e95-132">Chat</span><span class="sxs-lookup"><span data-stu-id="62e95-132">im:</span></span></p></td>
<td><p><span data-ttu-id="62e95-133">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="62e95-133">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="62e95-134">Zeigt ein Fenster "Unterhaltung" mit dem SIP-URI an, in dem ausschließlich Sofortnachrichten gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="62e95-134">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="62e95-135">Akzeptiert mehrere SIP-URIs, die innerhalb von spitzen Klammern ( &lt; &gt; ) ohne Trennzeichen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="62e95-135">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="62e95-136">In der folgenden Tabelle sind Beispiele für diese Befehlszeilenparameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="62e95-136">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="62e95-137">Beispiele für Befehlszeilenparameter</span><span class="sxs-lookup"><span data-stu-id="62e95-137">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62e95-138">Instance</span><span class="sxs-lookup"><span data-stu-id="62e95-138">Instance</span></span></th>
<th><span data-ttu-id="62e95-139">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="62e95-139">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62e95-140">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="62e95-140">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="62e95-141">Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</span><span class="sxs-lookup"><span data-stu-id="62e95-141">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e95-142">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="62e95-142">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="62e95-143">Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</span><span class="sxs-lookup"><span data-stu-id="62e95-143">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e95-144">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="62e95-144">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="62e95-145">Öffnet eine Nur-Telefon-Ansicht mit kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="62e95-145">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62e95-146">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="62e95-146">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="62e95-147">Öffnet ein Fenster "Unterhaltung" mit kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="62e95-147">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62e95-148">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="62e95-148">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="62e95-149">Öffnet ein Unterhaltungsfenster und zeigt Besprechungs-audioverknüpfungs Optionen an.</span><span class="sxs-lookup"><span data-stu-id="62e95-149">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

