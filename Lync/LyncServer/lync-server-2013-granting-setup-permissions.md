---
title: 'Lync Server 2013: Gewähren von Setupberechtigungen'
TOCTitle: Gewähren von Setupberechtigungen
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398225(v=OCS.15)
ms:contentKeyID: 49293276
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gewähren von Setupberechtigungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-08-27_

Mit dem Cmdlet **Grant-CsSetupPermission** können Sie der Gruppe "RTCUniversalServerAdmins" Lese-, Schreib-, ReadSPN- und WriteSPN-Berechtigungen für eine angegebene Organisationseinheit (Organizational Unit, OU) in Active Directory zuweisen. Anschließend können Mitglieder der Gruppe "RTCUniversalServerAdmins" in dieser OU Server mit Lync Server 2013 in der angegebenen Domäne installieren, ohne Mitglied der Gruppe "Domänen-Admins" zu sein.

Verwenden Sie das Cmdlet **Test-CsSetupPermission** zum Überprüfen der Berechtigungen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** gewähren.

Mit dem Cmdlet **Revoke-CsSetupPermission** können Sie Berechtigungen entfernen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** zugewiesen haben.

## So gewähren Sie Setupberechtigungen

1.  Melden Sie sich bei einem Computer mit Lync Server 2013 in der Domäne an, in der Sie Berechtigungen gewähren möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

## So überprüfen Sie Setupberechtigungen

1.  Melden Sie sich bei einem Computer mit Lync Server 2013 in der Domäne an, in der Sie mit dem Cmdlet **Grant-CsSetupPermission** gewährte Setupberechtigungen überprüfen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

## So entziehen Sie Setupberechtigungen

1.  Melden Sie sich bei einem Computer mit Lync Server 2013 in der Domäne an, in der Sie mit dem Cmdlet **Grant-CsSetupPermission** gewährte Setupberechtigungen entziehen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

