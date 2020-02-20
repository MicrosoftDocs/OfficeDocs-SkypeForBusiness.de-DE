---
title: Entfernen von "BackCompatSite"
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f431ada6c48e830cfa06af98f5937cae9fa4d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Entfernen von "BackCompatSite"

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Nach dem Deaktivieren aller Pools und dem Deinstallieren aller Edgeserver führen Sie den Zusammenführungs-Assistenten des Topologie-Generators aus, um **BackCompatSite** zu entfernen.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>So entfernen Sie "BackCompatSite" aus dem Topologie-Generator

1.  Öffnen Sie im Topologie-Generator eine vorhandene Bereitstellung.

2.  Klicken Sie im Menü **Aktion** auf **Topologie von Office Communications Server 2007 R2 zusammenführen**.

3.  Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

4.  Stellen Sie auf der Seite **Legacy Edge angeben** sicher, dass die Liste der Edgeserver leer ist. Wenn die Liste nicht leer ist, verwenden Sie die **Entfernen** -Schaltfläche, um alle Legacy-Edgeserver zu entfernen, und klicken Sie dann auf **weiter**.
    
    ![Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"")  

5.  Klicken Sie auf der Seite **Internen SIP-Port angeben** auf **Weiter**.

6.  Klicken Sie auf der Seite **Zusammenfassung** auf **weiter** , um mit dem Zusammenführen der Topologien zu beginnen, um die Legacy Website zu entfernen.

7.  Stellen Sie in der Spalte **Status** sicher, dass der Wert **Erfolg** lautet, und klicken Sie zum Schließen des Assistenten auf **Fertig stellen**.

8.  Erweitern Sie im linken Bereich des Topologie-Generators die Option "BackCompatSite", und stellen Sie sicher, dass keine Server aufgeführt sind.

9.  Klicken Sie mit der rechten Maustaste auf **BackCompatSite**, und klicken Sie dann auf **Löschen**.

10. Wählen Sie im Topologie-Generator**** den obersten Knoten **Lync Server** aus.

11. Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus, und klicken Sie auf **Weiter**.

12. Klicken Sie nach dem Abschließen des **Veröffentlichungs-Assistenten** auf **Fertig stellen**, um den Assistenten zu schließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

