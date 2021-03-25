---
title: Verwalten der zweistufigen Authentifizierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Zusammenfassung: Verwalten der zweistufigen Authentifizierung in Skype for Business Server.'
ms.openlocfilehash: 8e8f665d824cd5f21cc2ca874668eba90bc97c4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119544"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Verwalten der zweistufigen Authentifizierung in Skype for Business Server
 
**Zusammenfassung:** Verwalten der zweistufigen Authentifizierung in Skype for Business Server.
  
Die zweistufige Authentifizierung bietet eine verbesserte Sicherheit, da Benutzer zwei Authentifizierungs- oder Identifikationsmethoden bereitstellen müssen, nämlich eine Kombination aus Benutzername und Kennwort sowie ein Token oder Zertifikat. Dies wird auch als "etwas, das Sie haben, etwas, das Sie kennen" bezeichnet. 
  
Ein typisches Beispiel für die zweistufige Authentifizierung mit einem Zertifikat ist die Verwendung von Smartcards. Eine Smartcard enthält ein dem Benutzerkonto zugeordnetes Zertifikat und kann anhand von Benutzer- und Zertifikatinformationen überprüft werden, die auf einem Server gespeichert sind. Durch vergleichen der Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat überprüft der Server die Anmeldeinformationen und authentifiziert den Benutzer.
  
Berücksichtigen Sie die folgenden Themen beim Konfigurieren einer Skype for Business Server-Umgebung zur Unterstützung der zweistufigen Authentifizierung.
  
## <a name="client-support"></a>Clientunterstützung

Der kumulative Updates für Lync Server 2013: July 2013-Desktopclient und der Skype for Business-Client sind die einzigen Clients, die derzeit die zweistufige Authentifizierung unterstützen.
  
## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Kunden werden dringend aufgefordert, die zweistufige Authentifizierung mithilfe von dedizierten Skype for Business Server mit Edge-, Director- und Benutzerpools zu implementieren. Um die passive Authentifizierung für Benutzer zu aktivieren, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert werden, einschließlich der folgenden:
  
|**Konfigurationstyp**|**Diensttyp**|**Serverrolle**|**Zu deaktivierende Authentifizierungsart**|
|:-----|:-----|:-----|:-----|
|Webdienst  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Webdienst  <br/> |WebServer  <br/> |Front-End-  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Microsoft Edge  <br/> |Kerberos und NTLM  <br/> |
|Proxy  <br/> |Registrierungsstelle  <br/> |Front-End-  <br/> |Kerberos und NTLM  <br/> |
   
Wenn diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, können sich alle anderen Versionen des Clients nicht erfolgreich anmelden, sobald die zweistufige Authentifizierung innerhalb der Bereitstellung aktiviert ist.
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business Service Discovery

DNS-Einträge, die von internen und/oder externen Clients zum Ermitteln von Skype for Business-Diensten verwendet werden, sollten so konfiguriert werden, dass sie in einen Skype for Business-Server aufgelöst werden, der nicht für die zweistufige Authentifizierung aktiviert ist. Bei dieser Konfiguration müssen Benutzer aus Skype for Business-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, keine PIN für die Authentifizierung eingeben, während Benutzer aus Skype for Business Pools, die für die zweistufige Authentifizierung aktiviert sind, ihre PIN für die Authentifizierung eingeben müssen.
  
## <a name="exchange-authentication"></a>Exchange-Authentifizierung

Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, stellen möglicherweise fest, dass bestimmte Features im Client nicht verfügbar sind. Dies ist derzeit entwurfsabhängig, da der Skype for Business-Client die zweistufige Authentifizierung für Features, die von der Exchange-Integration abhängig sind, nicht unterstützt.
  
## <a name="contacts"></a>Kontakte

Skype for Business-Benutzer, die für die Nutzung des Unified Contact Store-Features konfiguriert sind, stellen nach der Anmeldung mit zweistufiger Authentifizierung fest, dass ihre Kontakte nicht mehr verfügbar sind.
  
Verwenden Sie das **Cmdlet Invoke-CsUcsRollback,** um vorhandene Benutzerkontakte aus dem einheitlichen Kontaktspeicher zu entfernen und sie in Skype for Business Server zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.
  
## <a name="skill-search"></a>Kompetenzsuche

Kunden, die das Feature "Kompetenzsuche" in ihrer Skype for Business-Umgebung konfiguriert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn Skype for Business für die zweistufige Authentifizierung aktiviert ist. Dies ist ein Entwurf, da Microsoft SharePoint derzeit keine zweistufige Authentifizierung unterstützt.
  
## <a name="credentials"></a>Anmeldeinformationen

Es gibt eine Reihe von Bereitstellungsüberlegungen im Zusammenhang mit gespeicherten Skype for Business-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.
  
### <a name="deleting-saved-credentials"></a>Löschen gespeicherter Anmeldeinformationen

Benutzer sollten  die Option Meine Anmeldeinformationen löschen im Skype for Business-Client verwenden und ihren SIP-Profilordner aus %localappdata%\Microsoft\Office\15.0\Skype for Business löschen, bevor sie versuchen, sich zum ersten Mal mit der zweistufigen Authentifizierung zu signieren.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Bei der Kerberos- oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet. In einer typischen Skype for Business Server-Bereitstellung, in der Kerberos und/oder NTLM für die Authentifizierung aktiviert sind, sollten Benutzer ihre Anmeldeinformationen nicht jedes Mal eingeben müssen, wenn sie sich anmelden.
  
Wenn Benutzer unbeabsichtigt zur Eingabe von Anmeldeinformationen aufgefordert werden, bevor sie zur Eingabe ihrer PIN aufgefordert werden, wird der **Registrierungsschlüssel DisableNTCredentials** möglicherweise unbeabsichtigt auf Clientcomputern konfiguriert, möglicherweise über Gruppenrichtlinien.
  
Um die zusätzliche Eingabeaufforderung für Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die Skype for Business-Verwaltungsvorlage, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool anzuwenden:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Wenn sich ein Benutzer zum ersten Mal bei Skype for Business einschreibt, wird der Benutzer aufgefordert, sein Kennwort zu speichern. Bei Auswahl dieser Option können das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows-Anmeldeinformationen des Benutzers im Anmeldeinformations-Manager des lokalen Computers gespeichert werden.
  
Die **SavePassword-Registrierungseinstellung** sollte deaktiviert werden, wenn Skype for Business für die Unterstützung der zweistufigen Authentifizierung konfiguriert ist. Um zu verhindern, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die Skype for Business-Verwaltungsvorlage, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool anzuwenden:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0-Tokenwiedergabe

AD FS 2.0 bietet ein Feature, das als Tokenwiedergabeerkennung bezeichnet wird, mit dem mehrere Tokenanforderungen mit demselben Token erkannt und dann verworfen werden können. Wenn dieses Feature aktiviert ist, schützt die Erkennung von Tokenwiedergaben die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass das gleiche Token nie mehr als einmal verwendet wird.
  
Dieses Feature sollte in Situationen aktiviert werden, in denen die Sicherheit sehr wichtig ist, z. B. bei der Verwendung von Kiosken. Weitere Informationen zur Erkennung von Tokenwiedergaben finden Sie unter [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).
  
## <a name="external-user-access"></a>Externer Benutzerzugriff

Das Konfigurieren eines ADFS-Proxys oder Reverseproxys zur Unterstützung der zweistufigen Skype for Business-Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server](configure-two-factor.md)
