---
title: Benutzermodell für lync Server 2013 Konferenz
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc74259f9a5cb6ee40cb29fbab56e638ba78b79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Das Benutzermodell für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Ein wichtiger Bestandteil des Benutzermodells für lync Server Konferenzen ist die Besprechungsgröße. Nach dem Erfassen der Daten von den verschiedenen Datenpunkten (wie im vorigen Abschnitt beschrieben) wurde Folgendes ermittelt:

  - Im Durchschnitt weisen die meisten Besprechungen eine Teilnehmerzahl von vier bis sechs Personen auf

  - Circa 80 Prozent der Besprechungen haben weniger als 20 Teilnehmer.

  - 99,98 Prozent der Besprechungen haben weniger als 100 Teilnehmer.

Neben dem Besprechungsumfang berücksichtigt das Konferenzbenutzermodell auch eine Reihe von Faktoren, wie zum Beispiel:

  - **Gleichzeitige Besprechungen**   wie viele Benutzer werden in Besprechungen gleichzeitig erwartet?

  - **Medienmischung**   welche Arten von Medien sind verfügbar und werden von Benutzern in Besprechungen voraussichtlich verwendet?

  - **Benutzertypen**   sind Benutzer interne Benutzer, Remotebenutzer, Verbundbenutzer oder anonyme Benutzer?

  - **Meeting-Ramp up time**   wie lange dauert es, bis alle Benutzer einer Besprechung an einer Besprechung teilnehmen?

Ausführliche Informationen zum Benutzermodell finden Sie unter [Benutzermodelle in lync Server 2013](lync-server-2013-user-models.md).

Zur Ermittlung der Anzahl von Besprechungen und Benutzern, die für den Test verwendet wurden, wurde wie folgt vorgegangen:

  - Die Gesamtzahl der Benutzer in einer Organisation (zum Beispiel 80.000 Benutzer) wurde mit der Gleichzeitigkeitsrate von Besprechungen (zum Beispiel 5 % aller Benutzer) multipliziert, um die Gesamtzahl der Benutzer zu ermitteln, die erwartungsgemäß zur gleichen Zeit an Besprechungen teilnehmen (in diesem Beispiel 4.000 Benutzer).

  - Die Gesamtzahl der Benutzer wurde durch die Anzahl der lync Server 2013, Front-End-Server in der Bereitstellung (beispielsweise 8 Server) dividiert, um die geschätzte Anzahl der Besprechungsteilnehmer pro Front-End-Server zu ermitteln (in diesem Beispiel 500 Benutzer pro Front-End-Server).

  - Die Anzahl der Benutzer pro Front-End-Server wurde durch die durchschnittliche Besprechungsgröße (beispielsweise 4 Benutzer) dividiert, um die geschätzte durchschnittliche Anzahl von Besprechungen pro Front-End-Server zu ermitteln (in diesem Beispiel 125 Besprechungen pro Front-End-Server).

  - Um die pro-Medien-Last auf jeder Front-End-Server zu erhalten, schätzten wir die Medienmischung. Wenn beispielsweise 75% der Besprechungen mehr als nur Audiounterstützung erfordern und 50% dieser Besprechungen Anwendungsfreigabe erfordern, verbinden sich durchschnittlich 47 Besprechungen und 188 Benutzer gleichzeitig mit jedem Front-End-Server für die Anwendungsfreigabe.

  - Es wurden verschiedene Besprechungsgrößen getestet (auf Basis des Modells mit bis zu 250 Benutzern in einem freigegebenen Pool), um die Serverskalierbarkeit zu gewährleisten.

</div>

<span> </span>

</div>

</div>

</div>

