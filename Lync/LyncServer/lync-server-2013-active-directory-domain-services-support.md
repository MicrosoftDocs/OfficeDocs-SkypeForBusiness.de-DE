---
title: 'Lync Server 2013: Unterstützung der Active Directory-Domänendienste'
TOCTitle: Unterstützung der Active Directory-Domänendienste
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412831(v=OCS.15)
ms:contentKeyID: 49295089
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung der Active Directory-Domänendienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Lync Server 2013 wird ein zentralen Verwaltungsspeicher zum Speichern von Konfigurationsdaten für Server und Dienste verwendet, anstatt hierfür wie in früheren Versionen auf Active Directory-Domänendienste zurückzugreifen. Lync Server 2013 speichert allerdings Folgendes weiterhin in den Active Directory-Domänendiensten (AD DS):

  - **Schemaerweiterungen**
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Lync Server 2010- und Office Communications Server 2007 R2-Klassen zum Aufrechterhalten der Abwärtskompatibilität mit zuvor unterstützten Versionen

  - **Daten** (die im erweiterten Lync Server 2013-Schema und vorhandenen Klassen gespeichert sind)
    
      - Den Benutzer-SIP-URI und andere Einstellungen
    
      - Kontaktobjekte für Anwendungen (z. B. die Reaktionsgruppenanwendung und die Konferenzzentrale)
    
      - Zur Abwärtskompatibilität veröffentlichte Daten
    
      - Einen Dienststeuerungspunkt für den zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)

In diesem Abschnitt werden die Anforderungen an die AD DS-Unterstützung für Lync Server 2013 beschrieben. Ausführliche Informationen zur Topologieunterstützung finden Sie unter [Unterstützte Active Directory-Topologien in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation.

## Unterstützte Betriebssysteme auf Domänencontrollern

Lync Server 2013 unterstützt Domänencontroller mit den folgenden Betriebssystemen:

  - Windows Server 2012 R2 

  - Windows Server 2012 

  - Windows Server 2008 R2-Betriebssystem

  - Windows Server 2008-Betriebssystem

  - Windows Server 2008 Enterprise 32-Bit

  - Die 32-Bit- und 64-Bit-Version des Betriebssystems Window Server 2003 R2

  - Die 32-Bit- und 64-Bit-Version des Betriebssystems Windows Server 2003

## Gesamtstruktur- und Domänenfunktionsebene

Alle Domänen, in denen Sie Lync Server 2013 bereitstellen, müssen auf eine Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft werden.

Alle Gesamtstrukturen, in denen Sie Lync Server 2013 bereitstellen, müssen auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft werden.

## Unterstützung für schreibgeschützte Domänencontroller

Lync Server 2013 unterstützt Active Directory-Domänendienste-Bereitstellungen, die schreibgeschützte Domänencontroller oder schreibgeschützte Katalogserver enthalten, sofern nicht schreibgeschützte Domänencontroller verfügbar sind.

## Domänennamen

Lync Server unterstützt keine Domänen mit einfacher Bezeichnung. Beispielsweise wird eine Gesamtstruktur mit der Stammdomäne **contoso.local** unterstützt, die Stammdomäne **local** hingegen nicht. Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zur Konfiguration von Windows für Domänen mit DNS-Namen mit einfacher Bezeichnung" unter [http://go.microsoft.com/fwlink/?LinkId=143752](http://go.microsoft.com/fwlink/?linkid=143752).


> [!NOTE]
> Lync Server unterstützt die Umbenennung von Domänen nicht. Wenn Sie eine Domäne umbenennen müssen, in der Lync Server bereitgestellt ist, müssen Sie zuerst Lync Server deinstallieren, die Domäne umbenennen und Lync Server dann wieder installieren.



## Gesperrte AD DS-Umgebungen

In einer gesperrten AD DS-Umgebung werden Benutzer- und Computerobjekte häufig in speziellen Organisationseinheiten abgelegt. Dabei ist die Vererbung von Berechtigungen deaktiviert, um zum Schutz der administrativen Delegierung beizutragen und um die Verwendung von Gruppenrichtlinienobjekten zur Durchsetzung von Sicherheitsrichtlinien zu ermöglichen. Lync Server 2013 kann in einer gesperrten Active Directory-Umgebung bereitgestellt werden. Ausführliche Informationen zur Bereitstellung von Lync Server in einer gesperrten Umgebung finden Sie unter [Vorbereiten gesperrter Active Directory-Domänendienste in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

