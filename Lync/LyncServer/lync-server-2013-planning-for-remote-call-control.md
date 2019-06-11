---
title: 'Lync Server 2013: Planen der Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="9408f-102">Planen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9408f-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9408f-103">_**Letztes Änderungsdatum des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="9408f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="9408f-104">In lync Server 2013 ermöglicht die Unterstützung von Szenarien für die Remoteanrufsteuerung, dass Benutzer Ihre PBX-Telefone (Private Branch Exchange) mithilfe von lync 2013 auf Ihren Desktopcomputern steuern können.</span><span class="sxs-lookup"><span data-stu-id="9408f-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="9408f-105">In diesem Abschnitt werden die Features für die Remoteanrufsteuerung und die Anforderungen für die Bereitstellung der Remoteanrufsteuerung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9408f-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="9408f-106">Durch die Integration zwischen einer Telefonanlage und lync Server 2013 können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, die lync 2013-Benutzeroberfläche verwenden, um Anrufe auf Ihren Telefonanlagen zu steuern, und zwar wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9408f-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9408f-107">Letztendlich bestimmen die Funktionen der Telefonanlage, die das PBX-Telefon eines Benutzers hostet, die Features für die Remoteanrufsteuerung, die für diesen Benutzer verfügbar sein werden.</span><span class="sxs-lookup"><span data-stu-id="9408f-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="9408f-108">Führen eines ausgehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="9408f-108">Make an outgoing call</span></span>

  - <span data-ttu-id="9408f-109">Annehmen eines eingehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="9408f-109">Answer an incoming call</span></span>

  - <span data-ttu-id="9408f-110">Annehmen eines eingehenden Anrufs mit einer Chatnachricht</span><span class="sxs-lookup"><span data-stu-id="9408f-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9408f-111">Das heißt, wenn die Telefonnummer des Anrufers einer Chat Adresse in der globalen Adressliste (GAL) Ihrer Organisation, in der lync-Kontaktliste des berufenen oder in der Organisation eines Verbundpartners zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9408f-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="9408f-112">Anrufdurchstellung</span><span class="sxs-lookup"><span data-stu-id="9408f-112">Transfer a call</span></span>

  - <span data-ttu-id="9408f-113">Weiterleiten eines eingehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="9408f-113">Forward an incoming call</span></span>

  - <span data-ttu-id="9408f-114">Anrufe in Wartestellung setzen</span><span class="sxs-lookup"><span data-stu-id="9408f-114">Place calls on hold</span></span>

  - <span data-ttu-id="9408f-115">Wechseln zwischen mehreren gleichzeitigen anrufen</span><span class="sxs-lookup"><span data-stu-id="9408f-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="9408f-116">Annehmen eines zweiten Anrufs während eines Anrufs (also Anklopfen)</span><span class="sxs-lookup"><span data-stu-id="9408f-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="9408f-117">Dial Dual-Tone-mehr Frequenz (DTMF)-Ziffern</span><span class="sxs-lookup"><span data-stu-id="9408f-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="9408f-118">Geben Sie im Unterhaltungsfenster Notizen in Microsoft Office OneNote-Notizenprogramm ein.</span><span class="sxs-lookup"><span data-stu-id="9408f-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="9408f-119">Wenn ein Benutzer für die Remoteanrufsteuerung aktiviert ist, stellt lync 2013 dem Benutzer zudem die folgenden Anrufinformationen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="9408f-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="9408f-120">Kennung eines Anrufers anhand des Namens, wenn die Telefonnummer des Anrufers in der Liste "Kontakte" des Microsoft Office Outlook-Messaging-und-Zusammenarbeits-Clients, der lync-Kontaktliste oder der GAL Ihrer Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9408f-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="9408f-121">Frühere eingehende und ausgehende Anrufe, die im Ordner "Konversations Verlauf" in Outlook gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="9408f-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="9408f-122">Benachrichtigungen über verpasste Anrufe, die an den Outlook-Posteingangsordner des Benutzers gesendet werden, aber nur generiert werden, wenn lync ausgeführt wird, wenn der eingehende Anruf eingegangen ist.</span><span class="sxs-lookup"><span data-stu-id="9408f-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="9408f-123">Remote Anrufsteuerung und Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="9408f-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="9408f-124">Obwohl die Features für die Remoteanrufsteuerung von den Enterprise-VoIP-Features getrennt sind und Benutzer nicht für beide Funktionen aktiviert werden können, bietet Enterprise-VoIP eine Teilmenge der Features, die auch für Benutzer verfügbar sind, die für die Remoteanrufsteuerung aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9408f-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="9408f-125">Wenn Enterprise-VoIP bereitgestellt wird, können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, lync für den Zugriff auf die folgenden Enterprise-VoIP-Features verwenden:</span><span class="sxs-lookup"><span data-stu-id="9408f-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="9408f-126">Tätigen und empfangen von Audioanrufen an einen anderen lync-Client</span><span class="sxs-lookup"><span data-stu-id="9408f-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="9408f-127">Teilnehmen am Audioteil einer Konferenz, die von einem Benutzer erstellt wurde, der für Enterprise-VoIP aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="9408f-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9408f-128">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9408f-128">In This Section</span></span>

  - [<span data-ttu-id="9408f-129">Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9408f-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

