---
title: 'Lync Server 2013: Übersicht über die Vorbereitung der Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51d0fec8f36749f52acf3272bf83dee3170da8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Übersicht über die Vorbereitung der Active Directory-Domänendienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Wenn Sie die Active Directory-Domänendienste für Ihre lync Server 2013-Bereitstellung vorbereiten möchten, müssen Sie drei Schritte in einer bestimmten Reihenfolge ausführen.

In der folgenden Tabelle werden die Schritte beschrieben, die zum Vorbereiten von AD DS für lync Server erforderlich sind.

### <a name="active-directory-preparation-steps"></a>Vorbereitungsschritte für Active Directory

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
<th>Wo ausführen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Vorbereiten des Active Directory-Schemas in Lync Server 2013</a></p></td>
<td><p>Erweitert das Active Directory-Schema durch Hinzufügen neuer Klassen und Attribute, die von lync Server verwendet werden.</p>
<p>Einmaliges ausführen für jede Gesamtstruktur in Ihrer Bereitstellung, in der lync Server bereitgestellt wird.</p></td>
<td><p>Für den Schemamaster in der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird.</p>
<div>

> [!NOTE]  
> Sie müssen diesen Schritt nicht in der Stammdomäne ausführen, wenn Sie über Berechtigungen für den Schemamaster verfügen, aber Sie müssen Mitglied der Gruppe "Schemaadministratoren" in der Stammdomäne und ein Mitglied der Gruppe "Organisations-Admins" auf dem Schemamaster sein. Führen Sie in einer Ressourcengesamtstruktur-Topologie diesen Schritt nur in der Ressourcengesamtstruktur und nicht in allen Benutzergesamtstrukturen aus. Führen Sie in einer zentralen Gesamtstrukturtopologie diesen Schritt nur in der zentralen Gesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Vorbereiten der Gesamtstruktur für Lync Server 2013</a></p></td>
<td><p>Erstellt globale Einstellungen und universelle Gruppen, die von lync Server verwendet werden.</p>
<p>Einmaliges ausführen für jede Gesamtstruktur in Ihrer Bereitstellung, in der lync Server bereitgestellt wird.</p></td>
<td><p>In der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird. Damit Sie diesen Schritt ausführen können, müssen Sie Mitglied der Gruppe Organisations-Admins sein.</p>
<div>

> [!NOTE]  
> Führen Sie in einer Ressourcengesamtstruktur-Topologie diesen Schritt nur in der Ressourcengesamtstruktur und nicht in allen Benutzergesamtstrukturen aus. Führen Sie in einer zentralen Gesamtstrukturtopologie diesen Schritt nur in der zentralen Gesamtstruktur und nicht in allen Benutzergesamtstrukturen aus.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Vorbereiten von Domänen für Lync Server 2013</a></p></td>
<td><p>Fügt Berechtigungen für Objekte hinzu, die von Mitgliedern universeller Gruppen verwendet werden sollen.</p>
<p>Einmal pro Benutzerdomäne oder Server Domäne ausführen.</p>
<div>

> [!NOTE]  
> Wenn Sie von lync Server 2010 zu lync Server 2013 migrieren, zeigt der Bereitstellungs-Assistent möglicherweise an, dass die Domänenvorbereitung bereits abgeschlossen ist. Sie müssen die Domänenvorbereitung nicht erneut ausführen. Es wurden keine Berechtigungen von lync Server 2010 zu lync Server 2013 geändert.


</div></td>
<td><p>Auf einem Mitgliedsserver in jeder Domäne, in der lync Server bereitgestellt wird. Damit Sie diesen Schritt ausführen können, müssen Sie Mitglied der Gruppe der Domänenadministratoren sein.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 speichert ähnlich wie lync Server 2010 einen Großteil der Konfigurationsinformationen im zentralen Verwaltungsspeicher statt in AD DS, wie dies bei Office Communications Server 2007 R2 der Fall war. Die folgenden Informationen werden jedoch in AD DS gespeichert:

  - **Schema Erweiterungen**:
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität

<!-- end list -->

  - **Daten** (im erweiterten lync Server-Schema und in vorhandenen Schemaklassen gespeichert):
    
      - Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen
    
      - Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale
    
      - Ein Zeiger auf den zentralen Verwaltungsspeicher
    
      - Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)

In lync Server 2013 delegieren Sie Setup und Verwaltung, indem Sie der universellen RTCUniversalServerAdmins-Gruppe Setup Berechtigungen erteilen, damit Mitglieder dieser Gruppe lync Server 2013 auf einem lokalen Server installieren und aktivieren können (nachdem der Server dem Topologie, veröffentlicht und aktiviert). Die Delegierten Benutzer müssen lokale Administratoren auf dem Computer sein, auf dem Sie lync Server 2013 installieren und aktivieren, aber Sie müssen nicht Mitglieder der Gruppe der Domänenadministratoren sein. Sie können auch Berechtigungen für Objekte in angegebenen Organisationseinheiten (Organizational Units, OUs) erteilen, damit Mitglieder der universellen Gruppen, die während der Gesamtstrukturvorbereitung erstellt wurden, auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.

Bei neuen Bereitstellungen von lync Server 2013 müssen die globalen Einstellungen im Container Konfiguration gespeichert werden. Wenn Ihre Organisation ein Upgrade von einer früheren Version durchläuft und Sie weiterhin über globale Einstellungen im Systemcontainer verfügen, wird der Systemcontainer weiterhin unterstützt.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server 2013 verwendet werden](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

