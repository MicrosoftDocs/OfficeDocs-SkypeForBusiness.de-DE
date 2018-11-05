---
title: Probleme beim Umgebungstest
TOCTitle: Probleme beim Umgebungstest
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205421(v=OCS.15)
ms:contentKeyID: 49296021
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Probleme beim Umgebungstest

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Mit Best Practices Analyzer können Sie sicherstellen, dass Ihre Lync Server 2013-Umgebung eine unterstützte Konfiguration ist. Im Rahmen der Prüfung von Active Directory-Domänendienste (Active Directory Domain Services, AD\&nbsp;DS) führt Best Practices Analyzer folgende Aktionen aus:

  - Überprüfen der Gesamtstruktur und der Schemavorbereitung von Active Directory-Domänendienste.

  - Feststellen der Anzahl der Standorte und Domänen von Active Directory-Domänendienste in der Bereitstellung.

  - Überprüfen der Gesamtstruktur- und der Domänenebenen.

  - Überprüfen der Domänencontrollerversion.

  - Feststellen des Domänen-, Konfigurations- und Schemanamenskontextes.

  - Feststellen der Anzahl der aktivierten Benutzer.

  - Überprüfen, wo die globalen Einstellungen für Active Directory-Domänendienste gespeichert sind.

  - Überprüfen der Dienstverbindungspunkte für Lync Server.

  - Feststellen der Datenbankversion.

## Beheben von Problemen mit der Umgebung

Wenn beim Testen der Umgebung Probleme festgestellt wurden, sind wahrscheinlich Probleme mit der Active Directory-Konfiguration oder mit der Ebene der Software, die auf bestimmten Servern ausgeführt wird, die Ursache hierfür. Beispiel: Wenn Best Practices Analyzer in einer Umgebung Domänencontroller identifiziert, auf denen Windows Server\&nbsp;2000 ausgeführt wird, erhalten Sie eine Warnmeldung und müssen diese Domänencontroller auf eine unterstützte Version von Windows Server upgraden.

