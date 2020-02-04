---
title: 'Lync Server 2013: Konfigurieren des Dateispeichers'
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
ms.openlocfilehash: 1bbb932a602ad1fc49907be9c5ab2777bc7a415f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Konfigurieren des Dateispeichers für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-05-23_

Lync Server 2013 unterstützt die Verwendung von Dateifreigaben in einem verteilten Datei System (DFS). Ausführliche Informationen zu DFS für Windows Server 2008 finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)der schrittweisen Anleitung zu DFS für Windows Server 2008 unter. Um ein DFS zu verwenden, benötigt lync Server 2013 Folgendes:

  - Namespaces sind Domänen basiert

  - Auf allen Namespaceservern wird ein minimales Windows 2008 ausgeführt.

Das Setup von lync Server 2013 erfordert, dass Berechtigungen für den freigegebenen Ordner den vollständigen Zugriff auf den Administrator ermöglichen. Lync Server 2013 verwendet dann NTFS-Dateiberechtigungen, um die Ordner zu ACL. Geerbte DFS-Freigabeberechtigungen werden nicht verwendet, um den Zugriff zu beschränken.

Weitere Informationen zu den Anforderungen an Dateifreigaben finden Sie unter unter [Stützung von Dateispeicher in lync Server 2013](lync-server-2013-file-storage-support.md) in der Dokumentation zur Unterstützung.

<div>


> [!NOTE]  
> Möglicherweise suchen Sie nach Informationen zum Konfigurieren einer nicht DFS-Freigabe. Wenn dies der Fall ist, lesen Sie <A href="lync-server-2013-hardware-setup.md">Hardware-Setup für lync Server 2013</A>.



</div>

Im folgenden Verfahren wird beschrieben, wie Sie die Berechtigungen für freigegebene Ordner mithilfe des DFS-Namespace-Assistenten richtig konfigurieren (wie im DFS-Setup Handbuch beschrieben).

<div>

## <a name="to-configure-shared-folder-permissions"></a>So konfigurieren Sie Berechtigungen für freigegebene Ordner

1.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **DFS-Verwaltung**.

2.  Klicken Sie in der Konsolenstruktur des DFS-Verwaltungs-Snap-Ins mit der rechten Maustaste auf den Namespaceserver (beispielsweise filesrv1.contoso.com), und klicken Sie dann auf **Einstellungen bearbeiten**.

3.  Wählen Sie **Berechtigungen für freigegebene Ordner**aus.

4.  Wählen Sie **benutzerdefinierte Berechtigungen verwenden**aus.

5.  Wählen Sie für die Gruppe Administratoren unter **zulassen**die folgenden Optionen aus:
    
      - **Vollzugriff**
    
      - **Änderung**
    
      - **Lesen**

6.  Klicken Sie auf über **nehmen**, und klicken Sie dann auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

