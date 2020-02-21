---
title: 'Lync Server 2013: Installieren der Operations Manager-Agent-Dateien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e685abf7916c446bf9acf73e50f5633271b2942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Installieren der Operations Manager-Agent-Dateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Führen Sie die folgenden Schritte aus, um die Operations Manager-Agentdateien auf dem Computer zu installieren.

1.  Doppelklicken Sie auf den System Center-Setupmedien auf **SetupOM.exe**.

2.  Klicken Sie im System Center Operations Manager-Setupprogramm auf **Operations Manager-Agent installieren**.

3.  Klicken Sie im System Center-Setup-Assistenten auf der Willkommensseite**** des Assistenten auf **Weiter**.

4.  Wählen Sie auf der Seite **Zielordner** den Ordner aus, in dem die Operations Manager-Agentdateien installiert werden sollen, und klicken Sie dann auf **Weiter**.

5.  Wählen Sie auf der Seite **Verwaltungsgruppenkonfiguration** die Option **Verwaltungsgruppeninformationen angeben** aus, und klicken Sie dann auf **Weiter**.

6.  Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** in das Feld **Verwaltungsgruppenname** den Namen Ihrer Operations Manager-Verwaltungsgruppe ein, und geben Sie dann den Hostnamen Ihres Operations Manager-Servers (beispielsweise ATL-SCOM-001) in das Feld **Verwaltungsserver** ein. Wenn Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer in das Feld Verwaltungs Server Port ein. Belassen Sie andernfalls den Port mit dem Standardwert 5723, und klicken Sie auf **weiter**.

7.  Wählen Sie auf der Seite **Agentaktionskonto** die Option **Lokales System** aus, und klicken Sie dann auf **Weiter**.

8.  Wählen Sie auf der Seite **Microsoft Update** die Option **Ich möchte Microsoft Update nicht verwenden** aus, und klicken Sie dann auf **Weiter**.

9.  Klicken Sie auf der Seite **Bereit zum Installieren** auf **Installieren**.

10. Klicken Sie auf der Seite **Fertigstellen des System Center Operations Manager-Setup-Assistenten** auf **Fertig stellen**.

11. Klicken Sie auf **Beenden**.

Wenn Sie System Center 2007 R2 verwenden, können Sie überprüfen, ob der Agent erstellt wurde, indem Sie auf **Start**, auf **Alle Programme**, auf **System Center Operations Manager 2007 R2**und dann auf **Operations Manager-Shell**klicken. Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell Befehl ein, und drücken Sie dann die EINGABETASTE:

    Get-Agent 

Eine Liste aller Operations Manager-Agents wird angezeigt.

Falls Sie System Center 2012 verwenden, führen Sie den folgenden Befehl in der Operations Manager 2012-Shell aus:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

