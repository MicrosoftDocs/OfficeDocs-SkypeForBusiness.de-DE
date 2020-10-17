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
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a>Bereitstellen des einheitlichen Kontaktspeichers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-06-06_

Für die Aktivierung des einheitlichen Kontaktspeichers in lync Server 2013 müssen keine topologieeinstellungen vorgenommen werden. Wenn Sie den Kontaktspeicher für Benutzer aktivieren möchten, müssen Sie die folgenden Punkte sicherstellen:

  - Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).

  - Benutzer melden sich mindestens einmal mit lync 2013 an.

Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer mit lync 2013 anmeldet, kann der Benutzer über lync 2013, Outlook 2013 oder Outlook Web Access auf seine lync-Kontakte zugreifen und diese verwalten. Der Benutzer muss nicht bei lync angemeldet sein, um seine Kontakte in Outlook oder Outlook Web Access verwalten zu können.

<div>


> [!IMPORTANT]  
> Wenn sich ein Benutzer von lync 2010 nach der Migration anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (also hinzufügen, löschen, verlagern, markieren, Markierung oder ändern).



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in lync Server 2013](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher in lync Server 2013](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [Wiederherstellen migrierter Benutzer in lync Server 2013](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

