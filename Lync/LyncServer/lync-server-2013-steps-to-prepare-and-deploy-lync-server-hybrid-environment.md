---
title: 'Lync Server 2013: Schritte zur Vorbereitung und Bereitstellung einer Lync Server-Hybridumgebung'
TOCTitle: Schritte zur Vorbereitung und Bereitstellung einer Lync Server 2013-Hybridumgebung
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205157(v=OCS.15)
ms:contentKeyID: 49294980
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schritte zur Vorbereitung und Bereitstellung einer Lync Server 2013-Hybridumgebung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In der folgenden Tabelle sind die Schritte aufgelistet, die erforderlich sind, um Ihre Umgebung auf eine Hybridbereitstellung mit Microsoft Lync Online und Microsoft Office 365 vorzubereiten.


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
<td><p></p></td>
<td><p>Erstellen eines Mandantenkontos für Office 365 und Aktivieren von Lync Online</p></td>
<td><p>Weitere Informationen zu Office 365 und Lync Online finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</p>
<p>Machen Sie sich mit den <a href="http://go.microsoft.com/fwlink/p/?linkid=401408">Systemanforderungen</a> vertraut, um sicherzustellen, dass Ihre Umgebung für Office 365 bereit ist.</p>
<p>Einzelheiten zum Einrichten von Office 365 finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=254982">Erste Schritte mit Office 365</a> und <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Einrichten von Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Hinzufügen einer Domäne und Überprüfen des Domänenbesitzes</p></td>
<td><p>Ihre Domäne wird manchmal auch als <em>Vanity-Domäne</em> bezeichnet. Sie müssen Ihre Domäne dem Office 365-Mandanten hinzufügen und dann den Schritten zum Überprüfen der Domäne mit Office 365 folgen. Anhand dieser Schritte soll bestätigt werden, dass Sie der Besitzer der Domäne sind.</p>
<p>Führen Sie die unter <a href="http://go.microsoft.com/fwlink/p/?linkid=254983">Hinzufügen Ihrer Domäne zu Office 365</a> beschriebenen Schritte aus, um Ihre Domäne zum Office 365-Mandanten hinzuzufügen.</p>
<p>Führen Sie alle Schritte in jedem Abschnitt des Themas aus, einschließlich &quot;Bearbeiten von DNS-Einträgen für Ihre Office 365-Dienste&quot;.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Überprüfen der Bereitschaft der Umgebung</p></td>
<td><p>Sie können den Office 365-Setup-Assistenten verwenden, der Ihnen bei der Bereitstellung von Office 365 hilft. Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=254985">Verwenden des Setup-Assistenten zum Bestimmen der Office 365-Bereitschaft</a></p>
<p>Einzelheiten zum Verwenden des Tools und zur Bereitstellung von Office 365 finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=257337">Office 365-Bereitstellungsleitfaden</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Vorbereiten der Active Directory-Synchronisierung</p></td>
<td><p>Die Active Directory-Synchronisierung sorgt dafür, dass Ihre lokale Active Directory-Bereitstellung ständig mit Office 365 synchronisiert ist. Dadurch können Sie synchronisierte Versionen aller Benutzerkonten und -gruppen erstellen. Zudem wird die Synchronisierung der globalen Adressenliste (GAL) aus Ihrer lokalen Microsoft Exchange Server-Umgebung mit Microsoft Exchange Online ermöglicht.</p>
<div>

> [!IMPORTANT]
> Sie müssen die AD-Konten für alle Lync-Benutzer in Ihrem Unternehmen zwischen der lokalen und der Onlinebereitstellung von Lync synchronisieren. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.


</div>
<p>Um Ihre Umgebung für die Active Directory-Synchronisierung vorzubereiten, führen Sie die unter <a href="http://go.microsoft.com/fwlink/p/?linkid=254988">Roadmap für die Verzeichnissynchronisierung</a> beschriebenen Schritte durch, einschließlich der Einrichtung der einmaligen Anmeldung.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Zertifikate für Active Directory-Verbunddienste (AD FS) erstellen</p></td>
<td><p>Sie müssen die Zertifikate erstellen, die für den Identitätsverbund mit Office 365 verwendet werden. Weitere Informationen finden Sie im Abschnitt &quot;Verbundserverzertifikate&quot; des Themas &quot;Planen und Bereitstellen von AD FS zur Verwendung beim einmaligen Anmelden&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Implementieren und Verwalten des einmaligen Anmeldens mit AD FS</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Zertifikate für AD FS zuweisen</p></td>
<td><p>Nachdem Sie die Zertifikate erstellt haben, die für den Identitätsverbund mit Office 365 verwendet werden, müssen Sie die Zertifikate installieren und zuweisen.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Migieren von Pilotbenutzern zu Skype for Business Online</p></td>
<td><p>Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren der Umgebung für Skype for Business Online abgeschlossen haben, können Sie damit beginnen, Pilotbenutzer zu Lync Online zu migrieren.</p>
<p>Informationen finden Sie unter <a href="lync-server-2013-move-users-to-lync-online.md">Verschieben von Benutzern zu Lync Online in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Verwalten von Benutzern in einer Hybridbereitstellung</p></td>
<td><p>Ausführliche Informationen zum Verwalten von Benutzern in einer Hybridbereitstellung finden Sie unter <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Verwalten von Benutzern in einer Lync Server 2013-Hybridbereitstellung</a>.</p></td>
</tr>
</tbody>
</table>

