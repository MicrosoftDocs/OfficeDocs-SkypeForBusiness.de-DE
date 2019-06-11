---
title: 'Lync Server 2013: Hinzufügen einer Survivable Branch Appliance zu Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-23_

Wenn Sie beabsichtigen, eine Survivable Branch-Appliance bereitzustellen, müssen Sie die Survivable Branch-Appliance zu Active Directory-Domänendiensten hinzufügen. Führen Sie dieses Verfahren am zentralen Standort aus.

<div>


> [!IMPORTANT]  
> Führen Sie dieses Verfahren nur aus, wenn Sie eine Survivable Branch-Appliance bereitstellen. Führen Sie das Programm nicht aus, wenn Sie einen Überlebenden Verzweigungs Server bereitstellen.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>So fügen Sie eine Survivable Branch-Appliance zu Active Directory-Domänendiensten hinzu

1.  Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Unternehmensadministratoren" an.

2.  Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.

3.  Klicken Sie im Menü **Aktionen** auf **neu** , und klicken Sie dann auf **Computer**.

4.  Geben Sie im Dialogfeld **Neues Objekt – Computer** einen Namen für das Survivable Branch Appliance-Computer Objekt ein (beispielsweise BranchOffice1), und klicken Sie dann auf **ändern**.

5.  Fügen Sie im Dialogfeld **Benutzer oder Gruppe auswählen** die RTCUniversalSBATechnicians-Gruppe hinzu, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Ein Mitglied der RTCUniversalSBATechnicians-Gruppe auf der Zweigstelle fügt dieses Gerät später zur Domäne hinzu.

    
    </div>

6.  Klicken Sie auf **OK** , um das Survivable Branch Appliance-Computerobjekt zu speichern.

7.  Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **ADSI-Bearbeitung**.

8.  Klicken Sie in der **ADSI-Bearbeitung**mit der rechten Maustaste auf das Computerobjekt, das Sie in den vorherigen Schritten erstellt haben, und klicken Sie dann auf **Eigenschaften**.

9.  Klicken Sie in der Liste Attribut auf **servicePrincipalName**, und klicken Sie dann auf **Bearbeiten**.

10. Geben Sie im Feld **Wert zum Hinzufügen** den Namen\<Host/\> SBA \<-FQDN\> ein, wobei SBA-FQDN der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihrer Survivable Branch Appliance ist. Geben Sie beispielsweise **Host/BranchOffice1. contoso. com**ein.

11. Klicken Sie auf **OK** , um die **servicePrincipalName** -Attributeinstellung zu speichern, und klicken Sie dann auf **OK** , um die Computerobjekt Eigenschaften zu speichern.

12. Klicken Sie in **Active Directory-Benutzer und-Computer**mit der rechten Maustaste auf **Benutzer**, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.

13. Geben Sie Informationen in den Assistenten ein, um ein Domänenbenutzerkonto für einen Survivable Branch Appliance-Techniker zu erstellen.

14. Klicken Sie in **Active Directory-Benutzer und-Computer**auf **Benutzer**, klicken Sie mit der rechten Maustaste auf das Benutzerobjekt, und klicken Sie dann auf **zu einer Gruppe hinzufügen**.

15. Geben Sie in **Geben Sie die zu wählenden Objektnamen ein** **RTCUniversalSBATechnicians**ein, und klicken Sie dann auf **OK**.

16. Wiederholen Sie die Schritte 12-15 für jeden Zweigstellen Techniker.

**Nächster Schritt**: [Hinzufügen von Zweigstellen zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

