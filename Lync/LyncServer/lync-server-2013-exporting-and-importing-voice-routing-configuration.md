---
title: 'Lync Server 2013: Exportieren und Importieren der VoIP-Routingkonfiguration'
description: 'Lync Server 2013: Exportieren und Importieren der VoIP-Routingkonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94a9c02672debae9f5b30e3a1a96856050d6ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564771"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a>Exportieren und Importieren der VoIP-Routingkonfiguration in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Wenn Sie Ihre VoIP-Routingkonfiguration ohne Veröffentlichung speichern möchten, führen Sie die folgenden Schritte aus, um die lync Server-Systemsteuerung Konfigurations Export-und Importbefehle zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. Wenn Sie eine VoIP-Routing Konfigurationsdatei (. vcfg) importieren, Änderungen an der VoIP-Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, geben die Seiten in der Gruppe **VoIP-Routing** in lync Server-Systemsteuerung an, dass keine Commits für Änderungen an der VoIP-Weiterleitung vorgenommen werden. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.

<div>


> [!IMPORTANT]  
> Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der <STRONG>VoIP-Routing</STRONG> Gruppe vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (. vcfg) gespeichert. Auf diese Weise können Sie Konfigurationsänderungen für das VoIP-Routing in mehreren lync Server-Systemsteuerung Sitzungen vornehmen, bevor Sie die Änderungen veröffentlichen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Exportieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [Importieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a>Verwandte Abschnitte

</div>

</div>

<span> </span>

</div>

</div>

</div>

