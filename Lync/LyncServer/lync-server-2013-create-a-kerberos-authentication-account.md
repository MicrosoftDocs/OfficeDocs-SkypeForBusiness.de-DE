---
title: 'Lync Server 2013: Erstellen eines Kerberos-Authentifizierungskontos'
TOCTitle: Erstellen eines Kerberos-Authentifizierungskontos
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398449(v=OCS.15)
ms:contentKeyID: 49294208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-01-02_

Für die folgenden Schritte sollten Sie auf dem Server oder der Domäne mindestens als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.

Sie können für jeden Standort ein eigenes Kerberos-Authentifizierungskonto oder ein einziges Kerberos-Authentifizierungskonto für alle Standorte erstellen. Mit Windows PowerShell-Cmdlets können Sie die Konten erstellen, verwalten und ermitteln, welche Konten einzelnen Sites zugeordnet sind. Im Topologie-Generator und in der Systemsteuerung für Lync Server 2013 werden Kerberos-Authentifizierungskonten nicht angezeigt. Gehen Sie wie folgt vor, um ein oder mehrere Benutzerkonten zur Kerberos-Authentifizierung zu erstellen.

## So erstellen Sie ein Kerberos-Konto

1.  Melden Sie sich an einem Computer als Mitglied der Gruppe "Domänen-Admins" in der Domäne an, in der Lync Server 2013 ausgeführt wird, oder auf dem die Verwaltungstools installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl über die Befehlszeile aus:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Beispiel:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Öffnen Sie **Active Directory-Benutzer und -Computer** , erweitern Sie den Container **Users** , und überprüfen Sie, ob sich das Computerobjekt für das Benutzerkonto in diesem Container befindet.

