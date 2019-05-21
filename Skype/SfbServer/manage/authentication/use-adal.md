---
title: Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: In diesem Artikel wird die Verwendung der modernen Authentifizierung (basierend auf der Active Directory Authentication Library (Adal) und OAuth 2,0) erläutert, die im kumulativen Update vom März 2016 für Skype for Business für Skype for Business Server 2015 zu finden ist.
ms.openlocfilehash: 9fe4470e1f8f6e2cd345cd176250fb1ffb16448f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286123"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
 
In diesem Artikel wird die Verwendung der modernen Authentifizierung (basierend auf der Active Directory Authentication Library (Adal) und OAuth 2,0) erläutert, die im kumulativen Update vom März 2016 für Skype for Business für Skype for Business Server 2015 oder von Initial gefunden werden kann. Release für Skype for Business Server 2019.
  
## <a name="whats-in-this-article"></a>Inhalt dieses Themas

[Konfigurieren von Adal in Ihrem Pool und Festlegen von AD FS als Sicherheitstoken-Server](use-adal.md#BKMK_Config)
  
[Weitere Optionen für die Aktivierung der ADAL-Anmeldung (zum Beispiel Office-Client-Apps)](use-adal.md#BKMK_Options)
  
[Clients, bei denen moderne Authentifizierung/ADAL nicht unterstützt wird](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Konfigurieren von Adal in Ihrem Pool und Festlegen von AD FS als Sicherheitstoken-Server
<a name="BKMK_Config"> </a>

In diesem Verfahren verbinden Sie Ihre Installation von AD FS mit einem Skype for Business-Server Pool, der für Adal konfiguriert ist.
  
1. Installieren Sie das kumulative Update vom März 2016 (oder neuer) für Skype for Business Server 2015 auf Ihrem Skype for Business Server-Pool oder Standard Edition-Server. (Planen Sie nach Bedarf Wartungsfenster, um Windows Update für die automatische Installation auszuführen.)
    
2. Laden Sie auf Ihren lokalen AD FS-Servern das Setup-AdfsOAuthTrustForSfB-Skript [herunter](https://aka.ms/sfbadalscripts) . (Dies muss pro AD FS-Farm oder unabhängigen AD FS-Servern erfolgen. Es muss nicht auf AD FS-Proxys oder Webanwendungs Proxys ausgeführt werden.)
    
3. Notieren Sie sich die vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen und externen Webdiensts für Ihren Skype for Business Server-Pool oder Standard Edition-Server. Tun Sie dies für alle Skype for Business-Pools.
    
4. Führen `Setup-AdfsOAuthTrustForSfB.ps1` Sie aus PowerShell auf dem AD FS-Server (s) (für Windows Server 2012 R2) `Setup-Adfs2016OAuthTrustForSfB.ps1` oder (für Windows Server 2016 oder höher). Sie müssen die richtigen URLs für die vollqualifizierten Domänennamen (Fully Qualified Domain Name, interne und externe Web Service) eingeben. Nachfolgend ein Beispiel:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Wenn Sie weitere Pools verwenden, müssen Sie die Pool-Webdienste-URLs manuell zur vertrauenswürdigen Skype for Business Server-Vertrauensstellung in AD FS hinzufügen.
    
    > [!IMPORTANT]
    > Es ist nicht möglich, passive Authentifizierung für einen Pool und außerdem ADAL zu verwenden. Sie müssen passive Authentifizierung deaktivieren, damit Sie ADAL verwenden können. Informationen zu PowerShell-Cmdlets zum Einrichten der Authentifizierung für einen Pool finden Sie in [diesem](https://technet.microsoft.com/en-us/library/gg398396.aspx) Artikel.
  
    > [!TIP]
    > Wenn Sie über weitere Pools verfügen, müssen Sie diese als [Bezeichner](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) zur vertrauenswürdigen Seite der vertrauenden Seite in AD FS. > hinzufügen und dann zu Ihrem AD FS-Server wechseln und die AD FS-Verwaltung öffnen. Erweitern von Vertrauens \> Stellungen für vertrauenswürdige Beziehungen. Klicken Sie mit der rechten Maustaste auf die Liste der vertrauenden Seite, und klicken Sie \> mit \> der rechten Maustaste auf Eigenschaftenbezeichner geben Sie \> die zusätzlichen Pool-URL (s) ein, und klicken Sie auf hinzufügen. 
  
5. Kehren Sie zu Ihrem Skype for Business Server-Front-End-oder Standard Edition-Server zurück. Hier müssen Sie Cmdlets ausführen, mit denen ein OAuth-Server erstellt und diese OAuth-Konfiguration so geändert wird, dass Sie mit Skype for Business funktioniert. Sie müssen diesen Schritt nur einmal pro Skype for Business Server-Bereitstellung ausführen. Hier ist ein Beispiel:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > Die "Identität"-URL, die Sie in diesem Befehl sehen, ist eigentlich der Name des AD FS-Verbunddiensts, den Sie in der AD FS \> -Verwaltung sehen können, wenn Sie mit der rechten Maustaste auf Diensteigenschaften klicken. Der "Typ" ist immer "ADFS", und das "MetadataURL" ist immer \<Ihr AD FS-Dienst\> Name + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Testen Sie die neue Konfiguration weiterhin auf Ihrem Skype for Business Server-Front-End-oder Standard Edition-Server, indem Sie die SIP-Adresse eines Benutzers und den FQDN des Pools eingeben. Sie müssen diesen Schritt nur einmal pro Skype for Business Server-Bereitstellung ausführen. Hier ist ein Beispiel:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Wenn Sie dazu aufgefordert werden, achten Sie darauf, die Anmeldeinformationen des Testnutzers einzugeben. Stellen Sie sicher, dass der Test erfolgreich beendet wird.
    
    > [!NOTE]
    > Wenn Ihre STS-URL *intern* in AD FS aufgelöst wird, wird die Eingabeaufforderung als **Windows-Sicherheits** Aufforderung angezeigt. Sollte die URL extern aufgelöst werden, sehen Sie eine Eingabeaufforderung namens **Anmelden**. Normalerweise sollte an dieser Stelle die **Windows Security**-Eingabeaufforderung angezeigt werden. Beachten Sie, dass dieses Verhalten unterschiedlich ausfallen kann, speziell wenn Sie formularbasierte Authentifizierung (FBA) implementiert haben.
  
Beachten Sie auch, wenn die STS-URL zu einem internen AD FS-Server aufgelöst wird und die integrierte Windows-Authentifizierung in Browsern aktiviert ist, Computer, auf denen sich viele verschiedene Benutzer bei Clientanwendungen anmelden, möglicherweise Fehler bei der Authentifizierung aufweisen, es sei denn, der Browser ist explizit so konfiguriert, dass Benutzer zur Eingabe Ihrer Anmeldeinformationen in einer bestimmten Browser-Sicherheits Zone aufgefordert werden. Denken Sie zum Beispiel an einen Kiosk. Das Konto der Anmeldung beim Betriebssystem kann ein anderes als das Benutzerkonto der Anmeldung beim Skype for Business-Client sein. In einem solchen Fall könnten die hier beschriebenen Fehler auftreten.
    
Sie können diese Browsereinstellung in Internet Explorer sehen und ändern, indem \> Sie auf die Registerkarte " \> Extras" \> (oder \> auf die Schaltfläche "Internetoptionen") und die Sicherheits Zone (wie Lokales Intranet) klicken. Klicken Sie in diesem Dialogfeld auf „Stufe anpassen“ und blättern Sie im Dialogfeld „Einstellungen“ bis zum Ende der Liste. Unter Benutzer \> Authentifizierungs \> Anmeldung sehen Sie eine Option zur Eingabeaufforderung für Benutzername und Kennwort. Bei einem Kiosk, bei dem der Nutzer, der den Skype for Business-Client startet, ein anderer ist (ein anderes Konto hat) als der beim Computer angemeldete Nutzer, empfiehlt es sich, diese Option für diese Computer in einer Gruppenrichtlinie probehalber auf „EIN“ zu stellen.
    
Letzten Endes (ganz wichtig) könnten Sie feststellen, dass mehr als eine Eingabeaufforderung (die des Sicherheitssystems) die Informationen fordert, die für die Authentifizierung bzw. Autorisierung Ihres Kontos notwendig sind.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Weitere Optionen für die Aktivierung der ADAL-Anmeldung (zum Beispiel Office-Client-Apps)
<a name="BKMK_Options"> </a>

Nachdem Adal für Ihre Skype for Business-und (automatisch) für Office 2016-Client-apps plattformübergreifend konfiguriert wurde, sollten Sie es möglicherweise für Exchange Online nutzen (sofern es nicht standardmäßig aktiviert ist) oder in Office 2013-Clients.
  
> [!IMPORTANT]
> Müssen Sie wissen, was Sie von den modernen Authentifizierungs Anmeldungen von Ihren Client-apps erwarten können? Sehen Sie sich an [, wie die moderne Authentifizierung für Office 2013-und Office 2016-Client-apps funktioniert](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Wenn Sie die moderne Authentifizierung für Exchange Online aktivieren möchten, müssen Sie einige PowerShell-Cmdlets ausführen. Im Fall von Office 2013-Client-apps müssen Sie einige Registrierungsschlüssel auf Clientcomputern ändern.
  
- Stellen Sie eine Verbindung mit Exchange Online her, und führen Sie die folgenden Cmdlets aus:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Legen Sie diese Registrierungsschlüssel für jedes Gerät oder jeden Computer fest, auf dem Sie die moderne Authentifizierung aktivieren möchten. In größeren Organisationen benötigen Sie ein Gruppenrichtlinienobjekt (GPO). Informationen zum Erstellen eines Gruppenrichtlinienobjekts finden Sie in [diesem ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)Artikel unter "Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer mit einem Domänenbeitritt".
    
|Registrierungsschlüssel  <br/> |Typ  <br/> |Wert  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Nachdem Sie diese Schlüssel festgesetzt haben, müssen Sie Ihre Office-apps so einrichten, dass Sie die mehrstufige [Authentifizierung (MFA) mit Office 365 verwenden](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Um die moderne Authentifizierung auf Geräten für Office 2013 zu deaktivieren, setzen Sie den Registrierungsschlüssel HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL auf den Wert 0 (null). Beachten Sie, dass ein ähnlicher Registrierungsschlüssel (HKCU\SOFTWARE\Microsoft\Office\ **16,0** \Common\Identity\EnableADAL) auch verwendet werden kann, um die moderne Authentifizierung auf Geräten für Office 2016 zu deaktivieren.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clients, bei denen moderne Authentifizierung/ADAL nicht unterstützt wird
<a name="BKMK_Support"> </a>

Einige Clientversionen unterstützen OAuth nicht. Sie können Ihre Version des Office-Clients in der Systemsteuerung überprüfen. Unter „Programme hinzufügen oder entfernen“ können Sie die Versionsnummer Ihrer Version mit den Versionen (oder Versionsbereichen) abgleichen, die hier aufgeführt sind:
  
- Office-Client 15,0. [0000-4766].\*
    
- Office-Client 16,0. [0000-4293].\*
    
- Office-Client 16.0.6001.[0000–1032]
    
- Office-Client 16,0. [6000-6224].\*
    
> [!NOTE]
> Hybrid-moderne Authentifizierung ist auch in Skype for Business lokal verfügbar, wenn Sie mehr wissen möchten, besuchen Sie bitte die [Anleitung zur Konfiguration von Skype for Business lokal für die Verwendung der modernen Hybrid Authentifizierung](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) .
