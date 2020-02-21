---
title: 'Lync Server 2013: Überprüfen der Normalisierung und des Routings von VoIP-Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f9cd0beea65cfb1718fea3bc1c0235eb7554ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Überprüfen der Normalisierung und des Routings von sprach Nummern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-19_

Die richtige Normalisierung und Weiterleitung von Nummern ist für eine funktionale Enterprise-VoIP-Umgebung sehr wichtig. Vor allem bei Migrationen von einer Nebenstellenanlage zur eigenständigen lync Server Umgebung ist einer der Schlüssel für eine erfolgreiche Migration das aufdecken und dokumentieren aller vorhandenen Wählregeln sowie das Erstellen geeigneter Normalisierungsregeln, VoIP-Richtlinien, Telefonverwendungen und-Routen.

Das Validieren von Nummern Normalisierung und-Routing ist nicht nur bei Migrationen wichtig, sondern auch während eines normalen, stabilen Betriebs des Systems.

Es wird empfohlen, diese Überprüfung täglich mithilfe der lync Server-Systemsteuerung durchzuführen, beginnend mit der Entwicklung einer robusten Reihe von Testfällen für den aktuellen Satz von Normalisierungsregeln, die in den lync Server globalen Einstellungen veröffentlicht wurden. Diese Testfälle sollten täglich ausgeführt werden, um unerwünschte Änderungen hervorzuheben, die für die Wähleinstellungen vorgenommen wurden und für die ein Commit ausgeführt wurde.

Lync Server-Systemsteuerung unterstützt Sie auch beim visualisieren, testen, ändern, archivieren und Freigeben von Konfigurationsinformationen für das VoIP-Routing sowie beim Ändern von Normalisierungsregeln für Enterprise-VoIP,-Wählpläne,-VoIP-Richtlinien und-Routen. Es verfügt über zusätzliche Funktionen für Folgendes:

  - Exportieren und importieren oder Sichern von VoIP-Routingdaten zwischen Systemen.

  - Testen von Konfigurationsänderungen vor dem Hochladen auf ein Live-System.

  - Erstellen und Ausführen von Konfigurations Testfälle, um die Verwendbarkeit von Routingdaten zu gewährleisten, nachdem Sie Änderungen daran vorgenommen haben, aber bevor Sie die Änderungen an einem bereitgestellten System vornehmen.

  - Erstellen und Ändern von Nummern Normalisierungsregeln, Standortprofilen, VoIP-Richtlinien und Routingdaten, ohne die erforderlichen regulären Ausdrücke zu schreiben.

  - Analysieren eines Standortprofils zur Kompatibilität mit dem lync Server Phone Edition.

  - Weitere Informationen zu VoIP-Routing Tests finden Sie unter [Test Voice Routing in lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Siehe auch


[Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

