---
title: 'Lync Server 2013: Migrieren von lync Online-Benutzern zu lync lokal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8806610d8ede0932a9e1f6048d892a48f104d3
ms.sourcegitcommit: e487637fc122727b41b37961f208ddc0d20a3fce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34847916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrieren von lync Online-Benutzern zu lync lokal in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Diese Schritte sind nur für die Migration von Benutzerkonten erforderlich, die ursprünglich für lync in lync Online aktiviert waren, bevor Sie lync lokal bereitgestellt haben. Informationen zum Verschieben von Benutzern, die ursprünglich für lync lokal aktiviert wurden und später in lync Online verschoben wurden, finden Sie unter <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung</A>.<BR>Darüber hinaus müssen alle Benutzer, die verschoben werden, über Konten im lokalen Active Directory verfügen.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrieren von Benutzerkonten, die ursprünglich in lync Online aktiviert sind, lokal in lync

1.  Stellen Sie zunächst sicher, dass Ihre Organisation für Hybrid konfiguriert ist.
    
      - Installieren Sie das Azure Active Directory-Synchronisierungs Tool. Weitere Informationen finden Sie unter <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Wenn Sie Ihren Benutzern die Verwendung von einmaligem Anmelden für lync Online ermöglichen möchten, installieren Sie die <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>Active Directory-Verbunddienste.
    
      - Geben Sie in Ihrer lokalen Bereitstellung in der lync Server-Verwaltungsshell die folgenden Cmdlets ein, um den Hostinganbieter für lync online zu erstellen:
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Vergewissern Sie sich, dass Sie auf Ihren lokalen Edgeserver über die Zertifikatkette verfügen, die die Verbindung zu lync Online ermöglicht, wie in der folgenden Tabelle dargestellt. Sie können diese Kette hier herunterladen:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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

3.  Aktivieren Sie in Ihrem lokalen Active Directory die betroffenen Benutzerkonten für lync lokal. Geben Sie dafür für einen einzelnen Benutzer das folgende Cmdlet ein:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Oder erstellen Sie ein Skript, das Benutzernamen aus einer Datei liest und sie als Eingabe für das Cmdlet „Enable-CsUser“ bereitstellt:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Führen Sie Dirsync aus, um die lync Online-Benutzer mit den aktualisierten lokalen lync-Benutzern zu synchronisieren.

5.  Aktualisieren Sie einige DNS-Einträge, um den gesamten SIP-Datenverkehr an lync lokal zu leiten:
    
      - Aktualisieren Sie den Eintrag **lyncdiscover.contoso.com** so, dass er auf den FQDN des lokalen Reverseproxyservers verweist.
    
      - Aktualisieren Sie das ***\_SIP *\_ . TLS.contoso.com** SRV-Eintrag, um die öffentliche IP-oder VIP-Adresse des Access Edge-Diensts von lync lokal zu beheben.
    
      - Aktualisieren Sie das ***\_sipfederationtls *\_ . TCP.contoso.com** SRV-Eintrag, um die öffentliche IP-oder VIP-Adresse des Access Edge-Diensts von lync lokal zu beheben.
    
      - Wenn in Ihrem Unternehmen Split-DNS (manchmal auch als „Split-Brain-DNS“ bezeichnet) verwendet wird, stellen Sie sicher, dass Benutzer, die Namen über die interne DNS-Zone auflösen, an den Front-End-Pool geleitet werden.

6.  Geben Sie `Get-CsUser` das Cmdlet ein, um einige Eigenschaften über die Benutzer zu überprüfen, die Sie verschieben möchten. Sie möchten sicherstellen, dass die HostingProviderProxyFQDN auf `"sipfed.online.lync.com"` festgelegte und die SIP-Adressen richtig festgesetzt sind.

7.  Verschieben Sie lync Online-Benutzer in die lokale lync-app.
    
    Geben Sie Folgendes ein, um einen einzelnen Benutzer zu verschieben:
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Sie können mehrere Benutzer verschieben, indem Sie das Cmdlet **Get-CsUSer** mit dem Parameter –Filter verwenden, um Benutzer mit einer bestimmten Eigenschaft auszuwählen. So können Sie beispielsweise alle lync Online-Benutzer auswählen, indem Sie für {Hosting Provider – EQ "sipfed.online.lync.om"} filtern. Sie können dann die zurückgegebenen Benutzer an das Cmdlet **Move-CsUSer** weiterleiten, wie unten gezeigt.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Das Format der für den **HostedMigrationOverrideUrl** -Parameter angegebenen URL muss die URL des Pools sein, in dem der gehostete Migrationsdienst ausgeführt wird, im folgenden Format *:\<https://Pool\>FQDN/HostedMigration/ hostedmigrationService. svc*.
    
    Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten
    
    1.  Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.
    
    2.  Öffnen Sie das **lync Admin Center**.
    
    3.  Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis zu **lync.com**aus, und kopieren Sie Sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:
        
        `https://admin0a.online.lync.com`
    
    5.  Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
        
        Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Standardmäßig beträgt die maximale Größe für Transaktionsprotokolldateien der rtcxds-Datenbank 16 GB. Das ist möglicherweise nicht ausreichend, wenn Sie viele Benutzer auf einmal verschieben, insbesondere wenn das Spiegeln aktiviert ist. Sie können dieses Problem umgehen, indem Sie die Dateigröße erhöhen oder die Protokolldateien regelmäßig sichern. Weitere Informationen finden Sie unter <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.

    
    </div>

8.  Dies ist ein optionaler Schritt. Wenn Sie eine Integration in Exchange 2013 Online benötigen, müssen Sie einen zusätzlichen Hostinganbieter verwenden. Ausführliche Informationen finden Sie unter [Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

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
    <th>Korrekter Wert für lync Online-Benutzer</th>
    <th>Der richtige Wert für lync-lokal Benutzer</th>
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
    <td><p>sip:username@contoso.com</p></td>
    <td><p>sip:username@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Aktiviert</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Jeder Benutzer, der verschoben wurde, muss sich bei lync abmelden und dann wieder anmelden. Wenn Sie sich anmelden, sollten Sie ihre Kontaktlisten überprüfen und bei Bedarf Kontakte hinzufügen.
    
    Beachten Sie, dass geplante Besprechungen nicht von lync online zu lync lokal migriert werden. Benutzer müssen diese Besprechungen erneut planen, nachdem sie verschoben wurden.
    
    Nachdem die DNS-Einträge aktualisiert wurden und alle Benutzer an Premise weitergeleitet werden, weist das Hostinganbieter-Attribut den lync-Benutzer an, entweder SRV-Einträge zu verwenden oder Sie an den Online Anbieter "sipfed.online.lync.com" zu verweisen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

