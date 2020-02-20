---
title: Lync Server 2013 Chat und Anwesenheit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1c612102cb34113c96d02e9e408563a16bfb3bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="25edf-102">Chat und Anwesenheitsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25edf-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25edf-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="25edf-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="25edf-104">Instant Messaging (Sofortnachrichten) und Anwesenheit werden in jeder lync Server-Bereitstellung automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="25edf-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="25edf-105">*Anwesenheitsinformationen* ermöglichen es Benutzern, Kollegen zum richtigen Zeitpunkt und über den richtigen Kommunikationskanal zu erreichen und erhöhen so die Produktivität in der Arbeitsumgebung.</span><span class="sxs-lookup"><span data-stu-id="25edf-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="25edf-106">Zu den Anwesenheitsinformationen eines Benutzers gehören Informationen wie Verfügbarkeit, Kommunikationsbereitschaft, weitere Hinweise (z. B. Standort und Status) und Angaben dazu, über welchen Kommunikationskanal der Benutzer erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="25edf-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="25edf-107">Präsenz wird in lync Server mit Bildern, Standortinformationen und einem umfangreichen Satz von Anwesenheitsstatus verbessert, der "aus Arbeit", "nicht stören" und "gleich wieder da", zusätzlich zu den grundlegenden Zuständen wie "verfügbar", "beschäftigt" und "in einer Konferenz" umfasst.</span><span class="sxs-lookup"><span data-stu-id="25edf-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="25edf-108">Administratoren können außerdem benutzerdefinierte, organisationsspezifische Anwesenheitszustände definieren.</span><span class="sxs-lookup"><span data-stu-id="25edf-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="25edf-p102">Mit der Kontaktverwaltung und den Benutzerzugriffsoptionen können Benutzer steuern, welche Informationen anderen Benutzern angezeigt werden. Benutzer können verschiedene Kontaktebenen festlegen, für die jeweils verschiedene Stufen von Anwesenheitsinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="25edf-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="25edf-p103">Mit einem einfachen Blick auf eine Kontaktliste erhalten Benutzer alle für sie relevanten Informationen. Einfache farbige Symbole weisen auf den Anwesenheitsstatus anderer Benutzer hin, und es werden Bilder und Standorte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25edf-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="25edf-113">Bei der Integration von lync Server und anderen Produkten wie Outlook und SharePoint wird jedes Mal, wenn der Name eines Kontakts angezeigt wird, beispielsweise in einer e-Mail-Nachricht oder auf einer Teamwebsite, auch der Status und die Kontaktinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25edf-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="25edf-114">Wenn Sie Exchange 2013 bereitstellen, können lync Server und Exchange 2013 darüber hinaus einen einheitlichen Kontaktspeicher freigeben, auf den von Clients der beiden Produkte zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="25edf-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="25edf-115">Mit Chatnachrichten in lync Server können sich Benutzer schnell und zeitnah informieren.</span><span class="sxs-lookup"><span data-stu-id="25edf-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="25edf-116">Wenn es Ihnen lieber ist, können Ihre Benutzer auch mit Benutzern öffentlicher Chat Netzwerke wie MSN/Windows Live, Yahoo\!und AOL kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="25edf-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="25edf-117">Beachten Sie, dass für Verbindungen mit öffentlichen Chat Diensten mit Windows Live, AOL und Yahoo möglicherweise eine separate Lizenz erforderlich ist.\!</span><span class="sxs-lookup"><span data-stu-id="25edf-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="25edf-118">Lync Server umfasst auch die Kompatibilität mit dem Extensible Messaging and Presence Protocol (XMPP), damit Ihre Benutzer Chatnachrichten und Anwesenheitsinformationen mit Benutzern von XMPP-Diensten wie Google Talk austauschen können.</span><span class="sxs-lookup"><span data-stu-id="25edf-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="25edf-119">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="25edf-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="25edf-120">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="25edf-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="25edf-121">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="25edf-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="25edf-122">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="25edf-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="25edf-123">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="25edf-123">has been announced.</span></span> <span data-ttu-id="25edf-124">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25edf-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="25edf-125">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="25edf-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="25edf-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="25edf-126">Messenger.</span></span> <span data-ttu-id="25edf-127">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="25edf-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="25edf-128">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="25edf-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="25edf-129">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="25edf-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="25edf-130">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="25edf-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="25edf-131">Anhand der aufgezeichneten Unterhaltungen können Benutzer ihre älteren Sofortnachrichten verfolgen und Informationen abrufen, die möglicherweise Monate zuvor per Sofortnachricht mitgeteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="25edf-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="25edf-132">Mit dem Feature für beständigen Chat können Benutzer an mehrteiligen, themenbasierten Unterhaltungen teilnehmen, die im Laufe der Zeit beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="25edf-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="25edf-133">In Chatrooms (Diskussionsforen) veröffentlichte Nachrichten können langlebig sein (d. h. dauerhaft verfügbar), sodass Benutzer aus unterschiedlichen Standorten und Abteilungen an dem Chat teilnehmen können, selbst wenn sie nicht alle zum gleichen Zeitpunkt online sind.</span><span class="sxs-lookup"><span data-stu-id="25edf-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="25edf-134">Wenn Ihre Organisation rechtliche Vorschriften bezüglich Compliance einhalten muss, können Sie eine Archivierungsfunktion für Nachrichten bereitstellen, um die Inhalte von Sofortnachrichten für alle Benutzer in Ihrer Organisation oder auch nur für bestimmte festgelegte Benutzer zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="25edf-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="25edf-135">Wenn Sie auch Exchange 2013 bereitstellen, kann Ihr Chat Archiv in das in-situ-Speicherfeature von Exchange integriert werden, um eine einfache Verwaltungserfahrung für ihre Kompatibilität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="25edf-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

