---
title: Konfigurieren der passiven Authentifizierung in Lync Server
TOCTitle: Konfigurieren der passiven Authentifizierung in Lync Server
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308569(v=OCS.15)
ms:contentKeyID: 56269320
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der passiven Authentifizierung in Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2013-07-11_

Im folgenden Abschnitt wird beschrieben, wie Lync Server 2013 mit dem Kumulativen Update: Juli 2013 konfiguriert wird, um passive Authentifizierung zu unterstützen. Nach der Aktivierung müssen Lync-Benutzer, die für zweistufige Authentifizierung aktiviert sind, eine physische oder virtuelle SmartCard und eine gültige PIN für die Anmeldung beim Lync 2013-Client mit dem Kumulativen Update: Juli 2013 verwenden.


> [!NOTE]
> Kunden wird dringend empfohlen, passive Authentifizierung für Registrierungsstellen und Webdienste auf der Dienstebene zu aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf der globalen Ebene aktiviert wird, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem Lync 2013-Desktopclient mit dem Kumulativen Update: Juli 2013 anmelden.



## Webdienstkonfiguration

In den folgenden Schritten wird die Erstellung einer angepassten Webdienstkonfiguration für Directorserver, Enterprise Pools und Standard Edition-Server, die für passive Authentifizierung aktiviert werden sollen, beschrieben.

**So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration**

1.  Melden Sie sich bei Ihrem Lync Server 2013-Front-End-Server mit dem Kumulativen Update: Juli 2013 mit einem Lync-Administratorkonto an.

2.  Starten Sie die Verwaltungsshell für Lync Server 2013.

3.  Erstellen Sie auf der Lync Server-Verwaltungsshell-Befehlszeile eine neue Webdienstkonfiguration für jeden Directorserver, Enterprise Pool und Standard Edition-Server, der für die passive Authentifizierung aktiviert werden soll, indem Sie den folgenden Befehl ausführen:
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    

    > [!WARNING]
    > Der Wert für den vollqualifizierten Domänennamen in "WsFedPassiveMetadataUri" ist der Name des Partnerverbunddiensts Ihres AD FS 2.0-Servers. Sie können den Wert des Namens des Partnerverbunddiensts in der AD FS 2.0-Verwaltungskonsole abrufen, indem Sie im Navigationsbereich auf <STRONG>Dienst</STRONG> klicken und dann <STRONG>Eigenschaften des Verbunddiensts bearbeiten</STRONG> auswählen.



4.  Überprüfen Sie, ob die Werte von "UseWsFedPassiveAuth" und "WsFedPassiveMetadataUri" richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  Für Clients stellt die passive Authentifizierung die am wenigsten vorzuziehende Authentifizierungsmethode für die Authentifizierung mithilfe von Webtickets dar. Für alle Directorserver, Enterprise Pools und Standard Edition-Server, die für passive Authentifizierung aktiviert werden sollen, müssen alle anderen Authentifizierungsarten mithilfe des folgenden Befehls in den Lync-Webdiensten deaktiviert werden:
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  Überprüfen Sie, ob alle anderen Authentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

## Proxykonfiguration

Wenn die Zertifikatauthentifizierung für die Lync-Webdiensste deaktiviert ist, verwendet der Lync-Client für die Authentifizierung beim Registrierungsstellendienst eine weniger bevorzugte Authentifizierungsart, wie etwa Kerberos oder NTLM. Die Zertifikatauthentifizierung ist nach wie vor erforderlich, um dem Lync-Client das Abrufen eines Webtickets zu ermöglichen, jedoch müssen Kerberos und NTLM für den Registrierungsstellendienst deaktiviert werden.

In den folgenden Schritten wird die Erstellung einer angepassten Proxykonfiguration für Edge Pools, Enterprise Pools und Standard Edition-Server, die für passive Authentifizierung aktiviert werden sollen, beschrieben.

**So erstellen Sie eine benutzerdefinierte Proxykonfiguration**

1.  Erstellen Sie auf der Lync Server-Verwaltungsshell-Befehlszeile eine neue Proxykonfiguration für jeden Lync Server 2013-Edge Pool, Enterprise Pool und Standard Edition-Server mit dem Kumulativen Update: Juli 2013, der für passive Authentifizierung aktiviert werden soll, indem Sie die folgenden Befehle ausführen:
    
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False

       &nbsp;
    
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False

2.  Überprüfen Sie, ob alle anderen Proxyauthentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

