---
title: 'Lync Server 2013: Bereitstellen von lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Bereitstellen von lync Web App in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-18_

Lync Web App ist ein Internetinformationsdienste (IIS)-WebClient, der mit lync Server 2013 installiert und standardmäßig aktiviert ist. Es sind keine weiteren Schritte erforderlich, um lync Web App auf dem Server zu aktivieren oder den WebClient für Benutzer bereitzustellen. Wenn ein Benutzer auf eine Besprechungs-URL klickt, aber der lync 2013-Client nicht installiert ist, wird dem Benutzer die Option zur Teilnahme an der Besprechung mit der neuesten Version von lync Web App angezeigt.

Die sprach-, Video-und Freigabefunktionen in lync Web App erfordern ein Microsoft ActiveX-Steuerelement. Sie können entweder das ActiveX-Steuerelement im Voraus installieren oder es Benutzern ermöglichen, es zu installieren, wenn Sie dazu aufgefordert werden, was geschieht, wenn Sie lync Web App zum ersten Mal verwenden oder wenn Sie zum ersten Mal auf ein Feature zugreifen, das das ActiveX-Steuerelement erfordert.

<div class=" ">


> [!NOTE]  
> In lync Server 2013-Edgeserver-Bereitstellungen ist für den lync Web App-Clientzugriff ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich. Außerdem müssen Sie einfache URLs veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> und <A href="lync-server-2013-planning-for-simple-urls.md">Planen einfacher URLs in lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Aktivieren der mehrstufigen Authentifizierung für lync Web App

Die lync Server 2013-Version von lync Web App unterstützt die mehrstufige Authentifizierung. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins anfordern, um Benutzer zu authentifizieren, die von externen Netzwerken beitreten, wenn Sie sich bei lync-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie den Active Directory Federation Service (AD FS)-Verbundserver bereitstellen und die passive Authentifizierung in lync Server 2013 aktivieren. Nach der Konfiguration von AD FS werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-Website mit mehrstufiger Authentifizierung angezeigt, die die Herausforderung Benutzername und Kennwort zusammen mit allen weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält. .

<div class=" ">


> [!IMPORTANT]  
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren 
> <UL>
> <LI>
> <P>Mehrstufige ADFS-Authentifizierung funktioniert, wenn der Besprechungsteilnehmer und der Organisator sich beide in der gleichen Organisation befinden oder beide aus einer AD FS-Partnerverbundorganisation stammen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Partnerverbundbenutzer, da sie von der Webinfrastruktur von Lync Server aktuell nicht unterstützt wird.</P>
> <LI>
> <P>Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Beibehaltung von Cookies auf den Lastenausgleichsgeräten, damit alle Anforderungen vom lync Web App-Client vom gleichen Front-End-Server verarbeitet werden.</P>
> <LI>
> <P>Wenn Sie eine vertrauende Vertrauensstellung zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge ihrer lync-Besprechungen zu überspannen. Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.</P>
> <LI>
> <P>Diese Konfiguration gilt nicht für mobile Lync-Clients.</P></LI></UL>



</div>

**So konfigurieren Sie die mehrstufige Authentifizierung**

1.  Installieren Sie eine AD FS-Verbundserverrolle. Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory-Verbunddienste 2,0 unter<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" im Abschnitt Planen und Bereitstellen von AD FS für die Verwendung mit dem Thema für einmaliges [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)anmelden unter.

3.  Führen Sie über die Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:
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

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann die Web-Komponenten von lync Web App stören. Um Probleme mit lync Web App-Benutzern zu vermeiden, stellen Sie sicher, dass BranchCache nicht aktiviert ist.

Ausführliche Informationen zum Deaktivieren von BranchCache finden Sie im BranchCache-Bereitstellungshandbuch, das im Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) und im HTML-Format in der technischen Bibliothek für Windows Server 2008 R2 unter [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)auf Word-Format verfügbar ist.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Überprüfen der lync Web App-Bereitstellung

Mit dem Cmdlet „Test-CsUcwaConference“ können Sie überprüfen, ob zwei Testbenutzer über die Unified Communications-Web-API (UCWA) an einer Konferenz teilnehmen können. Details zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Problembehandlung der Plug-in-Installation unter Windows Server 2008 R2

Wenn die Installation des Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlschlägt, müssen Sie möglicherweise die Internet Explorer-Sicherheitseinstellung oder die DisableMSI-Registrierungsschlüsseleinstellung ändern.

**So ändern Sie die Sicherheitseinstellung in Internet Explorer**

1.  Öffnen Sie Internet Explorer.

2.  Klicken Sie auf **Extras**, auf **Internetoptionen** und anschließend auf **Erweitert**.

3.  Scrollen Sie nach unten zum Abschnitt **Sicherheit**.

4.  Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Wenn diese Option ausgewählt ist, wird auch beim Versuch, eine Anlage aus lync Web App herunterzuladen, ein Fehler ausgelöst.

    
    </div>

5.  Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

**So ändern Sie die Registrierungseinstellung "DisableMSI"**

1.  Klicken Sie auf  **Start ** und dann auf  **Ausführen**.

2.  Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3.  Navigieren Sie zu\_den\_HKEY\\-\\Software\\Richtlinien\\für\\lokale Computer Microsoft Windows Installer.

4.  Bearbeiten oder fügen Sie den Registrierungsschlüssel DisableMSI vom Typ\_reg DWORD hinzu, und setzen Sie ihn auf 0.

5.  Nehmen Sie an der Besprechung erneut teil.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Web App-unterstützte Plattformen für lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

