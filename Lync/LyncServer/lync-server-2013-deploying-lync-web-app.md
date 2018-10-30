---
title: Bereitstellen von Lync Web App
TOCTitle: Bereitstellen von Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205190(v=OCS.15)
ms:contentKeyID: 49295163
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Lync Web App

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Web App ist ein IIS-Webclient, der zusammen mit Lync Server 2013 installiert wird und standardmäßig aktiviert ist. Es sind keine zusätzlichen Schritte erforderlich, um entweder Lync Web App auf dem Server zu aktivieren oder den Webclient für Benutzer bereitzustellen. Wenn ein Benutzer auf eine Besprechungs-URL klickt, jedoch über keinen installierten Lync 2013-Client verfügt, wird dem Benutzer eine Option angezeigt, um über die neueste Version von Lync Web App an der Besprechung teilzunehmen.

Für die VoIP-, Video- und Freigabefeatures in Lync Web App ist ein Microsoft ActiveX-Steuerelement erforderlich. Sie können das ActiveX-Steuerelement entweder im Voraus installieren oder Benutzern erlauben, es zu installieren, wenn sie dazu aufgefordert werden. Dies geschieht, wenn sie Lync Web App erstmals verwenden oder erstmals auf ein Feature zugreifen, wofür das ActiveX-Steuerelement erforderlich ist.


> [!NOTE]
> In Lync Server 2013-Edgeserver-Bereitstellungen ist im Umkreisnetzwerk ein HTTPS-Reverseproxy für Lync Web App-Clientzugriff erforderlich. Sie müssen zudem einfache URLs. Details finden Sie untere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverseproxyservern für Lync Server 2013</A> und <A href="lync-server-2013-planning-for-simple-urls.md">Planung für einfache URLs in Lync Server 2013</A>.



## Aktivieren der mehrstufigen Authentifizierung für Lync Web App

Die Lync Server 2013-Version von Lync Web App unterstützt die mehrstufige Authentifizierung. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden erforderlich machen, beispielsweise Smartcards oder PINs, um Benutzer, die von externen Netzwerken aus teilnehmen, zu authentifizieren, wenn sie sich bei Lync-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie Active Directory-Verbunddienste-Verbundserver bereitstellen und die passive Authentifizierung in Lync Server 2013 aktivieren. Nach der Konfiguration von Active Directory-Verbunddiensten werden externe Benutzer, die versuchen sich bei Lync-Besprechungen anzumelden, auf einer Webseite mit Informationen zur mehrstufigen Authentifizierung für Active Directory-Verbunddienste angezeigt, die den Benutzernamen und das Kennwortniveau zusammen mit den zusätzlichen von Ihnen konfigurierten Authentifizierungsmethoden enthält.


> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung zu konfigurieren 
> <UL>
> <LI>
> <P>Mehrstufige ADFS-Authentifizierung funktioniert, wenn der Besprechungsteilnehmer und der Organisator sich beide in der gleichen Organisation befinden oder beide aus einer AD FS-Partnerverbundorganisation stammen. Die mehrstufige ADFS-Authentifizierung funktioniert nicht für Lync-Partnerverbundbenutzer, da sie von der Webinfrastruktur von Lync Server aktuell nicht unterstützt wird.</P>
> <LI>
> <P>Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies auf den Geräten zum Lastenausgleich, sodass alle Anforderungen des Lync Web App-Clients vom selben Front-End-Server verarbeitet werden.</P>
> <LI>
> <P>Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen Lync Server und Active Directory-Verbunddienste-Servern einrichten, weisen Sie eine Gültigkeitsdauer des Token zu, die die maximale Länge Ihrer Lync-Besprechungen umfasst. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</P>
> <LI>
> <P>Diese Konfiguration gilt nicht für mobile Lync-Clients.</P></LI></UL>



**Konfigurieren der mehrstufigen Authentifizierung**

1.  Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Details können Sie dem Bereitstellungshandbuch für AD FS 2.0 unter [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x407) entnehmen.

2.  Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt "Verbundserverzertifikate" des Themas "Planen und Bereitstellen von AD FS für die Verwendung beim einmaligen Anmelden" unter [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Führen Sie von der Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

      &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules

       &nbsp;
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## BranchCache-Konfiguration

Das BranchCache-Feature in Windows 7 und Windows Server 2008 R2 kann Konflikte mit Lync Web App-Webkomponenten verursachen. Damit bei Lync Web App-Benutzern keine Probleme diesbezüglich auftreten, sollte BranchCache nicht aktiviert sein.

Details zum Deaktivieren von BranchCache finden Sie im Bereitstellungshandbuch für BranchCache. Dieses kann im Word-Format im Microsoft Download Center unter [http://go.microsoft.com/fwlink/?linkid=268788\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268788%26clcid=0x407) und im HTML-Format in der technischen Bibliothek von Windows Server 2008 R2 unter [http://go.microsoft.com/fwlink/?linkid=268789\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268789%26clcid=0x407) heruntergeladen werden.

## Überprüfen der Lync Web App-Bereitstellung

Sie können das Cmdlet "Test-CsUcwaConference" verwenden, um sicherzustellen, dass ein Paar von Testbenutzern in einer Konferenz unter Verwendung der Unified Communications-Web-API (UCWA) teilnehmen können. Details zu diesem Cmdlet finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference) in der Lync Server-Verwaltungsshell-Dokumentation.

## Problembehandlung von Plug-In-Installationen auf Windows Server 2008 R2

Wenn die Installation von Plug-Ins auf einem Computer mit Windows Server 2008 R2 fehlerhaft ist, müssen Sie möglicherweise die Internet Explorer-Sicherheitseinstellung oder die DisableMSI-Registrierungsschlüsseleinstellung ändern.

**Ändern der Sicherheitseinstellung in Internet Explorer**

1.  Öffnen Sie Internet Explorer.

2.  Klicken Sie auf **Extras**, dann auf **Internetoptionen** und anschließend auf **Erweitert**.

3.  Führen Sie einen Bildlauf zum Bereich **Sicherheit** durch.

4.  Deaktivieren Sie **Verschlüsselte Seiten nicht auf dem Datenträger speichern**, und klicken Sie dann auf **OK**.
    

    > [!NOTE]
    > Ist diese Option ausgewählt, verursacht diese Einstellung beim Versuch, eine Anlage von Lync Web App herunterzuladen, einen Fehler.



5.  Nehmen Sie an der Besprechung erneut teil. Das Plug-In sollte ohne Fehler Elemente herunterladen.

**Ändern der "DisableMSI"-Registrierungseinstellung**

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie **regedit** ein, um auf den Registrierungs-Editor zuzugreifen.

3.  Navigieren Sie zu "HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer".

4.  Bearbeiten oder fügen Sie den "DisableMSI"-Registrierungsschlüssel des Typs REG\_DWORD hinzu, und legen Sie ihn auf "0" fest.

5.  Nehmen Sie an der Besprechung erneut teil.

## Siehe auch

#### Konzepte

[Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Unterstützte Lync Web App-Plattformen für Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)

