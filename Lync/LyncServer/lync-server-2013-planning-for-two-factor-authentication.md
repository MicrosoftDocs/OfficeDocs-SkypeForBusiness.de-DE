---
title: 'Lync Server 2013: Planen der zweistufigen Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planen der zweistufigen Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-04-06_

Im folgenden wird eine Liste der Bereitstellungsüberlegungen beim Konfigurieren einer Microsoft lync Server 2013-Umgebung zur Unterstützung der zweistufigen Authentifizierung aufgeführt.

<div>

## <a name="client-support"></a>Clientunterstützung

Die lync 2013-kumulativen Updates für lync Server 2013: Juli 2013-Desktop Client und alle mobilen Clients unterstützen derzeit die zweistufige Authentifizierung.

</div>

<div>

## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Kunden werden dringend ermutigt, die zweistufige Authentifizierung mit dedizierten lync Server 2013 mit kumulativen Updates für lync Server 2013: Juli 2013 Edge-, Director-und Benutzer Pools bereitzustellen. Um die passive Authentifizierung für lync-Benutzer zu aktivieren, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert sein, einschließlich der folgenden:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Konfigurationstyp</th>
<th>Diensttyp</th>
<th>Serverrolle</th>
<th>Zu deaktivierender Authentifizierungstyp</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Webdienst</p></td>
<td><p>WebServer</p></td>
<td><p>Director</p></td>
<td><p>Kerberos, NTLM und Zertifikat</p></td>
</tr>
<tr class="even">
<td><p>Webdienst</p></td>
<td><p>WebServer</p></td>
<td><p>Front-End</p></td>
<td><p>Kerberos, NTLM und Zertifikat</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Edge</p></td>
<td><p>Kerberos und NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrierungsstelle</p></td>
<td><p>Front-End</p></td>
<td><p>Kerberos und NTLM</p></td>
</tr>
</tbody>
</table>


Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, können sich alle anderen Versionen des lync-Clients nicht erfolgreich anmelden, wenn die zweistufige Authentifizierung innerhalb Ihrer Bereitstellung aktiviert ist.

</div>

<div>

## <a name="lync-service-discovery"></a>Lync-Dienstermittlung

DNS-Einträge, die von internen und/oder externen Clients zum Ermitteln von lync-Diensten verwendet werden, sollten so konfiguriert werden, dass Sie auf einen lync-Server aufgelöst werden, der für die zweistufige Authentifizierung nicht aktiviert ist. Bei dieser Konfiguration müssen Benutzer aus lync-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, keine PIN zur Authentifizierung eingeben, während Benutzer aus lync-Pools, die für die zweistufige Authentifizierung aktiviert sind, Ihre PIN eingeben müssen, um authentifizieren.

</div>

<div>

## <a name="exchange-authentication"></a>Exchange-Authentifizierung

Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, können feststellen, dass bestimmte Features im lync-Client nicht verfügbar sind. Dies ist derzeit beabsichtigt, da der lync-Client die zweistufige Authentifizierung für Features, die von der Exchange-Integration abhängig sind, nicht unterstützt.

</div>

<div>

## <a name="lync-contacts"></a>Lync-Kontakte

Lync-Benutzer, die für die Nutzung des Unified Contact Store-Features konfiguriert sind, werden feststellen, dass Ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.

Sie sollten das Cmdlet **Invoke-CsUcsRollback** verwenden, um vorhandene Benutzer Kontakte aus dem Unified Contact Store zu entfernen und in lync Server 2013 zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.

</div>

<div>

## <a name="skill-search"></a>Qualifikationssuche

Kunden, die das Feature für die Fertigkeits Suche in ihrer lync-Umgebung konfiguriert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn lync für die zweistufige Authentifizierung aktiviert ist. Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan die zweistufige Authentifizierung nicht unterstützt.

</div>

<div>

## <a name="lync-credentials"></a>Lync-Anmeldeinformationen

Es gibt eine Reihe von Bereitstellungsüberlegungen mit gespeicherten lync-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.

<div>

## <a name="deleting-saved-credentials"></a>Löschen von gespeicherten Anmeldeinformationen

Desktop Clientbenutzer sollten die Option **Meine Anmeldeinformationen löschen** im lync-Client verwenden und Ihren SIP-Profilordner von% LocalAppData\\% Microsoft\\Office\\15,0\\lync löschen, bevor Sie versuchen, das erste Mal mithilfe der zweistufigen Authentifizierung zu signieren.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Im Rahmen der Kerberos- oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet. In einer typischen lync Server 2013-Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer nicht bei jeder Anmeldung Ihre Anmeldeinformationen eingeben müssen.

Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).

Um die zusätzliche Aufforderung zur Eingabe von Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative lync-Vorlage, um auf alle Benutzer für einen bestimmten Pool über Gruppenrichtlinien zuzutreffen:

HKEY\_-\_Software\\\\Richtlinien\\für lokale\\Computer\\Microsoft\\Office 15,0 lync

REG\_DWORD: DisableNTCredentials

Wert: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Wenn sich ein Benutzer zum ersten Mal bei lync anmeldet, wird der Benutzer aufgefordert, sein Kennwort zu speichern. Wird diese Option ausgewählt, ermöglicht sie es, dass das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows-Anmeldeinformationen des Benutzers in der Anmeldeinformationsverwaltung auf dem lokalen Computer gespeichert werden.

Die Registrierungseinstellung **SavePassword** sollte deaktiviert werden, wenn lync so konfiguriert ist, dass die zweistufige Authentifizierung unterstützt wird. Wenn Sie verhindern möchten, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative lync-Vorlage, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:

HKEY\_-\_aktuelle\\Benutzer\\Software\\Microsoft\\Office\\15,0 lync

REG\_DWORD: SavePassword

Wert: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0-Tokenwiederholung

AD FS 2.0 stellt eine Funktion bereit, die als Tokenwiederholungserkennung bezeichnet wird und mit welcher mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist diese Funktion aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.

Diese Funktion sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise bei der Nutzung von Kiosken. Weitere Informationen zur Erkennung von Token-Wiedergabe finden Sie unter Bewährte Methoden für die sichere Planung und Bereitstellung von [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)AD FS 2,0 unter.

</div>

<div>

## <a name="external-user-access"></a>Zugriff von externen Benutzern

Die Konfiguration eines AD FS-Proxys oder eines Reverse-Proxys zur Unterstützung der zweistufigen lync-Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

