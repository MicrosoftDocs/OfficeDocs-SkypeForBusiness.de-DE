---
title: 'Lync Server 2013: Chat und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18eb3d4a7fa5daaa59817d2eefde7af3a8e3f494
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="5fcf2-102">Chat und Anwesenheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcf2-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fcf2-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5fcf2-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5fcf2-104">Instant Messaging (im) und Anwesenheit werden in jeder lync Server-Bereitstellung automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="5fcf2-105">\*\* Mit Anwesenheitsinformationen können Benutzer sich zur richtigen Zeit mit der richtigen Kommunikationsform an Kollegen wenden und so zu einer produktiveren Arbeitsumgebung führen.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="5fcf2-106">Die Anwesenheit eines Benutzers ist eine Sammlung von Informationen, die Verfügbarkeit, Kommunikationsbereitschaft, zusätzliche Notizen (wie Standort und Status) sowie die Art und Weise, wie der Benutzer kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="5fcf2-107">Der Anwesenheitsstatus wird in lync Server mit Bildern, Standortinformationen und einem umfangreichen Satz an Anwesenheitsstatus verbessert, in dem "aus Arbeit", "nicht stören" und "gleich zurück", zusätzlich zu den grundlegenden Zuständen wie "verfügbar", "beschäftigt" und "in einer Konferenz" enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="5fcf2-108">Administratoren können auch benutzerdefinierte, organisationsspezifische Anwesenheitsstatus definieren.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="5fcf2-109">Mit den Optionen für die Kontaktverwaltung und den Benutzer Zugriff können Benutzer steuern, welche Informationen andere Personen sehen können.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="5fcf2-110">Benutzer können unterschiedliche Ebenen von Kontakten einrichten, die jeweils unterschiedliche Ebenen von Anwesenheitsinformationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="5fcf2-111">Wenn Sie sich einfach eine Kontaktliste ansehen, können Benutzer alles finden, was Sie auf einen Blick wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="5fcf2-112">Einfache farbige Symbole deuten auf den Anwesenheitsstatus anderer Benutzer hin, und Bild und Standort werden ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="5fcf2-113">Bei der Integration zwischen lync Server und anderen Produkten wie Outlook und SharePoint wird immer dann der Status und die Kontaktinformationen angezeigt, wenn der Name eines Kontakts angezeigt wird, beispielsweise in einer e-Mail-Nachricht oder auf einer Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="5fcf2-114">Wenn Sie Exchange 2013 bereitstellen, können lync Server und Exchange 2013 zudem einen einheitlichen Kontaktspeicher freigeben, auf den Clients eines der beiden Produkte zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="5fcf2-115">Mit Chatnachrichten in lync Server können Benutzer sich schnell und zeitnah über Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="5fcf2-116">Wenn Sie möchten, können Ihre Benutzer auch mit Benutzern von öffentlichen Chat Netzwerken wie MSN/Windows Live, Yahoo\!und AOL kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="5fcf2-117">Beachten Sie, dass für öffentliche Chat Verbindungen mit Windows Live, AOL und Yahoo möglicherweise eine separate Lizenz erforderlich ist.\!</span><span class="sxs-lookup"><span data-stu-id="5fcf2-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="5fcf2-118">Lync Server umfasst auch die Kompatibilität von Extensible Messaging and Presence Protocol (XMPP), damit Ihre Benutzer Chatnachrichten und Anwesenheitsinformationen mit Benutzern von XMPP-Diensten wie Google Talk austauschen können.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="5fcf2-119">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5fcf2-120">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="5fcf2-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5fcf2-121">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="5fcf2-122">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fcf2-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5fcf2-123">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-123">has been announced.</span></span> <span data-ttu-id="5fcf2-124">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="5fcf2-125">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5fcf2-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-126">Messenger.</span></span> <span data-ttu-id="5fcf2-127">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="5fcf2-128">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5fcf2-129">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5fcf2-130">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5fcf2-131">Der Konversations Verlauf ermöglicht Benutzern, alte Chat Unterhaltungen nachzuverfolgen und Informationen abzurufen, die möglicherweise bereits vor Monaten von Chatnachrichten mitgeteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="5fcf2-132">Das Feature "beständiger Chat" ermöglicht Benutzern die Teilnahme an mehrteiligen, themenbasierten Konversationen, die im Laufe der Zeit fortbestehen.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="5fcf2-133">Nachrichten, die in Chatrooms (Diskussionsforen) gepostet wurden, können persistent sein (im Laufe der Zeit verfügbar), damit Personen an verschiedenen Standorten und Abteilungen teilnehmen können, selbst wenn Sie nicht alle gleichzeitig online sind.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="5fcf2-134">Wenn Ihre Organisation Konformitätsrichtlinien beachten muss, können Sie eine Nachrichten Archivierungsfunktion bereitstellen, um den Inhalt von Sofortnachrichten für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer, die Sie angeben, zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="5fcf2-135">Wenn Sie auch Exchange 2013 bereitstellen, kann Ihr im-Archiv in das in-situ-Speicherfeature von Exchange integriert werden, um eine einheitliche Verwaltungsoberfläche für Ihre Compliance bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5fcf2-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

