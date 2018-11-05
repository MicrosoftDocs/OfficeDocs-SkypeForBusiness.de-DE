---
title: 'Lync Server 2013: Testen der Funktionsfähigkeit der Kerberos-Authentifizierung und Erstellen eines Berichts'
TOCTitle: Testen der Funktionsfähigkeit der Kerberos-Authentifizierung und Erstellen eines Berichts
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398925(v=OCS.15)
ms:contentKeyID: 49295526
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testen der Funktionsfähigkeit der Kerberos-Authentifizierung und Erstellen eines Berichts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Sie können das Cmdlet **Test-CsKerberosAccountAssignment**  Windows PowerShell verwenden, um die Funktionsfähigkeit einer Standortzuweisung für die Kerberos-Authentifizierung zu testen und einen Bericht zu erstellen. Dieser Befehl fragt den im erforderlichen Parameter "Identity" angegebenen Standort ab. Der optionale Parameter "Report" weist das Cmdlet an, einen HTML-Bericht in das Verzeichnis "C:\\Logs" auf dem Computer zu generieren, auf dem der Befehl ausgeführt wird. Bei Verwendung des optionalen Parameters "Verbose" werden auf dem Bildschirm ausführliche Informationen zur Aktivität ausgegeben.

## So testen Sie die Funktionsfähigkeit der Kerberos-Authentifizierung an einem Standort und erstellen einen Bericht

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" bei einem Computer in der Domäne an, auf dem Lync Server 2013 ausgeführt wird. Alternativ können Sie sich bei einem Computer anmelden, auf dem die Verwaltungstools installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl über die Befehlszeile aus:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Beispiel:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

