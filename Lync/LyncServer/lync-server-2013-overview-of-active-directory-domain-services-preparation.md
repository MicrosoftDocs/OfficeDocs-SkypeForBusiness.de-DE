---
title: 'Lync Server 2013: Übersicht über die Vorbereitung der Active Directory-Domänendienste'
TOCTitle: Übersicht über die Vorbereitung der Active Directory-Domänendienste
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398869(v=OCS.15)
ms:contentKeyID: 49295440
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Vorbereitung der Active Directory-Domänendienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zur Vorbereitung von Active Directory-Domänendienste für Ihre Lync Server 2013-Bereitstellung müssen Sie drei Schritte in einer festgelegten Reihenfolge ausführen.

In der folgenden Tabelle werden die Schritte beschrieben, die erforderlich sind, um AD DS für Lync Server vorzubereiten.

### Schritte zur Vorbereitung von Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Schritt</th>
<th>Beschreibung</th>
<th>Ausführung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Vorbereiten des Active Directory-Schemas in Lync Server 2013</a></p></td>
<td><p>Erweitert das Active Directory-Schema, indem neue Klassen und Attribute hinzugefügt werden, die von Lync Server verwendet werden.</p>
<p>Führen Sie diesen Schritt einmal für jede Gesamtstruktur in Ihrer Bereitstellung aus, in der Lync Server bereitgestellt werden soll.</p></td>
<td><p>Für den Schemamaster in der Stammdomäne jeder Gesamtstruktur, in der Lync Server bereitgestellt werden soll.</p>
<div>

> [!NOTE]
> Sie müssen diesen Schritt nicht in der Stammdomäne ausführen, wenn Sie über Berechtigungen für den Schemamaster verfügen, Sie müssen jedoch Mitglied der Gruppe "Schema-Admins" in der Stammdomäne und Mitglied der Gruppe "Organisations-Admins" auf dem Schemamaster sein. Führen Sie diesen Schritt in einer Topologie mit Ressourcengesamtstruktur nur in der Ressourcengesamtstruktur aus, nicht in Benutzergesamtstrukturen. Führen Sie diesen Schritt in einer Topologie mit zentraler Gesamtstruktur nur in der zentralen Gesamtstruktur aus, nicht in Benutzergesamtstrukturen.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Vorbereiten der Gesamtstruktur für Lync Server 2013</a></p></td>
<td><p>Erstellt globale Einstellungen und universelle Gruppen, die von Lync Server verwendet werden.</p>
<p>Führen Sie diesen Schritt einmal für jede Gesamtstruktur in Ihrer Bereitstellung aus, in der Lync Server bereitgestellt werden soll.</p></td>
<td><p>In der Stammdomäne jeder Gesamtstruktur, in der Lync Server bereitgestellt werden soll. Zum Ausführen dieses Schritts müssen Sie Mitglied der Gruppe &quot;Organisations-Admins&quot; sein.</p>
<div>

> [!NOTE]
> Führen Sie diesen Schritt in einer Topologie mit Ressourcengesamtstruktur nur in der Ressourcengesamtstruktur aus, nicht in Benutzergesamtstrukturen. Führen Sie diesen Schritt in einer Topologie mit zentraler Gesamtstruktur nur in der zentralen Gesamtstruktur aus, nicht in Benutzergesamtstrukturen.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Vorbereiten von Domänen für Lync Server 2013</a></p></td>
<td><p>Fügt Berechtigungen für Objekte hinzu, die von Mitgliedern der universellen Gruppen verwendet werden.</p>
<p>Führen Sie diesen Schritt einmal für jede Benutzer- oder Serverdomäne aus.</p>
<div>

> [!NOTE]
> Wenn Sie von Lync Server 2013 zu Lync Server 2010 migrieren, werden Sie möglicherweise vom Bereitstellungs-Assistenten darüber informiert, dass die Domänenvorbereitung bereits abgeschlossen ist. Sie müssen die Domänenvorbereitung nicht erneut ausführen. Die Berechtigungen in Lync Server 2013 wurden in Lync Server 2010 geändert.


</div></td>
<td><p>Auf einem Mitgliedsserver in jeder Domäne, in der Lync Server bereitgestellt werden soll. Zum Ausführen dieses Schritts müssen Sie Mitglied der Gruppe &quot;Domänen-Admins&quot; sein.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 speichert wie Lync Server 2010 einen Großteil der Konfigurationsinformationen nicht mehr wie dies bei Office Communications Server 2007 R2 der Fall war in den Active Directory-Domänendiensten (AD DS), sondern im zentralen Verwaltungsspeicher. Die folgenden Informationen werden jedoch in AD DS gespeichert:

  - **Schemaerweiterungen**:
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Office Communications Server 2007 R2-Klassen zum Aufrechterhalten der Abwärtskompatibilität

<!-- end list -->

  - **Daten** (werden im erweiterten Lync Server-Schema und in vorhandenen Schemaklassen gespeichert):
    
      - Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen
    
      - Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale
    
      - Verweis auf zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)

In Lync Server 2013 delegieren Sie Setup und Verwaltung, indem Sie der universellen Gruppe RTCUniversalServerAdmins Setupberechtigungen gewähren, sodass Mitglieder dieser Gruppe Lync Server 2013 auf einem lokalen Server installieren und aktivieren können (nachdem der Server der Topologie hinzugefügt, veröffentlicht und aktiviert wurde). Die delegierten Benutzer müssen lokale Administratoren auf dem Computer sein, auf dem sie Lync Server 2013 installieren und aktivieren möchten, sie müssen jedoch keine Mitglieder der Gruppe Domänen-Admins sein. Sie können auch Objekten in bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen Gruppen auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe Domänen-Admins zu sein.

In neuen Lync Server 2013-Bereitstellungen müssen globale Einstellungen im Konfigurationscontainer gespeichert werden. Wenn Ihre Organisation ein Upgrade einer früheren Version durchführt und sich im Systemcontainer globale Einstellungen befinden, wird der Systemcontainer weiterhin unterstützt.

## Siehe auch

#### Konzepte

[Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server 2013 verwendet werden](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  

#### Weitere Ressourcen

[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)

