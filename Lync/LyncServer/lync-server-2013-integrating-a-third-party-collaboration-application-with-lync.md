---
title: Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync
description: Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync.
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
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552651"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="eaa6d-103">Integrieren einer Anwendung für die Zusammenarbeit eines Drittanbieters mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaa6d-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaa6d-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="eaa6d-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="eaa6d-105">Sie können lync 2013 in eine beliebige Anwendung für die Online Zusammenarbeit von Drittanbietern integrieren, indem Sie der Registrierung Informationen zur Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="eaa6d-106">Sie können lync 2013 verwenden, um Datenkonferenz Sitzungen zu starten, die auf einem internen Server, einem Internet basierten Dienst oder beides gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="eaa6d-107">Die Zusammenarbeits-oder Datenkonferenz Sitzung kann aus der Kontaktliste oder aus einer vorhandenen Chat-, sprach-oder Videositzung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="eaa6d-108">Lync 2013 fungiert nur als das Vehikel für das Starten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="eaa6d-109">Alle vorhandenen lync 2013 Unterhaltungen bleiben aktiv, nachdem die Online Zusammenarbeitssitzung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="eaa6d-110">In den folgenden Abschnitten wird beschrieben, wie Sie lync 2013 in Internet basierte und serverbasierte Zusammenarbeitsanwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="eaa6d-111">Integrieren einer Internet-Based-Zusammenarbeitsanwendung in lync 2013</span><span class="sxs-lookup"><span data-stu-id="eaa6d-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="eaa6d-112">Im Allgemeinen müssen die folgenden Schritte ausgeführt werden, um eine Drittanbieteranwendung für die Zusammenarbeit zu integrieren:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="eaa6d-113">Der Registrierung werden Informationen zur Anwendung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="eaa6d-114">Der Organisator meldet sich bei lync 2013 an und wählt Kontakte für die Datenfreigabe und Zusammenarbeit aus.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="eaa6d-115">Oder der Organisator befindet sich bereits in einer Unterhaltung und beschließt, eine Datenkonferenz zu starten.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="eaa6d-116">Lync 2013 die Registrierung liest, startet die Zusammenarbeitsanwendung und sendet dann eine benutzerdefinierte SIP-Nachricht – ein appINVITE – an die ausgewählten Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="eaa6d-117">Die Teilnehmer nehmen die Einladung an, und die Zusammenarbeitsanwendung wird auf dem Computer der einzelnen Personen gestartet.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="eaa6d-118">Lync 2013 verwendet die Registrierung, um zu bestimmen, welche Zusammenarbeitsanwendung verwendet werden soll, und startet diese Anwendung dann mithilfe der Parameter, die in der appINVITE-Nachricht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="eaa6d-119">In der folgenden Tabelle werden die Registrierungseinträge beschrieben, die für die Integration einer Internet basierten Zusammenarbeitsanwendung mit lync 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="eaa6d-120">Diese Einträge werden an folgendem Speicherort in der Registrierung gespeichert:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="eaa6d-121">HKEY \_ local \_ Machine \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \\ SessionManager- \\ apps- \\ Parameter</span><span class="sxs-lookup"><span data-stu-id="eaa6d-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="eaa6d-122">Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="eaa6d-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eaa6d-123">Name</span><span class="sxs-lookup"><span data-stu-id="eaa6d-123">Name</span></span></th>
<th><span data-ttu-id="eaa6d-124">Typ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-124">Type</span></span></th>
<th><span data-ttu-id="eaa6d-125">Daten</span><span class="sxs-lookup"><span data-stu-id="eaa6d-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-126">Name</span><span class="sxs-lookup"><span data-stu-id="eaa6d-126">Name</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-128">Der Name der Anwendung für lync 2013 Menüs.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-129">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="eaa6d-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-131">Pfad zu Symbol mit 16 Pixel x 16 Pixel, BMP oder PNG.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-132">Pfad</span><span class="sxs-lookup"><span data-stu-id="eaa6d-132">Path</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-134">Teilnehmerpfad zum Starten der Anwendung für die Onlinezusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-135">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="eaa6d-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-137">Organisatorpfad zum Starten der Anwendung für die Onlinezusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="eaa6d-138">Dieser Pfad kann einen oder mehrere benutzerdefinierte Parameter enthalten, die im Unterschlüssel "Parameters" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="eaa6d-139">Beispiel: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="eaa6d-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-140">SessionType</span><span class="sxs-lookup"><span data-stu-id="eaa6d-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="eaa6d-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-p106">0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="eaa6d-144">1 = Sitzung mit zwei Teilnehmern (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="eaa6d-144">1 = Two-party session (default).</span></span> <span data-ttu-id="eaa6d-145">Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="eaa6d-146">Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="eaa6d-147">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-147">2 = Multiparty session.</span></span> <span data-ttu-id="eaa6d-148">Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer, woraufhin Sie aufgefordert werden, die angegebene Anwendung auf Ihrem eigenen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-149">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="eaa6d-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-p109">Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="eaa6d-153">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="eaa6d-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-154">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eaa6d-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-155">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="eaa6d-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-156">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="eaa6d-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-157">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eaa6d-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="eaa6d-158">Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eaa6d-159">In der folgenden Tabelle werden die Registrierungseinträge für Parameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="eaa6d-160">Diese Einträge finden Sie unter HKEY \_ aktuelle \_ Benutzer \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \\ SessionManager \\ \\ -apps-Parameter.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="eaa6d-161">Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="eaa6d-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eaa6d-162">Name</span><span class="sxs-lookup"><span data-stu-id="eaa6d-162">Name</span></span></th>
<th><span data-ttu-id="eaa6d-163">Typ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-163">Type</span></span></th>
<th><span data-ttu-id="eaa6d-164">Daten</span><span class="sxs-lookup"><span data-stu-id="eaa6d-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-165">Param1</span><span class="sxs-lookup"><span data-stu-id="eaa6d-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-167">Wird im Tokenformat ( <code>%Parm1%</code> ) verwendet, um dem Registrierungsschlüssel OriginatorPath benutzerspezifische Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-168">Param2</span><span class="sxs-lookup"><span data-stu-id="eaa6d-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-170">Siehe Param1.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-171">Param3</span><span class="sxs-lookup"><span data-stu-id="eaa6d-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-173">Siehe Param1.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eaa6d-174">Im folgenden Beispiel werden die Registrierungseinstellungen Adatum-Zusammenarbeits Client mit lync 2013 integriert:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="eaa6d-175">Integrieren einer Server-Based-Zusammenarbeitsanwendung in lync 2013</span><span class="sxs-lookup"><span data-stu-id="eaa6d-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="eaa6d-176">Die Einstellungen zum Hinzufügen von Befehlen zum Starten einer Server basierten Zusammenarbeitsanwendung in lync 2013 ähneln denen im vorherigen Abschnitt, der die Integration einer Internet-Based Zusammenarbeitsanwendung mit lync 2013 beschreibt.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="eaa6d-177">"OriginatorPath" ist jedoch nicht erforderlich, und einige Werte sind geändert.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="eaa6d-178">Registrierungseinträge werden an folgendem Speicherort eingefügt:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="eaa6d-179">HKEY \_ local \_ Machine \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \\ SessionManager- \\ apps- \\ Parameter</span><span class="sxs-lookup"><span data-stu-id="eaa6d-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="eaa6d-180">Registrierungseinträge für eine serverbasierte Anwendung für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="eaa6d-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eaa6d-181">Name</span><span class="sxs-lookup"><span data-stu-id="eaa6d-181">Name</span></span></th>
<th><span data-ttu-id="eaa6d-182">Typ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-182">Type</span></span></th>
<th><span data-ttu-id="eaa6d-183">Daten</span><span class="sxs-lookup"><span data-stu-id="eaa6d-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-184">Name</span><span class="sxs-lookup"><span data-stu-id="eaa6d-184">Name</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-186">Name der Anwendung, wie er im Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="eaa6d-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="eaa6d-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-189">Wert = 1.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-189">Value = 1.</span></span> <span data-ttu-id="eaa6d-190">Legt den Anwendungstyp auf "protocol" fest.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-190">Sets the application type to protocol.</span></span> <span data-ttu-id="eaa6d-191">Die weiteren möglichen Werte gelten in diesem Fall nicht.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="eaa6d-192">Wenn der Wert nicht vorhanden ist, wird applicationtype auf 0 (ausführbar) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-193">Pfad</span><span class="sxs-lookup"><span data-stu-id="eaa6d-193">Path</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-195">Zum Starten der Anwendung für die Zusammenarbeit verwendetes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="eaa6d-196">Für Live Meeting 2007 ist der Wert von Path auf festgelegt <code>meet:%conf-uri%</code> .</span><span class="sxs-lookup"><span data-stu-id="eaa6d-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-197">SessionType</span><span class="sxs-lookup"><span data-stu-id="eaa6d-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="eaa6d-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-p114">0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="eaa6d-201">1 = Sitzung mit zwei Teilnehmern (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="eaa6d-201">1 = Two-party session (default).</span></span> <span data-ttu-id="eaa6d-202">Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="eaa6d-203">Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="eaa6d-204">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-204">2 = Multiparty session.</span></span> <span data-ttu-id="eaa6d-205">Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer, woraufhin Sie aufgefordert werden, die angegebene Anwendung auf Ihrem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eaa6d-206">MCUType</span><span class="sxs-lookup"><span data-stu-id="eaa6d-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-208">DATA = Typ des Servers.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eaa6d-209">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="eaa6d-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="eaa6d-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="eaa6d-211">Eine Liste der Menüs, in denen dieser Befehl durch Semikolons getrennt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="eaa6d-212">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="eaa6d-213">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="eaa6d-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-214">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eaa6d-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-215">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="eaa6d-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-216">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="eaa6d-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="eaa6d-217">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="eaa6d-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="eaa6d-218">Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</span><span class="sxs-lookup"><span data-stu-id="eaa6d-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eaa6d-219">Im folgenden Beispiel werden Befehle zum Starten des Adatum-Zusammenarbeits Clients in lync 2013 hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="eaa6d-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

