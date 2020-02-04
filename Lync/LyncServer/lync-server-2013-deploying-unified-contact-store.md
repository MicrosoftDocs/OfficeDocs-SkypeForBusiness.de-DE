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

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a>Bereitstellen des einheitlichen Kontaktspeichers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-06-06_

Für die Aktivierung des Unified Contact Stores in lync Server 2013 sind keine topologieeinstellungen erforderlich. Für die Aktivierung des Unified Contact Store für Benutzer ist Folgendes erforderlich:

  - Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).

  - Benutzer melden sich mindestens einmal mit lync 2013 an.

Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer mit lync 2013 anmeldet, kann der Benutzer über lync 2013, Outlook 2013 oder Outlook Web Access auf seine lync-Kontakte zugreifen und diese verwalten. Der Benutzer muss nicht bei lync angemeldet sein, um seine Kontakte aus Outlook oder Outlook Web Access zu verwalten.

<div>


> [!IMPORTANT]  
> Wenn ein Benutzer sich nach der Migration von lync 2010 anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (das heißt, Sie können diese Kontakte hinzufügen, löschen, verschieben, markieren, Markierung oder ändern).



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in Lync Server 2013](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [Migrieren von Benutzern zum einheitlichen Kontaktspeicher in Lync Server 2013](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [Zurücksetzen von migrierten Benutzern in Lync Server 2013](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

