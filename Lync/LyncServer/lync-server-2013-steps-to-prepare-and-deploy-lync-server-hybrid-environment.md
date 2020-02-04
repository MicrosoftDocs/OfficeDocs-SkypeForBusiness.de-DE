---
title: 'Lync Server 2013: Schritte zur Vorbereitung und Bereitstellung einer Lync Server-Hybridumgebung'
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
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Schritte zur Vorbereitung und Bereitstellung einer Lync Server 2013-Hybridumgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In der folgenden Tabelle sind die erforderlichen Schritte zum Vorbereiten Ihrer Umgebung für eine hybridbereitstellung mit Skype for Business Online und Microsoft Office 365 aufgeführt.


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
<p>Details zum Einrichten von Office 365 finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Erste Schritte mit Office 365</a> und <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Einrichten von Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Hinzufügen einer Domäne und Überprüfen des Domänenbesitzes</p></td>
<td><p>Ihre Domäne wird manchmal auch als <em>Vanity-Domäne</em> bezeichnet. Sie müssen Ihre Domäne dem Office 365-Mandanten hinzufügen und dann den Schritten zum Überprüfen der Domäne mit Office 365 folgen. Anhand dieser Schritte soll bestätigt werden, dass Sie der Besitzer der Domäne sind.</p>
<p>Wenn Sie Ihre Domäne Ihrem Office 365-Mandanten hinzufügen möchten, führen Sie die unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Hinzufügen Ihrer Domäne zu Office 365</a>beschriebenen Schritte aus.</p>
<p>Führen Sie alle Schritte in jedem Abschnitt des Themas aus, einschließlich &quot;Bearbeiten von DNS-Einträgen für Ihre Office 365-Dienste.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Überprüfen der Umgebungs Bereitschaft</p></td>
<td><p>Sie können den Office 365-Setup-Assistenten verwenden, um die Bereitstellung von Office 365 zu unterstützen. Weitere Informationen finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Verwenden des Setup-Assistenten zum Ermitteln der Bereitschaft von Office 365</a>.</p>
<p>Details zur Verwendung des Tools und zur Bereitstellung von Office 365 finden Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365-Bereitstellungshandbuch</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Vorbereiten der Active Directory-Synchronisierung</p></td>
<td><p>Die Active Directory-Synchronisierung sorgt dafür, dass Ihr lokales Active Directory kontinuierlich mit Office 365 synchronisiert wird. Auf diese Weise können Sie synchronisierte Versionen der einzelnen Benutzerkonten und Gruppen erstellen und außerdem die Synchronisierung der globalen Adressliste (GAL) von Ihrer lokalen Microsoft Exchange Server-Umgebung zu Microsoft Exchange Online aktivieren.</p>
<div>

> [!IMPORTANT]  
> Sie müssen die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online lync-Bereitstellungen synchronisieren, auch wenn Benutzer nicht nach lync Online verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.


</div>
<p>Wenn Sie Ihre Umgebung für die Active Directory-Synchronisierung vorbereiten möchten, führen Sie die in der Roadmap für die <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Verzeichnissynchronisierung</a>beschriebenen Schritte aus, einschließlich der Einrichtung einer einmaligen Anmeldung.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Erstellen von Zertifikaten für Active Directory-Verbunddienste (AD FS)</p></td>
<td><p>Sie müssen die Zertifikate erstellen, die für den Identitätsverbund mit Office 365 verwendet werden. Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" im Abschnitt Planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checkliste: Verwenden von AD FS zum Implementieren und Verwalten des einmaligen Anmeldens</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Zuweisen von Zertifikaten für AD FS</p></td>
<td><p>Nachdem Sie die für den Identitätsverbund mit Office 365 verwendeten Zertifikate erstellt haben, müssen Sie diese installieren und zuweisen.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Verschieben von Pilotbenutzern in Skype for Business Online</p></td>
<td><p>Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren Ihrer Umgebung für Skype for Business Online abgeschlossen haben, können Sie mit dem Verschieben von Pilotbenutzern nach lync Online beginnen.</p>
<p>Informationen finden Sie unter <a href="lync-server-2013-move-users-to-lync-online.md">Verschieben von Benutzern nach lync Online in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verwalten von Benutzern in einer Hybridbereitstellung</p></td>
<td><p>Details zum Verwalten von Benutzern in einer hybridbereitstellung finden Sie unter Verwalten von <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Benutzern in einer hybriden lync Server 2013-Bereitstellung</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

