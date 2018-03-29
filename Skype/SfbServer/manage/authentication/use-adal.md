---
title: Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
 
This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
  
## <a name="whats-in-this-article"></a>Inhalt dieses Themas

[Was ist ADAL?](use-adal.md#BKMK_ADAL)
  
[Konfigurieren von ADAL in Ihrem Pool und Festlegen von ADFS als Sicherheitstokenserver](use-adal.md#BKMK_Config)
  
[Weitere Optionen für die Aktivierung der ADAL-Anmeldung (zum Beispiel Office-Client-Apps)](use-adal.md#BKMK_Options)
  
[Clients, bei denen moderne Authentifizierung/ADAL nicht unterstützt wird](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>Was ist ADAL?
<a name="BKMK_ADAL"> </a>

ADAL ist das Akronym für „Active Directory Authentication Library“ und bildet gemeinsam mit OAuth 2.0 die Grundlage für die moderne Authentifizierung. This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens. ADAL arbeitet mit OAuth 2.0 zusammen, um mehr Szenarien für Authentifizierung und Autorisierung wie mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und weitere Formen der SAML-Authentifizierung zu ermöglichen.
  
Viele Apps, die als Clients fungieren, können moderne Authentifizierung zur Unterstützung des Zugriffs auf gesicherte Ressourcen nutzen. In Skype for Business Server 2015, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.
  
Unterhaltungen mit moderner Authentifizierung (die auf ADAL und OAuth 2.0 gründen), haben einige Gemeinsamkeiten.
  
- There is a client making a request for a resource, in this case, the client is Skype for Business.
    
- There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server 2015.
    
- There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource. (OAuth ist auch unter dem aussagekräftigeren Namen „Server-to-Server“ bekannt und wird deshalb häufig als S2S abgekürzt.)
    
In Skype for Business Server 2015 Modern Authentication (ADAL) conversations, Skype for Business Server 2015 communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2). Die Authentifizierung kann über einen anderen beliebigen Identitätsanbieter (Identity Provider, IdP) erfolgen, aber Skype for Business Server muss für die direkte Kommunikation mit AD FS konfiguriert sein. If you haven't configured ADFS to work with Skype for Business Server 2015 please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.
  
> [!NOTE]
> During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved. For example, if the environment is purely Skype for Business Server 2015. This statement may be subject to change. 
  
Ein PowerShell-Paket einschließlich .ps1-Dateien mit den von ADAL verwendeten Befehlen muss für eine erfolgreiche Konfiguration heruntergeladen werden.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Konfigurieren von ADAL in Ihrem Pool und Festlegen von ADFS als Sicherheitstokenserver
<a name="BKMK_Config"> </a>

In this process, you connect your installation of ADFS to a Skype for Business Server 2015 pool that is configured for ADAL.
  
1. Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server 2015 pool or Standard Edition server. (Planen Sie nach Bedarf Wartungsfenster, um Windows Update für die automatische Installation auszuführen.)
    
2. On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script. (This needs to be done per ADFS farm or independent ADFS server(s). It does not need to be done on ADFS Proxy or proxies).
    
3. Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server 2015 pool or Standard Edition server. Tun Sie dies für alle Skype for Business-Pools.
    
4. Führen Sie über PowerShell auf dem oder den ADFS-Server(n)das Setup-Adfs OAuthTrustForSfB-Skript aus. Sie müssen die zutreffenden URLs für die FQDNs des internen und externen Webdienstes eingeben. Nachfolgend ein Beispiel:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server 2015 Relying Party Trust in ADFS.
    
    > [!IMPORTANT]
    > Es ist nicht möglich, passive Authentifizierung für einen Pool und außerdem ADAL zu verwenden. Sie müssen passive Authentifizierung deaktivieren, damit Sie ADAL verwenden können. For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management. Expand Trust Relationships \> Relying Party Trusts. Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add. 
  
5. Return to your Skype for Business Server 2015 Front End or Standard Edition server server. From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business. You only need to do this step once per Skype for Business Server 2015 deployment. Hier ist ein Beispiel:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties. The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Still on your Skype for Business Server 2015 Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN. You only need to do this step once per Skype for Business Server 2015 deployment. Hier ist ein Beispiel:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Wenn Sie dazu aufgefordert werden, achten Sie darauf, die Anmeldeinformationen des Testnutzers einzugeben. Stellen Sie sicher, dass der Test erfolgreich beendet wird.
    
    > [!NOTE]
    > When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt. Sollte die URL extern aufgelöst werden, sehen Sie eine Eingabeaufforderung namens **Anmelden**. Normalerweise sollte an dieser Stelle die **Windows Security**-Eingabeaufforderung angezeigt werden. Beachten Sie, dass dieses Verhalten unterschiedlich ausfallen kann, speziell wenn Sie formularbasierte Authentifizierung (FBA) implementiert haben.
  
Beachten Sie außerdem: Wenn die STS-URL zu einem internen ADFS-Server aufgelöst wird und in Browsern integrierte Windows-Authentifizierung aktiviert ist, können auf Computern, auf denen sich viele verschiedene Nutzer für Client-Anwendungen anmelden, Authentifizierungsfehler auftreten, wenn nicht der Browser ausdrücklich dafür konfiguriert ist, Nutzern eine Eingabeaufforderung für ihre Anmeldedaten in einer bestimmten Browser-Sicherheitszone zu präsentieren. Denken Sie zum Beispiel an einen Kiosk. Das Konto der Anmeldung beim Betriebssystem kann ein anderes als das Benutzerkonto der Anmeldung beim Skype for Business-Client sein. In einem solchen Fall könnten die hier beschriebenen Fehler auftreten.
    
You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet). Klicken Sie in diesem Dialogfeld auf „Stufe anpassen“ und blättern Sie im Dialogfeld „Einstellungen“ bis zum Ende der Liste. Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'. Bei einem Kiosk, bei dem der Nutzer, der den Skype for Business-Client startet, ein anderer ist (ein anderes Konto hat) als der beim Computer angemeldete Nutzer, empfiehlt es sich, diese Option für diese Computer in einer Gruppenrichtlinie probehalber auf „EIN“ zu stellen.
    
Letzten Endes (ganz wichtig) könnten Sie feststellen, dass mehr als eine Eingabeaufforderung (die des Sicherheitssystems) die Informationen fordert, die für die Authentifizierung bzw. Autorisierung Ihres Kontos notwendig sind.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Weitere Optionen für die Aktivierung der ADAL-Anmeldung (zum Beispiel Office-Client-Apps)
<a name="BKMK_Options"> </a>

Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.
  
> [!IMPORTANT]
> Need to know what to expect from Modern Authentication sign-ins from your client apps? Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets. In the case of Office 2013 client apps, you will need to change some registry keys on client machines.
  
- Connect to Exchange Online and run the following cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Legen Sie diese Registrierungsschlüssel für jedes Gerät oder jeden Computer fest, auf dem Sie die moderne Authentifizierung aktivieren möchten. In größeren Organisationen benötigen Sie ein Gruppenrichtlinienobjekt (GPO). For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.
    
||||
|:-----|:-----|:-----|
|Registrierungsschlüssel  <br/> |Typ  <br/> |Wert  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Once these keys are set, set your Office 2013 apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero. Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clients, bei denen moderne Authentifizierung/ADAL nicht unterstützt wird
<a name="BKMK_Support"> </a>

Einige Clientversionen unterstützen OAuth nicht. Sie können Ihre Version des Office-Clients in der Systemsteuerung überprüfen. Unter „Programme hinzufügen oder entfernen“ können Sie die Versionsnummer Ihrer Version mit den Versionen (oder Versionsbereichen) abgleichen, die hier aufgeführt sind:
  
- Office Client 15.0.[0000-4766].\*
    
- Office Client 16.0.[0000-4293].\*
    
- Office-Client 16.0.6001.[0000–1032]
    
- Office Client 16.0.[6000-6224].\*
    

