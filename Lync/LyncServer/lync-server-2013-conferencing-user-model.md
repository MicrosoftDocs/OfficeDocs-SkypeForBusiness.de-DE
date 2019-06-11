---
title: Lync Server 2013 Conferencing-Benutzermodell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Das Konferenzbenutzer Modell in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Ein wichtiger Bestandteil des Benutzermodells von lync Server Conferencing ist die Besprechungsgröße. Nach dem Sammeln von Daten aus mehreren Datenpunkten (wie im vorherigen Abschnitt beschrieben) haben wir Folgendes festgelegt:

  - Bei den meisten Besprechungen handelt es sich tatsächlich um kleine Besprechungs Besprechungen mit durchschnittlich vier bis sechs Teilnehmern.

  - Ungefähr 80 Prozent der Besprechungen haben weniger als 20 Teilnehmer.

  - 99,98% der Besprechungen haben weniger als 100 Teilnehmer.

Neben der Größe der Besprechung berücksichtigt das Konferenzbenutzer Modell auch eine Reihe von Faktoren, wie beispielsweise:

  - **Gleich**   zeitige Besprechungen, wie viele Benutzer gleichzeitig in Besprechungen erwartet werden?

  - **Medienmischung**   welche Medientypen sind verfügbar und werden von Benutzern in Besprechungen erwartet?

  - **Benutzertypen**   sind Benutzer interne Benutzer, Remotebenutzer, Verbundbenutzer oder anonyme Benutzer?

  - **Besprechung Hochfahren Zeit**   wie lange dauert es, bis alle Benutzer einer Besprechung an einer Besprechung teilnehmen?

Details zum Benutzermodell finden Sie unter [Benutzermodelle in lync Server 2013](lync-server-2013-user-models.md).

Zum Ermitteln der Anzahl von Besprechungen und Benutzern, die für Tests verwendet werden sollen, haben wir die folgenden Schritte durchführen:

  - Nahm die Gesamtzahl der Benutzer in einer Organisation (beispielsweise 80.000-Benutzer) an und multipliziert Sie mit der Parallelitätsrate der Besprechung (beispielsweise 5% aller Benutzer), um die Gesamtzahl der Benutzer zu ermitteln, die gleichzeitig in Besprechungen erwartet werden (in diesem Beispiel , 4000-Benutzer).

  - Dividiert die Gesamtzahl der Benutzer durch die Anzahl der lync Server 2013-Front-End-Server in der Bereitstellung (beispielsweise 8 Server), um die geschätzte Anzahl der Besprechungsteilnehmer pro Front-End-Server (in diesem Beispiel 500-Benutzer pro Front-End-Server) zu ermitteln.

  - Die Anzahl der Benutzer pro Front-End-Server wurde durch die durchschnittliche Besprechungsgröße (beispielsweise 4 Benutzer) dividiert, um die geschätzte durchschnittliche Anzahl der Besprechungen pro Front-End-Server (in diesem Beispiel 125-Besprechungen pro Front-End-Server) zu ermitteln.

  - Um die pro-Medien-Auslastung auf jedem Front-End-Server zu erhalten, schätzten wir den Media Mix. Wenn Sie beispielsweise davon ausgehen, dass 75% der Besprechungen mehr als nur Audio-Unterstützung erfordern und 50% dieser Besprechungen Anwendungsfreigabe erfordern, verbinden sich im Durchschnitt 47 Besprechungen und 188-Benutzer gleichzeitig mit jedem Front-End-Server für die Anwendungsfreigabe.

  - Eine Vielzahl von Besprechungs Größen getestet (basierend auf unserem Benutzermodell mit bis zu 250 Benutzern in einem gemeinsamen Pool), um die Serverskalierbarkeit zu gewährleisten.

</div>

<span> </span>

</div>

</div>

</div>

