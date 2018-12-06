---
title: 'Lync Server 2013: Melden von Kerberos-Kontozuweisungen'
TOCTitle: Melden von Kerberos-Kontozuweisungen
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398343(v=OCS.15)
ms:contentKeyID: 49294001
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Melden von Kerberos-Kontozuweisungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Mit dem Cmdlet **Get-CsKerberosAccountAssignment** können Sie Informationen zu Kontozuweisungen für die Kerberos-Authentifizierung sowie Berichtinformationen zu den aktuellen Zuweisungen in Ihrer Bereitstellung abrufen.

## So rufen Sie Kontozuweisungen für die Kerberos-Authentifizierung für einen Standort ab

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" bei einem Computer in der Domäne an, auf dem Lync Server 2013 ausgeführt wird. Alternativ können Sie sich bei einem Computer anmelden, auf dem die Verwaltungstools installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile einen der folgenden Befehle aus:
    
      - Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung in Ihrer Organisation und Zurückgeben von Informationen zu den einzelnen Zuweisungen führen Sie das Cmdlet ohne Parameter aus:
        
            Get-CsKerberosAccountAssignment
    
      - Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung in Ihrer Bereitstellung und Zurückgeben von Standortzuweisungsinformationen zu den einzelnen Zuweisungen führen Sie das Cmdlet mit dem Identitätsparameter aus:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Beispiel:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Zum Abrufen aller Kontozuweisungen für die Kerberos-Authentifizierung an einem einzelnen Standort und Zurückgeben von Informationen zu den einzelnen Zuweisungen führen Sie das Cmdlet mit dem Filterparameter aus:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Beispiel:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        

        > [!NOTE]
        > Bei Angabe von "*SiteName" als Filterparameter werden Informationen zu sämtlichen Standorten zurückgegeben, deren Standort-ID den angegebenen Standortnamen enthält (z.&nbsp;B. alle Standorte mit der Zeichenfolge "Redmond" in der Standort-ID).


