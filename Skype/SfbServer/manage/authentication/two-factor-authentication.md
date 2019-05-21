---
title: Verwalten der zweistufigen Authentifizierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Zusammenfassung: Verwalten der zweistufigen Authentifizierung in Skype for Business Server.'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297561"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Verwalten der zweistufigen Authentifizierung in Skype for Business Server
 
**Zusammenfassung:** Verwalten Sie die zweistufige Authentifizierung in Skype for Business Server.
  
Die zweistufige Authentifizierung bietet eine verbesserte Sicherheit, indem gefordert wird, dass Benutzer zwei Authentifizierungskriterien erfüllen: eine Kombination aus Benutzername und Kennwort sowie ein Token oder Zertifikat. Dies ist auch bekannt als "etwas, das Sie haben, etwas, das Sie kennen." 
  
Ein typisches Beispiel für eine zweistufige Authentifizierung ist die Nutzung von Smartcards. Eine Smartcard enthält ein Zertifikat, das einem Benutzerkonto zugewiesen ist und welches mit den Benutzer- und Zertifikatinformationen überprüft werden kann, die auf einem Server gespeichert sind. Durch Abgleichen der Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat überprüft der Server die Anmeldeinformationen, sodass er den Benutzer authentifizieren kann.
  
Berücksichtigen Sie bei der Konfiguration einer Skype for Business Server-Umgebung die folgenden Themen, um die zweistufige Authentifizierung zu unterstützen.
  
## <a name="client-support"></a>Clientunterstützung

Die kumulativen Updates für lync Server 2013: Juli 2013-Desktop Client und der Skype for Business-Client sind die einzigen Clients, die derzeit die zweistufige Authentifizierung unterstützen.
  
## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Kunden werden dringend ermutigt, die zweistufige Authentifizierung über dedizierten Skype for Business-Server mit Edge-, Director-und User-Pools bereitzustellen. Um die passive Authentifizierung für Benutzer zu aktivieren, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert werden, einschließlich der folgenden:
  
|**Konfigurationstyp**|**Diensttyp**|**Server Rolle**|**Zu deaktivierender Authentifizierungstyp**|
|:-----|:-----|:-----|:-----|
|Webdienst  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Webdienst  <br/> |WebServer  <br/> |Front-End  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos und NTLM  <br/> |
|Proxy  <br/> |Registrierungsstelle  <br/> |Front-End  <br/> |Kerberos und NTLM  <br/> |
   
Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, ist es mit keiner anderen Version des Clients möglich, sich erfolgreich anzumelden, sobald die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert wurde.
  
## <a name="skype-for-business-service-discovery"></a>Ermittlung der Skype for Business-Services

DNS-Einträge, die von internen und/oder externen Clients zur Erkennung von Skype for Business-Diensten verwendet werden, sollten so konfiguriert werden, dass Sie zu einem Skype for Business-Server aufgelöst werden, der für die zweistufige Authentifizierung nicht aktiviert ist. Mit dieser Konfiguration sind Benutzer aus Skype for Business-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, nicht zur Eingabe einer PIN zur Authentifizierung verpflichtet, während Benutzer aus Skype for Business-Pools, die für die zweistufige Authentifizierung aktiviert sind, erforderlich, um die PIN zur Authentifizierung einzugeben.
  
## <a name="exchange-authentication"></a>Exchange-Authentifizierung

Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, können feststellen, dass bestimmte Features im Client nicht verfügbar sind. Dies ist derzeit beabsichtigt, da der Skype for Business-Client keine zweistufige Authentifizierung für Features unterstützt, die von der Exchange-Integration abhängig sind.
  
## <a name="contacts"></a>Kontakte

Skype for Business-Benutzer, die für die Nutzung des Unified Contact Store-Features konfiguriert sind, werden feststellen, dass Ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.
  
Sie sollten das Cmdlet **Invoke-CsUcsRollback** verwenden, um vorhandene Benutzer Kontakte aus dem Unified Contact Store zu entfernen und in Skype for Business Server zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.
  
## <a name="skill-search"></a>Qualifikationssuche

Kunden, die die Fertigkeits Suchfunktion in Ihrer Skype for Business-Umgebung konfiguriert haben, werden feststellen, dass diese Funktion nicht funktioniert, wenn Skype for Business für die zweistufige Authentifizierung aktiviert ist. Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan die zweistufige Authentifizierung nicht unterstützt.
  
## <a name="credentials"></a>Anmeldeinformationen

Es gibt eine Reihe von Bereitstellungsüberlegungen für gespeicherte Skype for Business-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.
  
### <a name="deleting-saved-credentials"></a>Löschen von gespeicherten Anmeldeinformationen

Benutzer sollten die Option **Meine Anmeldeinformationen löschen** im Skype for Business-Client verwenden und Ihren SIP-Profilordner aus%LocalAppData%\Microsoft\Office\15.0\Skype for Business löschen, bevor Sie versuchen, das erste Mal unter Verwendung von zwei Faktoren zu signieren. Authentifizierung.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Bei der Kerberos-oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet. In einer typischen Skype for Business Server-Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer nicht bei jeder Anmeldung Ihre Anmeldeinformationen eingeben müssen.
  
Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).
  
Um die zusätzliche Aufforderung zur Eingabe von Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage "Skype for Business", um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet, wird der Benutzer aufgefordert, sein Kennwort zu speichern. Wenn diese Option aktiviert ist, kann das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows-Anmeldeinformationen des Benutzers gespeichert werden, die im Anmelde Informations Manager des lokalen Computers gespeichert werden.
  
Die Registrierungseinstellung **SavePassword** sollte deaktiviert sein, wenn Skype for Business so konfiguriert ist, dass die zweistufige Authentifizierung unterstützt wird. Wenn Sie verhindern möchten, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage "Skype for Business", um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0-Tokenwiederholung

AD FS 2.0 stellt eine Funktion bereit, die als Tokenwiederholungserkennung bezeichnet wird und mit welcher mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist diese Funktion aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.
  
Diese Funktion sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise bei der Nutzung von Kiosken. Weitere Informationen zur Erkennung von Token-Wiedergabe finden Sie unter [bewährte Methoden für die sichere Planung und Bereitstellung von AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Zugriff von externen Benutzern

Die Konfiguration eines ADFS-Proxys oder eines Reverse-Proxys zur Unterstützung der zweistufigen Authentifizierung von Skype for Business in externen Netzwerken wird in diesen Themen nicht behandelt.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server](configure-two-factor.md)
  
