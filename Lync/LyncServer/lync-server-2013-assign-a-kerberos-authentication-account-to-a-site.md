---
title: 'Lync Server 2013: Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort'
TOCTitle: Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425901(v=OCS.15)
ms:contentKeyID: 49293763
ms.date: 04/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-04-18_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Nach der Erstellung des Kerberos-Kontos müssen Sie dieses einem Standort zuweisen. Es handelt sich hierbei um einen Lync Server 2013-Standort, nicht um einen Active Directory-Standort. Sie können pro Bereitstellung mehrere Kerberos-Authentifizierungskonten erstellen, einem Standort kann jedoch nur jeweils ein Konto zugewiesen werden. Verwenden Sie das folgende Verfahren, um ein zuvor erstelltes Kerberos-Authentifizierungskonto einem Standort zuzuweisen. Ausführliche Informationen zum Erstellen des Kerberos-Kontos finden Sie unter [Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

## So weisen Sie ein Kerberos-Authentifizierungskonto einem Standort zu

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" bei einem Computer in der Domäne an, auf dem Lync Server 2013 ausgeführt wird. Alternativ können Sie sich bei einem Computer anmelden, auf dem die Verwaltungstools installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:
    
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount" -Identity "site:SiteName"
        
       &nbsp;
    
        Enable-CsTopology
    
    Beispiel:
    
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth" -Identity "site:redmond"

       &nbsp;
    
        Enable-CsTopology
    

    > [!NOTE]
    > Sie müssen den Parameter "UserAccount" im Format "Domäne\Benutzer" angeben. Das Format "Benutzer@Domäne.Erweiterung" wird zur Referenzierung der für die Kerberos-Authentifizierung erstellten Computerobjekte nicht unterstützt.

    

    > [!IMPORTANT]
    > Nach dem Durchführen von Änderungen an der Kerberos-Authentifizierung, beispielsweise nach dem Hinzufügen oder Entfernen eines Kontos, müssen Sie das Cmdlet <STRONG>Enable-CsTopology</STRONG> an der Lync Server-Verwaltungsshell-Eingabeaufforderung ausführen.


