---
title: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c47e6d78d3bd9522b8f0369924f05f8f939037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Herunterladen der Topologie aus einer vorhandenen Bereitstellung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Beim Erstellen eines lync Server 2013-Pools verwenden Sie den zentralen Verwaltungsspeicher, der lync Server 2010 zugeordnet ist. Wenn Sie den Topologie-Generator bei der ersten Verwendung und nachfolgenden Bearbeitungssitzungen starten, werden Sie aufgefordert, den Speicherort anzugeben, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll. Da Sie bereits eine lync Server 2010-Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen. Der Topologie-Generator liest die Datenbank und ruft die aktuelle Definition ab.

**So laden Sie eine Topologie aus einer vorhandenen Bereitstellung herunter**

1.  Öffnen Sie den **lync Server**-Bereitstellungs-Assistenten.

2.  Klicken Sie auf der Seite **lync Server 2013 – Deployment-Assistent** auf **Verwaltungs Tools installieren**.

3.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013** , und klicken Sie dann auf **lync Server Topology Builder**.

4.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**.
    
    ![Einstellungen des Bereitstellungs-Assistenten für Topologie-Generator] (images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Einstellungen des Bereitstellungs-Assistenten für Topologie-Generator")

5.  Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.

6.  Erweitern Sie den lync Server-Knoten, wie hier gezeigt, um die verschiedenen Server Rollen in der Bereitstellung anzuzeigen.
    
    ![Allgemeine Eigenschaften des Topology Builder-Servers] (images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Allgemeine Eigenschaften des Topology Builder-Servers")

</div>

<span> </span>

</div>

</div>

</div>

