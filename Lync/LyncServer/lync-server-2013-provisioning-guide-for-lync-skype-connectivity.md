---
title: 'Lync Server 2013: Leitfaden zur Anleitung zur Lync-Skype Konnektivität'
description: 'Lync Server 2013: Leitfaden zur Anleitung zur Lync-Skype Konnektivität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9859a7a621ba4329fe0436fe50a0d9de1d0ae1ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569091"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="aef92-103">Leitfaden zur Anleitung zur Lync-Skype Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aef92-103">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef92-104">_**Letztes Änderungsstand des Themas:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="aef92-104">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="aef92-105">Lync Server 2013 unterstützt die Konnektivität mit Skype.</span><span class="sxs-lookup"><span data-stu-id="aef92-105">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="aef92-106">Diese Konnektivität ermöglicht es ihren lync 2013 Benutzern, Skype-Kontakte mithilfe des Microsoft-Kontos des Skype-Benutzers (MSA) hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="aef92-106">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="aef92-107">Skype-Clients können auch lync-Benutzer zu Ihrer Kontaktliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aef92-107">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="aef92-108">Basierend auf Richtlinien, die in lync Server administrativ festgelegt sind, können lync-und Skype-Benutzer über Chatnachrichten kommunizieren, die Anwesenheit von einander anzeigen und Audio-und Videoanrufe initiieren.</span><span class="sxs-lookup"><span data-stu-id="aef92-108">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="aef92-109">Lync-Skype Konnektivität ist auch ein Feature von lync Online und kann für lync Online Kunden aus der lync-Verwaltungskonsole im Microsoft 365 Admin Center aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="aef92-109">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="aef92-110">Wenn lync Server bereits für die Verbindung mit Windows Messenger mithilfe der öffentlichen Instant Messaging-Konnektivität (PIC) konfiguriert ist, ist Ihre Bereitstellung bereits für die Lync-Skype Konnektivität konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="aef92-110">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="aef92-111">Die einzige Änderung, die Sie möglicherweise in Frage stellen sollten, ist, den vorhandenen Messenger PIC-Eintrag als Skype umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="aef92-111">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="aef92-112">Ausführliche Informationen finden Sie weiter unten in diesem Handbuch unter Konfigurieren der Skype PIC-Anbieter Einstellung für lync.</span><span class="sxs-lookup"><span data-stu-id="aef92-112">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aef92-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aef92-113">In This Section</span></span>

  - [<span data-ttu-id="aef92-114">Hinweis zu Lync-Skype Konnektivität in lync Server 2013 für lync Online Kunden</span><span class="sxs-lookup"><span data-stu-id="aef92-114">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="aef92-115">Zugreifen auf die lync Server-Website für die Konnektivität von öffentlichen Instant Messaging-Diensten von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aef92-115">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="aef92-116">Aktivieren Lync-Skype Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aef92-116">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="aef92-117">Verwenden Lync-Skype Konnektivität in lync Server 2013 als Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="aef92-117">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="aef92-118">Häufig gestellte Fragen: lync Server 2013 für Skype-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="aef92-118">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

