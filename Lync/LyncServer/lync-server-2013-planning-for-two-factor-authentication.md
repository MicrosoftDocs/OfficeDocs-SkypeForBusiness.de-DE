---
title: Planen für zweistufige Authentifizierung
TOCTitle: Planen für zweistufige Authentifizierung
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308562(v=OCS.15)
ms:contentKeyID: 56269256
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen für zweistufige Authentifizierung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Dieser Artikel enthält eine Zusammenstellung von Bereitstellungsüberlegungen für den Fall, dass eine Microsoft Lync Server 2013-Umgebung so konfiguriert werden soll, dass sie zweistufige Authentifizierung unterstützt.

## Clientunterstützung

Der Lync 2013-Desktopclient mit den kumulativen Updates für Lync Server 2013 vom Juli 2013 ist der einzige Lync-Client, der momentan zweistufige Authentifizierung unterstützt.

## Anforderungen im Hinblick auf die Topologie

Kunden wird unbedingt empfohlen, mithilfe von dedizierten Lync Server 2013-Edge-, Director- und Benutzerpools mit kumulativen Updates für Lync Server 2013 vom Juli 2013 zweistufige Authentifizierung bereitzustellen. Soll passive Authentifizierung für Lync-Benutzer aktiviert werden, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert werden. Dazu gehören:


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
<td><p>Registrar</p></td>
<td><p>Front-End</p></td>
<td><p>Kerberos und NTLM</p></td>
</tr>
</tbody>
</table>


Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, ist es mit keiner anderen Version des Lync-Clients möglich, sich erfolgreich anzumelden, sobald die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert wurde.

## Ermitteln von Lync-Diensten

DNS-Einträge, die von internen und/oder externen Clients dazu verwendet werden, Lync-Dienste zu ermitteln, müssen so konfiguriert sein, dass sie aufgelöst auf einen Lync-Server verweisen, der nicht für zweistufige Authentifizierung aktiviert ist. Bei dieser Konfiguration werden Benutzer von Lync-Pools, die nicht für zweistufige Authentifizierung aktiviert sind, nicht zur Eingabe einer PIN aufgefordert, um sich zu authentifizieren, wogegen Benutzer aus Lync-Pools, die für zweistufige Authentifizierung aktiviert sind, zur Eingabe ihrer jeweiligen PIN aufgefordert werden, um sich zu authentifizieren.

## Exchange-Authentifizierung

Kunden, die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, stellen möglicherweise fest, dass bestimmte Features im Lync-Client nicht verfügbar sind. Dies ist momentan entwurfsbedingt, weil der Lync-Client zweistufige Authentifizierung nicht für Features unterstützt, die von der Exchange-Integration abhängen.

## Lync-Kontakte

Lync-Benutzer, deren Konfiguration die Nutzung des einheitlichen Kontaktspeichers bedingt, werden feststellen, dass ihre Kontakte nach einer Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.

Sie sollten das Cmdlet **Invoke-CsUcsRollback** verwenden, um vorhandene Benutzerkontakte aus dem einheitlichen Kontaktspeicher zu entfernen und in Lync Server 2013 zu speichern, bevor Sie zweistufige Authentifizierung aktivieren.

## Qualifikationssuche

Kunden, die das Feature für Qualifikationssuche in ihrer Lync-Umgebung aktiviert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn Lync für zweistufige Authentifizierung aktiviert ist. Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan zweistufige Authentifizierung nicht unterstützt.

## Lync-Anmeldeinformationen

Es gibt einige Bereitstellungsüberlegungen hinsichtlich gespeicherter Lync-Anmeldeinforrmationen, die Benutzer betreffen können, in deren Konfiguration die Nutzung von zweistufiger Authentifizierung festgelegt ist.

## Löschen von gespeicherten Anmeldeinformationen

Benutzer sollten die Option **Meine Anmeldeinformationen löschen** im Lync-Client verwenden und ihren SIP-Profilordner aus "%localappdata%\\Microsoft\\Office\\15.0\\Lync" löschen, bevor sie erstmalig versuchen, sich über die zweistufige Authentifizierung anzumelden.

## DisableNTCredentials

Im Rahmen der Kerberos- oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet. In einer üblichen Lync Server 2013-Bereitstellung, in der Kerberos und/oder NTLM für eine Authentifizierung aktiviert sind, sollte es nicht erforderlich sein, dass Benutzer jedes Mal, wenn sie sich anmelden, ihre Anmeldeinformationen eingeben müssen.

Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).

Soll die zusätzliche Eingabeaufforderung für Anmeldeinformationen verhindert werden, erstellen Sie folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Lync-Vorlage, um den Eintrag über eine Gruppenrichtlinie für alle Benutzer eines bestimmten Pools anzuwenden:

HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: DisableNTCredentials

Wert: 0x0

## SavePassword

Wenn ein Benutzer sich das erste Mal bei Lync anmeldet, wird er aufgefordert, sein Kennwort zu speichern. Wird diese Option ausgewählt, ermöglicht sie es, dass das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows-Anmeldeinformationen des Benutzers in der Anmeldeinformationsverwaltung auf dem lokalen Computer gespeichert werden.

Die Registrierungseinstellung **SavePassword** muss deaktiviert sein, wenn Lync so konfiguriert ist, dass zweistufige Authentifizierung unterstützt wird. Soll verhindert werden, dass Benutzer ihre Kennwörter speichern können, erstellen Sie folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Lync-Vorlage, um den Eintrag über eine Gruppenrichtlinie für alle Benutzer eines bestimmten Pools anzuwenden:

HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: SavePassword

Wert: 0x0

## AD FS 2.0-Tokenwiederholung

AD FS 2.0 stellt ein Feature bereit, das als Tokenwiederholungserkennung bezeichnet wird und mit dem mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist dieses Feature aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.

Dieses Feature sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise wenn Kioske verwendet werden. Weitere Informationen zur Tokenwiederholungserkennung (token replay detection) finden Sie unter "Best Practices for Secure Planning and Deployment of AD FS 2.0" unter [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).

## Zugriff von externen Benutzern

Wie ein ADFS-Proxy oder Reverseproxy zu konfigurieren ist, damit er eine zweistufige Lync-Authentifizierung unterstützt, ist nicht Gegenstand dieses Themas.

