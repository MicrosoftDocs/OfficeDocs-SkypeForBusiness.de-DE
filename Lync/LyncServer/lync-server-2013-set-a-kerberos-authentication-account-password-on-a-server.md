---
title: 'Lync Server 2013: Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server'
TOCTitle: Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398734(v=OCS.15)
ms:contentKeyID: 49294742
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Festlegen eines Kennworts für das Kerberos-Authentifizierungskonto auf einem Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Für das Kerberos-Konto muss für jeden Standort, der über Front-End-Server, Standard Edition-Server und Director-Server verfügt, ein Kennwort eingerichtet werden. Zum Einrichten des Kennworts können Sie das Cmdlet **Set-CsKerberosAccountPassword** in der Windows PowerShell auf einem Server am Standort ausführen (z. B. auf dem Front-End-Server). Das Cmdlet **Set-CsKerberosAccountPassword** muss für jeden Standort ausgeführt werden. Das Cmdlet konfiguriert die Internetinformationsdienste (Internet Information Services, IIS) für den Webdienstedienst und legt anschließend das Kennwort für das Computerkonto in Active Directory-Domänendienste fest. Bei einer alternativen Methode wird IIS abhängig davon, welcher Parameter mit dem Cmdlet verwendet wird, auf einem Server konfiguriert, während ein anderer Server verwendet wird, der als Quelle des Kerberos-Kontokennworts konfiguriert wurde.

Bei Verwendung des Cmdlets **Set-CsKerberosAccountPassword** zum Festlegen des Kennworts legt Kerberos das Kennwort auf eine nach dem Zufallsprinzip generierte Zeichenfolge fest. Dieses Cmdlet kontaktiert alle IIS-Instanzen an allen zentralen Lync Server 2013-Standorten, denen dieses Konto zugeordnet ist.

## So legen Sie ein Kennwort für ein Kerberos-Authentifizierungskonto fest

1.  Melden Sie sich bei einem Domänencomputer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Beispiel:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    

    > [!NOTE]
    > Sie müssen den Parameter "UserAccount" im Format "Domäne\Benutzer" angeben. Das Format "Benutzer@Domäne.Erweiterung" wird zur Referenzierung der für die Kerberos-Authentifizierung erstellten Computerobjekte nicht unterstützt.

    

    > [!IMPORTANT]
    > Nach dem Durchführen von Änderungen an der Kerberos-Authentifizierung, beispielsweise nach dem Hinzufügen oder Entfernen eines Kontos, müssen Sie das Cmdlet <STRONG>Enable-CsTopology</STRONG> an der Lync Server-Verwaltungsshell-Eingabeaufforderung ausführen.


