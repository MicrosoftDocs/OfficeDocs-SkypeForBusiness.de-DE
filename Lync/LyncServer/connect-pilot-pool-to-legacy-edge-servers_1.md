---
title: Verbinden des Pilotpools mit Edgeservern der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Verbinden des Pilotpools mit Edgeservern der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Nach der Bereitstellung von lync Server 2013 ist eine Föderations Route für diesen Standort nicht konfiguriert. Um die von Office Communications Server 2007 R2 verwendete Federated-Route zu verwenden, muss lync Server 2013 für die Verwendung dieser Route konfiguriert sein.

Um die lync Server 2013-Website für die Verwendung des Directors und des Edge-Servers des BackCompatSite zu aktivieren, verwenden Sie den Topologie-Generator, um den Legacy-Edge-Pool zuzuordnen.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>So ordnen Sie den Legacy-Edge-Pool mithilfe des Topologie-Generators zu

1.  Öffnen Sie die Topologie des pilotpools im Topologie-Generator.

2.  Wählen Sie Ihre lync Server 2013-Website aus.

3.  Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten**.

4.  Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann den Office Communications Server 2007 R2-Director oder den Office Communications Server 2007 R2-Edgeserver aus, wenn kein Director aufgeführt ist.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"] (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Dialogfeld \"Eigenschaften bearbeiten\", Seite \"Verbund Route\"")  

5.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

6.  Navigieren Sie im Topologie-Generator unter dem lync Server 2013-Knoten zu den Front-End-Pools **Standard Edition Server** oder **Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

7.  Aktivieren Sie unter **Zuordnungen**das Kontrollkästchen neben **Edge-Pool zuordnen (für Medienkomponenten)**.

8.  Wählen Sie in der Liste die Edge-Server-Oberfläche für den BackCompatSite aus.
    
    ![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"] (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Dialogfeld \"Eigenschaften bearbeiten\", Seite \"Allgemein\"")  

9.  Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.

10. Wählen Sie im **Topologie-Generator**den obersten Knoten, **lync Server**, aus.

11. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.

12. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

