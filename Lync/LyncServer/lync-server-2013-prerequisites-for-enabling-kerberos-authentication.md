---
title: 'Lync Server 2013: Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung'
TOCTitle: Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425909(v=OCS.15)
ms:contentKeyID: 49293782
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Vergewissern Sie sich vor der Aktivierung der Kerberos-Authentifizierung, dass Sie alle erforderlichen Vorbereitungen in Bezug auf Konfiguration und Infrastruktur abgeschlossen haben:

  - Das Active Directory-Schema wurde für Lync Server 2013 erweitert.

  - Die Active Directory-Gesamtstrukturvorbereitung für Lync Server 2013 wurde abgeschlossen.

  - Die Active Directory-Domänenvorbereitung für Lync Server 2013 wurde abgeschlossen.

  - zentralen Verwaltungsspeicher wurde installiert und ist einsatzbereit.

  - Die Topologie wurde mit dem Topologie-Generator erstellt und veröffentlicht.

  - Die für die Webdienste erforderlichen Server und Rollen wurden definiert und bereitgestellt, Front-End-Server, Standard Edition-Server und Director-Server eingeschlossen.

  - Internetinformationsdienste (Internet Information Services, IIS) wurde mit den empfohlenen Rollendiensten zur Unterstützung der Webdienste in Lync Server 2013 konfiguriert und bereitgestellt.

Wenn alle Anforderungen erfüllt wurden, können Sie für die Webdienste eines oder mehrere Konten für die Kerberos-Authentifizierung in Ihrer Bereitstellung erstellen. Sie müssen pro Bereitstellung mindestens ein Kerberos-Authentifizierungskonto erstellen. Sie können jedoch ein Konto für jeden Standort erstellen, um eine lokale Kerberos-Authentifizierung am Standort zu ermöglichen. Pro Standort kann nur ein Kerberos-Authentifizierungskonto angegeben werden.

