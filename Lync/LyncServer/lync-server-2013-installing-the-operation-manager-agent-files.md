---
title: 'Lync Server 2013: Installieren der Operations Manager-Agentendateien'
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
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Installieren der Operations Manager-Agentendateien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Führen Sie die folgenden Schritte aus, um die Operations Manager-Agentendateien auf dem Computer zu installieren.

1.  Doppelklicken Sie auf Ihrem System Center-Setup Medium auf **SetupOM. exe**.

2.  Klicken Sie im System Center Operation Manager-Setup auf **Operations Manager-Agent installieren**.

3.  Klicken Sie im System Center-Setup-Assistenten auf der Seite Willkommen beim Setup-Assistenten von **System Center Operations Manager** auf **weiter**.

4.  Wählen Sie auf der Seite **Zielordner** den Ordner aus, in dem die Operations Manager-Agentendateien installiert werden sollen, und klicken Sie dann auf **weiter**.

5.  Wählen Sie auf der Seite **Verwaltungsgruppenkonfiguration** die Option **Verwaltungsgruppeninformationen angeben**aus, und klicken Sie dann auf **weiter**.

6.  Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** den Namen Ihrer Operations Manager-Verwaltungsgruppe im Feld **Verwaltungsgruppenname** ein, und geben Sie dann den Hostnamen Ihres Operations Manager-Servers (beispielsweise ATL-SCOM-001) im Feld **Verwaltungsserver** ein. Wenn Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer in das Feld Verwaltungs Server Port ein. Andernfalls können Sie den Port mit dem Standardwert 5723 und dann auf **weiter**klicken.

7.  Wählen Sie auf der Seite **Agent-Aktionskonto** die Option **Lokales System**aus, und klicken Sie dann auf **weiter**.

8.  Wählen Sie auf der Seite **Microsoft Update** die Option **Ich möchte Microsoft Update nicht verwenden**aus, und klicken Sie dann auf **weiter**.

9.  Klicken Sie auf der Seite **bereit zur Installation** auf **Installieren**.

10. Klicken Sie auf der Seite **abschließen des Setup-Assistenten von System Center Operations Manager** auf **Fertig stellen**.

11. Klicken Sie auf **Beenden**.

Wenn Sie System Center 2007 R2 verwenden, können Sie überprüfen, ob der Agent erstellt wurde, indem Sie auf **Start**klicken, auf **Alle Programme**klicken, auf **System Center Operations Manager 2007 R2**klicken und dann auf **Operations Manager-Shell**klicken. Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell-Befehl ein, und drücken Sie dann die EINGABETASTE:

    Get-Agent 

Auf dem Bildschirm wird eine Liste aller Operations Manager-Agents angezeigt.

Wenn Sie System Center 2012 verwenden, führen Sie diesen Befehl aus der Shell für Operations 2012-Manager aus:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

