---
title: 'Lync Server 2013: Migrieren von lync Online Benutzern lokal zu lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e87b977dd70227d134e5feae8df2ea089e216df3
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migrieren von lync Online Benutzern lokal zu lync in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Diese Schritte sind nur für die Migration von Benutzerkonten erforderlich, die ursprünglich für lync in lync Online aktiviert waren, bevor Sie lync lokal bereitgestellt haben. Informationen zum Verschieben von Benutzern, die ursprünglich für lync lokal aktiviert waren und dann später in lync Online verschoben wurden, finden Sie unter <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung</A>.<BR>Darüber hinaus müssen alle Benutzer, die verschoben werden, über Konten im lokalen Active Directory verfügen.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migrieren von Benutzerkonten, die ursprünglich in lync Online für lync lokal aktiviert wurden

1.  Stellen Sie zunächst sicher, dass Ihre Organisation für Hybrid konfiguriert ist.
    
      - Installieren Sie das Azure Active Directory-Synchronisierungs Tool. Weitere Informationen finden Sie unter <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Um Ihren Benutzern die Verwendung von einmaligem Anmelden für lync online zu ermöglichen, installieren Sie Active Directory <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>Verbunddienste.
    
      - Geben Sie in Ihrer lokalen Bereitstellung in lync Server-Verwaltungsshell die folgenden Cmdlets ein, um den Hostinganbieter für lync online zu erstellen:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Stellen Sie sicher, dass Sie auf Ihren lokalen Edgeserver die Zertifikatkette haben, die die Verbindung mit lync Online ermöglicht, wie in der folgenden Tabelle dargestellt. Sie können diese Kette hier herunterladen:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>Microsoft Internet Authority (neues Zertifizierungsstellenzertifikat)</p></td>
    <td><p>Intermediate-Zertifizierungsstelle</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine auth Ca2 (New emissioning Ca2)</p></td>
    <td><p>Intermediate-Zertifizierungsstelle</p></td>
    </tr>
    </tbody>
    </table>

3.  Aktivieren Sie in Ihrer lokalen Active Directory die betroffenen Benutzerkonten für lync lokal. Sie können dies für einen einzelnen Benutzer tun, indem Sie das folgende Cmdlet eingeben:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Sie können auch ein Skript erstellen, das Benutzernamen aus einer Datei liest und diese als Eingabe für das Cmdlet Enable-CsUser bereitstellt:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Führen Sie Dirsync aus, um die lync Online Benutzer mit den aktualisierten lokalen lync-Benutzern zu synchronisieren.

5.  Aktualisieren Sie einige DNS-Einträge, um den gesamten SIP-Datenverkehr lokal an lync weiterzuleiten:
    
      - Aktualisieren Sie den **lyncdiscover.contoso.com** -Eintrag, sodass ein Datensatz auf den FQDN des lokalen Reverse-Proxyservers verweist.
    
      - Aktualisieren Sie das ***\_SIP *\_ . TLS.contoso.com** -SRV-Eintrag, der in die öffentliche IP-oder VIP-Adresse des Zugriffs-Edgedienst von lync lokal aufgelöst wird.
    
      - Aktualisieren Sie das ***\_sipfederationtls *\_ . TCP.contoso.com** -SRV-Eintrag, der in die öffentliche IP-oder VIP-Adresse des Zugriffs-Edgedienst von lync lokal aufgelöst wird.
    
      - Wenn Ihre Organisation Split-DNS verwendet (manchmal auch "Split-Brain-DNS" genannt), stellen Sie sicher, dass Benutzer, die Namen über die interne DNS-Zone auflösen, an den Front-End-Pool weitergeleitet werden.

6.  Geben Sie `Get-CsUser` das Cmdlet ein, um einige Eigenschaften zu den Benutzern zu überprüfen, die Sie verschieben möchten. Sie möchten sicherstellen, dass das HostingProviderProxyFQDN auf `"sipfed.online.lync.com"` festgelegt ist und dass die SIP-Adressen richtig festgelegt sind.

7.  Migrieren Sie lync Online Benutzer lokal zu lync.
    
    Geben Sie Folgendes ein, um einen einzelnen Benutzer zu verlagern:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Sie können mehrere Benutzer mithilfe des Cmdlets **Get-CsUSer** mit dem Parameter – Filter migrieren, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen. Sie können beispielsweise alle lync Online Benutzer auswählen, indem Sie nach {Hosting Provider – EQ "sipfed.online.lync.om"} filtern. Anschließend können Sie die zurückgegebenen Benutzer an das Cmdlet " **CsUSer** " weiterleiten, wie unten dargestellt.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, im folgenden Format: *https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.
    
    Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Office 365 organisationskonto anzeigen.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-organization"></a>So bestimmen Sie die URL des gehosteten Migrations Diensts für Ihre Office 365 Organisation
    
    1.  Melden Sie sich als Administrator bei Ihrer Office 365 Organisation an.
    
    2.  Öffnen Sie das **lync Admin Center**.
    
    3.  Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie. Eine Beispiel-URL sieht wie folgt aus:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:
        
        `https://admin0a.online.lync.com`
    
    5.  Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
        
        Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Die standardmäßige maximale Größe für Transaktionsprotokolldateien der "rtcxds"-Datenbank beträgt 16 GB. Dies ist möglicherweise nicht groß genug, wenn Sie eine große Anzahl von Benutzern gleichzeitig verschieben, insbesondere dann, wenn die Spiegelung aktiviert ist. Um dies zu umgehen, können Sie die Dateigröße vergrößern oder die Protokolldateien regelmäßig sichern. Weitere Informationen finden Sie unter <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.

    
    </div>

8.  Dies ist ein optionaler Schritt. Wenn Sie eine Integration mit Exchange 2013 online durchführen müssen, müssen Sie einen zusätzlichen Hosting-Anbieter verwenden. Ausführliche Informationen finden Sie unter [Configuring on-premises lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Die Benutzer werden nun verschoben. Geben Sie dieses Cmdlet ein, um zu überprüfen, ob ein Benutzer die richtigen Werte für die in der folgenden Tabelle aufgeführten Attribute aufweist:
    
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
    <th>Korrekter Wert für lync Online Benutzer</th>
    <th>Korrekter Wert für lync-lokale Benutzer</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>Hostinganbieter</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>Aktiviert</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Jeder Benutzer, der verschoben wurde, muss sich von lync abmelden und sich dann wieder anmelden. Wenn Sie sich anmelden, sollten Sie ihre Kontaktlisten überprüfen und bei Bedarf Kontakte hinzufügen.
    
    Beachten Sie, dass geplante Besprechungen nicht von lync online zu lync lokal migriert werden. Benutzer müssen diese Besprechungen nach dem Verschieben neu planen.
    
    Nachdem die DNS-Einträge aktualisiert wurden und alle Benutzer an die Prämisse weitergeleitet wurden, weist das Hostinganbieter-Attribut den lync-Benutzer an, entweder SRV-Einträge zu verwenden oder Sie an den Online Anbieter "sipfed.online.lync.com" zu verweisen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

