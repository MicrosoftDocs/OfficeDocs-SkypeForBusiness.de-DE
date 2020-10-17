---
title: Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20397cf75b5f1f33004865b7c3ac364b45ed2c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514932"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Führen Sie das folgende Verfahren aus, um einen Vermittlungsserver, der mit einem Standard Edition-Server oder Front-End-Pool verbunden ist, auf einen eigenständigen Vermittlungsserver für eine Bereitstellung mit einem einzigen Standort umzustellen.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>So stellen Sie einen verbundenen Vermittlungsserver auf einen eigenständigen Vermittlungsserver um

1.  Öffen Sie über den Topologie-Generator eine vorhandene Topologie.

2.  Navigieren Sie im linken Bereich zu **Vermittlungspools**.

3.  Klicken Sie mit der rechten Maustaste auf **Vermittungspools**, und klicken Sie dann auf **Neuer Vermittlungsserver**.

4.  Geben Sie auf der Seite **Neuen Vermittlungspool definieren** den vollqualifizierten Domänennamen (FQDN) des neuen Vermittlungsserverpools ein. Geben Sie außerdem an, ob dieser Pool einen einzelnen oder mehrere Server enthalten soll, und klicken Sie dann auf **Weiter**.

5.  Wählen Sie den nächsten Front-End-Server-Hoppool aus, an den der neue Vermittlungsserver eingehende Anrufe weiterleiten soll, und klicken Sie auf **Weiter**.

6.  Wählen Sie den Edgepool aus, der von dem neuen Vermittlungsserver verwendet werden soll, und klicken Sie auf **Weiter**.

7.  Ordnen Sie auf der Seite **PSTN-Gateways angeben** das vorherige PSTN-Gateway dem Vermittlungsserver zu. Wählen Sie das Gateway aus, und klicken Sie dann auf **Hinzufügen**.

8.  Klicken Sie auf **Fertig stellen**, um den Assistenten zum Definieren eines neuen Vermittlungspools **** zu schließen.

9.  Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.

10. Klicken Sie im Bereich **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.

11. Führen Sie die Schritte unter [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Vermittlungsserver zu installieren.

12. Nachdem die Dateien auf dem Vermittlungsserver installiert worden sind, kehren Sie zum Topologie-Generator zurück, und navigieren Sie im linken Bereich zu dem Pool.

13. Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

14. Deaktivieren Sie unter **Vermittlungsserver** das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert**, und klicken Sie dann auf **OK**.

15. Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.

16. Wählen Sie im Menü **Aktion****Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.

</div>

</div>

<span> </span>

</div>

</div>

</div>

