---
title: 'Lync Server 2013: Hinzufügen einer Survivable Branch Appliance zu Active Directory'
TOCTitle: Hinzufügen einer Survivable Branch Appliance zu Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425906(v=OCS.15)
ms:contentKeyID: 49293774
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-23_

Wenn Sie die Bereitstellung einer Survivable Branch-Anwendung planen, müssen Sie die Survivable Branch-Anwendung zu den Active Directory-Domänendiensten (AD DS) hinzufügen. Führen Sie dieses Verfahren am zentralen Standort aus.


> [!IMPORTANT]
> Führen Sie dieses Verfahren nur aus, wenn Sie eine Survivable Branch-Anwendung bereitstellen. Führen Sie dieses Verfahren nicht aus, wenn Sie einen Survivable Branch-Server bereitstellen.



## So fügen Sie den Active Directory-Domänendiensten eine Survivable Branch Appliance hinzu

1.  Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.

2.  Klicken Sie nacheinander auf **Start** , **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer** .

3.  Klicken Sie im Menü **Aktionen** auf **Neu** und dann auf **Computer** .

4.  Geben Sie im Dialogfeld **Neues Objekt - Computer** einen Namen für das Survivable Branch-Anwendung-Computerobjekt ein (z. B. BranchOffice1), und klicken Sie dann auf **Ändern** .

5.  Fügen Sie im Dialogfeld **Benutzer oder Gruppe auswählen** die Gruppe "RTCUniversalSBATechnicians" hinzu, und klicken Sie auf **OK** .
    

    > [!NOTE]
    > Ein Mitglied der Gruppe "RTCUniversalSBATechnicians" am Zweigstellenstandort wird dieses Gerät später der Domäne hinzufügen.



6.  Klicken Sie auf **OK** , um das Survivable Branch-Anwendung-Computerobjekt zu speichern.

7.  Klicken Sie auf **Start** und auf **Verwaltung** und anschließend auf **ADSI-Editor** .

8.  Klicken Sie im **ADSI-Editor** mit der rechten Maustaste auf das Computerobjekt, das Sie im vorherigen Schritt erstellt haben, und klicken Sie dann auf **Eigenschaften** .

9.  Klicken Sie in der Attributliste auf **servicePrincipalName** und anschließend auf **Bearbeiten** .

10. Geben Sie im Feld **Hinzuzufügender Wert** den Wert "HOST/\<SBA-FQDN\>" ein, wobei "\<SBA-FQDN\>" für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Survivable Branch-Anwendung steht. Geben Sie beispielsweise **HOST/BranchOffice1.contoso.com** ein.

11. Klicken Sie auf **OK** , um die Attributeinstellung **servicePrincipalName** zu speichern, und klicken Sie dann auf **OK** , um die Eigenschaften des Computerobjekts zu speichern.

12. Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users** , klicken Sie auf **Neu** und anschließend auf **Benutzer** .

13. Geben Sie Informationen im Assistenten ein, um ein Domänenbenutzerkonto für einen Survivable Branch-Anwendung-Techniker zu erstellen.

14. Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users** , klicken Sie mit der rechten Maustaste auf das Benutzerobjekt, und klicken Sie dann auf **Einer Gruppe hinzufügen** .

15. Geben Sie unter **Geben Sie die zu verwendenden Objektnamen ein** den Wert **RTCUniversalSBATechnicians** ein, und klicken Sie dann auf **OK** .

16. Wiederholen Sie die Schritte 12 bis 15 für jeden Techniker am Zweigstellenstandort.

**Next step**: [Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

