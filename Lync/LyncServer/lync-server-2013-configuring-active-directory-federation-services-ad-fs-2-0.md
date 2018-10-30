---
title: Konfigurieren von Active Directory-Verbunddienste (AD FS 2.0)
TOCTitle: Konfigurieren von Active Directory-Verbunddienste (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308561(v=OCS.15)
ms:contentKeyID: 56269249
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Active Directory-Verbunddienste (AD FS 2.0)

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Im folgenden Abschnitt wird beschrieben, wie Active Directory-Verbunddienste (AD FS 2.0) konfiguriert werden muss, damit mehrstufige Authentifizierung unterstützt wird. Informationen, wie AD FS 2.0 installiert wird, finden Sie unter "AD FS 2.0 Step-by-Step and How To Guides" unter [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).


> [!NOTE]
> Wenn Sie AD FS 2.0 installieren, dürfen Sie nicht den Windows Server Manager verwenden, um die Active Directory-Verbunddienste-Rolle hinzuzufügen. Laden Sie stattdessen das Paket "Active Directory Federation Services 2.0 RTW" von <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A> herunter, und installieren Sie das Paket.




**So konfigurieren Sie AD FS für zweistufige Authentifizierung**

1.  Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.

2.  Starten Sie Windows PowerShell.

3.  Führen Sie aus der Windows PowerShell-Befehlszeile den folgenden Befehl aus:
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Richten Sie eine Partnerschaft mit jedem Lync Server 2013 Director-, Enterprise Pool- oder Standard Edition-Server mit den kumulativen Updates für Lync Server 2013 vom Juli 2013 ein, der für passive Authentifizierung aktiviert werden soll. Führen Sie dazu den folgenden Befehl aus, wobei Sie den Servernamen durch denjenigen Ihrer Bereitstellung ersetzen:
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Starten Sie aus dem Menü "Verwaltung" die AD FS 2.0-Verwaltungskonsole.

6.  Erweitern Sie **Vertrauensstellungen** \> **Vertrauensstellungen der vertrauenden Seite**.

7.  Vergewissern Sie sich, dass für Ihren Lync Server 2013 Director-, Enterprise Pool- oder Standard Edition-Server mit den kumulativen Updates für Lync Server 2013 vom Juli 2013 eine neue Vertrauensstellung erstellt wurde.

8.  Erstellen Sie eine Ausstellungsautorisierungsregel für Ihre Vertrauensstellung der vertrauenden Seite, und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules

9.  Erstellen Sie eine Ausstellungstransformationsregel für Ihre Vertrauensstellung der vertrauenden Seite, und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:
    
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules

10. Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf Ihre Vertrauensstellung der vertrauenden Seite, und wählen Sie **Anspruchsregeln bearbeiten** aus.

11. Wählen Sie die Registerkarte **Ausstellungsautorisierungsregeln** aus, und vergewissern Sie sich, dass die neue Autorisierungsregel erfolgreich erstellt wurde.

12. Wählen Sie die Registerkarte **Ausstellungstransformationsregeln** aus, und vergewissern Sie sich, dass die neue Transformationsregel erfolgreich erstellt wurde.

