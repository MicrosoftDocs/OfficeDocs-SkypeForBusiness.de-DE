---
title: Importieren von Richtlinien und Einstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4a4d86d687236934c319e3fb7bd5e6c8027a73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Importieren von Richtlinien und Einstellungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Nachdem Sie Ihre Office Communications Server 2007 R2-Topologieinformationen mit Ihrem lync Server 2013-Pilot Pool zusammengeführt haben, müssen Sie ein lync Server 2013-Verwaltungsshell-Cmdlet ausführen, um die Richtlinien und Konfigurationseinstellungen von Office Communications Server 2007 R2 zu migrieren. zu Ihrem lync Server 2013-Pilot Pool.

Mit dem Cmdlet " **Import-CsLegacyConfiguration** " werden Richtlinien, VoIP-Routen, Wählpläne, Communicator Web Access-URLs und Einwahl Zugriffsnummern in lync Server 2013 importiert.

<div>

## <a name="to-migrate-policies-and-settings"></a>So migrieren Sie Richtlinien und Einstellungen

1.  Starten Sie auf dem lync Server 2013-Front-End-Server die lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsLegacyConfiguration
    
    Nachdem die Richtlinien importiert wurden, führen Sie die folgenden Schritte aus, um die importierten Richtlinien in der lync Server-Systemsteuerung anzuzeigen.

</div>

<div>

## <a name="to-view-imported-policies"></a>So zeigen Sie importierte Richtlinien an

1.  Öffnen Sie die lync Server 2013-Systemsteuerung.

2.  Klicken Sie auf **sprach Routing** , und zeigen Sie die importierten Richtlinien an.

3.  Klicken Sie auf **Konferenzen** , und zeigen Sie die importierten Richtlinien an.

4.  Klicken Sie auf **Föderation und externer Zugriff** , und zeigen Sie die importierten Richtlinien an.

5.  Klicken Sie auf **Überwachung und Archivierung** , und zeigen Sie die importierten Richtlinien an.

</div>

</div>

<span> </span>

</div>

</div>

</div>

