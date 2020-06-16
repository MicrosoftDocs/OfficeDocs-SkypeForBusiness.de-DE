---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Edgeservern der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Nach der Bereitstellung lync Server 2013 ist eine Verbund Route für diesen Standort nicht konfiguriert. Um die von Office Communications Server 2007 R2 verwendete Verbund Route verwenden zu können, müssen lync Server 2013 für die Verwendung dieser Route konfiguriert sein.

Damit die lync Server 2013 Website den Director und Edgeserver des BackCompatSite verwenden kann, ordnen Sie die Legacy Edgepool mithilfe des Topologie-Generators zu.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu

1.  Öffnen Sie den Pilotpool im Topologie-Generator.

2.  Wählen Sie Ihre lync Server 2013 Website aus.

3.  Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten**.

4.  Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann den Office Communications Server 2007 R2 Director oder den Office Communications Server 2007 R2 Edgeserver, wenn kein Director aufgeführt ist.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"")  

5.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.

6.  Navigieren Sie im Topologie-Generator unter dem Knoten lync Server 2013 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

7.  Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**.

8.  Wählen Sie in der Liste die Edgeserverschnittstelle für BackCompatSite aus.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")  

9.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.

10. Wählen Sie im Topologie-Generator**** den obersten Knoten aus, **Lync Server**.

11. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.

12. Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

