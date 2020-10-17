---
title: Übersicht über lync Server 2013 Einwahlkonferenzen
description: Lync Server 2013 Übersicht über Einwahlkonferenzen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa9418c13b56faab747d2c92df3301fe15d722eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549481"
---
# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="18a13-103">Übersicht über Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18a13-103">Overview of dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18a13-104">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="18a13-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="18a13-105">Wenn Ihre Organisation über Benutzer verfügt, die lync Server 2013 lokalen Konferenzen teilnehmen müssen, wenn Sie nicht im Büro sind oder keinen Zugriff auf einen Computer haben, können Sie Einwahlkonferenzen bereitstellen, damit Sie über ein PSTN-Telefon (Public Switched Telephone Network) an der Konferenz teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="18a13-105">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="18a13-106">Einwahlkonferenzen sind ein optionales Feature, das Sie bei der Bereitstellung von lync Server 2013 Konferenzen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="18a13-106">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="18a13-107">Bei Einwahlkonferenzen werden zwar einige der lync Server 2013 Komponenten verwendet, die Enterprise-VoIP verwendet, aber Sie können Einwahlkonferenzen auch dann bereitstellen, wenn Sie Enterprise-VoIP nicht bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="18a13-107">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18a13-108">Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Sie in jedem Pool bereitstellen, in dem Sie lync Server 2013 Konferenzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="18a13-108">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="18a13-109">Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Einwahlfunktion in jedem Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="18a13-109">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="18a13-110">Diese Anforderung unterstützt das Feature für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer lync Server 2013 Konferenz in einem anderen Pool teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="18a13-110">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="18a13-p103">Konferenzen müssen in der Besprechungsrichtlinie für den Zugriff per Einwahl aktiviert werden. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:</span><span class="sxs-lookup"><span data-stu-id="18a13-p103">Conferences must be enabled for dial-in access in meeting policy. By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="18a13-113">Eine numerische Konferenz-ID, die zur Identifizierung der Konferenz dient.</span><span class="sxs-lookup"><span data-stu-id="18a13-113">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="18a13-114">Mindestens eine PSTN-Zugriffsnummer.</span><span class="sxs-lookup"><span data-stu-id="18a13-114">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="18a13-115">Ein Link zu einer Seite "Einstellungen für Einwahlkonferenzen", die eine vollständige Liste der Zugriffsnummern mit ihren zugeordneten Sprachen enthält; ein Ort zum Erstellen, zurücksetzen oder Aufheben der Blockierung persönlicher Identifikationsnummern (Pins); und andere Informationen, wie etwa DTMF-Steuerelemente (Dual-Tone Multi-Frequency).</span><span class="sxs-lookup"><span data-stu-id="18a13-115">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="18a13-116">Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="18a13-116">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="18a13-117">Enterprise-Benutzer verfügen über Active Directory-Domänendienste Anmeldeinformationen und lync Server 2013 Konten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="18a13-117">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="18a13-118">Anonyme Benutzer verfügen nicht über Anmeldeinformationen innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="18a13-118">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="18a13-119">Im Zusammenhang mit Einwahlkonferenzen wird ein Benutzer in einer Organisation eines Verbundpartners, der über PSTN eine Verbindung mit einer Konferenz herstellt, als anonymer Benutzer betrachtet.</span><span class="sxs-lookup"><span data-stu-id="18a13-119">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="18a13-120">Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="18a13-120">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="18a13-121">Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="18a13-121">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="18a13-122">Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="18a13-122">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="18a13-123">Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben.</span><span class="sxs-lookup"><span data-stu-id="18a13-123">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="18a13-124">In der Front-End-Server wird die Kombination aus vollständiger Telefonnummer oder Durchwahl und PIN verwendet, um Enterprise-Benutzer eindeutig ihren Active Directory Anmeldeinformationen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="18a13-124">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="18a13-125">So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert.</span><span class="sxs-lookup"><span data-stu-id="18a13-125">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="18a13-126">Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.</span><span class="sxs-lookup"><span data-stu-id="18a13-126">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18a13-127">Unternehmensbenutzer, die sich über ein Office-IP-Telefon oder über lync Server 2013 oder lync 2010 Attendant einwählen, werden nicht zur Eingabe Ihrer Telefonnummer aufgefordert, da Sie bereits authentifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="18a13-127">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="18a13-p106">Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="18a13-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18a13-p107">Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt.</span><span class="sxs-lookup"><span data-stu-id="18a13-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="18a13-p108">Zu einem geplanten Zeitpunkt kann der Besprechungsorganisator den Zugriff auf die Besprechung einschränken, indem er die Besprechung als geschlossen oder gesperrt kennzeichnet. In diesem Fall müssen sich Einwahlbenutzer authentifizieren. Wenn Einwahlbenutzer nicht authentifiziert werden können oder keine Authentifizierung durchführen möchten, werden sie in die Lobby umgeleitet. Sie warten in der Lobby, bis der Besprechungsleiter ihre Teilnahme bestätigt oder ablehnt oder die Verbindung aufgrund einer Zeitüberschreitung getrennt wird. Während der Wartezeit wird für Einwahlbenutzer Musik wiedergegeben. Nachdem Einwahlbenutzer zu einer Konferenz zugelassen wurden, können sie am Audioteil der Konferenz teilnehmen und DTMF-Befehle (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren) über die Telefontastatur ausführen. Besprechungsleiter von Einwahlkonferenzen nutzen DTMF-Befehle zum Steuern, ob sich Teilnehmer selbst stumm schalten können oder nicht, zum Sperren oder Aufheben der Sperrung einer Konferenz, zum Zulassen von Teilnehmern aus der Lobby und zum Ein- und Ausschalten von Ansagen beim Beitreten und Verlassen. Konferenzleiter können mithilfe von DTMF-Befehlen zudem alle Teilnehmer aus der Lobby zulassen. Durch diese Aktion werden die Berechtigungen für die Besprechung so geändert, dass anschließend sämtliche Benutzer zugelassen werden, die der Besprechung beitreten. Alle eingewählten Teilnehmer können DTMF-Befehle ausführen, um Hilfeinformationen abzuhören, die Namen der Teilnehmer wiederzugeben und sich selbst stumm zu schalten.</span><span class="sxs-lookup"><span data-stu-id="18a13-p108">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate. If dial-in users fail or choose not to authenticate, they are transferred to the lobby. They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected. Dial-in users hear music if they are waiting to be admitted to the conference. After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad. Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off. Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins. All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="18a13-143">Für eingewählte Teilnehmer werden unabhängig davon, ob sie sich über das Festnetz einwählen oder nicht, während der Konferenz persönliche Ansagen wiedergegeben. Diese Informationen umfassen z. B., ob die Teilnehmer stumm geschaltet wurden oder nicht, ob die Besprechung aufgezeichnet wird oder ob Benutzer in der Lobby warten.</span><span class="sxs-lookup"><span data-stu-id="18a13-143">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18a13-144">Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="18a13-144">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

