---
title: 'Lync Server 2013: Unterstützung der Active Directory-Domänendienste'
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
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Unterstützung der Active Directory-Domänendienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Lync Server 2013 verwendet den zentralen Verwaltungsspeicher, um Konfigurationsdaten für Server und Dienste zu speichern, anstatt sich wie in der Vergangenheit auf die Active Directory-Domänendienste für diese Informationen zu verlassen. Lync Server 2013 speichert weiterhin die folgenden in AD DS:

  - **Schemaerweiterungen**
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für lync Server 2010 und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit vorherigen unterstützten Versionen

  - **Daten** (im erweiterten Schema von lync Server 2013 und in vorhandenen Klassen gespeichert)
    
      - Der Benutzer-SIP-URI und andere Einstellungen
    
      - Kontaktobjekte für Anwendungen (beispielsweise die Anwendung "Reaktionsgruppe" und die Anwendung "Conferencing Attendant")
    
      - Aus Gründen der Abwärtskompatibilität veröffentlichte Daten
    
      - Einen Dienst Kontrollpunkt (Service Control Point, SCP) für den zentralen Verwaltungsspeicher
    
      - Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)

In diesem Abschnitt werden die AD DS-Supportanforderungen für lync Server 2013 beschrieben. Details zur Topologie-Unterstützung finden Sie unter unter [stützte Active Directory-Topologien in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Dokumentation zur Unterstützung.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Unterstützte Domänen Controller-Betriebssysteme

Lync Server 2013 unterstützt Domänencontroller, auf denen die folgenden Betriebssysteme ausgeführt werden:

  - Windows Server 2012 R2-Betriebssystem

  - Betriebssystem Windows Server 2012

  - Windows Server 2008 R2-Betriebssystem

  - Windows Server 2008-Betriebssystem

  - Windows Server 2008 Enterprise 32-Bit

  - Die 32-Bit-oder 64-Bit-Versionen des Windows Server 2003 R2-Betriebssystems

  - Die 32-Bit-oder 64-Bit-Versionen des Windows Server 2003-Betriebssystems

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Gesamtstruktur-und Domänenfunktionsebene

Sie müssen alle Domänen auslösen, in denen Sie lync Server 2013 auf einer Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 bereitstellen.

Alle Gesamtstrukturen, in denen Sie lync Server 2013 bereitstellen, müssen auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft werden.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Unterstützung von schreibgeschützten Domänencontrollern

Lync Server 2013 unterstützt die Bereitstellung von Active Directory-Domänendiensten mit schreibgeschützten Domänencontrollern oder schreibgeschützten globalen Katalogservern, sofern schreibbare Domänencontroller verfügbar sind.

</div>

<div>

## <a name="domain-names"></a>Domänennamen

Lync Server unterstützt keine Single-Labeling-Domänen. Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne mit dem Namen **contoso. local** unterstützt, aber eine Stammdomäne mit dem Namen **local** wird nicht unterstützt. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einer [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)Bezeichnung" unter.

<div>


> [!NOTE]  
> Lync Server unterstützt keine Umbenennung von Domänen. Wenn Sie eine Domäne umbenennen müssen, in der lync Server bereitgestellt wird, müssen Sie zunächst lync Server deinstallieren, dann die Domäne umbenennen und dann lync Server erneut installieren.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Gesperrte AD DS-Umgebungen

In einer gesperrten AD DS-Umgebung werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierter Berechtigungsvererbung angeordnet, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zu ermöglichen, um Sicherheitsrichtlinien. Lync Server 2013 kann in einer gesperrten Active Directory-Umgebung bereitgestellt werden. Ausführliche Informationen dazu, was für die Bereitstellung von lync Server in einer gesperrten Umgebung erforderlich ist, finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

