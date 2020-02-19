---
title: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ebf73ad647003a1835a235bda240229433ac6d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Herunterladen der Topologie aus einer vorhandenen Bereitstellung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Beim Erstellen eines lync Server 2013 Pools verwenden Sie die zentraler Verwaltungsspeicher, die lync Server 2010 zugeordnet ist. Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll. Da Sie bereits eine lync Server 2010 Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen. Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab.

**So laden Sie eine Topologie aus einer vorhandenen Bereitstellung herunter**

1.  Öffnen Sie den**** Lync Server-Bereitstellungs-Assistenten.

2.  Klicken Sie auf der Seite **Lync Server 2013 – Bereitstellungs-Assistent** auf **Verwaltungstools installieren**.

3.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013** , und klicken Sie dann auf **lync Server Topologie-Generator**.

4.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.
    
    ![Einstellungen für den Bereitstellungs-Assistenten für Topologie-Generator](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Einstellungen für den Bereitstellungs-Assistenten für Topologie-Generator")

5.  Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.

6.  Erweitern Sie den Lync Server-Knoten (siehe Abbildung), um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.
    
    ![Topologie-Generator-Serverrolle: Allgemeine Eigenschaften](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topologie-Generator-Serverrolle: Allgemeine Eigenschaften")

</div>

<span> </span>

</div>

</div>

</div>

