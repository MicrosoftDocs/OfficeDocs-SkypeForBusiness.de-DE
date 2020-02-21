---
title: Lync Server 2013 Enterprise-VoIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="e7562-102">Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7562-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7562-103">_**Letztes Änderungsstand des Themas:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="e7562-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="e7562-104">Mit Enterprise-VoIP bietet lync Server ein eigenständiges VoIP-Angebot (Voice over Internet Protocol) zum Erweitern oder ersetzen herkömmlicher Nebenstellenanlagen (Private Branch Exchange, Nebenstellenanlage).</span><span class="sxs-lookup"><span data-stu-id="e7562-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="e7562-105">Enterprise-VoIP-Benutzer können Kollegen im VoIP-Netzwerk oder in der Nebenstellenanlage Ihrer Organisation anrufen, und Sie können herkömmliche Telefonnummern außerhalb Ihrer Organisation anrufen.</span><span class="sxs-lookup"><span data-stu-id="e7562-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="e7562-106">Die Enterprise-VoIP-Lösung umfasst allgemeine Anruffunktionen wie Antwort, Weiterleitung, Übertragung, Aufbewahrung, Umleitung, Freigabe und Parken sowie erweiterte 9-1-1 (E9-1-1)-Anrufe (E9-1-1 ist nur in den USA verfügbar.) Enterprise-VoIP unterstützt auch eine Vielzahl von aktuellen und älteren IP-und USB-Geräten.</span><span class="sxs-lookup"><span data-stu-id="e7562-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="e7562-107">Platzieren und empfangen von Anrufen</span><span class="sxs-lookup"><span data-stu-id="e7562-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="e7562-108">Mithilfe von lync können Benutzer Anrufe tätigen, indem Sie einen Namen oder eine Telefonnummer auf der Tastatur eingeben oder eine Wähltastatur auf dem Bildschirm verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7562-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="e7562-109">Benutzer können Anrufe auch direkt aus der Kontaktliste initiieren.</span><span class="sxs-lookup"><span data-stu-id="e7562-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="e7562-110">Sie können auch lync Phone Edition-Geräte bereitstellen, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e7562-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="e7562-111">Benutzer können mehrere Telefongeräte bei lync Server registriert haben und problemlos zwischen ihnen wechseln können.</span><span class="sxs-lookup"><span data-stu-id="e7562-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="e7562-112">Benutzer werden auf allen Geräten gleichzeitig auf eingehende Anrufe mit anpassbaren Klingeltönen auf IP-Telefongeräten und einer Benachrichtigung ähnlich einer Sofortnachricht auf Ihrem PC aufmerksam gemacht.</span><span class="sxs-lookup"><span data-stu-id="e7562-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="e7562-113">Benutzer können auch eine einzelne Telefonnummer festlegen, die eine Verbindung zu Ihrem Telefon, PC und Mobiltelefon herstellt, sodass Sie unabhängig von ihrer Position erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="e7562-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="e7562-114">Grundlegende Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="e7562-114">Basic Call Features</span></span>

<span data-ttu-id="e7562-115">Während eines Anrufs kann ein Benutzer zusätzliche eingehende Anrufe beantworten oder ausgehende Anrufe initiieren, und der vorhandene aktive Anruf wird automatisch in den Haltestatus versetzt.</span><span class="sxs-lookup"><span data-stu-id="e7562-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="e7562-116">Anrufe können von einem Benutzer zu einem anderen übertragen werden, entweder direkt oder nachdem der erste Benutzer mit dem zweiten Benutzer privat gesprochen hat.</span><span class="sxs-lookup"><span data-stu-id="e7562-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="e7562-117">Benutzer können auch Anrufe an ein anderes Gerät übertragen; Beispielsweisekönnten Sie einen aktiven Anruf an Ihr Mobiltelefon übertragen, wenn Sie die Tür ihres Büros verlassen.</span><span class="sxs-lookup"><span data-stu-id="e7562-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="e7562-118">Umfassendere Kommunikation</span><span class="sxs-lookup"><span data-stu-id="e7562-118">Richer Communications</span></span>

<span data-ttu-id="e7562-119">Wenn Sie mit einem anderen Benutzer mit lync kommunizieren, können Benutzer dem Anruf problemlos Text, Video oder Desktopfreigaben hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7562-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="e7562-120">Das Feature "do-not-Disturb" ist in die Anwesenheitseinstellungen in lync integriert.</span><span class="sxs-lookup"><span data-stu-id="e7562-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="e7562-121">Mit Exchange Unified Messaging (um) können lync und lync Server in Microsoft Exchange Server 2013 und Microsoft Outlook 2013 integriert werden.</span><span class="sxs-lookup"><span data-stu-id="e7562-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="e7562-122">Benutzer können sehen, ob Sie neue Voicemails sowohl in Ihrem lync-Fenster als auch in e-Mail haben.</span><span class="sxs-lookup"><span data-stu-id="e7562-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="e7562-123">Während Sie in der e-Mail klicken, können Sie die Voicemail-Audiodaten in einer e-Mail-Nachricht wiedergeben oder ein Transkript der Voicemailnachricht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e7562-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="e7562-124">Erweiterte Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="e7562-124">Advanced Calling Features</span></span>

