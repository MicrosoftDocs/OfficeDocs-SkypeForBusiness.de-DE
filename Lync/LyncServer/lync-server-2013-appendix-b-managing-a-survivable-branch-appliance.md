---
title: 'Lync Server 2013: Anhang B: Verwalten einer Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b16d4c55197785a6df12ad2031dbd2e624501ebd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Anhang B: Verwalten einer Survivable Branch Appliance in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

In diesem Thema werden die Verfahren zum Verwalten einer Survivable Branch-Appliance beschrieben. Insbesondere wird beschrieben, wie eine überlebensfähige Branch Appliance ersetzt und umbenannt wird und wie der lync Server 2013-Front-End-Pool geändert wird, dem die Survivable Branch-Appliance zugeordnet ist.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>So ersetzen Sie eine Survivable Branch-Appliance

1.  Beenden Sie alle lync Server 2013-Dienste auf der Survivable Branch-Appliance. (Weitere Informationen finden Sie in der Vendor-Dokumentation für Survivable Branch Appliances.)

2.  Empfohlen Entfernen Sie die Survivable Branch-Appliance aus der Domäne.

3.  Führen Sie die folgenden Schritte aus, um das Computerobjekt Survivable Branch Appliance in den Active Directory-Domänendiensten zu löschen:
    
      - Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Unternehmensadministratoren" an.
    
      - Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.
    
      - Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance-Objekt, und klicken Sie auf **Löschen**.

4.  Fügen Sie das Computerobjekt der Survivable Branch Appliance erneut hinzu. (Weitere Informationen finden Sie unter [Hinzufügen einer Survivable Branch-Appliance zu Active Directory in lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Warten Sie, bis die Active Directory-Replikation durchgeführt wird.

6.  Öffnen Sie die lync Server-Verwaltungsshell, und geben Sie **enable-CSTopology**ein.

7.  Verbinden Sie die neue Survivable Branch-Appliance mit dem Netzwerk, und führen Sie die Schritte unter [Bereitstelleneiner überlebensfähigen Branch-Appliance oder eines Servers mit lync Server 2013-Central-Websiteaufgaben](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) aus, und [Stellen Sie eine Survivable Branch-Appliance oder einen Server mit lync Server 2013-Branch Site-Aufgabe bereit](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>So benennen Sie eine Survivable Branch-Appliance um

1.  Verschieben von Benutzern auf die zentrale Website Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Beenden Sie alle lync Server 2013-Dienste auf der Survivable Branch-Appliance. (Weitere Informationen finden Sie in der Vendor-Dokumentation für Survivable Branch Appliances.)

3.  Führen Sie die folgenden Schritte aus, um die Survivable Branch-Appliance aus der Topologie zu entfernen:
    
      - Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.
    
      - Erweitern Sie in der Konsolenstruktur **Verzweigungs Websites**, klicken Sie auf die Survivable Branch-Appliance, und klicken Sie dann im Bereich "Aktion" auf **Löschen** .

4.  Entfernen Sie die Survivable Branch-Appliance aus der Domäne.

5.  Führen Sie die folgenden Schritte aus, um das Computerobjekt Survivable Branch Appliance in Active Directory zu löschen:
    
      - Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Unternehmensadministratoren" an.
    
      - Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.
    
      - Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance-Objekt, und klicken Sie auf **Löschen**.

6.  Wiederherstellen der Überlebenden Branch-Appliance auf die Werkseinstellungen (Weitere Informationen finden Sie in der Vendor-Dokumentation für Survivable Branch Appliances.)

7.  Führen Sie die Schritte unter [Bereitstelleneiner überlebensfähigen Zweigstelle oder eines Servers mit lync Server 2013 – zentrale Websiteaufgaben](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) aus, und [Stellen Sie eine Survivable Branch Appliance oder einen Server mit lync Server 2013-Branch Site Task bereit](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Verschieben Sie Benutzer in die umbenannte Survivable Branch Appliance. Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>So ändern Sie den lync Server-Front-End-Pool, dem die Survivable Branch-Appliance zugeordnet ist

1.  Verschieben Sie Benutzer aus der Survivable Branch-Appliance in den lync Server-Front-End-Pool am zentralen Standort. Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Beenden Sie alle lync Server-Dienste auf der Survivable Branch-Appliance. (Weitere Informationen finden Sie in der Dokumentation zum Survivable Branch Appliance-Hersteller).

3.  Führen Sie die folgenden Schritte aus, um den lync Server-Front-End-Pool zu aktualisieren, dem die Survivable Branch-Appliance zugeordnet ist:
    
      - Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.
    
      - Erweitern Sie **Zweigstellen**.
    
      - Klicken Sie mit der rechten Maustaste auf das zu ändernde Survivable Branch Appliance-Objekt, und klicken Sie auf **Eigenschaften bearbeiten** .
    
      - Wählen Sie unter Widerstandsfähigkeit den neuen Front-End-Pool aus, dem die Survivable Branch-Appliance zugeordnet werden soll, und klicken Sie dann auf **weiter**.
    
      - Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch-Appliance, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.

4.  Starten Sie alle lync Server-Dienste auf der Survivable Branch-Appliance neu.

5.  Testen Sie die Survivable Branch-Appliance. Ausführliche Informationen finden Sie unter [private Benutzer auf einer Survivable Branch-Appliance oder einem Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Verschieben Sie Benutzer aus dem lync Server-Front-End-Pool am zentralen Standort in die Survivable Branch-Appliance.

</div>

</div>

<span> </span>

</div>

</div>

</div>

