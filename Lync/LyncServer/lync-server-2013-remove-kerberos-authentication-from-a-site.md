---
title: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung aus einem Standort'
TOCTitle: Entfernen der Kerberos-Authentifizierung aus einem Standort
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398749(v=OCS.15)
ms:contentKeyID: 49294774
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen der Kerberos-Authentifizierung aus einem Standort in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Wenn Sie die Kerberos-Authentifizierung von einem Standort entfernen oder einen Standort außer Betrieb nehmen möchten, müssen Sie die Zuweisung des Kerberos-Authentifizierungskontos mithilfe des Cmdlets **Remove-CsKerberosAccountAssignment** aus dem Standort entfernen. Führen Sie die folgenden Schritte aus, um die Zuweisung des Kerberos-Authentifizierungskontos zu entfernen. Dabei wird die Zuweisung von allen Computern an diesem Standort entfernt.


> [!WARNING]
> Wenn Sie ein Kerberos-aktiviertes Konto dauerhaft außer Betrieb nehmen, sollten Sie das Konto über "Active Directory-Benutzer und -Computer" aus Active Directory-Domänendienste löschen, nachdem Sie die Zuweisung entfernt haben. Wenn Sie das Objekt in der Zukunft verwenden möchten, sollten Sie das Active Directory-Objekt beibehalten.



## So entfernen Sie die Kerberos-Authentifizierung aus einem Standort

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" bei einem Computer in der Domäne an, auf dem Lync Server 2013 ausgeführt wird. Alternativ können Sie sich bei einem Computer anmelden, auf dem die Verwaltungstools installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:
    
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"

       &nbsp;
    
        Enable-CsTopology
    
    Beispiel:
    
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"

       &nbsp;
    
        Enable-CsTopology
    

    > [!IMPORTANT]
    > Nach dem Durchführen von Änderungen an der Kerberos-Authentifizierung, beispielsweise nach dem Hinzufügen oder Entfernen eines Kontos, müssen Sie das Cmdlet <STRONG>Enable-CsTopology</STRONG> an der Lync Server-Verwaltungsshell-Eingabeaufforderung ausführen.


