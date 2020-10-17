---
title: 'Lync Server 2013: Übersicht über die Active Directory-Domänendienste Vorbereitung'
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
ms.openlocfilehash: 0074b1739cd571db46fc704d4863ac4f0462c99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500582"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Übersicht über die Active Directory-Domänendienste Vorbereitung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Um Active Directory-Domänendienste für Ihre lync Server 2013-Bereitstellung vorzubereiten, müssen Sie drei Schritte in einer bestimmten Reihenfolge ausführen.

In der folgenden Tabelle werden die erforderlichen Schritte zum Vorbereiten AD DS auf lync Server beschrieben.

### <a name="active-directory-preparation-steps"></a>Schritte zur Vorbereitung von Active Directory

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
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Vorbereiten des Active Directory Schemas in lync Server 2013</a></p></td>
<td><p>Erweitert das Active Directory Schema durch Hinzufügen neuer Klassen und Attribute, die von lync Server verwendet werden.</p>
<p>Führen Sie eine einmalige Ausführung für jede Gesamtstruktur in Ihrer Bereitstellung aus, in der lync Server bereitgestellt wird.</p></td>
<td><p>Für den Schemamaster in der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird.</p>
<div>

> [!NOTE]  
> Sie müssen diesen Schritt nicht in der Stammdomäne ausführen, wenn Sie über Berechtigungen für den Schemamaster verfügen, Sie müssen jedoch Mitglied der Gruppe "Schema-Admins" in der Stammdomäne und Mitglied der Gruppe "Organisations-Admins" auf dem Schemamaster sein. Führen Sie diesen Schritt in einer Topologie mit Ressourcengesamtstruktur nur in der Ressourcengesamtstruktur aus, nicht in Benutzergesamtstrukturen. Führen Sie diesen Schritt in einer Topologie mit zentraler Gesamtstruktur nur in der zentralen Gesamtstruktur aus, nicht in Benutzergesamtstrukturen.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Vorbereiten der Gesamtstruktur auf lync Server 2013</a></p></td>
<td><p>Erstellt globale Einstellungen und universelle Gruppen, die von lync Server verwendet werden.</p>
<p>Führen Sie eine einmalige Ausführung für jede Gesamtstruktur in Ihrer Bereitstellung aus, in der lync Server bereitgestellt wird.</p></td>
<td><p>In der Stammdomäne jeder Gesamtstruktur, in der lync Server bereitgestellt wird. Zum Ausführen dieses Schritts müssen Sie Mitglied der Gruppe "Organisations-Admins" sein.</p>
<div>

> [!NOTE]  
> Führen Sie diesen Schritt in einer Topologie mit Ressourcengesamtstruktur nur in der Ressourcengesamtstruktur aus, nicht in Benutzergesamtstrukturen. Führen Sie diesen Schritt in einer Topologie mit zentraler Gesamtstruktur nur in der zentralen Gesamtstruktur aus, nicht in Benutzergesamtstrukturen.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Vorbereiten von Domänen für lync Server 2013</a></p></td>
<td><p>Fügt Berechtigungen für Objekte hinzu, die von Mitgliedern der universellen Gruppen verwendet werden.</p>
<p>Führen Sie diesen Schritt einmal für jede Benutzer- oder Serverdomäne aus.</p>
<div>

> [!NOTE]  
> Wenn Sie von lync Server 2010 zu lync Server 2013 migrieren, weist der Bereitstellungs-Assistent möglicherweise darauf hin, dass die Domänenvorbereitung bereits abgeschlossen ist. Sie müssen die Domänenvorbereitung nicht erneut ausführen. Berechtigungen wurden nicht von lync Server 2010 zu lync Server 2013 geändert.


</div></td>
<td><p>Auf einem Mitgliedsserver in jeder Domäne, in der lync Server bereitgestellt wird. Zum Ausführen dieses Schritts müssen Sie Mitglied der Gruppe "Domänen-Admins" sein.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 wie lync Server 2010 speichert viele Konfigurationsinformationen im zentralen Verwaltungsspeicher anstelle von in AD DS, wie es in Office Communications Server 2007 R2 der Fall war. Die folgenden Informationen werden jedoch in AD DS gespeichert:

  - **Schemaerweiterungen**:
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Office Communications Server 2007 R2 Klassen zum aufrecht erhalten der Abwärtskompatibilität

<!-- end list -->

  - **Daten** (in lync Server Extended Schema und in vorhandenen Schemaklassen gespeichert):
    
      - Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen
    
      - Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale
    
      - Ein Verweis auf den zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)

In lync Server 2013 delegieren Sie Setup und Verwaltung, indem Sie der universellen RTCUniversalServerAdmins-Gruppe Setup Berechtigungen erteilen, sodass Mitglieder dieser Gruppe lync Server 2013 auf einem lokalen Server installieren und aktivieren können (nachdem der Server der Topologie hinzugefügt, veröffentlicht und aktiviert wurde). Die Delegierten Benutzer müssen lokale Administratoren auf dem Computer sein, auf dem Sie lync Server 2013 installieren und aktivieren, aber Sie müssen nicht Mitglieder der Gruppe "Domänen-Admins" sein. Sie können auch Objekten in bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen Gruppen auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.

Für neue Bereitstellungen von lync Server 2013 müssen globale Einstellungen im Konfigurationscontainer gespeichert werden. Wenn Ihre Organisation ein Upgrade von einer früheren Version durchführen und weiterhin über globale Einstellungen im Systemcontainer verfügt, wird der Systemcontainer weiterhin unterstützt.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vorbereiten des Active Directory Schemas in lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Active Directory von lync Server 2013 verwendeten Schemaerweiterungen, Klassen und Attribute](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Vorbereiten der Gesamtstruktur auf lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

