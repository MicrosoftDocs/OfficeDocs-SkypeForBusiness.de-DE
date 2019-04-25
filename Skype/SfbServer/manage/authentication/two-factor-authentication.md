---
title: Verwalten der zweistufigen Authentifizierung in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Zusammenfassung: Verwalten der zweistufigen Authentifizierung in Skype für Business Server.'
ms.openlocfilehash: ce6d43b8ace741a754cb4406235534fd83e414b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222877"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Verwalten der zweistufigen Authentifizierung in Skype für Business Server
 
**Zusammenfassung:** Verwalten Sie zweistufige Authentifizierung in Skype für Business Server.
  
Die zweistufige Authentifizierung bietet eine verbesserte Sicherheit, indem gefordert wird, dass Benutzer zwei Authentifizierungskriterien erfüllen: eine Kombination aus Benutzername und Kennwort sowie ein Token oder Zertifikat. Dies ist auch als "etwas, das Sie haben, etwas, den Sie kennen." 
  
Ein typisches Beispiel für eine zweistufige Authentifizierung ist die Nutzung von Smartcards. Eine Smartcard enthält ein Zertifikat, das einem Benutzerkonto zugewiesen ist und welches mit den Benutzer- und Zertifikatinformationen überprüft werden kann, die auf einem Server gespeichert sind. Durch Abgleichen der Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat überprüft der Server die Anmeldeinformationen, sodass er den Benutzer authentifizieren kann.
  
Beachten Sie die folgenden Betreffzeilen, bei einer Skype für Business Server-Umgebung zur Unterstützung der zweistufigen Authentifizierung zu konfigurieren.
  
## <a name="client-support"></a>Clientunterstützung

Das kumulative Updates für Lync Server 2013: Juli 2013 Desktopclient und der Skype für Business-Client sind die einzigen Clients, die derzeit zweistufigen Authentifizierung unterstützen.
  
## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Kunden werden dringend empfohlen, die zweistufige Authentifizierung mit dedizierten Skype für Business Server Edge, Director und Pools für Benutzer bereitstellen. Um passiven Authentifizierung für Benutzer aktivieren möchten, müssen für andere Rollen und Dienste, einschließlich der folgenden beiden Authentifizierungsmethoden deaktiviert werden:
  
|**Konfigurationstyp**|**Diensttyp**|**Serverrolle**|**Zu deaktivierender Authentifizierungstyp**|
|:-----|:-----|:-----|:-----|
|Webdienst  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Webdienst  <br/> |WebServer  <br/> |Front-End  <br/> |Kerberos, NTLM und Zertifikat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos und NTLM  <br/> |
|Proxy  <br/> |Registrierungsstelle  <br/> |Front-End  <br/> |Kerberos und NTLM  <br/> |
   
Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, ist es mit keiner anderen Version des Clients möglich, sich erfolgreich anzumelden, sobald die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert wurde.
  
## <a name="skype-for-business-service-discovery"></a>Ermittlung der Skype for Business-Services

DNS-Einträge, die von internen oder externen Clients zum Ermitteln von Skype für BusinessServices verwendet sollte so konfiguriert werden, einen Skype für Business Server erläutern, die für die zweistufige Authentifizierung nicht aktiviert ist. Mit dieser Konfiguration werden Benutzer von Skype für Business-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind nicht aufgefordert werden, geben eine PIN authentifiziert, während Benutzer von Skype für Business-Pools, die für die zweistufige Authentifizierung aktiviert sind, erforderlich, um ihre PIN zur Authentifizierung eingeben.
  
## <a name="exchange-authentication"></a>Exchange-Authentifizierung

Kunden, die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben möglicherweise fest, dass bestimmte Features im-Client nicht verfügbar sind. Dies ist derzeit konzipiert, die Skype für Business Client zweistufigen Authentifizierung für die Features nicht unterstützt, die Exchange-Integration abhängig sind.
  
## <a name="contacts"></a>Kontakte

Skype für Unternehmensbenutzer, die konfiguriert sind, um das Feature Unified Contact Store nutzen werden feststellen, dass ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.
  
Verwenden Sie das Cmdlet " **Invoke-CsUcsRollback** ", vorhandene Benutzerkontakte aus der einheitliche Kontaktspeicher entfernt und in Skype für Business Server vor der Aktivierung der zweistufigen Authentifizierung speichern.
  
## <a name="skill-search"></a>Qualifikationssuche

Kunden, die das Feature für die Suche nach Fertigkeiten in ihren Skype für geschäftsumgebung konfiguriert haben werden feststellen, dass dieses Feature nicht funktioniert, wenn Skype für Unternehmen für die zweistufige Authentifizierung aktiviert ist. Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan die zweistufige Authentifizierung nicht unterstützt.
  
## <a name="credentials"></a>Anmeldeinformationen

Es gibt eine Reihe von Bereitstellungsaspekte im Zusammenhang mit gespeicherten Skype für Business Anmeldeinformationen an, die Benutzern auswirkt, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.
  
### <a name="deleting-saved-credentials"></a>Löschen von gespeicherten Anmeldeinformationen

Benutzer sollten verwenden die Option **Meine Info - Anmeldung löschen** in der Skype für Business-Client und Löschen von ihre SIP-Profilordner aus %localappdata%\Microsoft\Office\15.0\Skype für Business vor dem Signieren zum ersten Mal mit zwei Faktoren Authentifizierung.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Mit der Kerberos- oder NTLM-Authentifizierungsmethode werden automatisch die Windows-Anmeldeinformationen des Benutzers für die Authentifizierung verwendet. In einer typischen Skype für Business Server-Bereitstellung, in denen Kerberos- und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer keinen ihre Anmeldeinformationen jedes Mal eingeben, die Anmeldung.
  
Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).
  
Um weitere Aufforderung zur erneuten Eingabe zu verhindern, erstellen Sie den folgenden Registrierungswert auf dem lokalen Computer oder der Skype für administrative Vorlage für Business auf alle Benutzer für einen bestimmten Pool mithilfe von Gruppenrichtlinien anwenden:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Wenn ein Benutzer bei Skype für Unternehmen zum ersten Mal anmeldet, wird der Benutzer aufgefordert, um das Kennwort zu speichern. Wenn ausgewählt haben, kann diese Option des Benutzers Client-Zertifikat in den persönlichen Zertifikatspeicher und Windows-Anmeldeinformationen des Benutzers, in dem Anmeldeinformations-Manager des lokalen Computers gespeichert werden sollen gespeichert werden.
  
Die Einstellung der Registrierung **SavePassword** sollte deaktiviert werden, wenn Skype für Unternehmen zur Unterstützung der zweistufigen Authentifizierung konfiguriert ist. Um zu verhindern, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungswert auf der lokalen Arbeitsstation, oder verwenden Sie die Skype für administrative Vorlage für Business auf alle Benutzer für einen bestimmten Pool mithilfe von Gruppenrichtlinien anwenden:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0-Tokenwiederholung

AD FS 2.0 stellt eine Funktion bereit, die als Tokenwiederholungserkennung bezeichnet wird und mit welcher mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist diese Funktion aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.
  
Diese Funktion sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise bei der Nutzung von Kiosken. Weitere Informationen zu token wiedergabeschutzes finden Sie unter [Bewährte Methoden für die Secure Planung und Bereitstellung von AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Zugriff von externen Benutzern

Konfigurieren eines AD FS-Proxy oder Reverseproxy zur Unterstützung der Skype für Business zweistufigen Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server](configure-two-factor.md)
  
