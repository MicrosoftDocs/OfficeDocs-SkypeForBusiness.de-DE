---
title: Migrieren von Lync Online-Benutzern zur lokalen Lync-Bereitstellung
TOCTitle: Migrieren von Lync Online-Benutzern zur lokalen Lync-Bereitstellung
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62247565
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Lync Online-Benutzern zur lokalen Lync-Bereitstellung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_


> [!IMPORTANT]
> Diese Schritte sind nur für die Migration von Benutzerkonten erforderlich, die ursprünglich für Lync in Lync Online aktiviert waren, bevor Sie Lync lokal bereitgestellt haben. Informationen zum Verschieben von Benutzern, die ursprünglich für die lokale Bereitstellung von Lync aktiviert waren und dann später zu Lync Online verschoben wurden, finden Sie unter <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Verwalten von Benutzern in einer Lync Server 2013-Hybridbereitstellung</A>.<BR>Darüber hinaus müssen alle Benutzer, die verschoben werden, über Konten im lokalen Active Directory verfügen.



## Migrieren von ursprünglich in Lync Online aktivierten Benutzerkonten zur lokalen Lync-Bereitstellung

1.  Stellen Sie zunächst sicher, dass Ihr Unternehmen für eine Hybridbereitstellung konfiguriert ist.
    
      - Installieren Sie das Windows Azure Active Directory-Synchronisierungstool. Weitere Informationen finden Sie unter <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Um Ihre Benutzer für die Verwendung des einmaligen Anmeldens zu aktivieren, installieren Sie Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.
    
      - Geben Sie in Ihrer lokalen Bereitstellung in der Lync Server-Verwaltungsshell die folgenden Cmdlets ein, um den Hostinganbieter für Lync Online zu erstellen:
        
            Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true

           &nbsp;
        
            New-CSHostingProvider -Identity LyncOnline -Name LyncOnlin -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

