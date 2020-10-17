---
title: 'Lync Server 2013: Active Directory-Domänendienste-Unterstützung'
description: 'Lync Server 2013: Active Directory-Domänendienste Support.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558681"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Active Directory-Domänendienste-Unterstützung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Lync Server 2013 verwendet den zentralen Verwaltungsspeicher zum Speichern von Konfigurationsdaten für Server und Dienste, anstatt sich auf Active Directory-Domänendienste für diese Informationen zu verlassen, wie in der Vergangenheit. In lync Server 2013 wird weiterhin Folgendes in AD DS gespeichert:

  - **Schemaerweiterungen**
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für lync Server 2010-und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit früheren unterstützten Versionen

  - **Daten** (in lync Server 2013 Extended Schema und in vorhandenen Klassen gespeichert)
    
      - SIP-URI des Benutzers und andere Benutzereinstellungen
    
      - Kontaktobjekte für Anwendungen (beispielsweise die Reaktionsgruppenanwendung und die Konferenzzentrale)
    
      - Aus Gründen der Abwärtskompatibilität veröffentlichte Daten
    
      - Einen Dienststeuerungspunkt (Service Control Points, SCP) für den zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)

In diesem Abschnitt werden die AD DS Supportanforderungen für lync Server 2013 beschrieben. Ausführliche Informationen zur Topologie-Unterstützung finden Sie unter [Supported Active Directory Topologies in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Unterstützte Domänen Controller-Betriebssysteme

Lync Server 2013 unterstützt Domänencontroller, die die folgenden Betriebssysteme ausführen:

  - Windows Server 2012 R2-Betriebssystem

  - Windows Server 2012 Betriebssystem

  - Windows Server 2008 R2-Betriebssystem

  - Windows Server 2008-Betriebssystem

  - Windows Server 2008 Enterprise 32-Bit

  - Die 32-Bit-oder 64-Bit-Versionen des Windows Server 2003 R2-Betriebssystems

  - Die 32-Bit-oder 64-Bit-Versionen des Windows Server 2003 Betriebssystems

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Gesamtstruktur-und Domänenfunktionsebene

Sie müssen alle Domänen, in denen Sie lync Server 2013 bereitstellen, auf einer Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 auslösen.

Alle Gesamtstrukturen, in denen Sie lync Server 2013 bereitstellen, müssen auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft werden.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Unterstützung für Read-Only Domänencontroller

Lync Server 2013 unterstützt Active Directory-Domänendienste-Bereitstellungen, die schreibgeschützte Domänencontroller oder schreibgeschützte globale Katalogserver enthalten, sofern schreibbare Domänencontroller verfügbar sind.

</div>

<div>

## <a name="domain-names"></a>Domänennamen

Lync Server bietet keine Unterstützung für Domänen mit einfacher Bezeichnung. Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne namens **contoso.local** unterstützt, eine Stammdomäne namens **local** hingegen nicht. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einfacher Bezeichnung" unter [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .

<div>


> [!NOTE]  
> Das Umbenennen von Domänen wird von lync Server nicht unterstützt. Wenn Sie eine Domäne umbenennen müssen, in der lync Server bereitgestellt wird, müssen Sie zunächst lync Server deinstallieren und dann die Domäne umbenennen und dann lync Server erneut installieren.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>AD DS Umgebungen gesperrt

In einer gesperrten AD DS Umgebung werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierten Berechtigungen vererbt, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zum Erzwingen von Sicherheitsrichtlinien zu ermöglichen. Lync Server 2013 können in einer gesperrten Active Directory Umgebung bereitgestellt werden. Ausführliche Informationen dazu, was für die Bereitstellung von lync Server in einer gesperrten Umgebung erforderlich ist, finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

