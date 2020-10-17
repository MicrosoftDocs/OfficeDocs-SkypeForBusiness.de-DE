---
title: 'Lync Server 2013: Anhang B: Verwalten eines Survivable Branch Appliance'
description: 'Lync Server 2013: Anhang B: Verwalten eines Survivable Branch Appliance.'
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
ms.openlocfilehash: e66d97f538ee751d7bf12b0d0f70ff3a3f5576b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561831"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Anhang B: Verwalten einer Survivable Branch Appliance in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

In diesem Thema werden die Verfahren zum Verwalten eines Survivable Branch Appliance beschrieben. Insbesondere wird das ersetzen und Umbenennen eines Survivable Branch Appliance und das Ändern der lync Server 2013 Front-End-Pool, der das Survivable Branch Appliance zugeordnet ist.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>So ersetzen Sie eine Survivable Branch Appliance

1.  Beenden Sie alle lync Server 2013 Dienste auf dem Survivable Branch Appliance. (Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)

2.  Empfohlen Entfernen Sie die Survivable Branch Appliance aus der Domäne.

3.  Löschen Sie das Survivable Branch Appliance Computerobjekt in Active Directory-Domänendienste, indem Sie die folgenden Schritte ausführen:
    
      - Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.
    
      - Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer**.
    
      - Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance Objekt, und klicken Sie auf **Löschen**.

4.  Fügen Sie das Computerobjekt Survivable Branch Appliance erneut hinzu. (Weitere Informationen finden Sie unter [Add a Survivable Branch Appliance to Active Directory in lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Warten Sie, bis Active Directory Replikation stattfindet.

6.  Öffnen Sie die lync Server-Verwaltungsshell, und geben Sie **enable-CSTopology**ein.

7.  Verbinden Sie den neuen Survivable Branch Appliance mit dem Netzwerk, und führen Sie die Schritte unter [Deploying a Survivable Branch Appliance or Server with lync Server 2013-Central Site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) aus, und [Stellen Sie einen Survivable Branch Appliance oder Server mit lync Server 2013-Branch Site Task bereit](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>So benennen Sie eine Survivable Branch Appliance um

1.  Verschieben Sie die Benutzer an den zentralen Standort. Ausführliche Informationen finden Sie unter [Verschiebe Benutzer in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Beenden Sie alle lync Server 2013 Dienste auf dem Survivable Branch Appliance. (Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)

3.  Führen Sie die folgenden Schritte aus, um den Survivable Branch Appliance aus der Topologie zu entfernen:
    
      - Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.
    
      - Erweitern Sie in der Konsolenstruktur **Zweigstellen**, klicken Sie auf die Survivable Branch Appliance, und klicken Sie dann im Aktionsbereich auf **Löschen** .

4.  Entfernen Sie die Survivable Branch Appliance aus der Domäne.

5.  Löschen Sie das Survivable Branch Appliance Computerobjekt in Active Directory, indem Sie die folgenden Schritte ausführen:
    
      - Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Organisations-Admins" an.
    
      - Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer**.
    
      - Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance Objekt, und klicken Sie auf **Löschen**.

6.  Stellen Sie die Survivable Branch Appliance auf Werkseinstellungen wieder her. (Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)

7.  Befolgen Sie die Schritte unter [Deploying a Survivable Branch Appliance or Server with lync Server 2013-Central Site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) und [Deploy a Survivable Branch Appliance or Server with lync Server 2013-Branch Site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Benutzer in das umbenannte Survivable Branch Appliance umsetzen. Ausführliche Informationen finden Sie unter [Verschiebe Benutzer in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>So ändern Sie den der Survivable Branch Appliance zugeordneten Lync Server-Front-End-Pool

1.  Migrieren von Benutzern aus dem Survivable Branch Appliance zum lync Server Front-End-Pool am zentralen Standort. Ausführliche Informationen finden Sie unter [Verschiebe Benutzer in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Beenden Sie alle lync Server Dienste auf dem Survivable Branch Appliance. (Weitere Informationen finden Sie in der Dokumentation zum Survivable Branch Appliance Anbieter).

3.  Führen Sie die folgenden Schritte aus, um die lync Server Front-End-Pool, der die Survivable Branch Appliance zugeordnet ist, zu aktualisieren:
    
      - Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.
    
      - Erweitern Sie **Zweigniederlassungen**.
    
      - Klicken Sie mit der rechten Maustaste auf das zu ändernde Survivable Branch Appliance Objekt, und klicken Sie auf **Eigenschaften bearbeiten** .
    
      - Wählen Sie unter Ausfallsicherheit die neue Front-End-Pool der Survivable Branch Appliance zugeordnet werden soll, und klicken Sie dann auf **weiter**.
    
      - Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den neuen Survivable Branch Appliance, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.

4.  Starten Sie alle lync Server Dienste auf dem Survivable Branch Appliance neu.

5.  Testen Sie die Survivable Branch Appliance. Ausführliche Informationen finden Sie unter [Home users on a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Migrieren von Benutzern aus dem lync Server Front-End-Pool am zentralen Standort in den Survivable Branch Appliance.

</div>

</div>

<span> </span>

</div>

</div>

</div>

