---
title: 'Lync Server 2013: Definieren und Konfigurieren einer Topologie im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Das Ausführen des Topologie-Generators zum Definieren einer neuen Topologie oder zum Ändern einer vorhandenen Topologie erfordert keine Mitgliedschaft in einem lokalen Administrator oder einer privilegierten Domänengruppe. Der Topologie-Generator führt Sie durch die Schritte, die erforderlich sind, um Ihre Topologie für einen Enterprise Edition-Front-End-Pool oder eine Standard Edition basierend auf Ihren Konfigurationsanforderungen zu definieren.

Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie lync Server 2013 auf Servern installieren können. Das folgende Verfahren enthält die erforderlichen Schritte zum Definieren einer neuen Topologie.

<div>

## <a name="to-define-a-topology"></a>So definieren Sie eine Topologie

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Wählen Sie im Topologie-Generator die Option **neue Topologie**aus. Sie werden aufgefordert, einen Speicherort und einen Dateinamen zum Speichern der Topologie einzugeben. Geben Sie der topologiedatei einen aussagekräftigen Namen, und übernehmen Sie die Standarderweiterung tbxml. Klicken Sie auf **OK**.

3.  Navigieren Sie zu dem Speicherort, an dem Sie die neue Topologie-XML-Datei speichern möchten, geben Sie einen Namen für die Datei ein, und klicken Sie auf **Speichern**.

4.  Geben Sie auf der Seite **primäre Domäne definieren** den Namen der primären SIP-Domäne für Ihre Organisation ein, und klicken Sie dann auf **weiter**.

5.  Geben Sie auf der Seite **zusätzliche unterstützte Domänen angeben** die Namen zusätzlicher Domänen ein, sofern vorhanden, und klicken Sie dann auf **weiter**.

6.  Geben Sie auf der Seite **erste Website definieren** einen Namen und eine Beschreibung für die erste Website ein, und klicken Sie dann auf **weiter**.

7.  Geben Sie auf der Seite **Website Details angeben** die Standortinformationen für die Website ein, und klicken Sie dann auf **weiter**.

8.  Vergewissern Sie sich, dass auf der Seite **neue Topologie erfolgreich definiert** ist, das Kontrollkästchen **neuen Front-End-Assistenten öffnen, wenn dieser Assistent geschlossen** wird, aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

Nachdem Sie die Topologie definiert und gespeichert haben, verwenden Sie den neuen Front-End-Assistenten, um einen Front-End-Pool oder Standard Edition-Server für Ihre Website zu definieren. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

