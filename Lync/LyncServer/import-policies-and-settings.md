---
title: Importieren von Richtlinien und Einstellungen
description: Importieren von Richtlinien und Einstellungen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569031"
---
# <a name="import-policies-and-settings"></a>Importieren von Richtlinien und Einstellungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Nachdem Sie die Office Communications Server 2007 R2 Topologieinformationen mit dem lync Server 2013 Pilot Pool zusammengeführt haben, müssen Sie ein Cmdlet der lync Server 2013 Verwaltungsshell ausführen, um Ihre Office Communications Server 2007 R2-Richtlinien und Konfigurationseinstellungen zu Ihrem lync Server 2013 Pilot-Pool zu migrieren.

Das Cmdlet **Import-CsLegacyConfiguration** importiert Richtlinien, VoIP-Routen, Wählpläne, Communicator-Webzugriffs-URLs und Zugriffsnummern für Einwahl Anrufe in lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Migrieren von Richtlinien und Einstellungen

1.  Starten Sie auf dem lync Server 2013-Front-End-Server den lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsLegacyConfiguration
    
    Nachdem die Richtlinien importiert wurden, verwenden Sie das folgende Verfahren, um die importierten Richtlinien im lync Server-Systemsteuerung anzuzeigen.

</div>

<div>

## <a name="to-view-imported-policies"></a>Anzeigen importierter Richtlinien

1.  Öffnen Sie lync Server 2013 Systemsteuerung.

2.  Klicken Sie auf **VoIP-Routing**, und zeigen Sie die importierten Richtlinien an.

3.  Klicken Sie auf **Konferenzen**, und zeigen Sie die importierten Richtlinien an.

4.  Klicken Sie auf die Option für Partnerverbund und externen Zugriff****, und zeigen Sie die importierten Richtlinien an.

5.  Klicken Sie auf **Überwachung und Archivierung**, und zeigen Sie die importierten Richtlinien an.

</div>

</div>

<span> </span>

</div>

</div>

</div>

