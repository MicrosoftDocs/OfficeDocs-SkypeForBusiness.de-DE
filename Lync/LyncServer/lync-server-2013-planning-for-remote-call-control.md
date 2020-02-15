---
title: 'Lync Server 2013: Planen der Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="c8110-102">Planen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8110-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8110-103">_**Letztes Änderungsstand des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="c8110-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="c8110-104">In lync Server 2013 ermöglicht die Unterstützung für Remote Anruf Steuerungs Szenarien Benutzern die Steuerung Ihrer PBX-Telefone (Private Branch Exchange) mithilfe von lync 2013 auf Ihren Desktopcomputern.</span><span class="sxs-lookup"><span data-stu-id="c8110-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="c8110-105">In diesem Abschnitt werden die Remoteanrufsteuerungsfunktionen sowie die Anforderungen für die Bereitstellung der Remoteanrufsteuerung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8110-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="c8110-106">Durch die Integration zwischen einer Nebenstellenanlage und lync Server 2013 können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, die lync 2013-Benutzeroberfläche verwenden, um Anrufe auf Ihren PBX-Telefonen auf folgende Weise zu steuern:</span><span class="sxs-lookup"><span data-stu-id="c8110-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8110-107">Welche Remoteanrufsteuerungsfunktionen für den Benutzern letztendlich verfügbar sind, hängt von den Funktionen der Nebenstellenanlage ab, die zum Hosten des Nebenstellentelefons eines Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8110-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="c8110-108">Tätigen eines ausgehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="c8110-108">Make an outgoing call</span></span>

  - <span data-ttu-id="c8110-109">Beantworten eines eingehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="c8110-109">Answer an incoming call</span></span>

  - <span data-ttu-id="c8110-110">Beantworten eines eingehenden Anrufs mit einer Sofortnachricht</span><span class="sxs-lookup"><span data-stu-id="c8110-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8110-111">Das heißt, wenn die Telefonnummer des Anrufers einer Sofortnachrichtenadresse in der globalen Adressliste (GAL) Ihrer Organisation, in der lync-Kontaktliste des angerufenen oder in der Organisation eines Verbundpartners zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c8110-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="c8110-112">Weiterleiten eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="c8110-112">Transfer a call</span></span>

  - <span data-ttu-id="c8110-113">Weiterleiten eines eingehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="c8110-113">Forward an incoming call</span></span>

  - <span data-ttu-id="c8110-114">Halten von Anrufen</span><span class="sxs-lookup"><span data-stu-id="c8110-114">Place calls on hold</span></span>

  - <span data-ttu-id="c8110-115">Wechseln zwischen mehreren gleichzeitigen Anrufen</span><span class="sxs-lookup"><span data-stu-id="c8110-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="c8110-116">Beantworten eines zweiten Anrufs, nachdem bereits ein Anruf entgegengenommen wurde (Anklopffunktion)</span><span class="sxs-lookup"><span data-stu-id="c8110-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="c8110-117">DTMF-Ziffern (Dial Dual-Tone Multifrequency, Mehrfrequenzverfahren)</span><span class="sxs-lookup"><span data-stu-id="c8110-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="c8110-118">Eingabe von Notizen im Fenster "Unterhaltung" in Microsoft Office OneNote</span><span class="sxs-lookup"><span data-stu-id="c8110-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="c8110-119">Wenn ein Benutzer für die Remoteanrufsteuerung aktiviert ist, stellt lync 2013 dem Benutzer außerdem die folgenden Anrufinformationen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c8110-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="c8110-120">Kennung eines Anrufers nach Namen, wenn die Telefonnummer des Anrufers in der Kontaktliste eines Benutzers mit Remoteanrufsteuerung Microsoft Office Outlook-Messaging und-Zusammenarbeitsclient, lync-Kontaktliste oder der GAL Ihrer Organisation vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c8110-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="c8110-121">Vergangene eingehende und ausgehende Anrufe, die im Ordner "Unterhaltungsverlauf" in Outlook gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c8110-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="c8110-122">Benachrichtigungen über verpasste Anrufe, die an den Outlook-Posteingangsordner des Benutzers gesendet werden, aber nur generiert werden, wenn lync beim Empfang des eingehenden Anrufs läuft.</span><span class="sxs-lookup"><span data-stu-id="c8110-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="c8110-123">Remoteanrufsteuerung und Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="c8110-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="c8110-124">Obwohl Funktionen zur Remoteanrufsteuerung von Enterprise-VoIP-Features getrennt sind und Benutzer nicht für beide aktiviert werden können, bietet Enterprise-VoIP eine Teilmenge der Features, die auch für Benutzer verfügbar sind, die für die Remoteanrufsteuerung aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c8110-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="c8110-125">Wenn Enterprise-VoIP bereitgestellt wird, können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, lync für den Zugriff auf die folgenden Enterprise-VoIP-Funktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c8110-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="c8110-126">Tätigen und empfangen von Audioanrufen an einen anderen lync-Client</span><span class="sxs-lookup"><span data-stu-id="c8110-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="c8110-127">Teilnahme am Audioteil einer Konferenz, die von einem Benutzer erstellt wurde, der für Enterprise-VoIP aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c8110-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8110-128">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c8110-128">In This Section</span></span>

  - [<span data-ttu-id="c8110-129">Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8110-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

