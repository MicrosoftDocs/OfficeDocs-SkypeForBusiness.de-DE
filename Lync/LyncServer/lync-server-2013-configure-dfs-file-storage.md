---
title: 'Lync Server 2013: Konfigurieren des DFS-Dateispeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7d5dc3675f06aafed18ddd18e430e2c61dc670
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537222"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Konfigurieren des DFS-Dateispeichers für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-05-23_

Lync Server 2013 unterstützt die Verwendung von Dateifreigaben in einem verteilten Datei System (DFS). Ausführliche Informationen zu DFS für Windows Server 2008 finden Sie in der schrittweisen Anleitung zu DFS für Windows Server 2008 unter [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Für die Verwendung eines DFS-lync Server 2013 ist Folgendes erforderlich:

  - Namespaces sind domänenbasiert

  - Auf allen Namespace-Servern wird mindestens Windows 2008 ausgeführt

Lync Server 2013 Setup erfordert, dass Berechtigungen für den freigegebenen Ordner den vollständigen Zugriff auf den Administrator ermöglichen. Lync Server 2013 verwendet dann NTFS-Dateiberechtigungen für ACL-Ordner. Zum Einschränken des Zugriffs werden keine geerbten DFS-Freigabeberechtigungen verwendet.

Ausführliche Informationen zu den Anforderungen an Dateifreigaben finden Sie unter [File Storage Support in lync Server 2013](lync-server-2013-file-storage-support.md) in der Unterstützungsdokumentation.

<div>


> [!NOTE]  
> Möglicherweise suchen Sie nach Informationen zum Konfigurieren einer nicht-DFS-Freigabe. Wenn dies der Fall ist, lesen Sie <A href="lync-server-2013-hardware-setup.md">Hardware-Setup für lync Server 2013</A>.



</div>

Im folgenden Verfahren wird die ordnungsgemäße Konfiguration von Berechtigungen für freigegebene Ordner mithilfe des DFS-Namespace-Assistenten beschrieben (siehe Beschreibung in der Anleitung zur DFS-Einrichtung).

<div>

## <a name="to-configure-shared-folder-permissions"></a>So konfigurieren Sie Berechtigungen für freigegebene Ordner

1.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und auf **Verwaltung**, und klicken Sie dann auf **DFS-Verwaltung**.

2.  Klicken Sie in der Konsolenstruktur des DFS-Verwaltungs-Snap-Ins mit der rechten Maustaste auf den Namespace-Server (z. B. "filesrv1.contoso.com"), und klicken Sie dann auf **Einstellungen bearbeiten**.

3.  Wählen Sie **Berechtigungen für freigegebene Ordner** aus.

4.  Wählen Sie **Benutzerdefinierte Berechtigungen verwenden** aus.

5.  Wählen Sie für die Administratorgruppe unter **Zulassen** Folgendes aus:
    
      - **Vollzugriff**
    
      - **Ändern**
    
      - **Lesen**

6.  Klicken Sie auf **Übernehmen** und dann auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

