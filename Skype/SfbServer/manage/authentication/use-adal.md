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
description: In diesem Artikel wird erläutert, wie modernen Authentifizierung (die auf dem Active Directory-Authentifizierung Library (ADAL) und OAuth 2.0 basiert) verwenden, die in der März 2016 nachlesen können kumulative Update für Skype für Unternehmen für Skype für Business Server 2015.
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
 
In diesem Artikel wird erläutert, wie modernen Authentifizierung (die auf dem Active Directory-Authentifizierung Library (ADAL) und OAuth 2.0 basiert) verwenden, die in der März 2016 nachlesen können kumulative Update für Skype für Unternehmen für Skype für Business Server 2015.
  
## <a name="whats-in-this-article"></a>Inhalt dieses Themas

[Was ist ADAL?](use-adal.md#BKMK_ADAL)
  
[Konfigurieren von ADAL in Ihrem Pool und Festlegen von ADFS als Sicherheitstokenserver](use-adal.md#BKMK_Config)
  
[Weitere Optionen für die Aktivierung der ADAL-Anmeldung (zum Beispiel Office-Client-Apps)](use-adal.md#BKMK_Options)
  
[Clients, bei denen moderne Authentifizierung/ADAL nicht unterstützt wird](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>Was ist ADAL?
<a name="BKMK_ADAL"> </a>

ADAL ist das Akronym für „Active Directory Authentication Library“ und bildet gemeinsam mit OAuth 2.0 die Grundlage für die moderne Authentifizierung. In dieser Codebibliothek dient zum gesicherte Ressourcen in Ihrem Verzeichnis Clientanwendungen (wie Skype für Unternehmen) über Sicherheitstoken zur Verfügung zu stellen. ADAL arbeitet mit OAuth 2.0 zusammen, um mehr Szenarien für Authentifizierung und Autorisierung wie mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und weitere Formen der SAML-Authentifizierung zu ermöglichen.
  
Viele Apps, die als Clients fungieren, können moderne Authentifizierung zur Unterstützung des Zugriffs auf gesicherte Ressourcen nutzen. In Skype für Business Server 2015 wird diese Technologie zwischen lokalen Clients und Servern verwendet, um Benutzern eine ordnungsgemäße Ebene der Autorisierung auf Ressourcen bieten.
  
Unterhaltungen mit moderner Authentifizierung (die auf ADAL und OAuth 2.0 gründen), haben einige Gemeinsamkeiten.
  
- Ein Client, eine Anforderung für eine Ressource vorhanden ist, der Client ist in diesem Fall Skype für Unternehmen.
    
- Es ist eine Ressource, zu der der Client eine bestimmte Zugriffsebene, benötigt, und diese Ressource wird durch einen Verzeichnisdienst gesichert, die Ressource ist in diesem Fall Skype für Business Server 2015.
    
- Besteht eine OAuth-Verbindung mit anderen Worten, eine Verbindung, die einen Benutzer Zugriff auf eine Ressource für das *Autorisieren* dediziert. (OAuth ist auch unter dem aussagekräftigeren Namen „Server-to-Server“ bekannt und wird deshalb häufig als S2S abgekürzt.)
    
Skype für Business Server 2015 modernen Authentifizierung (ADAL) Unterhaltungen kommuniziert Skype für Business Server 2015 über AD FS (AD FS 3.0 in Windows Server 2012 R2). Die Authentifizierung kann über einen anderen beliebigen Identitätsanbieter (Identity Provider, IdP) erfolgen, aber Skype for Business Server muss für die direkte Kommunikation mit AD FS konfiguriert sein. Wenn Sie AD FS Skype für Business Server 2015 entwickelt konfiguriert haben füllen Sie die [AD FS-Installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL ist in der März 2016 enthalten kumulative Update für Skype für Business Server 2015 und die März 2016 kumulative Update für Skype für Business **muss** installiert werden und für die erfolgreiche Konfiguration erforderlich ist.
  
> [!NOTE]
> Während der Erstveröffentlichung ist moderne Authentifizierung in einer lokalen Umgebung nur unterstützt, wenn es keine gemischter Skype-Topologie ist. Wenn beispielsweise die Umgebung rein Skype für Business Server 2015 ist. Mit dieser Anweisung möglicherweise kann geändert werden. 
  
Ein PowerShell-Paket einschließlich .ps1-Dateien mit den von ADAL verwendeten Befehlen muss für eine erfolgreiche Konfiguration heruntergeladen werden.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Konfigurieren von ADAL in Ihrem Pool und Festlegen von ADFS als Sicherheitstokenserver
<a name="BKMK_Config"> </a>

In diesem Prozess verbinden Sie die Installation von AD FS mit einer Skype für Business Server 2015-Pool, der für ADAL konfiguriert ist.
  
1. Installieren der März 2016 kumulative Update für Skype für Business Server 2015 zu Ihrer Skype für Business Server 2015 Pool oder Standard Edition-Server. (Planen Sie nach Bedarf Wartungsfenster, um Windows Update für die automatische Installation auszuführen.)
    
2. Auf Ihrer lokalen AD FS-Servern, [Laden Sie](https://aka.ms/sfbadalscripts) das Setup-AdfsOAuthTrustForSfB Skript. (Dies pro AD FS-Farm oder unabhängigen AD FS-Server ausgeführt werden soll. Es muss nicht auf AD FS-Proxy oder Proxys ausgeführt werden).
    
3. Notieren Sie sich von der internen und externen Webdienst vollqualifizierte Domänennamen (FQDNs) für Ihre Skype für Business Server 2015 Pool oder Standard Edition-Server. Tun Sie dies für alle Skype for Business-Pools.
    
4. Führen Sie über PowerShell auf dem oder den ADFS-Server(n)das Setup-Adfs OAuthTrustForSfB-Skript aus. Sie müssen die zutreffenden URLs für die FQDNs des internen und externen Webdienstes eingeben. Nachfolgend ein Beispiel:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Zusätzliche Pools müssen Sie die Webdienst-URLs Pool manuell die Skype für Business Server 2015 Vertrauensstellung für vertrauende Seite in AD FS hinzugefügt werden.
    
    > [!IMPORTANT]
    > Es ist nicht möglich, passive Authentifizierung für einen Pool und außerdem ADAL zu verwenden. Sie müssen passive Authentifizierung deaktivieren, damit Sie ADAL verwenden können. PowerShell-Cmdlets zum Festlegen der Authentifizierung für einen Pool finden Sie unter [in diesem](https://technet.microsoft.com/en-us/library/gg398396.aspx) Artikel.
  
    > [!TIP]
    > Wenn Sie zusätzliche Pools haben müssen Sie diese als [Bezeichner](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) hinzufügen, um die Vertrauensstellung für vertrauende Seite in AD FS. > Gehe zu AD FS-Server und öffnen Sie die AD FS-Verwaltung. Erweitern Sie Vertrauensstellungen \> Relying Party-Vertrauensstellungen. Mit der rechten Maustaste die Vertrauensstellung für vertrauende Seite, die aufgeführt wird und für Eigenschaften Rechtsklick \> Bezeichner \> Geben Sie die zusätzliche Pool URL(s) \> klicken Sie auf Hinzufügen. 
  
5. Geben Sie an Ihre Skype für Business Server 2015 Front-End oder Standard Edition-Server. Hier müssen Sie die Cmdlets ausführen, die OAuth-Server erstellen und ändern die OAuth-Konfiguration Skype für Unternehmen entwickelt. Sie müssen nur führen Sie diesen Schritt einmal pro Skype für Business Server 2015 Bereitstellung. Hier ist ein Beispiel:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > Die Sie in diesem Befehl finden Sie unter "Identität" URL ist tatsächlich ADFS Namen des Verbunddienstes können Sie die bei der Verwaltung von AD FS mit der rechten Maustaste Service \> Eigenschaften. Der "Typ" ist immer ADFS, und die 'Metadaten-URL' ist immer \<Your ADFS Dienstname\> + "/ FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Testen Sie noch auf Ihrem Skype für Business Server 2015 Front-End oder Standard Edition-Server die neue Konfiguration, indem Sie die SIP-Adresse eines Benutzers und FQDN des Pools eingeben. Sie müssen nur führen Sie diesen Schritt einmal pro Skype für Business Server 2015 Bereitstellung. Hier ist ein Beispiel:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Wenn Sie dazu aufgefordert werden, achten Sie darauf, die Anmeldeinformationen des Testnutzers einzugeben. Stellen Sie sicher, dass der Test erfolgreich beendet wird.
    
    > [!NOTE]
    > Wenn Ihr STS-URL in AD FS *intern* aufgelöst wird, werden die Aufforderung sehen Sie ein **Windows-Sicherheitshinweis** angezeigt. Sollte die URL extern aufgelöst werden, sehen Sie eine Eingabeaufforderung namens **Anmelden**. Normalerweise sollte an dieser Stelle die **Windows Security**-Eingabeaufforderung angezeigt werden. Beachten Sie, dass dieses Verhalten unterschiedlich ausfallen kann, speziell wenn Sie formularbasierte Authentifizierung (FBA) implementiert haben.
  
Beachten Sie außerdem: Wenn die STS-URL zu einem internen ADFS-Server aufgelöst wird und in Browsern integrierte Windows-Authentifizierung aktiviert ist, können auf Computern, auf denen sich viele verschiedene Nutzer für Client-Anwendungen anmelden, Authentifizierungsfehler auftreten, wenn nicht der Browser ausdrücklich dafür konfiguriert ist, Nutzern eine Eingabeaufforderung für ihre Anmeldedaten in einer bestimmten Browser-Sicherheitszone zu präsentieren. Denken Sie zum Beispiel an einen Kiosk. Das Konto der Anmeldung beim Betriebssystem kann ein anderes als das Benutzerkonto der Anmeldung beim Skype for Business-Client sein. In einem solchen Fall könnten die hier beschriebenen Fehler auftreten.
    
Sie können finden Sie unter und diese Browsereinstellung in Internet Explorer ändern, indem Sie auf \> Tools (oder die Zahnrad) \> Internetoptionen \> Registerkarte Sicherheit \> und die Sicherheitszone (beispielsweise Lokales Intranet). Klicken Sie in diesem Dialogfeld auf „Stufe anpassen“ und blättern Sie im Dialogfeld „Einstellungen“ bis zum Ende der Liste. Klicken Sie unter Benutzerauthentifizierung \> Anmeldung \> sehen Sie eine Option, um 'Nach Benutzername und Kennwort Fragen'. Bei einem Kiosk, bei dem der Nutzer, der den Skype for Business-Client startet, ein anderer ist (ein anderes Konto hat) als der beim Computer angemeldete Nutzer, empfiehlt es sich, diese Option für diese Computer in einer Gruppenrichtlinie probehalber auf „EIN“ zu stellen.
    
Letzten Endes (ganz wichtig) könnten Sie feststellen, dass mehr als eine Eingabeaufforderung (die des Sicherheitssystems) die Informationen fordert, die für die Authentifizierung bzw. Autorisierung Ihres Kontos notwendig sind.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Weitere Optionen für die Aktivierung der ADAL-Anmeldung (zum Beispiel Office-Client-Apps)
<a name="BKMK_Options"> </a>

Nun, ADAL für Ihre Skype für Unternehmen konfiguriert ist und (automatisch) für Office 2016 Clientanwendungen plattformübergreifend, möchten Sie möglicherweise für Exchange Online (wobei es ist nicht 'Auf' in der Standardeinstellung) oder in Office 2013-Clients nutzen.
  
> [!IMPORTANT]
> Möchten Sie wissen, was von modernen Authentifizierung Anmeldungen aus Ihrer Client-apps erwarten? Sehen Sie sich [wie modernen Funktionsweise der Authentifizierung für apps für Office 2013 und Office 2016 Client](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Um modernen Authentifizierung für Exchange Online zu aktivieren, müssen Sie einige PowerShell-Cmdlets ausführen. Im Fall von apps für Office 2013-Client müssen Sie einige Registrierungsschlüssel auf Clientcomputern zu ändern.
  
- Exchange Online her, und führen Sie die folgenden Cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Legen Sie diese Registrierungsschlüssel für jedes Gerät oder jeden Computer fest, auf dem Sie die moderne Authentifizierung aktivieren möchten. In größeren Organisationen benötigen Sie ein Gruppenrichtlinienobjekt (GPO). Informationen zum Erstellen eines Gruppenrichtlinienobjekts finden Sie unter "Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Domänencomputer verknüpften" [dieses ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)Artikels.
    
||||
|:-----|:-----|:-----|
|Registrierungsschlüssel  <br/> |Typ  <br/> |Wert  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Nachdem Sie diese Schlüssel festgelegt werden, legen Sie Ihre apps für Office 2013 [Multifaktor Authentifizierung (mehrstufiger Authentifizierung das) mit Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)verwenden.
  
> [!TIP]
> Zum Deaktivieren der modernen Authentifizierung auf Geräten für Office 2013 legen Sie den Registrierungsschlüssel HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL auf einen Wert von 0 (null). Beachten Sie, dass ein ähnlicher Registrierungsschlüssel (HKCU\SOFTWARE\Microsoft\Office\ **16,0** \Common\Identity\EnableADAL) auch deaktivieren der modernen Authentifizierung auf Geräten für Office 2016 verwendet werden kann.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clients, bei denen moderne Authentifizierung/ADAL nicht unterstützt wird
<a name="BKMK_Support"> </a>

Einige Clientversionen unterstützen OAuth nicht. Sie können Ihre Version des Office-Clients in der Systemsteuerung überprüfen. Unter „Programme hinzufügen oder entfernen“ können Sie die Versionsnummer Ihrer Version mit den Versionen (oder Versionsbereichen) abgleichen, die hier aufgeführt sind:
  
- Office-Client 15.0. [0000-4766].\*
    
- Office-Client 16,0. [0000-4293].\*
    
- Office-Client 16.0.6001.[0000–1032]
    
- Office-Client 16,0. [6000-6224].\*
    

