---
title: 'Lync Server 2013: Aktivieren von Benutzern für den einheitlichen Kontaktspeicher'
TOCTitle: Aktivieren von Benutzern für den einheitlichen Kontaktspeicher
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205024(v=OCS.15)
ms:contentKeyID: 49294505
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Wenn Sie Lync Server 2013 bereitstellen und die Topologie veröffentlichen, wird der einheitliche Kontaktspeicher standardmäßig für alle Benutzer aktiviert. Sie müssen keine zusätzlichen Schritte ausführen, um den einheitlichen Kontaktspeicher nach der Bereitstellung von Lync Server 2013 zu aktivieren. Sie können jedoch das **Set-CsUserServicesPolicy**-Cmdlet verwenden, um anzupassen, für welche Benutzer der einheitliche Kontaktspeicher verfügbar sein soll. Sie können diese Funktion global bzw. nach Standort, Mandant, Einzelperson oder Benutzergruppe aktivieren.

## So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie den einheitlichen Kontaktspeicher global für alle Lync Server-Benutzer aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Wenn Sie den einheitlichen Kontaktspeicher für die Benutzer an einem bestimmten Standort aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Beispiel:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Wenn Sie den einheitlichen Kontaktspeicher nach Mandant aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Beispiel:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Wenn Sie den einheitlichen Kontaktspeicher für bestimmte Benutzer aktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        

        > [!NOTE]
        > Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden.

        
        Beispiel:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        

        > [!NOTE]
        > Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen <EM>UCS Enabled Users</EM> erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist. Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d.&nbsp;h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.


