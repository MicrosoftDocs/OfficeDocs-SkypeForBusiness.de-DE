---
title: 'Lync Server 2013: Übersicht über die Überwachung'
description: 'Lync Server 2013: Übersicht über die Überwachung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f27d6aff71442c6193c220154af231481399ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577321"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="43bea-103">Übersicht über die Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bea-103">Overview of monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43bea-104">_**Letztes Änderungsstand des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="43bea-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="43bea-105">In Microsoft lync Server 2013 wird die Überwachung verwendet, um Verwendungsinformationen und QoE-Daten (Quality of Experience) zu den Kommunikationssitzungen zu erfassen, an denen Ihre Benutzer beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="43bea-105">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="43bea-106">Eine Sitzung ist ein allgemeiner Begriff, der sich auf die Verbindungen von Benutzern mit folgenden Elementen bezieht:</span><span class="sxs-lookup"><span data-stu-id="43bea-106">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="43bea-107">Konferenz</span><span class="sxs-lookup"><span data-stu-id="43bea-107">Conference</span></span>

  - <span data-ttu-id="43bea-108">Konferenzmodalitäten (wie Audio/Video oder Anwendungsfreigabe)</span><span class="sxs-lookup"><span data-stu-id="43bea-108">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="43bea-109">Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf</span><span class="sxs-lookup"><span data-stu-id="43bea-109">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43bea-110">Lync Server 2013 verfolgt die Informationen zu jeder Sitzung: Wer hat wen angerufen? welche Endpunkte in der Sitzung verwendet wurden; wie lange dauerte die Sitzung zuletzt; Was war die wahrgenommene Qualität der Sitzung; Und so weiter.</span><span class="sxs-lookup"><span data-stu-id="43bea-110">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="43bea-111">In lync Server wird jedoch der tatsächliche Aufruf selbst nicht aufgezeichnet und gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43bea-111">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="43bea-112">Dies umfasst auch Sofortnachrichtensitzungen: Obwohl lync Server Informationen zu Chatsitzungen aufzeichnet, wird keine Aufzeichnung aller Sofortnachrichten verwaltet, die während der Sitzung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="43bea-112">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="43bea-113">Die von lync Server gesammelten Anruf Detailinformationen können für eine beliebige Anzahl von Verwendungszwecken verwendet werden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="43bea-113">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="43bea-114">**Renditeanalyse (Return on Investment, ROI)**.</span><span class="sxs-lookup"><span data-stu-id="43bea-114">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="43bea-115">Administratoren können die von Monitoring Server gesammelten Nutzungsdaten mit ähnlichen Daten vergleichen, die für Ihr bisheriges Telefoniesystem erfasst wurden, um Kosteneinsparungen anzuzeigen und die Bereitstellung von lync Server zu rechtfertigen.</span><span class="sxs-lookup"><span data-stu-id="43bea-115">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="43bea-p104">**Verwalten des Gerätebestands**. Informationen bezüglich der Inventarverwaltung unterstützen Administratoren bei der Identifizierung alter Geräte, die ersetzt werden müssen. Außerdem können auf diese Weise kostenintensive Geräte identifiziert werden, die anscheinend gar nicht genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="43bea-p104">**Device Inventory Management**. Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="43bea-118">Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="43bea-118">Help Desk.</span></span> <span data-ttu-id="43bea-119">Durch die Problembehandlung von Daten können Supporttechniker ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, und zwar ohne dass Server-oder clientseitige Protokolle erfasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="43bea-119">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="43bea-120">Diese Informationen können von Supportmitarbeitern, die nicht über umfassende technische Kenntnisse in Microsoft lync 2013 und lync Server 2013 verfügen, leicht zugänglich und verstanden werden.</span><span class="sxs-lookup"><span data-stu-id="43bea-120">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="43bea-p106">**Systemproblembehandlung**. Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Tätigen eines Anrufs oder das Senden einer Sofortnachricht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="43bea-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="43bea-123">Zusätzlich zu diesen grundlegenden Anrufinformationen stellt der Monitoring Server auch einen Mechanismus bereit, der SIP-Endpunkten (wie lync 2013) ermöglicht, Informationen zur Problembehandlung bereitzustellen, auf die der Server andernfalls keinen Zugriff hat:</span><span class="sxs-lookup"><span data-stu-id="43bea-123">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="43bea-p107">**Medienmetriken mit Auswirkungen auf die Qualität**. Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs. Sie stellen eine Art "Reiseprotokoll" des Anrufs durch das Netzwerk dar und beinhalten Daten wie Paketverluste, Jitter und Roundtripzeiten. Anhand dieser Informationen lässt sich erkennen, was mit dem Anruf zwischen dem Verlassen des einen Benutzerendpunkts und dem Eintreffen am anderen Benutzerendpunkt passiert.</span><span class="sxs-lookup"><span data-stu-id="43bea-p107">**Media Metrics that Impact Quality**. These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network. These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="43bea-127">**Dem Endbenutzer gemeldete Probleme**.</span><span class="sxs-lookup"><span data-stu-id="43bea-127">**Issues Reported to the End User**.</span></span> <span data-ttu-id="43bea-128">Zu diesen Metriken gehören Benachrichtigungen über schlechte Qualität, die Endbenutzern in Fällen angezeigt lync 2013, in denen Sie zu weit von einem Mikrofon entfernt sind, zu leise sprechen, eine schlechte Netzwerkverbindung haben oder eine schlechte Qualität aufweisen, da ein anderes Programm auf dem Computer die verfügbaren Ressourcen verbraucht.</span><span class="sxs-lookup"><span data-stu-id="43bea-128">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="43bea-p109">**Umgebungsinformationen**. Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde und Angaben darüber, ob eine WLAN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="43bea-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="43bea-p110">Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, von dem der Anruf bereitgestellt wurde. Sie müssen nichts tun, damit diese Informationen von den Endpunkten übertragen werden. Das SIP-Protokoll ist bereits entsprechend konfiguriert. Wenn Sie diese Informationen jedoch erfassen und speichern möchten, müssen Sie die Überwachung aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von den Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein SQL Server-Datenbankpaar weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="43bea-p110">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call. You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol. However, if you want to collect and store that information, then you need to install and enable monitoring. If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="43bea-135">Beachten Sie, dass der Prozess der Installation und Konfiguration der Überwachung in lync Server 2013 vereinfacht wurde.</span><span class="sxs-lookup"><span data-stu-id="43bea-135">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="43bea-136">In früheren Versionen der Software war für die Überwachung eine separate Monitoring Server Rolle erforderlich, was in der Regel einen separaten Computer bedeutete, der als Monitoring Server verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="43bea-136">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="43bea-137">In lync Server 2013 wurde jedoch die Monitoring Server Rolle eliminiert.</span><span class="sxs-lookup"><span data-stu-id="43bea-137">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="43bea-138">Stattdessen wurde der Überwachungsdienst (in Form von "Unified Data Collection Agents") in allen Front-End-Servern zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="43bea-138">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="43bea-139">Dies hat mindestens zwei Hauptvorteile.</span><span class="sxs-lookup"><span data-stu-id="43bea-139">This has at least two major benefits.</span></span> <span data-ttu-id="43bea-140">Anordnung des Überwachungsdiensts:</span><span class="sxs-lookup"><span data-stu-id="43bea-140">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="43bea-141">Verringert die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="43bea-141">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="43bea-142">Weniger Monitoring Server-Rollen bedeuten gleichzeitig weniger Kosten, da weniger dedizierte Server für die Überwachung unterhalten werden müssen.</span><span class="sxs-lookup"><span data-stu-id="43bea-142">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="43bea-143">Reduziert die Komplexität von lync Server 2013-Setup und-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="43bea-143">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="43bea-144">Durch das Platzieren der Überwachungsdienste auf den einzelnen Front-End-Servern entfällt die Notwendigkeit der Installation, Konfiguration und Verwaltung von Monitoring Server-Rollen.</span><span class="sxs-lookup"><span data-stu-id="43bea-144">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="43bea-145">Weitere Informationen finden Sie im Thema [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md) im Bereitstellungshandbuch für lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="43bea-145">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

