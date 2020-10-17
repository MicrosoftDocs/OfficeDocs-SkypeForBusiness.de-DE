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
ms.openlocfilehash: a94d19026d2df00caf8079914d8b93bd70a87f6d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522852"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="432f0-102">Bereitstellen des einheitlichen Kontaktspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="432f0-102">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="432f0-103">_**Letztes Änderungsstand des Themas:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="432f0-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="432f0-104">Für die Aktivierung des einheitlichen Kontaktspeichers in lync Server 2013 müssen keine topologieeinstellungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="432f0-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="432f0-105">Wenn Sie den Kontaktspeicher für Benutzer aktivieren möchten, müssen Sie die folgenden Punkte sicherstellen:</span><span class="sxs-lookup"><span data-stu-id="432f0-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="432f0-106">Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).</span><span class="sxs-lookup"><span data-stu-id="432f0-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="432f0-107">Benutzer melden sich mindestens einmal mit lync 2013 an.</span><span class="sxs-lookup"><span data-stu-id="432f0-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="432f0-108">Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer mit lync 2013 anmeldet, kann der Benutzer über lync 2013, Outlook 2013 oder Outlook Web Access auf seine lync-Kontakte zugreifen und diese verwalten.</span><span class="sxs-lookup"><span data-stu-id="432f0-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="432f0-109">Der Benutzer muss nicht bei lync angemeldet sein, um seine Kontakte in Outlook oder Outlook Web Access verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="432f0-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="432f0-110">Wenn sich ein Benutzer von lync 2010 nach der Migration anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (also hinzufügen, löschen, verlagern, markieren, Markierung oder ändern).</span><span class="sxs-lookup"><span data-stu-id="432f0-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="432f0-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="432f0-111">In This Section</span></span>

  - [<span data-ttu-id="432f0-112">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="432f0-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="432f0-113">Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="432f0-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="432f0-114">Wiederherstellen migrierter Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="432f0-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

