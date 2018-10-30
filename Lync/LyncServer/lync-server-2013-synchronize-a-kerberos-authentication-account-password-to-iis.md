---
title: 'Lync Server 2013: Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS'
TOCTitle: Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398107(v=OCS.15)
ms:contentKeyID: 49293048
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2010-11-08_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Innerhalb eines Standorts können Front-End-Server, Standard Edition-Server und Director-Server ein Kerberos-Authentifizierungskonto verwenden, um Anforderungen an die Webdienste zu authentifizieren. Bei diesem Verfahren werden alle Server mit ausgeführten Webdiensten an einem Standort mit zugewiesenem Kerberos-Konto ermittelt und die Konfigurationseinstellungen der Internetinformationsdienste (Internet Information Services, IIS) zur Verwendung des Kerberos-Kontos aktualisiert. Ausführliche Informationen finden Sie unter [Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

## So legen Sie ein Kennwort für das Kerberos-Authentifizierungskonto fest

1.  Melden Sie sich bei einem Quellcomputer (z. B. "fe01.contoso.com") als Mitglied der Gruppe "RTCUniversalServerAdmins" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie in der Lync Server-Verwaltungsshell-Befehlszeile die folgenden zwei Befehle aus:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Beispiel:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    

    > [!IMPORTANT]
    > Bei den Namen für den Quell- und den Zielcomputer muss es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers handeln. Sie können den Pool-FQDN nur dann verwenden, wenn der Poolname mit dem Namen des Computers übereinstimmt, den Sie als Quell- oder Zielcomputer verwenden.

    

    > [!IMPORTANT]
    > Nach dem Durchführen von Änderungen an der Kerberos-Authentifizierung, beispielsweise nach dem Hinzufügen oder Entfernen eines Kontos, müssen Sie das Cmdlet <STRONG>Enable-CsTopology</STRONG> an der Lync Server-Verwaltungsshell-Eingabeaufforderung ausführen.