2.  Bestätigen Sie, dass auf Ihren lokalen Edgeservern die Zertifikatkette vorhanden ist, die eine Verbindung zu Lync Online ermöglicht, wie in der folgenden Tabelle gezeigt. Sie können diese Kette hier herunterladen: [https://corp.sts.microsoft.com/Onboard/ADFS\_Onboarding\_Pack/corp\_sts\_certs.zip](https://corp.sts.microsoft.com/onboard/adfs_onboarding_pack/corp_sts_certs.zip) .
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Zertifikat</th>
    <th>Zertifikatspeicher</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>Vertrauenswürdige Stammzertifizierungsstelle</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (Zertifikat einer neuen Zertifizierungsstelle)</p></td>
    <td><p>Zwischenzertifizierungsstelle</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (neue ausstellende CA2)</p></td>
    <td><p>Zwischenzertifizierungsstelle</p></td>
    </tr>
    </tbody>
    </table>


3.  Aktivieren Sie im lokalen Active Directory die betroffenen Benutzerkonten für die lokale Lync-Bereitstellung. Geben Sie dafür für einen einzelnen Benutzer das folgende Cmdlet ein:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Oder erstellen Sie ein Skript, das Benutzernamen aus einer Datei liest und sie als Eingabe für das Cmdlet „Enable-CsUser“ bereitstellt:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Führen Sie DirSync aus, um die Lync Online-Benutzer mit den aktualisierten Benutzern der lokalen Lync-Bereitstellung zu synchronisieren.

5.  Aktualisieren Sie einige DNS-Einträge, damit der gesamte SIP-Datenverkehr an die lokale Lync-Bereitstellung geleitet wird:
    
      - Aktualisieren Sie den Eintrag **lyncdiscover.contoso.com** so, dass er auf den FQDN des lokalen Reverseproxyservers verweist.
    
      - Aktualisieren Sie den SRV-Eintrag ***\_sip*.\_tls.contoso.com** so, dass er in die öffentliche IP- oder VIP-Adresse des Zugriffs-Edgediensts der lokalen Lync-Bereitstellung aufgelöst wird.
    
      - Aktualisieren Sie den SRV-Eintrag ***\_sipfederationtls*.\_tcp.contoso.com** so, dass er in die öffentliche IP- oder VIP-Adresse des Zugriffs-Edgediensts der lokalen Lync-Bereitstellung aufgelöst wird.
    
      - Wenn in Ihrem Unternehmen Split-DNS (manchmal auch als „Split-Brain-DNS“ bezeichnet) verwendet wird, stellen Sie sicher, dass Benutzer, die Namen über die interne DNS-Zone auflösen, an den Front-End-Pool geleitet werden.

6.  Geben Sie das Cmdlet `Get-CsUser` ein, um einige Eigenschaften der Benutzer zu überprüfen, die Sie verschieben werden. Sie sollten sicherstellen, dass HostingProviderProxyFQDN auf `"sipfed.online.lync.com"` festgelegt ist und die SIP-Adressen ordnungsgemäß eingerichtet sind.

7.  Verschieben Sie Lync Online-Benutzer zur lokalen Lync-Bereitstellung.
    
    Geben Sie Folgendes ein, um einen einzelnen Benutzer zu verschieben:
    
        $cred = Get-Credential

       &nbsp;
    
        Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
    
    Sie können mehrere Benutzer verschieben, indem Sie das Cmdlet **Get-CsUSer** mit dem Parameter –Filter verwenden, um Benutzer mit einer bestimmten Eigenschaft auszuwählen. Sie können beispielsweise alle Lync Online-Benutzer auswählen, indem Sie nach {Hosting Provider –eq “sipfed.online.lync.om”} filtern. Sie können dann die zurückgegebenen Benutzer an das Cmdlet **Move-CsUSer** weiterleiten, wie unten gezeigt.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Das Format der für den Parameter **HostedMigrationOverrideUrl** angegebenen URL muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, und muss folgendes Format haben: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.
    
    Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.
    
    ## So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten
    
    1.  Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.
    
    2.  Öffen Sie das **Lync Admin Center**.
    
    3.  Wenn das **Lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:
        
        `https://admin0a.online.lync.com`
    
    5.  Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
        
        Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

    > [!NOTE]
    > Standardmäßig beträgt die maximale Größe für Transaktionsprotokolldateien der rtcxds-Datenbank 16 GB. Das ist möglicherweise nicht ausreichend, wenn Sie viele Benutzer auf einmal verschieben, insbesondere wenn das Spiegeln aktiviert ist. Sie können dieses Problem umgehen, indem Sie die Dateigröße erhöhen oder die Protokolldateien regelmäßig sichern. Weitere Informationen finden Sie unter <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.



8.  Dies ist ein optionaler Schritt. Wenn Sie eine Integration in Exchange 2013 Online benötigen, müssen Sie einen zusätzlichen Hostinganbieter verwenden. Einzelheiten finden Sie unter [Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Die Benutzer sind jetzt verschoben. Geben Sie das folgende Cmdlet ein, um zu überprüfen, ob ein Benutzer korrekte Werte für die in der folgenden Tabelle gezeigten Attribute hat:
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Active Directory-Attribut</th>
    <th>Attributname</th>
    <th>Korrekter Wert für Lync Online-Benutzer</th>
    <th>Korrekter Wert für Benutzer der lokalen Lync-Bereitstellung</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Enabled</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Jeder verschobene Benutzer muss sich bei Lync ab- und dann erneut anmelden. Nach der Anmeldung sollte jeder Benutzer seine Kontaktlisten überprüfen und ggf. Kontakte hinzufügen.
    
    Beachten Sie, dass geplante Besprechungen nicht von Lync Online zur lokalen Lync-Bereitstellung migriert werden. Benutzer müssen diese Besprechungen erneut planen, nachdem sie verschoben wurden.
    
    Nachdem die DNS-Einträge aktualisiert sind und alle Benutzer an die lokale Bereitstellung geleitet wurden, leitet das HostingProvider-Attribut den Lync-Benutzer entweder zur Verwendung von SRV-Einträgen oder zum Onlineanbieter „sipfed.online.lync.com“ weiter.

