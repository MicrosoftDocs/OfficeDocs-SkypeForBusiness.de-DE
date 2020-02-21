---
title: 'Lync Server 2013: definieren und Konfigurieren einer Topologie im Topologie-Generator'
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
ms.openlocfilehash: 597f331ba95ee563155fdabc6b95d35367d12080
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Die Ausführung des Topologie-Generators zum Definieren einer neuen Topologie oder zum Ändern einer vorhandenen Topologie erfordert keine Mitgliedschaft in einem lokalen Administrator oder einer privilegierten Domänengruppe. Der Topologie-Generator führt Sie durch die Schritte, die erforderlich sind, um Ihre Topologie für ein Enterprise Edition-Front-End-Pool oder eine Standard Edition basierend auf Ihren Konfigurationsanforderungen zu definieren.

Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie lync Server 2013 auf Servern installieren können. Das folgende Verfahren umfasst die zum Definieren einer neuen Topologie erforderlichen Schritte.

<div>

## <a name="to-define-a-topology"></a>So definieren Sie eine Topologie

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Wählen Sie im Topologie-Generator die Option **neue Topologie**aus. Sie werden aufgefordert, einen Speicherort und einen Dateinamen zum Speichern der Topologie anzugeben. Geben Sie der Topologiedatei einen aussagekräftigen Namen, und übernehmen Sie die Standarderweiterung ".tbxml". Klicken Sie auf **OK**.

3.  Navigieren Sie zu dem Speicherort, in dem die XML-Datei der neuen Topologie gespeichert werden soll, geben Sie einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.

4.  Geben Sie auf der Seite **Primäre Domäne definieren** den Namen der primären SIP-Domäne für Ihre Organisation ein, und klicken Sie dann auf **Weiter**.

5.  Geben Sie auf der Seite **Weitere unterstützte Domänen angeben** gegebenenfalls die Namen weiterer Domänen ein, und klicken Sie anschließend auf **Weiter**.

6.  Geben Sie auf der Seite **Ersten Standort definieren** einen Namen und eine Beschreibung für den ersten Standort ein, und klicken Sie dann auf **Weiter**.

7.  Geben Sie auf der Seite **Standortdetails angeben** die Standortinformationen für den Standort ein, und klicken Sie dann auf **Weiter**.

8.  Stellen Sie auf der Seite **neue Topologie wurde erfolgreich definiert** sicher, dass das Kontrollkästchen **neuen Front-End-Assistenten öffnen, wenn dieser Assistent geschlossen** wird aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

Nachdem Sie die Topologie definiert und gespeichert haben, können Sie mit dem neuen Front-End-Assistenten eine Front-End-Pool oder Standard Edition-Server für Ihre Website definieren. Ausführliche Informationen finden Sie unter [define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

