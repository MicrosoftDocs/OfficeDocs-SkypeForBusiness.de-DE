---
title: Überprüfen der Konfigurationseinstellungen
description: Überprüfen Sie die Konfigurationseinstellungen.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7bb1135e95dafe51e906768fe0f4f0d57bf2d6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573111"
---
# <a name="verify-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-06_

Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das Cmdlet "lync Server 2013 **Get-CsManagementStoreReplicationStatus** " auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer in der Domäne, auf dem lync Server 2013 Core Components (OcsCore.msi) installiert ist.

Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an. Wenn dies der Fall ist, führen Sie das **Invoke-CsManagementStoreReplication-** Cmdlet aus, und lassen Sie die Replikation vor dem erneuten Ausführen des **Get-CsManagementStoreReplicationStatus** Zeit in Anspruch nehmen.

</div>

<span> </span>

</div>

</div>

</div>

