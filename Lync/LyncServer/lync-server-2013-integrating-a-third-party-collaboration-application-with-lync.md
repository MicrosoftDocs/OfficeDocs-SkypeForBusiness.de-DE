---
title: Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b95f79202cbf96568b98dcb802e97bf4ca2d32
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="256f6-102">Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="256f6-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="256f6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="256f6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="256f6-104">Sie können lync 2013 in eine beliebige Anwendung für die Online Zusammenarbeit von Drittanbietern integrieren, indem Sie der Registrierung Informationen zur Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="256f6-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="256f6-105">Sie können lync 2013 verwenden, um Datenkonferenz Sitzungen zu starten, die auf einem internen Server, einem Internet basierten Dienst oder in beiden gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="256f6-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="256f6-106">Die Zusammenarbeits-oder Datenkonferenz Sitzung kann über die Kontaktliste oder über eine vorhandene Chat-, sprach-oder Videositzung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="256f6-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="256f6-107">Lync 2013 fungiert nur als Vehikel für das Starten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="256f6-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="256f6-108">Alle vorhandenen lync 2013-Unterhaltungen bleiben nach Beginn der Online Zusammenarbeitssitzung aktiv.</span><span class="sxs-lookup"><span data-stu-id="256f6-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="256f6-109">In den folgenden Abschnitten wird beschrieben, wie Sie lync 2013 mit Internet basierten und Server basierten Zusammenarbeitsanwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="256f6-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="256f6-110">Integrieren einer Internet basierten Zusammenarbeitsanwendung in lync 2013</span><span class="sxs-lookup"><span data-stu-id="256f6-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="256f6-111">Im Allgemeinen sind die Schritte, die für die Integration einer Drittanbieter-Zusammenarbeitsanwendung erforderlich sind, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="256f6-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="256f6-112">Der Registrierung werden Informationen zur Anwendung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="256f6-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="256f6-113">Der Organisator meldet sich bei lync 2013 an und wählt Kontakte für die Datenfreigabe und Zusammenarbeit aus.</span><span class="sxs-lookup"><span data-stu-id="256f6-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="256f6-114">Oder der Organisator befindet sich möglicherweise bereits in einer Unterhaltung und entscheidet sich, Datenkonferenzen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="256f6-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="256f6-115">Lync 2013 liest die Registrierung, startet die Zusammenarbeitsanwendung und sendet dann eine benutzerdefinierte SIP-Nachricht – eine appINVITE – an die ausgewählten Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="256f6-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="256f6-116">Die Teilnehmer akzeptieren die Einladung, und die Zusammenarbeitsanwendung wird auf dem Computer jeder Person gestartet.</span><span class="sxs-lookup"><span data-stu-id="256f6-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="256f6-117">Lync 2013 verwendet die Registrierung, um zu ermitteln, welche Zusammenarbeitsanwendung verwendet werden soll, und startet dann die Anwendung mithilfe der Parameter, die in der appINVITE-Nachricht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="256f6-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="256f6-118">In der folgenden Tabelle werden die Registrierungseinträge beschrieben, die für die Integration einer Internet basierten Zusammenarbeitsanwendung in lync 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="256f6-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="256f6-119">Diese Einträge werden in der Registrierung an folgendem Speicherort gespeichert:</span><span class="sxs-lookup"><span data-stu-id="256f6-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="256f6-120">HKEY\_-\_Software\\\\für lokale\\Computer\\Microsoft\\Office\\15,0 lync\\SessionManager-apps\\-Parameter</span><span class="sxs-lookup"><span data-stu-id="256f6-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="256f6-121">Registrierungseinträge für eine Internet basierte Zusammenarbeitsanwendung</span><span class="sxs-lookup"><span data-stu-id="256f6-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="256f6-122">Name</span><span class="sxs-lookup"><span data-stu-id="256f6-122">Name</span></span></th>
<th><span data-ttu-id="256f6-123">Typ</span><span class="sxs-lookup"><span data-stu-id="256f6-123">Type</span></span></th>
<th><span data-ttu-id="256f6-124">Daten</span><span class="sxs-lookup"><span data-stu-id="256f6-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="256f6-125">Name</span><span class="sxs-lookup"><span data-stu-id="256f6-125">Name</span></span></p></td>
<td><p><span data-ttu-id="256f6-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-127">Der Anwendungsname für lync 2013-Menüs.</span><span class="sxs-lookup"><span data-stu-id="256f6-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="256f6-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="256f6-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-130">Pfad zu 16 Pixel x 16-Pixel-Symbol, BMP oder PNG.</span><span class="sxs-lookup"><span data-stu-id="256f6-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="256f6-131">Pfad</span><span class="sxs-lookup"><span data-stu-id="256f6-131">Path</span></span></p></td>
<td><p><span data-ttu-id="256f6-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-133">Teilnehmerpfad zum Starten der Anwendung für die Online Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="256f6-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="256f6-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="256f6-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-136">Organizer-Pfad zum Starten der Anwendung für die Online Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="256f6-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="256f6-137">Dieser Pfad kann einen oder mehrere benutzerdefinierte Parameter enthalten, die im Unterschlüssel Parameters definiert sind.</span><span class="sxs-lookup"><span data-stu-id="256f6-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="256f6-138">Zum Beispiel<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="256f6-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="256f6-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="256f6-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="256f6-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="256f6-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="256f6-141">0 = lokale Sitzung.</span><span class="sxs-lookup"><span data-stu-id="256f6-141">0 = Local session.</span></span> <span data-ttu-id="256f6-142">Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="256f6-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="256f6-143">1 = Sitzung mit zwei Teilnehmern (Standard).</span><span class="sxs-lookup"><span data-stu-id="256f6-143">1 = Two-party session (default).</span></span> <span data-ttu-id="256f6-144">Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="256f6-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="256f6-145">Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="256f6-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="256f6-146">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="256f6-146">2 = Multiparty session.</span></span> <span data-ttu-id="256f6-147">Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer und fordert Sie auf, die angegebene Anwendung auf Ihrem eigenen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="256f6-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="256f6-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="256f6-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-150">Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons.</span><span class="sxs-lookup"><span data-stu-id="256f6-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="256f6-151">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="256f6-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="256f6-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="256f6-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="256f6-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="256f6-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="256f6-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="256f6-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="256f6-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="256f6-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="256f6-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="256f6-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="256f6-157">Wenn ExtensibleMenu nicht definiert ist, werden die Standardwerte MainWindowRightClick und ConversationWindowActions verwendet.</span><span class="sxs-lookup"><span data-stu-id="256f6-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="256f6-158">In der folgenden Tabelle werden die Registrierungseinträge für Parameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="256f6-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="256f6-159">Diese Einträge finden Sie unter HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter.</span><span class="sxs-lookup"><span data-stu-id="256f6-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="256f6-160">Registrierungseinträge für eine Internet basierte Zusammenarbeitsanwendung</span><span class="sxs-lookup"><span data-stu-id="256f6-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="256f6-161">Name</span><span class="sxs-lookup"><span data-stu-id="256f6-161">Name</span></span></th>
<th><span data-ttu-id="256f6-162">Typ</span><span class="sxs-lookup"><span data-stu-id="256f6-162">Type</span></span></th>
<th><span data-ttu-id="256f6-163">Daten</span><span class="sxs-lookup"><span data-stu-id="256f6-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="256f6-164">Parameter1</span><span class="sxs-lookup"><span data-stu-id="256f6-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="256f6-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-166">Wird in tokenformat (<code>%Parm1%</code>) verwendet, um dem Registrierungsschlüssel OriginatorPath benutzerspezifische Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="256f6-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-167">Parameter2</span><span class="sxs-lookup"><span data-stu-id="256f6-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="256f6-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-169">Siehe parameter1.</span><span class="sxs-lookup"><span data-stu-id="256f6-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="256f6-170">Param3</span><span class="sxs-lookup"><span data-stu-id="256f6-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="256f6-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-172">Siehe parameter1.</span><span class="sxs-lookup"><span data-stu-id="256f6-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="256f6-173">Die folgenden Beispiel Registrierungseinstellungen integrieren den Adatum-Zusammenarbeits Client in lync 2013:</span><span class="sxs-lookup"><span data-stu-id="256f6-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="256f6-174">Integrieren einer Server basierten Zusammenarbeitsanwendung in lync 2013</span><span class="sxs-lookup"><span data-stu-id="256f6-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="256f6-175">Die Einstellungen zum Hinzufügen von Befehlen zum Starten einer Server basierten Zusammenarbeitsanwendung in lync 2013 ähneln denen im vorherigen Abschnitt, in dem eine Internet basierte Zusammenarbeitsanwendung mit lync 2013 integriert wurde.</span><span class="sxs-lookup"><span data-stu-id="256f6-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="256f6-176">Die OriginatorPath ist jedoch nicht erforderlich, und einige Werte werden geändert.</span><span class="sxs-lookup"><span data-stu-id="256f6-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="256f6-177">Registrierungseinträge werden an folgendem Speicherort gespeichert:</span><span class="sxs-lookup"><span data-stu-id="256f6-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="256f6-178">HKEY\_-\_Software\\\\für lokale\\Computer\\Microsoft\\Office\\15,0 lync\\SessionManager-apps\\-Parameter</span><span class="sxs-lookup"><span data-stu-id="256f6-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="256f6-179">Registrierungseinträge für eine Server basierte Zusammenarbeitsanwendung</span><span class="sxs-lookup"><span data-stu-id="256f6-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="256f6-180">Name</span><span class="sxs-lookup"><span data-stu-id="256f6-180">Name</span></span></th>
<th><span data-ttu-id="256f6-181">Typ</span><span class="sxs-lookup"><span data-stu-id="256f6-181">Type</span></span></th>
<th><span data-ttu-id="256f6-182">Daten</span><span class="sxs-lookup"><span data-stu-id="256f6-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="256f6-183">Name</span><span class="sxs-lookup"><span data-stu-id="256f6-183">Name</span></span></p></td>
<td><p><span data-ttu-id="256f6-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-185">Der Name der Anwendung, wie er im Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="256f6-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-186">Applicationtype</span><span class="sxs-lookup"><span data-stu-id="256f6-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="256f6-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="256f6-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="256f6-188">Wert = 1.</span><span class="sxs-lookup"><span data-stu-id="256f6-188">Value = 1.</span></span> <span data-ttu-id="256f6-189">Legt den Anwendungstyp auf Protocol fest.</span><span class="sxs-lookup"><span data-stu-id="256f6-189">Sets the application type to protocol.</span></span> <span data-ttu-id="256f6-190">In diesem Fall gelten die anderen möglichen Werte nicht.</span><span class="sxs-lookup"><span data-stu-id="256f6-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="256f6-191">Wenn es nicht vorhanden ist, wird applicationtype auf 0 (ausführbare Datei) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="256f6-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="256f6-192">Pfad</span><span class="sxs-lookup"><span data-stu-id="256f6-192">Path</span></span></p></td>
<td><p><span data-ttu-id="256f6-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-194">Das Protokoll, das zum Starten der Zusammenarbeitsanwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="256f6-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="256f6-195">Für Live Meeting 2007 ist der Wert von Path auf <code>meet:%conf-uri%</code>gesetzt.</span><span class="sxs-lookup"><span data-stu-id="256f6-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="256f6-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="256f6-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="256f6-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="256f6-198">0 = lokale Sitzung.</span><span class="sxs-lookup"><span data-stu-id="256f6-198">0 = Local session.</span></span> <span data-ttu-id="256f6-199">Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="256f6-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="256f6-200">1 = Sitzung mit zwei Teilnehmern (Standard).</span><span class="sxs-lookup"><span data-stu-id="256f6-200">1 = Two-party session (default).</span></span> <span data-ttu-id="256f6-201">Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="256f6-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="256f6-202">Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="256f6-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="256f6-203">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="256f6-203">2 = Multiparty session.</span></span> <span data-ttu-id="256f6-204">Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer und fordert Sie auf, die angegebene Anwendung auf Ihrem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="256f6-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="256f6-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="256f6-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="256f6-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-207">Data = der Servertyp.</span><span class="sxs-lookup"><span data-stu-id="256f6-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="256f6-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="256f6-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="256f6-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="256f6-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="256f6-210">Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons.</span><span class="sxs-lookup"><span data-stu-id="256f6-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="256f6-211">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="256f6-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="256f6-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="256f6-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="256f6-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="256f6-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="256f6-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="256f6-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="256f6-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="256f6-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="256f6-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="256f6-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="256f6-217">Wenn ExtensibleMenu nicht definiert ist, werden die Standardwerte MainWindowRightClick und ConversationWindowActions verwendet.</span><span class="sxs-lookup"><span data-stu-id="256f6-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="256f6-218">Im folgenden Beispiel werden Befehle zum Starten des Adatum-Zusammenarbeits Clients in lync 2013 hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="256f6-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

