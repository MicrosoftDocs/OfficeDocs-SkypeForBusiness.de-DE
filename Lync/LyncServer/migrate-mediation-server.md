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
ms.openlocfilehash: d7786ecfd72ac32de74c9947f0effa1fad0c9603
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migrieren des Vermittlungsservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Wenn Sie den Merge-Assistenten ausführen, wird Ihr Vermittlungsserver mit der lync Server 2013 Pilot Topologie zusammengeführt. Sie konfigurieren die lync Server 2013 Vermittlungsserver jedoch, nachdem alle Benutzer migriert wurden, da ein Office Communications Server 2007 R2 Pool nicht mit einem lync Server 2013 Vermittlungsserver kommunizieren kann. Während der parallelen Migration kommuniziert der lync Server 2013 Pool mit dem Office Communications Server 2007 R2 Vermittlungsserver.

Wenn Sie Ihre lync Server 2013 Vermittlungsserver konfigurieren, müssen Sie auch Ihre Office Communications Server 2007 R2 Gateways aktualisieren oder ersetzen. Lync Server 2013 Vermittlungsserver werden von Office Communications Server 2007 R2 Gateways nicht unterstützt. Sie müssen Gateways bereitstellen, die für lync Server 2013 zertifiziert sind, und Sie dem lync Server 2013 Vermittlungsserver zuordnen. Dieser Schritt ist erforderlich, bevor Sie Ihre Office Communications Server 2007 R2-Bereitstellung vollständig außer Betrieb nehmen können.

In den Themen in diesem Abschnitt werden Konfigurationsaufgaben beschrieben, die Sie nach Abschluss der Migration von lync Server 2013 Vermittlungsserver ausführen müssen. Der Übergang des verbundenen Vermittlungsservers in einen eigenständigen Vermittlungsserver ist eine optionale Aufgabe.

  - [Konfigurieren von Vermittlungsserver](configure-mediation-server.md)

  - [Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

