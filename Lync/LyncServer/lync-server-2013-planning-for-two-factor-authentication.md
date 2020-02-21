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
ms.openlocfilehash: 0738cb282ad2f1f375e89526fcdd1569a6707ad0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planen der zweistufigen Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-04-06_

Im folgenden finden Sie eine Liste der Bereitstellungsüberlegungen beim Konfigurieren einer Microsoft lync Server 2013 Umgebung zur Unterstützung der zweistufigen Authentifizierung.

<div>

## <a name="client-support"></a>Client Unterstützung

Die lync 2013 kumulativen Updates für lync Server 2013: July 2013 Desktop Client und alle mobilen Clients unterstützen derzeit die zweistufige Authentifizierung.

</div>

<div>

## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Kunden wird dringend empfohlen, die zweistufige Authentifizierung mithilfe dedizierter lync Server 2013 mit kumulierten Updates für lync Server 2013 bereitzustellen: July 2013 Edge, Director und User Pools. Zum Aktivieren der passiven Authentifizierung für lync-Benutzer müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert sein, einschließlich der folgenden:


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
<td><p>Webserver</p></td>
<td><p>Director</p></td>
<td><p>Kerberos, NTLM und Zertifikat</p></td>
</tr>
<tr class="even">
<td><p>Webdienst</p></td>
<td><p>Webserver</p></td>
<td><p>Front-End-</p></td>
<td><p>Kerberos, NTLM und Zertifikat</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Microsoft Edge</p></td>
<td><p>Kerberos und NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrierungsstelle</p></td>
<td><p>Front-End-</p></td>
<td><p>Kerberos und NTLM</p></td>
</tr>
</tbody>
</table>


Wenn diese Authentifizierungstypen auf Dienstebene deaktiviert sind, können sich alle anderen Versionen des lync-Clients nicht erfolgreich anmelden, wenn die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert ist.

</div>

<div>

## <a name="lync-service-discovery"></a>Lync-Dienstermittlung

DNS-Einträge, die von internen und/oder externen Clients zum Ermitteln von lync-Diensten verwendet werden, sollten so konfiguriert werden, dass Sie auf einen lync-Server aufgelöst werden, der nicht für die zweistufige Authentifizierung aktiviert ist. Bei dieser Konfiguration müssen Benutzer aus lync-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, keine PIN zur Authentifizierung eingeben, während Benutzer aus lync-Pools, die für die zweistufige Authentifizierung aktiviert sind, Ihre PIN eingeben müssen, um authentifizieren.

</div>

<div>

## <a name="exchange-authentication"></a>Exchange-Authentifizierung

Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, stellen möglicherweise fest, dass bestimmte Funktionen im lync-Client nicht verfügbar sind. Dies ist derzeit beabsichtigt, da der lync-Client die zweistufige Authentifizierung nicht für Features unterstützt, die von der Exchange-Integration abhängen.

</div>

<div>

## <a name="lync-contacts"></a>Lync-Kontakte

Lync-Benutzer, die für die Nutzung der Unified Contact Store-Funktion konfiguriert sind, werden feststellen, dass Ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.

Verwenden Sie das Cmdlet **Invoke-CsUcsRollback** , um vorhandene Benutzer Kontakte aus dem einheitlichen Kontaktspeicher zu entfernen und in lync Server 2013 zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.

</div>

<div>

## <a name="skill-search"></a>Skill-Suche

Kunden, die das Feature "Fähigkeitssuche" in ihrer lync-Umgebung konfiguriert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn lync für die zweistufige Authentifizierung aktiviert ist. Dies ist beabsichtigt, da Microsoft SharePoint derzeit keine zweistufige Authentifizierung unterstützt.

</div>

<div>

## <a name="lync-credentials"></a>Lync-Anmeldeinformationen

Es gibt eine Reihe von Überlegungen zur Bereitstellung von gespeicherten lync-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.

<div>

## <a name="deleting-saved-credentials"></a>Löschen gespeicherter Anmeldeinformationen

Benutzer von Desktop Clients sollten die **Option Meine Anmeldeinformationen löschen** im lync-Client verwenden und Ihren SIP-Profilordner aus% LocalAppData%\\Microsoft\\Office\\15,0\\lync löschen, bevor Sie versuchen, das erste Mal unter Verwendung der zweistufigen Authentifizierung zu signieren.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Bei der Kerberos-oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet. In einer typischen lync Server 2013-Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer nicht jedes Mal, wenn Sie sich anmelden, Ihre Anmeldeinformationen eingeben müssen.

Wenn Benutzer versehentlich zur Eingabe von Anmeldeinformationen aufgefordert werden, bevor Sie dazu aufgefordert werden, Ihre PIN einzugeben, kann der Registrierungsschlüssel **DisableNTCredentials** möglicherweise über eine Gruppenrichtlinie unbeabsichtigt auf Clientcomputern konfiguriert werden.

Um die zusätzliche Aufforderung zur Eingabe von Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage lync, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:

HKEY\_-\_Software\\\\Richtlinien\\für lokale\\Computer\\Microsoft\\Office 15,0 lync

REG\_DWORD: DisableNTCredentials

Wert: 0x0 festlegen

</div>

<div>

## <a name="savepassword"></a>SavePassword

Wenn sich ein Benutzer zum ersten Mal bei lync anmeldet, wird der Benutzer aufgefordert, sein Kennwort zu speichern. Wenn diese Option aktiviert ist, kann das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und in den Windows-Anmeldeinformationen des Benutzers gespeichert werden, damit diese im Credential Manager des lokalen Computers gespeichert werden.

Die Registrierungseinstellung **SavePassword** sollte deaktiviert werden, wenn lync für die Unterstützung der zweistufigen Authentifizierung konfiguriert ist. Wenn Sie verhindern möchten, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage lync, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:

HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync

REG\_DWORD: SavePassword

Wert: 0x0 festlegen

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Wiedergabe von AD FS 2.0 Token

AD FS 2.0 stellt ein Feature dar, das als Erkennung von Token-Wiedergaben bezeichnet wird, durch das mehrere Token-Anforderungen mit demselben Token erkannt und anschließend verworfen werden können. Wenn dieses Feature aktiviert ist, schützt die Token-Wiedergabeerkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-verbundprofil als auch im SAML-WebSSO-Profil, indem sichergestellt wird, dass das gleiche Token nie mehr als einmal verwendet wird.

Dieses Feature sollte in Situationen aktiviert sein, in denen Sicherheit ein sehr hoher Aspekt ist, beispielsweise bei der Verwendung von Kiosken. Weitere Informationen zur Erkennung von Token-Wiedergabe finden Sie unter Bewährte Methoden für die sichere Planung und bereit [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)Stellung von AD FS 2.0 unter.

</div>

<div>

## <a name="external-user-access"></a>Externer Benutzerzugriff

Die Konfiguration eines AD FS-Proxys oder Reverseproxy zur Unterstützung der zweistufigen lync-Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

