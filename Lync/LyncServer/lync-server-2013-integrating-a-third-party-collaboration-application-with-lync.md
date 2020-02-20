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
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="87884-102">Integrieren einer Anwendung für die Zusammenarbeit eines Drittanbieters mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87884-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87884-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="87884-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="87884-104">Sie können lync 2013 in eine beliebige Anwendung für die Online Zusammenarbeit von Drittanbietern integrieren, indem Sie der Registrierung Informationen zur Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="87884-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="87884-105">Sie können lync 2013 verwenden, um Datenkonferenz Sitzungen zu starten, die auf einem internen Server, einem Internet basierten Dienst oder beides gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="87884-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="87884-106">Die Zusammenarbeits-oder Datenkonferenz Sitzung kann aus der Kontaktliste oder aus einer vorhandenen Chat-, sprach-oder Videositzung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="87884-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="87884-107">Lync 2013 fungiert nur als das Vehikel für das Starten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="87884-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="87884-108">Alle vorhandenen lync 2013 Unterhaltungen bleiben aktiv, nachdem die Online Zusammenarbeitssitzung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="87884-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="87884-109">In den folgenden Abschnitten wird beschrieben, wie Sie lync 2013 in Internet basierte und serverbasierte Zusammenarbeitsanwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="87884-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="87884-110">Integrieren einer Anwendung für Internet basierte Zusammenarbeit mit lync 2013</span><span class="sxs-lookup"><span data-stu-id="87884-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="87884-111">Im Allgemeinen müssen die folgenden Schritte ausgeführt werden, um eine Drittanbieteranwendung für die Zusammenarbeit zu integrieren:</span><span class="sxs-lookup"><span data-stu-id="87884-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="87884-112">Der Registrierung werden Informationen zur Anwendung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="87884-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="87884-113">Der Organisator meldet sich bei lync 2013 an und wählt Kontakte für die Datenfreigabe und Zusammenarbeit aus.</span><span class="sxs-lookup"><span data-stu-id="87884-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="87884-114">Oder der Organisator befindet sich bereits in einer Unterhaltung und beschließt, eine Datenkonferenz zu starten.</span><span class="sxs-lookup"><span data-stu-id="87884-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="87884-115">Lync 2013 die Registrierung liest, startet die Zusammenarbeitsanwendung und sendet dann eine benutzerdefinierte SIP-Nachricht – ein appINVITE – an die ausgewählten Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="87884-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="87884-116">Die Teilnehmer nehmen die Einladung an, und die Zusammenarbeitsanwendung wird auf dem Computer der einzelnen Personen gestartet.</span><span class="sxs-lookup"><span data-stu-id="87884-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="87884-117">Lync 2013 verwendet die Registrierung, um zu bestimmen, welche Zusammenarbeitsanwendung verwendet werden soll, und startet diese Anwendung dann mithilfe der Parameter, die in der appINVITE-Nachricht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="87884-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="87884-118">In der folgenden Tabelle werden die Registrierungseinträge beschrieben, die für die Integration einer Internet basierten Zusammenarbeitsanwendung mit lync 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="87884-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="87884-119">Diese Einträge werden an folgendem Speicherort in der Registrierung gespeichert:</span><span class="sxs-lookup"><span data-stu-id="87884-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="87884-120">HKEY\_local\_Machine\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter</span><span class="sxs-lookup"><span data-stu-id="87884-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="87884-121">Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="87884-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87884-122">Name</span><span class="sxs-lookup"><span data-stu-id="87884-122">Name</span></span></th>
<th><span data-ttu-id="87884-123">Typ</span><span class="sxs-lookup"><span data-stu-id="87884-123">Type</span></span></th>
<th><span data-ttu-id="87884-124">Daten</span><span class="sxs-lookup"><span data-stu-id="87884-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87884-125">Name</span><span class="sxs-lookup"><span data-stu-id="87884-125">Name</span></span></p></td>
<td><p><span data-ttu-id="87884-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-127">Der Name der Anwendung für lync 2013 Menüs.</span><span class="sxs-lookup"><span data-stu-id="87884-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="87884-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="87884-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-130">Pfad zu Symbol mit 16 Pixel x 16 Pixel, BMP oder PNG.</span><span class="sxs-lookup"><span data-stu-id="87884-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87884-131">Pfad</span><span class="sxs-lookup"><span data-stu-id="87884-131">Path</span></span></p></td>
<td><p><span data-ttu-id="87884-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-133">Teilnehmerpfad zum Starten der Anwendung für die Onlinezusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="87884-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="87884-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="87884-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-136">Organisatorpfad zum Starten der Anwendung für die Onlinezusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="87884-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="87884-137">Dieser Pfad kann einen oder mehrere benutzerdefinierte Parameter enthalten, die im Unterschlüssel "Parameters" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="87884-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="87884-138">Beispiel: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="87884-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87884-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="87884-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="87884-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="87884-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="87884-p106">0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="87884-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="87884-143">1 = Sitzung mit zwei Teilnehmern (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="87884-143">1 = Two-party session (default).</span></span> <span data-ttu-id="87884-144">Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="87884-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="87884-145">Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</span><span class="sxs-lookup"><span data-stu-id="87884-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="87884-146">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="87884-146">2 = Multiparty session.</span></span> <span data-ttu-id="87884-147">Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer, woraufhin Sie aufgefordert werden, die angegebene Anwendung auf Ihrem eigenen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="87884-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="87884-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="87884-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-p109">Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="87884-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="87884-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="87884-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="87884-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="87884-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="87884-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="87884-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="87884-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="87884-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="87884-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="87884-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="87884-157">Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</span><span class="sxs-lookup"><span data-stu-id="87884-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87884-158">In der folgenden Tabelle werden die Registrierungseinträge für Parameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87884-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="87884-159">Diese Einträge finden Sie unter HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter.</span><span class="sxs-lookup"><span data-stu-id="87884-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="87884-160">Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="87884-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87884-161">Name</span><span class="sxs-lookup"><span data-stu-id="87884-161">Name</span></span></th>
<th><span data-ttu-id="87884-162">Typ</span><span class="sxs-lookup"><span data-stu-id="87884-162">Type</span></span></th>
<th><span data-ttu-id="87884-163">Daten</span><span class="sxs-lookup"><span data-stu-id="87884-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87884-164">Param1</span><span class="sxs-lookup"><span data-stu-id="87884-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="87884-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-166">Wird im Tokenformat (<code>%Parm1%</code>) verwendet, um dem Registrierungsschlüssel OriginatorPath benutzerspezifische Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="87884-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-167">Param2</span><span class="sxs-lookup"><span data-stu-id="87884-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="87884-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-169">Siehe Param1.</span><span class="sxs-lookup"><span data-stu-id="87884-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87884-170">Param3</span><span class="sxs-lookup"><span data-stu-id="87884-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="87884-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-172">Siehe Param1.</span><span class="sxs-lookup"><span data-stu-id="87884-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87884-173">Im folgenden Beispiel werden die Registrierungseinstellungen Adatum-Zusammenarbeits Client mit lync 2013 integriert:</span><span class="sxs-lookup"><span data-stu-id="87884-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="87884-174">Integrieren einer Server basierten Zusammenarbeitsanwendung mit lync 2013</span><span class="sxs-lookup"><span data-stu-id="87884-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="87884-175">Die Einstellungen zum Hinzufügen von Befehlen zum Starten einer Server basierten Zusammenarbeitsanwendung in lync 2013 ähneln denen im vorherigen Abschnitt und integrieren eine Internet basierte Zusammenarbeitsanwendung mit lync 2013.</span><span class="sxs-lookup"><span data-stu-id="87884-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="87884-176">"OriginatorPath" ist jedoch nicht erforderlich, und einige Werte sind geändert.</span><span class="sxs-lookup"><span data-stu-id="87884-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="87884-177">Registrierungseinträge werden an folgendem Speicherort eingefügt:</span><span class="sxs-lookup"><span data-stu-id="87884-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="87884-178">HKEY\_local\_Machine\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter</span><span class="sxs-lookup"><span data-stu-id="87884-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="87884-179">Registrierungseinträge für eine serverbasierte Anwendung für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="87884-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87884-180">Name</span><span class="sxs-lookup"><span data-stu-id="87884-180">Name</span></span></th>
<th><span data-ttu-id="87884-181">Typ</span><span class="sxs-lookup"><span data-stu-id="87884-181">Type</span></span></th>
<th><span data-ttu-id="87884-182">Daten</span><span class="sxs-lookup"><span data-stu-id="87884-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87884-183">Name</span><span class="sxs-lookup"><span data-stu-id="87884-183">Name</span></span></p></td>
<td><p><span data-ttu-id="87884-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-185">Name der Anwendung, wie er im Menü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87884-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="87884-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="87884-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="87884-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="87884-188">Wert = 1.</span><span class="sxs-lookup"><span data-stu-id="87884-188">Value = 1.</span></span> <span data-ttu-id="87884-189">Legt den Anwendungstyp auf "protocol" fest.</span><span class="sxs-lookup"><span data-stu-id="87884-189">Sets the application type to protocol.</span></span> <span data-ttu-id="87884-190">Die weiteren möglichen Werte gelten in diesem Fall nicht.</span><span class="sxs-lookup"><span data-stu-id="87884-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="87884-191">Wenn der Wert nicht vorhanden ist, wird applicationtype auf 0 (ausführbar) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="87884-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87884-192">Pfad</span><span class="sxs-lookup"><span data-stu-id="87884-192">Path</span></span></p></td>
<td><p><span data-ttu-id="87884-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-194">Zum Starten der Anwendung für die Zusammenarbeit verwendetes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="87884-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="87884-195">Für Live Meeting 2007 ist der Wert von Path auf <code>meet:%conf-uri%</code>festgelegt.</span><span class="sxs-lookup"><span data-stu-id="87884-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="87884-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="87884-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="87884-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="87884-p114">0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="87884-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="87884-200">1 = Sitzung mit zwei Teilnehmern (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="87884-200">1 = Two-party session (default).</span></span> <span data-ttu-id="87884-201">Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="87884-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="87884-202">Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</span><span class="sxs-lookup"><span data-stu-id="87884-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="87884-203">2 = mehrteilige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="87884-203">2 = Multiparty session.</span></span> <span data-ttu-id="87884-204">Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer, woraufhin Sie aufgefordert werden, die angegebene Anwendung auf Ihrem Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="87884-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87884-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="87884-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="87884-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-207">DATA = Typ des Servers.</span><span class="sxs-lookup"><span data-stu-id="87884-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87884-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="87884-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="87884-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="87884-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="87884-210">Eine Liste der Menüs, in denen dieser Befehl durch Semikolons getrennt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87884-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="87884-211">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="87884-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="87884-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="87884-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="87884-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="87884-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="87884-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="87884-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="87884-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="87884-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="87884-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="87884-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="87884-217">Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</span><span class="sxs-lookup"><span data-stu-id="87884-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87884-218">Im folgenden Beispiel werden Befehle zum Starten des Adatum-Zusammenarbeits Clients in lync 2013 hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="87884-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

