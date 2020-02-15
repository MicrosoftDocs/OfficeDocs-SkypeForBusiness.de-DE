---
title: 'Lync Server 2013: Starten von lync aus einer anderen Anwendung'
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
ms.openlocfilehash: c22f5e365e47ae7b6a41cd6e917b87718e07ac9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="e5250-102">Starten von lync aus einer anderen Anwendung</span><span class="sxs-lookup"><span data-stu-id="e5250-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5250-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e5250-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e5250-104">Sie können Befehlszeilenparameter verwenden, um lync 2013 schnell zu starten.</span><span class="sxs-lookup"><span data-stu-id="e5250-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="e5250-105">Wenn ein Benutzer beispielsweise auf eine Telefonnummer in einer anderen Anwendung klickt, kann die Anwendung eine Instanz von lync 2013 starten und einen Anruf an diese Nummer initiieren.</span><span class="sxs-lookup"><span data-stu-id="e5250-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="e5250-106">Lync 2013 können auch eine durch Semikolons getrennte Liste von Kontaktnamen für Mehrparteienkonferenzen erkennen.</span><span class="sxs-lookup"><span data-stu-id="e5250-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="e5250-107">Wenn lync 2013 für die automatische Anmeldung beim Start konfiguriert ist, wird beim Starten von lync 2013 mit Befehlszeilenparametern das lync-Hauptfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e5250-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="e5250-108">Wenn Lync nicht für die automatische Anmeldung beim Starten konfiguriert ist, wird das Anmeldefenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e5250-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="e5250-109">Die folgende Tabelle zeigt die verfügbaren Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5250-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="e5250-110">Lync 2013 Befehlszeilenparameter</span><span class="sxs-lookup"><span data-stu-id="e5250-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5250-111">Erweiterung</span><span class="sxs-lookup"><span data-stu-id="e5250-111">Extension</span></span></th>
<th><span data-ttu-id="e5250-112">Datenformat</span><span class="sxs-lookup"><span data-stu-id="e5250-112">Format of Data</span></span></th>
<th><span data-ttu-id="e5250-113">Aktion</span><span class="sxs-lookup"><span data-stu-id="e5250-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5250-114">Tel</span><span class="sxs-lookup"><span data-stu-id="e5250-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="e5250-115">Tel-URI</span><span class="sxs-lookup"><span data-stu-id="e5250-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="e5250-116">Öffnet das Fenster "Unterhaltung" für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</span><span class="sxs-lookup"><span data-stu-id="e5250-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5250-117">callto</span><span class="sxs-lookup"><span data-stu-id="e5250-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="e5250-118">"tel:", "sip:" oder Telefon-URI, der eingegeben werden kann</span><span class="sxs-lookup"><span data-stu-id="e5250-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="e5250-119">Öffnet das Fenster "Unterhaltung" für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</span><span class="sxs-lookup"><span data-stu-id="e5250-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5250-120">SIP</span><span class="sxs-lookup"><span data-stu-id="e5250-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="e5250-121">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="e5250-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e5250-122">Öffnet das Fenster "Unterhaltung" mit dem angegebenen SIP-URI (Uniform Resource Identifier) in der Teilnehmerliste.</span><span class="sxs-lookup"><span data-stu-id="e5250-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5250-123">SIPs</span><span class="sxs-lookup"><span data-stu-id="e5250-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="e5250-124">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="e5250-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e5250-125">Wenn lync 2013 für die Verwendung des TLS-Protokolls (Transport Layer Security) konfiguriert ist, funktioniert genau wie bei SIP:.</span><span class="sxs-lookup"><span data-stu-id="e5250-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="e5250-126">Wenn TLS nicht verwendet wird, wird der Benutzer in einem Dialogfeld informiert, dass eine höhere Sicherheitsstufe erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5250-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5250-127">conf</span><span class="sxs-lookup"><span data-stu-id="e5250-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="e5250-128">SIP-URI der Konferenz, an welcher der Benutzer teilnehmen möchte</span><span class="sxs-lookup"><span data-stu-id="e5250-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="e5250-p104">Bei Verwendung des URI-Werts "self" wird das Konferenzzustandsobjekt instanziiert, und es wird ausschließlich die Konferenzliste angezeigt. Andernfalls wird die Listenansicht geöffnet, eine INVITE-Anforderung wird jedoch nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="e5250-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5250-131">Chat</span><span class="sxs-lookup"><span data-stu-id="e5250-131">im:</span></span></p></td>
<td><p><span data-ttu-id="e5250-132">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="e5250-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e5250-133">Zeigt ein Fenster "Unterhaltung" mit dem SIP-URI an, in dem ausschließlich Sofortnachrichten gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e5250-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="e5250-134">Akzeptiert mehrere SIP-URIs, die innerhalb von&lt;&gt;spitzen Klammern () ohne Trennzeichen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e5250-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5250-135">In der folgenden Tabelle sind Beispiele für diese Befehlszeilenparameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5250-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="e5250-136">Beispiele für Befehlszeilenparameter</span><span class="sxs-lookup"><span data-stu-id="e5250-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5250-137">Instanz</span><span class="sxs-lookup"><span data-stu-id="e5250-137">Instance</span></span></th>
<th><span data-ttu-id="e5250-138">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="e5250-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5250-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="e5250-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="e5250-140">Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</span><span class="sxs-lookup"><span data-stu-id="e5250-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5250-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="e5250-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="e5250-142">Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</span><span class="sxs-lookup"><span data-stu-id="e5250-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5250-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e5250-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="e5250-144">Öffnet eine Nur-Telefon-Ansicht mit kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e5250-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5250-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e5250-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="e5250-146">Öffnet ein Fenster "Unterhaltung" mit kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e5250-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5250-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="e5250-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="e5250-148">Öffnet ein Unterhaltungsfenster und zeigt Besprechungs-audioverknüpfungs Optionen an.</span><span class="sxs-lookup"><span data-stu-id="e5250-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

