---
title: 'Lync Server 2013: Schritte zum Vorbereiten und Bereitstellen lync Server Hybridumgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc029df06f22524fa99c232edf6bbe6aa9759f5a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Schritte zum Vorbereiten und Bereitstellen lync Server 2013 Hybridumgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-08_

In der folgenden Tabelle sind die erforderlichen Schritte zum Vorbereiten der Umgebung für eine hybridbereitstellung mit Skype for Business Online und Microsoft Office 365 aufgeführt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Abgeschlossen?</th>
<th>Schritt</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Erstellen eines Mandanten Kontos für Office 365 und Aktivieren von lync Online</p></td>
<td><p>Informationen zu Office 365 und lync Online finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</p>
<p>Wenn Sie sicherstellen möchten, dass Ihre Umgebung für Office 365 bereit ist, lesen Sie die <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Anforderungen</a>.</p>
<p>Ausführliche Informationen zum Einrichten von Office 365 finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Erste Schritte mit Office 365</a> und <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Einrichten von Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Hinzufügen Ihrer Domäne und Überprüfen des Besitzes</p></td>
<td><p>Ihre Domäne wird manchmal auch als ihre Vanity- <em>Domäne</em>bezeichnet. Sie müssen Ihre Domäne Ihrer Office 365 Organisation hinzufügen und dann die Schritte ausführen, um die Domäne mit Office 365 zu überprüfen. Dadurch wird bestätigt, dass Sie der Besitzer der Domäne sind.</p>
<p>Führen Sie die unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Hinzufügen Ihrer Domäne zu Office 365</a>beschriebenen Schritte aus, um Ihre Domäne zu Ihrer Office 365 Organisation hinzuzufügen.</p>
<p>Führen Sie alle Schritte in den einzelnen Abschnitten des Themas aus, &quot;einschließlich Bearbeiten von DNS-Einträgen für Ihre Office 365 Dienste.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Überprüfen der Umgebungs Bereitschaft</p></td>
<td><p>Sie können den Office 365-Setup-Assistenten verwenden, um Sie bei der Bereitstellung von Office 365 zu unterstützen. Weitere Informationen finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">use Setup Assistant to bestimmen Office 365 Readiness</a>.</p>
<p>Ausführliche Informationen zur Verwendung des Tools und zum Bereitstellen von Office 365 finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 Deployment Guide</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Vorbereiten der Active Directory Synchronisierung</p></td>
<td><p>Durch Active Directory Synchronisierung wird Ihre lokale Active Directory kontinuierlich mit Office 365 synchronisiert. Auf diese Weise können Sie synchronisierte Versionen aller Benutzerkonten und Gruppen erstellen und außerdem die Synchronisierung der globalen Adressliste (GAL) zwischen der lokalen Exchange Server Umgebung und Microsoft Exchange Online aktivieren.</p>
<div>

> [!IMPORTANT]  
> Sie müssen die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online-lync-Bereitstellungen synchronisieren, auch wenn Benutzer nicht zu lync Online verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Online Benutzern in Ihrer Organisation möglicherweise nicht wie erwartet.


</div>
<p>Um Ihre Umgebung für Active Directory Synchronisierung vorzubereiten, befolgen Sie die unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Verzeichnis Synchronisierungs-Roadmap</a>beschriebenen Schritte, einschließlich der Einrichtung des einmaligen Anmeldens.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Erstellen von Zertifikaten für Active Directory Verbunddienste (AD FS)</p></td>
<td><p>Sie müssen die Zertifikate erstellen, die für den Identitätsverbund mit Office 365 verwendet werden. Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" des Themas planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Prüfliste: Verwenden von AD FS zum Implementieren und Verwalten des einmaligen Anmeldens</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Zuweisen von Zertifikaten für AD FS</p></td>
<td><p>Nachdem Sie die Zertifikate erstellt haben, die für den Identitätsverbund mit Office 365 verwendet werden, müssen Sie diese installieren und zuweisen.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Migrieren von Pilotbenutzern zu Skype for Business Online</p></td>
<td><p>Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren Ihrer Umgebung für Skype for Business Online abgeschlossen haben, können Sie mit dem Verschieben von Pilotbenutzern in lync Online beginnen.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-move-users-to-lync-online.md">Migrieren von Benutzern zu lync Online in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verwalten von Benutzern in einer hybridbereitstellung</p></td>
<td><p>Ausführliche Informationen zur Verwaltung von Benutzern in einer hybridbereitstellung finden Sie unter Verwalten von <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Benutzern in einer hybriden lync Server 2013-Bereitstellung</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

