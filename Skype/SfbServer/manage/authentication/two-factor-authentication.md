---
title: Verwalten der zweistufigen Authentifizierung in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Zusammenfassung: Verwalten der zweistufigen Authentifizierung in Skype for Business Server.'
---

# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Verwalten der zweistufigen Authentifizierung in Skype for Business Server
 
**Zusammenfassung:** Verwalten der zweistufigen Authentifizierung in Skype for Business Server.
  
Die zweistufige Authentifizierung bietet erhöhte Sicherheit, da Benutzer zwei Formen der Authentifizierung oder Identifizierung bereitstellen müssen, nämlich eine Kombination aus Benutzername und Kennwort und einem Token oder Zertifikat. Dies wird auch als "etwas, das Sie haben, etwas, das Sie kennen" bezeichnet. 
  
Ein typisches Beispiel für die zweistufige Authentifizierung mit einem Zertifikat ist die Verwendung von Smartcards. Eine Smartcard enthält ein dem Benutzerkonto zugeordnetes Zertifikat und kann anhand der auf einem Server gespeicherten Benutzer- und Zertifikatinformationen überprüft werden. Durch den Vergleich der Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat überprüft der Server die Anmeldeinformationen und authentifiziert den Benutzer.
  
Berücksichtigen Sie die folgenden Themen beim Konfigurieren einer Skype for Business Server-Umgebung zur Unterstützung der zweistufigen Authentifizierung.
  
## <a name="client-support"></a>Clientunterstützung

Die kumulativen Updates für Lync Server 2013: Desktopclient vom Juli 2013 und der Skype for Business-Client sind die einzigen Clients, die derzeit die zweistufige Authentifizierung unterstützen.
  
## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Kunden werden empfohlen, die zweistufige Authentifizierung mit dedizierten Skype for Business Server mit Edge-, Director- und Benutzerpools bereitzustellen. Um die passive Authentifizierung für Benutzer zu aktivieren, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert werden, einschließlich der folgenden:
  
|**Konfigurationstyp**|**Diensttyp**|**Serverrolle**|**Zu deaktivierende Authentifizierungstyp**|
|:-----|:-----|:-----|:-----|
|Webdienst  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Webdienst  <br/> |WebServer  <br/> |Front-End-  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Microsoft Edge  <br/> |Kerberos und NTLM  <br/> |
|Proxy  <br/> |Registrar  <br/> |Front-End-  <br/> |Kerberos und NTLM  <br/> |
   
Wenn diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, können sich alle anderen Versionen des Clients nicht erfolgreich anmelden, sobald die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert ist.
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business Service Discovery

DNS-Einträge, die von internen und/oder externen Clients zum Ermitteln Skype for Business Dienste verwendet werden, sollten so konfiguriert werden, dass sie in einen Skype for Business Server aufgelöst werden, der nicht für die zweistufige Authentifizierung aktiviert ist. Bei dieser Konfiguration müssen Benutzer aus Skype for Business Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, keine PIN eingeben, um sich zu authentifizieren, während Benutzer aus Skype for Business Pools, die für die zweistufige Authentifizierung aktiviert sind, ihre PIN eingeben müssen, um sich zu authentifizieren.
  
## <a name="exchange-authentication"></a>Exchange-Authentifizierung

Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, stellen möglicherweise fest, dass bestimmte Features im Client nicht verfügbar sind. Dieses Verhalten ist beabsichtigt, da der Skype for Business Client die zweistufige Authentifizierung für Features, die von Exchange Integration abhängig sind, nicht unterstützt.
  
## <a name="contacts"></a>Kontakte

Skype for Business Benutzer, die für die Nutzung der Funktion "Einheitlicher Kontakt Store" konfiguriert sind, werden feststellen, dass ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.
  
Verwenden Sie das Cmdlet **Invoke-CsUcsRollback**, um vorhandene Benutzerkontakte aus dem einheitlichen Kontakt-Store zu entfernen und in Skype for Business Server zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.
  
## <a name="skill-search"></a>Qualifikationssuche

Kunden, die das Feature "Qualifikationssuche" in ihrer Skype for Business Umgebung konfiguriert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn Skype for Business für die zweistufige Authentifizierung aktiviert ist. Dies ist beabsichtigt, da Microsoft SharePoint derzeit keine zweistufige Authentifizierung unterstützt.
  
## <a name="credentials"></a>Anmeldeinformationen

Es gibt eine Reihe von Bereitstellungsüberlegungen im Zusammenhang mit gespeicherten Skype for Business Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.
  
### <a name="deleting-saved-credentials"></a>Löschen gespeicherter Anmeldeinformationen

Benutzer sollten die Option **"Meine Anmeldeinformationen** löschen" im Skype for Business-Client verwenden und ihren SIP-Profilordner aus %localappdata%\Microsoft\Office\15.0\Skype for Business löschen, bevor sie versuchen, sich zum ersten Mal mithilfe der zweistufigen Authentifizierung anzumelden.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Bei der Kerberos- oder NTLM-Authentifizierungsmethode werden die Windows Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet. In einer typischen Skype for Business Server Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer ihre Anmeldeinformationen nicht jedes Mal eingeben müssen, wenn sie sich anmelden.
  
Wenn Benutzer versehentlich zur Eingabe von Anmeldeinformationen aufgefordert werden, bevor sie aufgefordert werden, ihre PIN einzugeben, wird der **Registrierungsschlüssel "DisableNTCredentials** " möglicherweise unbeabsichtigt auf Clientcomputern konfiguriert, möglicherweise über die Gruppenrichtlinie.
  
Um die zusätzliche Eingabeaufforderung für Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die Skype for Business administrative Vorlage, um alle Benutzer für einen bestimmten Pool mithilfe von Gruppenrichtlinien anzuwenden:
  
HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
REG_DWORD: DisableNTCredentials

Wert: 0x0
  
### <a name="savepassword"></a>SavePassword

Wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet, wird er aufgefordert, sein Kennwort zu speichern. Wenn diese Option ausgewählt ist, können das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows Anmeldeinformationen des Benutzers im Anmeldeinformations-Manager des lokalen Computers gespeichert werden.
  
Die **Registrierungseinstellung "SavePassword**" sollte deaktiviert werden, wenn Skype for Business für die Unterstützung der zweistufigen Authentifizierung konfiguriert ist. Um zu verhindern, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die Skype for Business administrative Vorlage, um alle Benutzer für einen bestimmten Pool mithilfe von Gruppenrichtlinien anzuwenden:
  
HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
REG_DWORD: SavePassword
  
Wert: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0-Tokenwiederholung

AD FS 2.0 stellt ein Feature bereit, das als Tokenwiederholungserkennung bezeichnet wird und mit dem mehrere Tokenanforderungen, die dasselbe Token verwenden, erkannt und dann verworfen werden können. Wenn dieses Feature aktiviert ist, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation profil als auch im SAML-WebSSO-Profil, indem sichergestellt wird, dass dasselbe Token nie mehrmals verwendet wird.
  
Dieses Feature sollte in Situationen aktiviert werden, in denen sicherheit ein sehr wichtiges Problem ist, z. B. bei der Verwendung von Kiosken. Weitere Informationen zur Erkennung der Tokenwiederholung finden Sie unter [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).
  
## <a name="guest-user-access"></a>Gastbenutzerzugriff

Das Konfigurieren eines ADFS-Proxys oder Reverseproxys zur Unterstützung Skype for Business zweistufigen Authentifizierung aus externen Netzwerken wird in diesen Themen nicht behandelt.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server](configure-two-factor.md)
