---
title: 'Lync Server 2013: entscheiden, wie Microsoft lync bereitgestellt wird'
description: 'Lync Server 2013: entscheiden, wie Microsoft lync bereitgestellt wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a800b51dfddc6f2c99e42c8f117056ed4091b6a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558101"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a>Entscheidung über die Bereitstellung von lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Bei der Planung von lync ist die erste wichtige Entscheidung, wie Microsoft lync bereitgestellt wird: als lync Server 2013 lokal oder lync online mit Microsoft 365 oder Office 365 in der Cloud.

  - **Lync Server 2013 lokal** : diese Option bietet den vollständigen lync-Featuresatz und bietet größtmögliche Flexibilität bei der Konfiguration, dem anpassen und dem Betrieb Ihrer Bereitstellung. Alle Server werden vor Ort installiert und von Ihrer Organisation verwaltet. Eine lokale Bereitstellung stellt die gesamte Palette von lync Server Funktionen bereit.

  - **Lync Online in der Cloud** Lync Online richtet sich an Organisationen, die die Kosten und Agilität von Cloud-basierten Chatnachrichten, Anwesenheitsinformationen und Besprechungen ohne Einbußen bei den Geschäftsklassen Funktionen von lync Server nutzen möchten. Mit lync Online wird die erforderliche Serverinfrastruktur von Microsoft bereitgestellt und verwaltet, und die laufende Wartung, Patches und Upgrades werden verarbeitet. Einige in einer lokalen Bereitstellung verfügbare Features sind in lync Online nicht verfügbar.

Welcher Bereitstellungstyp am besten für Sie geeignet ist, hängt von den Arbeitsauslastungen, die Sie bereitstellen möchten, sowie vom geografischen und wirtschaftlichen Status Ihrer Organisation ab.

<div>

## <a name="lync-server"></a>Lync Server

Eine lokale Lync Server-Bereitstellung eignet sich am besten für folgende Szenarien:

  - **Vollständige Enterprise-VoIP-Funktionen**     Wenn Sie beabsichtigen, eine vollständige Enterprise-VoIP-Lösung bereitzustellen, um Ihre Nebenstellenanlage zu ersetzen, oder die erweiterte Anruffunktionen verwendet, ist eine lokale lync Server Bereitstellung erforderlich. Eine lokale Bereitstellung unterstützt die direkte Konnektivität mit den Nebenstellenanlagen und Trunks sowie erweiterte Telefonfunktionen, wie Reaktionsgruppen und das Parken von Anrufen. Diese Features werden von lync Online derzeit nicht unterstützt.

  - **Medien Qualitätskontrollen**     Wenn Sie die gesamte Palette an Features zur Medien Qualitätssicherung wie Anrufsteuerung (Call Admission Control, CAC) und QoS-Features (Quality of Service) wünschen, benötigen Sie eine lokale Bereitstellung.

  - **Beständiger Chat**     Wenn Sie beständigen Chat für Ihre Organisation bereitstellen müssen, müssen Sie eine lokale Bereitstellung auswählen.

  - **Drittanbieter-Server Anwendungen**     Nur lokale Bereitstellungen können mit vertrauenswürdigen Drittanbieteranwendungen verwendet werden, die das verwaltete API von Microsoft Unified Communications (UCMA) verwenden.

  - **Multi-nationale/multiregionale Unternehmen, die regionale Unterstützung benötigen**     Wenn Sie über Rechenzentren in mehreren Ländern oder Regionen verfügen und Server auf regionaler Basis bereitgestellt und verwaltet werden müssen, ist eine lokale Bereitstellung am besten, da Sie diese Art von regionalen Verwaltungsfunktionen bereitstellt.

  - **Vollständige Kontrolle über Richtlinien, Berichte und Upgrades**     Mit einer lokalen lync Server-Bereitstellung haben Sie Zugriff auf den vollständigen Server-und Clientrichtlinien, Überwachung und andere Berichte sowie Timing von Upgrades. Lync Online stellt eine Teilmenge von Richtlinieneinstellungen und-Berichten bereit und bietet ein eingeschränktes, wenn auch erhebliches Fenster für das akzeptieren von Upgrades.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Falls keiner der in der Liste aufgeführten Faktoren für Sie von entscheidender Bedeutung ist, sollten Sie sich für Lync Online entscheiden, das einfacher bereitzustellen und zu verwalten ist. Lync Online bietet eine robuste Funktion für Sofortnachrichten, Anwesenheit und Konferenzen sowie Sprach-und Videoanrufe über IP zwischen Benutzern in Ihrer Organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>
