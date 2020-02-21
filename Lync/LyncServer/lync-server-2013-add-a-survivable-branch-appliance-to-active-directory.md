---
title: 'Lync Server 2013: Hinzufügen eines Survivable Branch Appliance zu Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d8efb03b4d67b6409f93b6a99d2314cb703952
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Hinzufügen eines Survivable Branch Appliance zu Active Directory in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-23_

Wenn Sie ein Survivable Branch Appliance bereitstellen möchten, müssen Sie den Survivable Branch Appliance Active Directory-Domänendienste hinzufügen. Führen Sie dieses Verfahren am zentralen Standort aus.

<div>


> [!IMPORTANT]  
> Führen Sie dieses Verfahren nur aus, wenn Sie ein Survivable Branch Appliance bereitstellen. Führen Sie ihn nicht aus, wenn Sie ein Survivable Branch Server bereitstellen.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>So fügen Sie den Active Directory-Domänendiensten eine Survivable Branch Appliance hinzu

1.  Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.

2.  Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer**.

3.  Klicken Sie im Menü **Aktionen** auf **Neu** und dann auf **Computer**.

4.  Geben Sie im Dialogfeld **Neues Objekt – Computer** einen Namen für das Survivable Branch Appliance Computer Objekt ein (beispielsweise BranchOffice1), und klicken Sie dann auf **ändern**.

5.  Fügen Sie im Dialogfeld **Benutzer oder Gruppe auswählen** die Gruppe "RTCUniversalSBATechnicians" hinzu, und klicken Sie auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Ein Mitglied der Gruppe "RTCUniversalSBATechnicians" am Zweigstellenstandort wird dieses Gerät später der Domäne hinzufügen.

    
    </div>

6.  Klicken Sie auf **OK** , um das Survivable Branch Appliance Computerobjekt zu speichern.

7.  Klicken Sie auf **Start** und auf **Verwaltung** und anschließend auf **ADSI-Editor**.

8.  Klicken Sie im **ADSI-Editor** mit der rechten Maustaste auf das Computerobjekt, das Sie im vorherigen Schritt erstellt haben, und klicken Sie dann auf **Eigenschaften**.

9.  Klicken Sie in der Attributliste auf **servicePrincipalName** und anschließend auf **Bearbeiten**.

10. Geben Sie im Feld **Hinzuzufügender Wert** Host\</SBA\> - \<FQDN ein\> , wobei SBA FQDN der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihrer Survivable Branch Appliance ist. Geben Sie beispielsweise **HOST/BranchOffice1.contoso.com** ein.

11. Klicken Sie auf **OK**, um die Attributeinstellung **servicePrincipalName** zu speichern, und klicken Sie dann auf **OK**, um die Eigenschaften des Computerobjekts zu speichern.

12. Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users**, klicken Sie auf **Neu** und anschließend auf **Benutzer**.

13. Geben Sie Informationen in den Assistenten ein, um ein Domänenbenutzerkonto für einen Survivable Branch Appliance Techniker zu erstellen.

14. Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users**, klicken Sie mit der rechten Maustaste auf das Benutzerobjekt, und klicken Sie dann auf **Einer Gruppe hinzufügen**.

15. Geben Sie unter **Geben Sie die zu verwendenden Objektnamen ein** den Wert **RTCUniversalSBATechnicians** ein, und klicken Sie dann auf **OK**.

16. Wiederholen Sie die Schritte 12 bis 15 für jeden Techniker am Zweigstellenstandort.

**Nächster Schritt**: [Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

