---
title: 'Lync Server 2013: Gewähren von Berechtigungen für die Organisationseinheit'
TOCTitle: Gewähren von Berechtigungen für die Organisationseinheit
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398763(v=OCS.15)
ms:contentKeyID: 49294811
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-05-14_

Mithilfe des Cmdlets **Grant-CsOuPermission** können Sie auch Objekten in bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein. Bei den Berechtigungen, die Sie der angegebenen Organisationseinheit hinzufügen, handelt es sich um die gleichen Berechtigungen, die das Cmdlet **Enable-CsAdDomain** während der Domänenvorbereitung den Containern für Computer und Benutzer hinzufügt.

Verwenden Sie das Cmdlet **Test-CsOuPermission** zum Überprüfen der Berechtigungen, die Sie mit dem Cmdlet **Grant-CsOuPermission** gewähren.

Mit dem Cmdlet **Revoke-CsOuPermission** können Sie Berechtigungen entfernen, die Sie mit dem Cmdlet **Grant-CsOuPermission** zugewiesen haben.

## So gewähren Sie Organisationseinheitenberechtigungen

1.  Melden Sie sich bei einem Computer mit Lync Server 2013 in der Domäne an, in der Sie Organisationseinheitenberechtigungen gewähren möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

## So überprüfen Sie Organisationseinheitenberechtigungen

1.  Melden Sie sich bei einem Computer mit Lync Server 2013 in der Domäne an, in der Sie mit dem Cmdlet **Grant-CsOuPermission** gewährte Organisationseinheitenberechtigungen überprüfen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

## So entziehen Sie Organisationseinheitenberechtigungen

1.  Melden Sie sich bei einem Computer mit Lync Server 2013 in der Domäne an, in der Sie mit dem Cmdlet **Grant-CsOuPermission** gewährte Organisationseinheitenberechtigungen entziehen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

