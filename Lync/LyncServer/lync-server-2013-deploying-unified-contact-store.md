---
title: 'Lync Server 2013: Bereitstellen des einheitlichen Kontaktspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d224ec7a9c452c45f9f3471403301460a2a31cc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="fc660-102">Bereitstellen des einheitlichen Kontaktspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc660-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc660-103">_**Letztes Änderungsdatum des Themas:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="fc660-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="fc660-104">Für die Aktivierung des Unified Contact Stores in lync Server 2013 sind keine topologieeinstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc660-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="fc660-105">Für die Aktivierung des Unified Contact Store für Benutzer ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="fc660-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="fc660-106">Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).</span><span class="sxs-lookup"><span data-stu-id="fc660-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="fc660-107">Benutzer melden sich mindestens einmal mit lync 2013 an.</span><span class="sxs-lookup"><span data-stu-id="fc660-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="fc660-108">Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer mit lync 2013 anmeldet, kann der Benutzer über lync 2013, Outlook 2013 oder Outlook Web Access auf seine lync-Kontakte zugreifen und diese verwalten.</span><span class="sxs-lookup"><span data-stu-id="fc660-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="fc660-109">Der Benutzer muss nicht bei lync angemeldet sein, um seine Kontakte aus Outlook oder Outlook Web Access zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fc660-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fc660-110">Wenn ein Benutzer sich nach der Migration von lync 2010 anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (das heißt, Sie können diese Kontakte hinzufügen, löschen, verschieben, markieren, Markierung oder ändern).</span><span class="sxs-lookup"><span data-stu-id="fc660-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fc660-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fc660-111">In This Section</span></span>

  - [<span data-ttu-id="fc660-112">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc660-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="fc660-113">Migrieren von Benutzern zum einheitlichen Kontaktspeicher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc660-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="fc660-114">Zurücksetzen von migrierten Benutzern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc660-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