<span data-ttu-id="e7562-125">Enterprise-VoIP umfasst auch mehrere erweiterte Anruffunktionen wie lync-Anrufdelegierung, Teamanrufe, gruppenanrufannahme und Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e7562-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="e7562-126">Mit der lync-Anrufdelegierung können Benutzer die Anrufbehandlung an einen oder mehrere Assistenten delegieren, indem Sie die Einstellungen für die **Anrufweiterleitung**für **Tools** \> \*\*\*\* \> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e7562-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="e7562-127">Der Stellvertreter kann mehrere Anruf Aufgaben im Namen des Benutzers ausführen, einschließlich der Überprüfung von anrufen, das Platzieren von Anrufen und das Initiieren von Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="e7562-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7562-128">Möglicherweise suchen Sie nach einer anderen ähnlich benannten Funktion, der lync-Kalender Delegierung.</span><span class="sxs-lookup"><span data-stu-id="e7562-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="e7562-129">Sie erfordert nicht die Enterprise-VoIP-Funktion und ermöglicht Benutzern das Planen von Online-lync-Besprechungen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="e7562-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="e7562-130">Wenn Sie hier auf der Suche nach diesen Informationen sind, empfehlen wir das Auschecken von "CsClientPolicy", um Informationen zum Aktivieren der Exchange-Delegat <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">-</A> Synchronisierung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e7562-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="e7562-131">Team Anrufe ermöglichen es einem Benutzer, eingehende Anrufe gleichzeitig an den Telefonen von Teamkollegen zu klingeln, damit alle Personen im Team den Anruf annehmen können.</span><span class="sxs-lookup"><span data-stu-id="e7562-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="e7562-132">Group Call Pickup, ein neues Feature in kumulierten Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe an Ihre Kollegen von ihren eigenen Telefonen aus zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="e7562-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="e7562-133">Die gruppenanrufannahme unterscheidet sich von der Team Berufung in erster Linie dadurch, dass ein eingehender Anruf nur am Telefon des beabsichtigten Empfängers klingelt, aber jeder andere Benutzer kann ihn über die Wahl einer Gruppennummer für die Anrufannahme wählen.</span><span class="sxs-lookup"><span data-stu-id="e7562-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="e7562-134">Reaktionsgruppen können für Warteschlangen und intelligent weiterleiten von Anrufen an designierte Agents eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="e7562-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="e7562-135">Häufige Verwendungen sind IT-Helpdesks, Hotlines für Personalwesen und andere interne Kontakt Center.</span><span class="sxs-lookup"><span data-stu-id="e7562-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="e7562-136">Enterprise-VoIP-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="e7562-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="e7562-137">Lync Server verwendet Standards und veröffentlichte Schnittstellen, um mit der vorhandenen Infrastruktur zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7562-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="e7562-138">Es unterstützt sowohl Gateway-als auch SIP-Optionen (beispielsweise SIP-Trunking) für die Zusammenschaltung mit IP-Nebenstellen Systemen und den PSTN-Netzwerken, sodass Sie Benutzer über einen Zeitraum zu Enterprise-VoIP migrieren und gleichzeitig die Unterbrechungen minimieren können.</span><span class="sxs-lookup"><span data-stu-id="e7562-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="e7562-139">Lync Server unterstützt herkömmliche Codecs wie g. 711, g. 722 und g. 723.1 für die Interoperabilität mit herkömmlichen VoIP-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="e7562-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="e7562-140">Mit der Anrufsteuerung (Call Admission Control, CAC) können Administratoren Beschränkungen für den lync Server von Sprach-und Videodaten Verkehr für eingeschränkte Netzwerkverbindungen festlegen und die Aktion angeben, die ausgeführt werden soll, wenn ein neuer Anruf den Höchstwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e7562-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="e7562-141">Die Aktionen können Routing durch einen alternativen Pfad einschließen oder den Anruf ablehnen.</span><span class="sxs-lookup"><span data-stu-id="e7562-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="e7562-142">Lync Server arbeitet mit Survivable Branch-Appliances von Drittanbietern zusammen, um lokale Anrufdienste und Verbindungen mit PSTN in Zweigniederlassungen bereitzustellen, falls ein WAN-Fehler am zentralen Standort vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e7562-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

