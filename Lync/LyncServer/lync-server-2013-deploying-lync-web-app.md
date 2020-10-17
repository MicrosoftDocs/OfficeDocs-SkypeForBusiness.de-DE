---
title: 'Lync Server 2013: Bereitstellen von lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2156466e0238a061f2358127c75408fa37e3b823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507532"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Bereitstellen von lync Web App in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-18_

Lync Web App ist ein Internet Information Services (IIS)-WebClient, der mit lync Server 2013 installiert wird und standardmäßig aktiviert ist. Es sind keine weiteren Schritte erforderlich, um entweder lync Web App auf dem Server zu aktivieren oder den WebClient für Benutzer bereitzustellen. Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber der lync 2013-Client nicht installiert ist, wird dem Benutzer die Möglichkeit geboten, an der Besprechung teilzunehmen, indem er die neueste Version von lync Web App verwendet.

Für die VoIP-, Video-und Freigabefunktionen in lync Web App ist ein Microsoft ActiveX-Steuerelement erforderlich. Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder Benutzern erlauben, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie das erste Mal lync Web App oder beim ersten Zugriff auf ein Feature, für das das ActiveX-Steuerelement erforderlich ist, verwenden.

<div class=" ">


> [!NOTE]  
> In lync Server 2013 Edgeserver-Bereitstellungen ist für lync Web App Clientzugriff ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich. Sie müssen zudem einfache URLs. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse Proxyservern für lync Server 2013</A> und <A href="lync-server-2013-planning-for-simple-urls.md">Planen für einfache URLs in lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Aktivieren der mehrstufigen Authentifizierung für lync Web App

Die lync Server 2013 Version von lync Web App unterstützt die mehrstufige Authentifizierung. Neben Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins zur Authentifizierung von Benutzern benötigen, die von externen Netzwerken beitreten, wenn Sie sich bei lync-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Verbundserver Active Directory Verbunddienst (AD FS) bereitstellen und die passive Authentifizierung in lync Server 2013 aktivieren. Nachdem AD FS konfiguriert wurde, werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-mehrstufigen Authentifizierungs Webseite angezeigt, die den Benutzernamen und die Kennwortabfrage sowie alle weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält.

<div class=" ">


> [!IMPORTANT]  
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren 
> <UL>
> <LI>
> <P>Die mehrstufige ADFS-Authentifizierung funktioniert, wenn sich der Besprechungsteilnehmer und der Organisator sowohl in derselben Organisation als auch in einer AD FS-Verbundorganisation befinden. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für lync-Verbundbenutzer, da Sie von der lync Server-Webinfrastruktur derzeit nicht unterstützt wird.</P>
> <LI>
> <P>Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies für die Lastenausgleichsmodule, damit alle Anforderungen des lync Web App Clients von derselben Front-End-Server verarbeitet werden.</P>
> <LI>
> <P>Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die sich über die maximale Länge ihrer lync-Besprechungen erstrecken kann. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</P>
> <LI>
> <P>Diese Konfiguration gilt nicht für lync Mobile-Clients.</P></LI></UL>



</div>

**Konfigurieren der mehrstufigen Authentifizierung**

1.  Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory Verbunddienste 2,0 unter <https://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Erstellen von Zertifikaten für AD FS. Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" des Themas planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .

3.  Führen Sie über die Befehlszeilenschnittstelle Windows PowerShell den folgenden Befehl aus:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>BranchCache-Konfiguration

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann mit lync Web App Webkomponenten in Konflikt stehen. Um Probleme für lync Web App Benutzer zu vermeiden, stellen Sie sicher, dass BranchCache nicht aktiviert ist.

Ausführliche Informationen zum Deaktivieren von BranchCache finden Sie im BranchCache-Bereitstellungshandbuch, das im Microsoft Download Center im [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) und im HTML-Format in der technischen Bibliothek von Windows Server 2008 R2 unter im Word-Format verfügbar ist [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) .

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Überprüfen der lync Web App-Bereitstellung

Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in der lync Server-Verwaltungsshell Dokumentation.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Problembehandlung bei der Plug-in-Installation auf Windows Server 2008 R2

Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Einstellung Internet Explorer Security oder die Einstellung des Registrierungsschlüssels DisableMSI ändern.

**Ändern der Sicherheitseinstellung in Internet Explorer**

1.  Öffnen Sie Internet Explorer.

2.  Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.

3.  Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.

4.  Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Wenn diese Einstellung aktiviert ist, tritt bei dem Versuch, eine Anlage aus lync Web App herunterzuladen, auch ein Fehler auf.

    
    </div>

5.  Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

**Ändern der "DisableMSI"-Registrierungseinstellung**

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3.  Navigieren Sie zu HKEY \_ local \_ Machine \\ Software \\ Policies \\ Microsoft \\ Windows \\ Installer.

4.  Bearbeiten oder fügen Sie den Registrierungsschlüssel DisableMSI vom Typ reg \_ DWORD hinzu, und legen Sie ihn auf 0 fest.

5.  Nehmen Sie an der Besprechung erneut teil.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Web App unterstützte Plattformen für lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

