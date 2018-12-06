---
title: 'Lync Server 2013: Unterstützte Serverkollokation für Edgekomponenten'
TOCTitle: Unterstützte Serverkollokation für Edgekomponenten
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425934(v=OCS.15)
ms:contentKeyID: 49293833
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Serverkollokation für Edgekomponenten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Zugriffs-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst werden gemeinsam auf den Edgeserver ausgeführt. Die folgenden Server bieten für den Zugriff durch externe Benutzer erforderliche Funktionen und müssen als dedizierte Server bereitgestellt werden:

  - Edgeserver

  - Director (optional)

  - Reverseproxy


> [!IMPORTANT]
> Es ist kein dedizierter Reverseproxy nur für Lync Server 2013 erforderlich. Sie können beispielsweise Dienste zur Veröffentlichung der Lync Server-Webdienste und gleichzeitig eine veröffentlichte Website für eine andere Website zur Verfügung stellen, die für Lync Server vollkommen irrelevant ist. Wenn Sie bereits über einen Reverseproxyserver im Umkreisnetzwerk verfügen, der andere Geräte unterstützt, können Sie diesen für Lync Server 2013 verwenden.


