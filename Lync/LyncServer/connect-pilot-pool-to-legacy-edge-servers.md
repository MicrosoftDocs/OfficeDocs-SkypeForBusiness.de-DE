---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 313d2201be5f5919aeec37087a02bf7f400d7ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Edgeservern der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Nach der Bereitstellung lync Server 2013 müssen Sie eine partnerverbundroute für Ihre Website konfigurieren. Um die von lync Server 2010 verwendete Verbund Route verwenden zu können, müssen lync Server 2013 für die Verwendung dieser Route konfiguriert sein.

Damit die lync Server 2013 Website den Director und Edgeserver der lync Server 2010-Bereitstellung verwenden kann, ordnen Sie die Legacy-Edgepool mithilfe des Topologie-Generators zu.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Edgepool der Vorgängerversion mithilfe des Topologie-Generators zu

1.  Öffnen Sie den **Topologie-Generator**.

2.  Wählen Sie Ihren Standort aus, der sich direkt unterhalb des **Lync Server**-Knotens befindet.

3.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.

4.  Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.

5.  Wählen Sie unter **Standort Verbund Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann den lync Server 2010 Director oder den lync Server 2010 Edgeserver, wenn kein Director aufgeführt ist.
    
    ![Eigenschaften bearbeiten, Verbund Route (Seite)](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Eigenschaften bearbeiten, Verbund Route (Seite)")  

6.  Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.

7.  Navigieren Sie im Topologie-Generator unter dem Knoten lync Server 2013 zu den Front-End-Pools **Standard Edition-Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

8.  Aktivieren Sie unter **Zuordnungen** das Kontrollkästchen neben **Edgepool zuordnen (für Medienkomponenten)**.

9.  Wählen Sie in der Liste den Edgeserver der Vorversion aus.
    
    ![Dialogfeld ' Eigenschaften bearbeiten ', auswählen des Legacy-Edges](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', auswählen des Legacy-Edges")  

10. Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.

11. Wählen Sie im Topologie-Generator**** den obersten Knoten aus, **Lync Server**.

12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.

13. Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

