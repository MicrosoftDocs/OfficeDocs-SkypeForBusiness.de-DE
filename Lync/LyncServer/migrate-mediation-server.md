---
title: Migrieren des Vermittlungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3478bb3bb837e44ed33597f72738b181b4c67561
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migrieren des Vermittlungsservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Wenn Sie den Zusammenführungs-Assistenten ausführen, wird Ihr Vermittlungsserver mit ihrer lync Server 2013-Pilot Topologie verbunden. Sie konfigurieren den lync Server 2013-Vermittlungsserver allerdings, nachdem alle Benutzer migriert wurden, weil ein Office Communications Server 2007 R2-Pool nicht mit einem lync Server 2013-Vermittlungsserver kommunizieren kann. Während der parallelen Migration kommuniziert der lync Server 2013-Pool mit dem Office Communications Server 2007 R2-Vermittlungsserver.

Wenn Sie Ihren lync Server 2013-Vermittlungsserver konfigurieren, müssen Sie auch Ihre Office Communications Server 2007 R2-Gateways aktualisieren oder ersetzen. Office Communications Server 2007 R2-Gateways unterstützen keinen lync Server 2013-Vermittlungsserver. Sie müssen Gateways bereitstellen, die für lync Server 2013 zertifiziert sind, und Sie dem lync Server 2013-Vermittlungsserver zuordnen. Dieser Schritt ist erforderlich, bevor Sie Ihre Office Communications Server 2007 R2-Bereitstellung vollständig außer Dienststellen können.

Die Themen in diesem Abschnitt beschreiben Konfigurationsaufgaben, die Sie ausführen müssen, nachdem Sie die Migration von lync Server 2013-Vermittlungsserver abgeschlossen haben. Der Übergang des beiliegenden Vermittlungsservers zu einem eigenständigen Vermittlungsserver ist eine optionale Aufgabe.

  - [Konfigurieren des Vermittlungsservers](configure-mediation-server.md)

  - [Ändern von VoIP-Routen zur Verwendung des neuen lync Server 2013-Vermittlungsservers](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Umstieg auf einen bereitstehenden Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

