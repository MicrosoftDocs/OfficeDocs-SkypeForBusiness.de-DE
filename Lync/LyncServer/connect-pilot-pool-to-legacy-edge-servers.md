---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc42c645548ea9bad072da5f18643271a9eceeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Edgeservern der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Nach der Bereitstellung von lync Server 2013 müssen Sie eine Verbund Route für Ihre Website konfigurieren. Um die von lync Server 2010 verwendete Föderations Route verwenden zu können, muss lync Server 2013 für die Verwendung dieser Route konfiguriert sein.

Damit die lync Server 2013-Website den Director und den Edgeserver der lync Server 2010-Bereitstellung verwenden kann, verwenden Sie den Topologie-Generator, um den Legacy-Edge-Pool zu verknüpfen.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Legacy-Edge-Pool mithilfe des Topologie-Generators zu

1.  Öffnen Sie den **Topologie-Generator**.

2.  Wählen Sie Ihre Website aus, die sich direkt unter dem **lync-Server** Knoten befindet.

3.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.

4.  Wählen Sie im linken Bereich **Föderations Route**aus.

5.  Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann den lync Server 2010 Director oder den lync Server 2010-Edgeserver aus, wenn kein Director aufgeführt ist.
    
    ![Eigenschaften bearbeiten, Seite "Verbund Route"] (images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Eigenschaften bearbeiten, Seite \"Verbund Route\"")  

6.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

7.  Navigieren Sie im Topologie-Generator unter dem lync Server 2013-Knoten zu den Front-End-Pools **Standard Edition Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

8.  Aktivieren Sie unter **Zuordnungen**das Kontrollkästchen neben **Edge-Pool zuordnen (für Medienkomponenten)**.

9.  Wählen Sie in der Liste den Legacy-Edgeserver aus.
    
    ![Dialogfeld "Eigenschaften bearbeiten", "Legacy Edge" auswählen] (images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Dialogfeld \"Eigenschaften bearbeiten\", \"Legacy Edge\" auswählen")  

10. Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

11. Wählen Sie im **Topologie-Generator**den obersten Knoten, **lync Server**, aus.

12. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.

13. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

